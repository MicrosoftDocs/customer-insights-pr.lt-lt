---
title: Prisijunkite prie „Azure Data Lake Storage Gen2“ paskyros su pagrindinėmis paslaugomis
description: Naudokite „Azure“ pagrindines paslaugas publikos įžvalgoms, kurios prisijungia prie jūsų turimo duomenų telkinio pridedant jį prie publikos įžvalgų.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596509"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Prijunkite „Azure Data Lake Storage Gen2“ paskyrą prie „Azure“ pagrindinių paslaugų publikos įžvalgoms

Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus. Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas. Perskaitykite tam, kad sužinotumėte, kaip prijungti publikos įžvalgas prie „Azure Data Lake Storage Gen2“ paskyros naudojant „Azure“ pagrindines paslaugas, o ne paskyros raktų talpinimą. 

Galite naudoti pagrindines paslaugas tam, kad saugiai [įtrauktumėte ar redaguotumėte „Common Data Model“ katalogą kaip duomenų šaltinį](connect-common-data-model.md) ar [sukurtumėte naują ar atnaujintumėte esamą aplinką](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - „Azure Data lake Gen2” saugyklos paskyrai, norinčiai naudotis pagrindine tarnyba, turi būti įjungta [Hierarchinė vardų sritis (HNS)](/azure/storage/blobs/data-lake-storage-namespace).
> - Jums reikia administratoriaus teisių jūsų „Azure“ prenumeratai siekiant sukurti pagrindines paslaugas.

## <a name="create-azure-service-principal-for-audience-insights"></a>Sukurti „Azure“ pagrindines paslaugos publikos įžvalgoms

Prieš sukurdami naujas pagrindines paslaugas publikos įžvalgoms, patikrinkite, ar jos jau yra jūsų organizacijoje.

### <a name="look-for-an-existing-service-principal"></a>Ieškokite esančių pagrindinių paslaugų

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

2. Pasirinkite **„Azure Active Directory“** iš „Azure“ paslaugų.

3. Skyriuje **Valdyti**, pasirinkite **Įmonės programos**.

4. Ieškokite publikos įžvalgų pirmosios šalies programos ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar pavadinimo „`Dynamics 365 AI for Customer Insights`“.

5. Jei surasite atitinkamą įrašą, reiškia, kad pagrindinės paslaugos publikos įžvalgoms egzistuoja. Jums nereikia dar kartą jo sukurti.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Momentinė nuotrauka rodanti esančias pagrindines paslaugas.":::
   
6. Jei negaunama jokių rezultatų sukurkite naujas pagrindines paslaugas.

### <a name="create-a-new-service-principal"></a>Sukurkite naujas pagrindines paslaugas

1. Įdiekite naujausią **„Azure Active Directory PowerShell for Graph“**. Dėl daugiau informacijos, žr. [Diegti „Azure Active Directory PowerShell for Graph“](/powershell/azure/active-directory/install-adv2).
   - Jūsų kompiuteryje pasirinkite „Windows“ mygtuką jūsų klaviatūroje ir ieškokite **„Windows PowerShell“** ir **Vykdyti kaip administratoriui**.
   
   - „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

2. Sukurkite pagrindines paslaugas publikos įžvalgoms su „Azure AD PowerShell Module“.
   - „PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Pakeiskite „jūsų nuomotojo ID“ esančiu jūsų nuomotojo ID, kuriame norite sukurti pagrindines paslaugas. Aplinkos pavadinimo parametras `AzureEnvironmentName` yra pasirinktinas.
  
   - Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ši komanda sukuria pagrindines paslaugas publikos įžvalgoms pasirinktame nuomotojuje.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros

Eikite į „Azure“ portalą tam, kad suteiktumėte leidimus pagrindinėms paslaugoms talpinimo paskyroje, kurioje norite naudoti publikos įžvalgas.

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

1. Atverkite talpinimo paskyrą, kurioje norite pagrindinių paslaugų prieigos prie publikos įžvalgų.

1. Pasirinkite **Prieigos valdymas (IAM)** iš naršymo juostos ir pasirinkite **Įtraukti** > **Įtraukti vaidmenis priskyrimą**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Momentinė ekrano nuotrauka rodanti „Azure“ portalą įtraukiant vaidmens priskyrimą.":::
   
1. **Įtraukti vaidmens priskyrimo** juostoje nustatykite šias ypatybes:
   - Vaidmuo: *„Storage Blob Data Contributor“*
   - Priskirkite prieigą prie: *Vartotojo, grupės ar pagrindinių paslaugų*
   - Pasirinkite: *„Dynamics 365 AI Customer Insights“* ( [jūsų sukurtos pagrindinės paslaugos](#create-a-new-service-principal))

1.  Pasirinkite **Įrašyti**.

Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Įveskite „Azure“ išteklių ID arba „Azure“ prenumeravimo išsamią informaciją į talpinimo paskyros priedą prie publikos įžvalgų.

Pridėkite „Azure Data Lake storage“ paskyrą publikos įžvalgose prie [talpinimo išvesties duomenų](manage-environments.md) ar [naudokite juos kaip duomenų šaltinį](connect-common-data-service-lake.md). Pasirinkus „Azure Data Lake“ parinktį ji leidžia jums rinktis tarp ištekliais pagrįstos ar prenumerata pagrįstos prieigos.

Atlikite tolesnius žingsnius tam, kad gautumėte reikiamą informaciją apie pasirinktą prieigą.

### <a name="resource-based-storage-account-connection"></a>Ištekliais pagrįstos saugyklos paskyros ryšys

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Eikite į **Nustatymai** > **Ypatybės** naršymo juostoje.

1. Kopijuokite talpinimo paskyros išteklių ID vertę.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopijuokite talpinimo paskyros išteklių ID vertę.":::

1. Publikos įžvalgose įveskite išteklių ID išteklių laukelyje rodomame talpinimo paskyros jungties ekrane.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::   
   
1. Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.

### <a name="subscription-based-storage-account-connection"></a>Prenumerata pagrįstos talpinimo paskyros jungtis

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Eikite į **Nustatymai** > **Ypatybės** naršymo juostoje.

1. Peržiūrėkite **Prenumerata**, **Išteklių grupė** ir talpinimo paskyros **Pavadinimas** siekiant užsitikrinti, kad pasirinkote tinkamas vertes publikos įžvalgose.

1. Publikos įžvalgose pasirinkite vertes arba atitinkamus laukelius pridedant talpinimo paskyrą.
   
1. Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]