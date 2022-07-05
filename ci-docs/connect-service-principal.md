---
title: Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą
description: Norėdami prisijungti prie savo duomenų telkinio, naudokite pagrindinę "Azure" tarnybą.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082243"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą

Šiame straipsnyje aptariama, kaip prisijungti Dynamics 365 Customer Insights Azure Data Lake Storage prie paskyros naudojant "Azure" paslaugos pagrindinę, o ne saugyklos abonemento raktus.

Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus. Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas. Galite naudoti pagrindinius paslaugų teikėjus, kad saugiai [įtrauktumėte arba redaguotumėte aplanką "Common Data Model" kaip duomenų šaltinis](connect-common-data-model.md) arba [sukurtumėte ar atnaujintumėte aplinką](create-environment.md).

> [!IMPORTANT]
>
> - "Data Lake Storage" paskyra, kuri naudos pagrindinę paslaugą, turi būti "Gen2" ir joje [turi būti įgalinta hierarchinė vardų sritis](/azure/storage/blobs/data-lake-storage-namespace). "Azure Data Lake Gen1" saugyklos paskyros nepalaikomos.
> - Jums reikia administratoriaus teisių, kad jūsų "Azure" klientas galėtų sukurti pagrindinį paslaugos teikėją.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Pagrindinės "Customer Insights" "Azure" tarnybos kūrimas

Prieš kurdami naują "Customer Insights" paslaugų teikėją, patikrinkite, ar jis jau yra jūsų organizacijoje.

### <a name="look-for-an-existing-service-principal"></a>Ieškokite esančių pagrindinių paslaugų

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

2. Iš **Azure paslaugos**, pasirinkite **Azure Active Directory**.

3. Dalyje **Valdyti** pasirinkite **"Microsoft" programa**.

4. Įtraukite programos ID filtrą **pradėkite nuo**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` pavadinimo arba ieškokite jo pavadinimo `Dynamics 365 AI for Customer Insights`.

5. Jei randate sutampantį įrašą, tai reiškia, kad pagrindinė paslauga jau yra.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrano kopija rodo esamą pagrindinę paslaugą.":::

6. Jei rezultatai nepateikiami, galite [sukurti naują paslaugos vykdytoją](#create-a-new-service-principal). Daugeliu atvejų jis jau egzistuoja ir jums tereikia suteikti leidimus paslaugos vykdytojui, kad galėtumėte pasiekti saugyklos paskyrą.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros

Eikite į "Azure" portalą ir suteikite teises paslaugos vykdytojui naudoti saugyklos paskyrą, kurią norite naudoti "Customer Insights". Saugojimo paskyrai arba konteineriui turi būti priskirtas vienas iš šių vaidmenų:

|Kredencialų|Reikalavimai|
|----------|------------|
|Šiuo metu prisijungęs vartotojas|**Vaidmuo**: "Storage Blob Data Reader", "Storage Blob" bendraautoris arba "Storage Blob" savininkas.<br>**Lygis**: leidimai gali būti suteikti saugyklos paskyroje arba konteineryje.</br>|
|"Customer Insights Service Principal" -<br>Naudojimas Azure Data Lake Storage kaip duomenų šaltinis</br>|1 parinktis<ul><li>**Vaidmuo**: "Storage Blob Data Reader", "Storage Blob Data Contributor" arba "Storage Blob Data Owner".</li><li>**Lygis**: leidimai turėtų būti suteikti saugyklos paskyroje.</li></ul>2 *parinktis (nebendrinant paslaugos pagrindinės prieigos prie saugyklos paskyros)*<ul><li>**1** vaidmuo: "Storage Blob Data Reader", "Storage Blob Data Contributor" arba "Storage Blob Data Owner".</li><li>**Lygis**: konteineriui turėtų būti suteikti leidimai.</li><li>**2** vaidmuo: "Storage Blob Data Delegator".</li><li>**Lygis**: leidimai turėtų būti suteikti saugyklos paskyroje.</li></ul>|
|"Customer Insights Service Principal" - <br>Naudojimas Azure Data Lake Storage kaip išvestis arba paskirties vieta</br>|1 parinktis<ul><li>**Vaidmuo**: "Storage Blob Data Contributor" arba "Storage Blob" savininkas.</li><li>**Lygis**: leidimai turėtų būti suteikti saugyklos paskyroje.</li></ul>2 *parinktis (nebendrinant paslaugos pagrindinės prieigos prie saugyklos paskyros)*<ul><li>**Vaidmuo**: "Storage Blob Data Contributor" arba "Storage Blob" savininkas.</li><li>**Lygis**: konteineriui turėtų būti suteikti leidimai.</li><li>**2** vaidmuo: "Storage Blob Delegator".</li><li>**Lygis**: leidimai turėtų būti suteikti saugyklos paskyroje.</li></ul>|

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

1. Atidarykite saugyklos paskyrą, prie kurios prieigą turėtų "Customer Insights" paslaugų vykdytojas.

1. Kairiojoje srityje pažymėkite **Prieigos valdiklis (IAM)** ir tada pasirinkite **Įtraukti** > **Įtraukti vaidmens priskyrimą**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrano kopija rodo Azure portalą, kai pridedamas vaidmens priskyrimas.":::

1. Srityje **Įtraukti vaidmenų priskyrimą** nustatykite šias ypatybes:
   - Vaidmuo: "Storage Blob Data Reader", "Storage Blob" bendraautoris arba "Storage Blob" savininkas, pagrįstas anksčiau išvardytais kredencialais.
   - Priskirkite prieigą prie: **Vartotojo, grupės ar pagrindinių paslaugų**
   - Pasirinkite narius: **"Dynamics 365 AI for Customer Insights** " ([pagrindinis aptarnavimo principas](#create-a-new-service-principal), kurį peržvelgėte anksčiau atlikdami šią procedūrą)

1. Pasirinkite **Peržiūra + priskyrimas**.

Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Įveskite "Azure" išteklių ID arba išsamią "Azure" prenumeratos informaciją į "Customer Insights" saugyklos abonemento priedą

"Customer Insights" galite pridėti "Data Lake Storage" paskyrą, kad išsaugotumėte išvesties duomenis [, arba](manage-environments.md) naudoti ją kaip duomenų šaltinis [.](connect-dataverse-managed-lake.md) Ši parinktis leidžia pasirinkti tarp ištekliaus grindžiamo ar prenumeratos grindžiamo metodo. Atsižvelgdami į tai, kurį metodą pasirinksite, atlikite veiksmus, nurodytus viename iš toliau nurodytų skyrių.

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

### <a name="create-a-new-service-principal"></a>Sukurkite naujas pagrindines paslaugas

1. Įdiekite naujausią Azure Active Directory versiją PowerShell Graph. Norėdami gauti daugiau informacijos, eikite [Įdiegti Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Kompiuteryje paspauskite klaviatūros klavišą "Windows" ir ieškokite **"Windows PowerShell** " ir pasirinkite **Vykdyti kaip administratorių**.

   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

2. Naudodami Azure AD „PowerShell“ modulį sukurkite pagrindinę Customer Insights.

   1. „PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Pakeiskite *[savo katalogo ID]* faktiniu "Azure" prenumeratos katalogo ID, jei norite sukurti pagrindinį paslaugos teikėją. Aplinkos pavadinimo parametras, `AzureEnvironmentName` yra pasirinktinis.
  
   1. Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ši komanda sukuria "Customer Insights" aptarnavimo pagrindą pasirinktoje "Azure" prenumeratoje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
