---
title: Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę tarnybą
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
ms.openlocfilehash: 36ad957f59b23df6ee83d9d90898ef03ddfd320a
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011851"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Prisijunkite prie Azure Data Lake Storage paskyros naudodami pagrindinę "Azure" tarnybą

Šiame straipsnyje aptariama, kaip prisijungti prie Dynamics 365 Customer Insights Azure Data Lake Storage paskyros naudojant "Azure" tarnybos pagrindinę direktorę, o ne saugyklos abonemento raktus.

Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus. Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas. Galite naudoti aptarnavimo principus, kad saugiai [įtrauktumėte arba redaguotumėte aplanką "Common Data Model" kaip duomenų šaltinis](connect-common-data-model.md) arba [sukurtumėte arba atnaujintumėte aplinką](create-environment.md).

> [!IMPORTANT]
>
> - Duomenų ežero saugyklos abonementas, kuriame bus naudojamas pagrindinis paslaugos vykdytojas, turi būti Gen2 ir turi turėti [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace). "Azure Data Lake Gen1" saugyklos abonementai nepalaikomi.
> - Jums reikia administratoriaus teisių, kad "Azure" klientas sukurtumėte pagrindinį paslaugų teikėją.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Pagrindinės "Customer Insights" "Azure" tarnybos kūrimas

Prieš kurdami naują "Customer Insights" aptarnavimo pagrindinį direktorių, patikrinkite, ar jis jau yra jūsų organizacijoje.

### <a name="look-for-an-existing-service-principal"></a>Ieškokite esančių pagrindinių paslaugų

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

2. Iš **Azure paslaugos**, pasirinkite **Azure Active Directory**.

3. Dalyje **Tvarkyti** pasirinkite **"Microsoft" taikomoji programa**.

4. Įtraukite filtrą, skirtą **programos ID pradėti**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nuo pavadinimo `Dynamics 365 AI for Customer Insights` arba ieškoti jo.

5. Jei randate sutampantį įrašą, tai reiškia, kad pagrindinė paslauga jau yra.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Ekrano kopija rodo esamą pagrindinę paslaugą.":::

6. Jei rezultatai negrąžinami, galite [sukurti naują aptarnavimo vykdytoją](#create-a-new-service-principal). Daugeliu atvejų jis jau egzistuoja ir jums tereikia suteikti leidimus pagrindinei tarnybos vykdytojui, kad galėtumėte pasiekti saugyklos paskyrą.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros

Eikite į "Azure" portalą, kad suteiktumėte teises aptarnavimo pagrindinei direktorei saugyklos abonementui, kurį norite naudoti "Customer Insights". Saugojimo sąskaitai arba konteineriui turi būti priskirtas vienas iš šių vaidmenų:

|Kredencialų|Reikalavimai|
|----------|------------|
|Šiuo metu prisijungęs vartotojas|**Vaidmuo**: saugyklos BLOB duomenų skaitytuvas, saugyklos BLOB bendraautoris arba saugyklos BLOB savininkas.<br>**Lygis**: teisės gali būti suteikiamos saugojimo paskyroje arba konteineryje.</br>|
|"Customer Insights Service" pagrindinis elementas –<br>Naudojimas Azure Data Lake Storage kaip duomenų šaltinis</br>|1 parinktis<ul><li>**Vaidmuo**: saugyklos BLOB duomenų skaitytuvas, saugyklos BLOB duomenų bendraautoris arba saugyklos BLOB duomenų savininkas.</li><li>**Lygis**: teisės turėtų būti suteikiamos saugojimo paskyroje.</li></ul>2 *galimybė (nebendrinant pagrindinės paslaugos prieigos prie saugyklos paskyros)*<ul><li>**1** vaidmuo: saugyklos BLOB duomenų skaitytuvas, saugyklos BLOB duomenų bendraautoris arba saugyklos BLOB duomenų savininkas.</li><li>**Lygis**: Leidimai turi būti suteikti konteineriui.</li><li>**2** vaidmuo: saugyklos BLOB duomenų delegatas.</li><li>**Lygis**: teisės turėtų būti suteikiamos saugojimo paskyroje.</li></ul>|
|"Customer Insights Service" pagrindinis elementas – <br>Naudojimas Azure Data Lake Storage kaip išvestis arba paskirties vieta</br>|1 parinktis<ul><li>**Vaidmuo**: saugyklos BLOB duomenų bendraautoris arba saugyklos BLOB savininkas.</li><li>**Lygis**: teisės turėtų būti suteikiamos saugojimo paskyroje.</li></ul>2 *galimybė (nebendrinant pagrindinės paslaugos prieigos prie saugyklos paskyros)*<ul><li>**Vaidmuo**: saugyklos BLOB duomenų bendraautoris arba saugyklos BLOB savininkas.</li><li>**Lygis**: Leidimai turi būti suteikti konteineriui.</li><li>**2** vaidmuo: saugyklos BLOB delegatorius.</li><li>**Lygis**: teisės turėtų būti suteikiamos saugojimo paskyroje.</li></ul>|

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.

1. Atidarykite saugyklos abonementą, prie kurio turėtų prieiti "Customer Insights" aptarnavimo vykdytojas.

1. Kairiojoje srityje pažymėkite **Prieigos valdiklis (IAM)** ir tada pasirinkite **Įtraukti** > **Įtraukti vaidmens priskyrimą**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Ekrano kopija rodo Azure portalą, kai pridedamas vaidmens priskyrimas.":::

1. Srityje **Įtraukti vaidmenų priskyrimą** nustatykite šias ypatybes:
   - Vaidmuo: saugyklos BLOB duomenų skaitytuvas, saugyklos BLOB bendraautoris arba saugyklos BLOB savininkas pagal pirmiau išvardytus kredencialus.
   - Priskirkite prieigą prie: **Vartotojo, grupės ar pagrindinių paslaugų**
   - Pasirinkite narius: **"Dynamics 365" AI, skirtą "Customer Insights"** (aptarnavimo vykdytojas [,](#create-a-new-service-principal) kurio ieškojote anksčiau šioje procedūroje)

1. Pasirinkite **Peržiūra + priskyrimas**.

Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Įveskite "Azure" išteklių ID arba "Azure" prenumeratos informaciją saugyklos abonemento priede prie "Customer Insights"

Galite pridėti "Data Lake Storage" abonementą "Customer Insights", kad išsaugotumėte [išvesties duomenis](manage-environments.md) arba [panaudotumėte juos kaip duomenų šaltinis](connect-dataverse-managed-lake.md). Ši parinktis leidžia pasirinkti tarp ištekliaus grindžiamo ar prenumeratos grindžiamo metodo. Atsižvelgdami į tai, kurį metodą pasirinksite, atlikite veiksmus, nurodytus viename iš toliau nurodytų skyrių.

### <a name="resource-based-storage-account-connection"></a>Ištekliais pagrįstos saugyklos paskyros ryšys

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Kairiojoje srityje eikite į **Parametrų** > **galiniai punktai**.

1. Kopijuokite talpinimo paskyros išteklių ID vertę.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopijuokite talpinimo paskyros išteklių ID vertę.":::

1. Programoje "Customer Insights" įterpkite ištekliaus ID į išteklių lauką, rodomą saugojimo abonemento ryšio ekrane.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::   

1. Tęskite likusius "Customer Insights" veiksmus, kad pridėtumėte saugyklos abonementą.

### <a name="subscription-based-storage-account-connection"></a>Prenumerata pagrįstos talpinimo paskyros jungtis

1. Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.

1. Kairiojoje srityje eikite į **Parametrų** > **Ypatybės**.

1. Peržiūrėkite **prenumeratą**, **išteklių grupę** ir **saugyklos abonemento pavadinimą**, kad įsitikintumėte, jog "Customer Insights" pasirinkote tinkamas reikšmes.

1. Pridėdami saugojimo abonementą, "Customer Insights" pasirinkite atitinkamų laukų reikšmes.

1. Tęskite likusius "Customer Insights" veiksmus, kad pridėtumėte saugyklos abonementą.

### <a name="create-a-new-service-principal"></a>Sukurkite naujas pagrindines paslaugas

1. Įdiekite naujausią Azure Active Directory versiją PowerShell Graph. Norėdami gauti daugiau informacijos, eikite [Įdiegti Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. Kompiuteryje paspauskite klaviatūros klavišą "Windows", ieškokite **"Windows PowerShell"** ir pasirinkite **Vykdyti administratoriaus teisėmis**.

   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.

2. Naudodami Azure AD „PowerShell“ modulį sukurkite pagrindinę Customer Insights.

   1. „PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Pakeiskite *[savo katalogo ID]* faktiniu "Azure" prenumeratos katalogo ID, kuriame norite sukurti pagrindinį paslaugų teikėją. Aplinkos pavadinimo parametras, `AzureEnvironmentName` yra pasirinktinis.
  
   1. Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Ši komanda sukuria "Customer Insights" aptarnavimo pagrindinę priemonę pasirinktoje "Azure" prenumeratoje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
