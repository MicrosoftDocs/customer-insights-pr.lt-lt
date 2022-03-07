---
title: Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę tarnybą
description: Norėdami prisijungti prie savo duomenų telkinio, naudokite pagrindinę "Azure" tarnybą.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d593880b06bd21e96826039a67382b75a4296a87
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354200"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą

Šiame straipsnyje aptariama, kaip prisijungti prie Dynamics 365 Customer Insights Azure Data Lake Storage paskyros naudojant "Azure" aptarnavimo pagrindinį, o ne saugyklos paskyros raktus. 

Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus. Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas. Galite naudoti aptarnavimo vadovus, kad saugiai [įtrauktumėte arba redaguotumėte aplanką "Common Data Model" kaip duomenų šaltinis](connect-common-data-model.md) arba [kurtumėte arba atnaujintumėte aplinką](create-environment.md).

> [!IMPORTANT]
> - Duomenų ežero saugyklos paskyra, kuri naudosis aptarnavimo pagrindiniu direktoriumi, turi būti Gen2 ir turėti [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace). "Azure Data Lake Gen1" saugyklos abonementai nepalaikomi.
> - Norint sukurti tarnybos vadovą, jums reikia administratoriaus teisių, kad sukurtumėte tarnybos vadovą.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Pagrindinės "Customer Insights" "Azure" tarnybos kūrimas

Prieš kurdami naują "Customer Insights" aptarnavimo pagrindinį vadovą, patikrinkite, ar jis jau yra jūsų organizacijoje.

### <a name="look-for-an-existing-service-principal"></a>Ieškokite esančių pagrindinių paslaugų

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

2. Iš **Azure paslaugos**, pasirinkite **Azure Active Directory**.

3. Skyriuje **Valdyti**, pasirinkite **Įmonės programos**.

4. Ieškokite „Microsoft” programos ID:
   - Auditorijos įžvalgos: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` su pavadinimu `Dynamics 365 AI for Customer Insights`
   - Įsitraukimo įžvalgos: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` su pavadinimu `Dynamics 365 AI for Customer Insights engagement insights`

5. Jei randate sutampantį įrašą, tai reiškia, kad pagrindinė paslauga jau yra. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrano kopija rodo esamą pagrindinę paslaugą.":::
   
6. Jei negaunama jokių rezultatų sukurkite naujas pagrindines paslaugas.

>[!NOTE]
>Norėdami pasinaudoti visa Dynamics 365 Customer Insights galia, siūlome į pagrindinį aptarnavimą įtraukti abi programas.

### <a name="create-a-new-service-principal"></a>Sukurkite naujas pagrindines paslaugas

1. Įdiekite naujausią Azure Active Directory versiją PowerShell Graph. Norėdami gauti daugiau informacijos, eikite [Įdiegti Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

2. Naudodami Azure AD „PowerShell“ modulį sukurkite pagrindinę Customer Insights.

   1. „PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Pakeiskite *[jūsų nuomotojo ID]* faktiniu jūsų nuomotojo ID, kuriame norite sukurti pagrindines paslaugas. Aplinkos pavadinimo parametras, `AzureEnvironmentName` yra pasirinktinis.
  
   1. Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ši komanda sukuria pagrindines paslaugas publikos įžvalgoms pasirinktame nuomotojuje. 

   1. Įveskite `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ši komanda sukuria pagrindinę aptarnavimo paslaugą įtraukimo įžvalgoms pasirinktam nuomotojui.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros

Eikite į „Azure“ portalą tam, kad suteiktumėte leidimus pagrindinėms paslaugoms talpinimo paskyroje, kurioje norite naudoti publikos įžvalgas.

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

1. Atverkite talpinimo paskyrą, kurioje norite pagrindinių paslaugų prieigos prie publikos įžvalgų.

1. Kairiojoje srityje pažymėkite **Prieigos valdiklis (IAM)** ir tada pasirinkite **Įtraukti** > **Įtraukti vaidmens priskyrimą**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrano kopija rodo Azure portalą, kai pridedamas vaidmens priskyrimas.":::

1. Srityje **Įtraukti vaidmenų priskyrimą** nustatykite šias ypatybes:
   - Vaidmuo: **„Storage Blob Data Contributor“**
   - Priskirkite prieigą prie: **Vartotojo, grupės ar pagrindinių paslaugų**
   - Pažymėkite: **"Dynamics 365" AI Customer Insights** ir **"Dynamics 365" AI Customer Insights bendradarbiavimo įžvalgos** (dvi [pagrindinės paslaugos](#create-a-new-service-principal) kurias sukūrėte anksčiau šios procedūros metu)

1.  Pasirinkite **Įrašyti**.

Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Įveskite „Azure“ išteklių ID arba „Azure“ prenumeravimo išsamią informaciją į talpinimo paskyros priedą prie publikos įžvalgų.

Galite pridėti „Data Lake Storage” paskyrą auditorijos įžvalgoms, kad [būtų išsaugoti išvesties duomenys](manage-environments.md) arba [naudokite juos kaip duomenų šaltinį](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). Ši parinktis leidžia pasirinkti tarp ištekliaus grindžiamo ar prenumeratos grindžiamo metodo. Atsižvelgdami į tai, kurį metodą pasirinksite, atlikite veiksmus, nurodytus viename iš toliau nurodytų skyrių.

### <a name="resource-based-storage-account-connection"></a>Ištekliais pagrįstos saugyklos paskyros ryšys

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Kairiojoje srityje eikite į **Parametrų** > **Ypatybės**.

1. Kopijuokite talpinimo paskyros išteklių ID vertę.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopijuokite talpinimo paskyros išteklių ID vertę.":::

1. Auditorijos įžvalgose įterpkite ištekliaus ID į išteklių lauką, rodomą saugyklos paskyros prisijungimo ekrane.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::   

1. Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.

### <a name="subscription-based-storage-account-connection"></a>Prenumerata pagrįstos talpinimo paskyros jungtis

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Kairiojoje srityje eikite į **Parametrų** > **Ypatybės**.

1. Peržiūrėkite **Prenumerata**, **Išteklių grupė** ir talpinimo paskyros **Pavadinimas** siekiant užsitikrinti, kad pasirinkote tinkamas vertes publikos įžvalgose.

1. Kai pridedate saugyklos paskyrą, auditorijos įžvalgose pasirinkite atitinkamų laukų reikšmes.

1. Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]