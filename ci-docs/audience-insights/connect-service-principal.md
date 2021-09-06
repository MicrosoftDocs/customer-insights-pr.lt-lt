---
title: Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę tarnybą
description: Norėdami prisijungti prie savo duomenų telkinio, naudokite pagrindinę "Azure" tarnybą.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461158"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus. Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas. Sužinokite, kaip prisijungti prie Dynamics 365 Customer Insights su Azure Data Lake Storage paskyra, naudojant "Azure" pagrindinę paslaugą, vietoj saugyklos paskyros raktų. 

Pagrindinę tarnybą galite naudoti, jei norite saugiai [įtraukti arba redaguoti Bendrą duomenų modelio aplanką kaip duomenų šaltinį](connect-common-data-model.md) arba [kurti ar naujinti aplinką](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - "Data Lake" saugyklos paskyra, kurią naudos<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> pagrindinė tarnyba turi turėti [įgalintą hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).
> - Jums reikia administratoriaus teisių jūsų „Azure“ prenumeratai siekiant sukurti pagrindines paslaugas.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Pagrindinės "Customer Insights" "Azure" tarnybos kūrimas

Prieš kurdami naują pagrindinę auditorijos įžvalgų ar įtraukimo įžvalgų tarnybą, patikrinkite, ar ji jau yra jūsų organizacijoje.

### <a name="look-for-an-existing-service-principal"></a>Ieškokite esančių pagrindinių paslaugų

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

2. Iš **Azure paslaugos**, pasirinkite **Azure Active Directory**.

3. Skyriuje **Valdyti**, pasirinkite **Įmonės programos**.

4. Ieškokite „Microsoft“<!--note from editor: Via Microsoft Writing Style Guide.--> Programos ID:
   - Auditorijos įžvalgos: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` su pavadinimu `Dynamics 365 AI for Customer Insights`
   - Įsitraukimo įžvalgos: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` su pavadinimu `Dynamics 365 AI for Customer Insights engagement insights`

5. Jei randate sutampantį įrašą, tai reiškia, kad pagrindinė paslauga jau yra. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrano kopija rodo esamą pagrindinę paslaugą.":::
   
6. Jei negaunama jokių rezultatų sukurkite naujas pagrindines paslaugas.

>[!NOTE]
>Norėdami pasinaudoti visa Dynamics 365 Customer Insights galia, siūlome į pagrindinį aptarnavimą įtraukti abi programas.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Sukurkite naujas pagrindines paslaugas
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Įdiekite naujausią Azure Active Directory versiją PowerShell Graph. Norėdami gauti daugiau informacijos, eikite [Įdiegti Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

2. Naudodami Azure AD „PowerShell“ modulį sukurkite pagrindinę Customer Insights.

   1. „PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Pakeiskite *"[savo nuomotojo ID]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> su faktiniu nuomotojo ID, kur norite sukurti pagrindinę aptarnavimo tarnybą. Aplinkos pavadinimo parametras, `AzureEnvironmentName` yra pasirinktinis.
  
   1. Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ši komanda sukuria pagrindines paslaugas publikos įžvalgoms pasirinktame nuomotojuje. 

   1. Įveskite `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Ši komanda sukuria pagrindinę aptarnavimo paslaugą įtraukimo įžvalgoms<!--note from editor: Edit okay?--> pasirinktame nuomotoje.

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

Galite<!--note from editor: Edit suggested only if this section is optional.--> pridėkite "Data Lake" saugyklos paskyrą auditorijos įžvalgoms, kad [būtų išsaugoti išvesties duomenys](manage-environments.md) arba [naudokite juos kaip duomenų šaltinį](connect-common-data-service-lake.md). Ši parinktis leidžia pasirinkti tarp ištekliaus grindžiamo ar prenumeratos grindžiamo metodo. Atsižvelgdami į tai, kurį metodą pasirinksite, atlikite veiksmus, nurodytus viename iš toliau nurodytų skyrių.<!--note from editor: Suggested.-->

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