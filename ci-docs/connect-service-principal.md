---
title: Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą
description: Norėdami prisijungti prie savo duomenų telkinio, naudokite pagrindinę "Azure" tarnybą.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304207"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą

Dynamics 365 Customer Insights suteikia galimybę prisijungti prie Azure Data Lake Storage paskyros naudojant "Azure" paslaugos pagrindinę, o ne saugyklos paskyros raktus.

Automatiniai įrankiai, naudojantys "Azure" paslaugas, turi turėti ribotas teises. Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas. Naudokite paslaugų vykdytojus, kad saugiai [įtrauktumėte arba redaguotumėte aplanką "Common Data Model" kaip duomenų šaltinis](connect-common-data-model.md) arba [sukurtumėte ar atnaujintumėte aplinką](create-environment.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- "Data Lake Storage" paskyra, kurioje bus naudojamas paslaugos vykdytojas, turi būti "Gen2". "Azure Data Lake Gen1" saugyklos paskyros nepalaikomos.
- "Data Lake Storage" paskyroje [įgalinta hierarchinė vardų sritis](/azure/storage/blobs/data-lake-storage-namespace).
- Administratoriaus teisės jūsų "Azure" klientas, jei turite sukurti naują paslaugos vykdytoją.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Pagrindinės "Customer Insights" "Azure" tarnybos kūrimas

Prieš kurdami naują "Customer Insights" paslaugų teikėją, patikrinkite, ar jis jau yra jūsų organizacijoje. Daugeliu atvejų jis jau egzistuoja.

### <a name="look-for-an-existing-service-principal"></a>Ieškokite esančių pagrindinių paslaugų

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

2. Iš **Azure paslaugos**, pasirinkite **Azure Active Directory**.

3. Dalyje **Valdyti** pasirinkite **"Microsoft" programa**.

4. Įtraukite programos ID filtrą **pradėkite nuo**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` pavadinimo arba ieškokite jo pavadinimo `Dynamics 365 AI for Customer Insights`.

5. Jei randate sutampantį įrašą, tai reiškia, kad pagrindinė paslauga jau yra. [Suteikite paslaugos vykdytojo teises](#grant-permissions-to-the-service-principal-to-access-the-storage-account) pasiekti saugyklos paskyrą.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrano kopija rodo esamą pagrindinę paslaugą.":::

6. Jei rezultatai nepateikiami, [sukurkite naują paslaugos vykdytoją](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Sukurkite naujas pagrindines paslaugas

1. Įdiekite naujausią Azure Active Directory versiją PowerShell Graph. Norėdami gauti daugiau informacijos, eikite [Įdiegti Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Kompiuteryje paspauskite klaviatūros klavišą "Windows" ir ieškokite **"Windows PowerShell** " ir pasirinkite **Vykdyti kaip administratorių**.

   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

2. Naudodami Azure AD „PowerShell“ modulį sukurkite pagrindinę Customer Insights.

   1. „PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Pakeiskite *[savo katalogo ID]* faktiniu "Azure" prenumeratos katalogo ID, jei norite sukurti pagrindinį paslaugos teikėją. Aplinkos pavadinimo parametras, `AzureEnvironmentName` yra pasirinktinis.
  
   1. Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ši komanda sukuria "Customer Insights" aptarnavimo pagrindą pasirinktoje "Azure" prenumeratoje.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros

Norint suteikti teises saugyklos abonemento, kurį norite naudoti "Customer Insights", paslaugų vykdytojui, saugojimo paskyrai arba konteineriui turi būti priskirtas vienas iš šių vaidmenų:

|Kredencialų|Reikalavimai|
|----------|------------|
|Šiuo metu prisijungęs vartotojas|**Vaidmuo**: "Storage Blob Data Reader", "Storage Blob" bendraautoris arba "Storage Blob" savininkas.<br>**Lygis**: leidimai, suteikti saugyklos paskyroje arba konteineryje.</br>|
|"Customer Insights Service Principal" -<br>Naudojimas Azure Data Lake Storage kaip duomenų šaltinis</br>|1 parinktis<ul><li>**Vaidmuo**: "Storage Blob Data Reader", "Storage Blob Data Contributor" arba "Storage Blob Data Owner".</li><li>**Lygis**: saugyklos paskyroje suteikti leidimai.</li></ul>2 *parinktis (nebendrinant paslaugos pagrindinės prieigos prie saugyklos paskyros)*<ul><li>**1** vaidmuo: "Storage Blob Data Reader", "Storage Blob Data Contributor" arba "Storage Blob Data Owner".</li><li>**Lygis**: konteineriui suteiktos teisės.</li><li>**2** vaidmuo: "Storage Blob Data Delegator".</li><li>**Lygis**: saugyklos paskyroje suteikti leidimai.</li></ul>|
|"Customer Insights Service Principal" - <br>Naudojimas Azure Data Lake Storage kaip išvestis arba paskirties vieta</br>|1 parinktis<ul><li>**Vaidmuo**: "Storage Blob Data Contributor" arba "Storage Blob" savininkas.</li><li>**Lygis**: saugyklos paskyroje suteikti leidimai.</li></ul>2 *parinktis (nebendrinant paslaugos pagrindinės prieigos prie saugyklos paskyros)*<ul><li>**Vaidmuo**: "Storage Blob Data Contributor" arba "Storage Blob" savininkas.</li><li>**Lygis**: konteineriui suteiktos teisės.</li><li>**2** vaidmuo: "Storage Blob Delegator".</li><li>**Lygis**: saugyklos paskyroje suteikti leidimai.</li></ul>|

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

1. Atidarykite saugyklos paskyrą, prie kurios prieigą turėtų "Customer Insights" paslaugų vykdytojas.

1. Kairiojoje srityje pažymėkite **Prieigos valdiklis (IAM)** ir tada pasirinkite **Įtraukti** > **Įtraukti vaidmens priskyrimą**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrano kopija rodo Azure portalą, kai pridedamas vaidmens priskyrimas.":::

1. Srityje **Įtraukti vaidmenų priskyrimą** nustatykite šias ypatybes:
   - **Vaidmuo**: "Storage Blob Data Reader", "Storage Blob" bendraautoris arba "Storage Blob" savininkas, pagrįstas anksčiau išvardytais kredencialais.
   - **Prieigos priskyrimas**: **vartotojui, grupei arba paslaugos vykdytojui**
   - **Pasirinkite** narius: **"Dynamics 365 AI for Customer Insights** " ([pagrindinis aptarnavimo principas](#create-a-new-service-principal), kurį peržvelgėte anksčiau atlikdami šią procedūrą)

1. Pasirinkite **Peržiūra + priskyrimas**.

Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Įveskite "Azure" išteklių ID arba išsamią "Azure" prenumeratos informaciją į "Customer Insights" saugyklos abonemento priedą

Pridėkite "Data Lake Storage" paskyrą "Customer Insights", kad išsaugotumėte [išvesties duomenis](manage-environments.md) arba [naudotumėte ją kaip duomenų šaltinis](connect-dataverse-managed-lake.md). Pasirinkite ištekliais [pagrįstą](#resource-based-storage-account-connection) arba [prenumerata pagrįstą](#subscription-based-storage-account-connection) metodą ir atlikite šiuos veiksmus.

### <a name="resource-based-storage-account-connection"></a>Ištekliais pagrįstos saugyklos paskyros ryšys

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Kairiojoje srityje eikite į **Parametrų** > **galiniai punktai**.

1. Kopijuokite talpinimo paskyros išteklių ID vertę.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopijuokite talpinimo paskyros išteklių ID vertę.":::

1. Programoje "Customer Insights" ištekliaus ID įterpkite išteklių lauke, rodomame saugyklos abonemento ryšio ekrane.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::

1. Tęskite likusius veiksmus programoje "Customer Insights", kad pridėtumėte saugyklos paskyrą.

### <a name="subscription-based-storage-account-connection"></a>Prenumerata pagrįstos talpinimo paskyros jungtis

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Kairiojoje srityje eikite į **Parametrų** > **Ypatybės**.

1. Peržiūrėkite **prenumeratą**, **išteklių grupę** ir **saugyklos abonemento pavadinimą**, kad įsitikintumėte, jog "Customer Insights" pasirinkote tinkamas reikšmes.

1. Programoje "Customer Insights" pridėdami saugyklos paskyrą pasirinkite atitinkamų laukų reikšmes.

1. Tęskite likusius veiksmus programoje "Customer Insights", kad pridėtumėte saugyklos paskyrą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
