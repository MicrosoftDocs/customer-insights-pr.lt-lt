---
title: Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje
description: Sužinokite, kaip prijungti "Customer Insights" ir Microsoft Dataverse suprasti išvesties objektus, eksportuojamus į Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833686"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje

"Customer Insights" suteikia galimybę išvesties objektus padaryti pasiekiamus kaip [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ši integracija leidžia lengvai dalytis duomenimis ir pasirinktinai kurti naudojant mažo kodo / ne kodo metodą. Išvesties [objektai](#output-entities) yra pasiekiami kaip aplinkos lentelės Dataverse. Galite naudoti duomenis bet kuriai kitai programai, pagrįstai Dataverse lentelėmis. Šios lentelės įgalina scenarijus, pvz., automatizuotas darbo eigas naudojant Power Automate arba kuriant programas su Power Apps.

Prisijungimas prie savo Dataverse aplinkos taip pat leidžia jums nuryti [duomenis iš vietinis duomenų šaltinių naudojant Power Platform duomenų srautus ir šliuzus](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Būtinosios sąlygos

- "Customer Insights" ir Dataverse aplinkos turi būti talpinamos tame pačiame regione.
- Turite atlikti visuotinį administratoriaus vaidmenį Dataverse aplinkoje. Patikrinkite, ar ši [Dataverse aplinka susieta su](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
- Jokia kita "Customer Insights" aplinka dar nesusieta su aplinka, Dataverse prie kurios norite prisijungti. Sužinokite, kaip pašalinti [esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).
- Aplinka Microsoft Dataverse gali prisijungti tik prie vieno saugyklos abonemento. Jis taikomas tik tuo atveju, jei konfigūruojate aplinką, kad galėtumėte [naudoti savo Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Aplinkos prijungimas Dataverse prie "Customer Insights"

Šis **Microsoft Dataverse** veiksmas leidžia susieti "Customer Insights" su Dataverse aplinka kuriant ["Customer Insights" aplinką](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="duomenų bendrinimas su Microsoft Dataverse automatiniu įgalinimu naujoms grynosioms aplinkoms.":::

Administratoriai gali konfigūruoti "Customer Insights", kad prijungtų esamą Dataverse aplinką. Pateikdamas URL Dataverse aplinkai, jis pridedamas prie naujos "Customer Insights" aplinkos.

Jei nenorite naudoti esamos Dataverse aplinkos, sistema sukuria naują nuomotojo "Customer Insights" duomenų aplinką. [Power Platform administratoriai gali valdyti, kas gali kurti aplinkas](/power-platform/admin/control-environment-creation). Kai nustatote naują "Customer Insights" aplinką ir administratorius išjungė aplinkų Dataverse kūrimą visiems, išskyrus administratorius, gali būti, kad negalėsite sukurti naujos aplinkos.

**Įgalinkite duomenų bendrinimą** pažymėdami Dataverse žymės langelį Duomenų bendrinimas.

Jei naudojate savo duomenų ežero saugyklos paskyrą, jums taip pat reikia **teisių identifikatoriaus**. Norėdami gauti daugiau informacijos, kaip gauti teisių identifikatorių, peržiūrėkite šį skyrių.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Įgalinti duomenų bendrinimą su Dataverse savo Azure Data Lake Storage (Peržiūra)

Norint įgalinti duomenų bendrinimą, kai Microsoft Dataverse jūsų aplinka [naudoja jūsų paskyrą Azure Data Lake Storage,](own-data-lake-storage.md) reikia papildomos konfigūracijos. Vartotojas, nustatantis "Customer Insights" aplinką, turi turėti bent **saugyklos BLOB duomenų skaitytuvo** teises *kliento kliento konteineryje* CustomerInsights Azure Data Lake Storage.

1. "Azure" prenumeratoje sukurkite dvi saugos grupes – vieną **"Reader"** saugos grupę ir vieną **bendraautorių** saugos grupę ir nustatykite paslaugą Microsoft Dataverse kaip abiejų saugos grupių savininkę.
2. Tvarkykite "Access Control List" (ACL) savo saugyklos abonemento konteineryje CustomerInsights per šias saugos grupes. Įtraukite paslaugą Microsoft Dataverse ir visas Dataverse verslo programas, pvz., "Dynamics 365 Marketing", į **"Reader"** saugos grupę su **tik** skaitymo teisėmis. Įtraukite *tik* "Customers Insights" taikomąją programą į bendraautorių **saugos** grupę, kad suteiktumėte ir **skaitymo, ir rašymo** teises rašyti profilius ir įžvalgas.

### <a name="limitations"></a>Apribojimai

Naudojant su savo Dataverse paskyra yra du apribojimai Azure Data Lake Storage:

- Yra organizacijos ir Dataverse paskyros susiejimas vienas su Azure Data Lake Storage vienu. Dataverse Kai organizacija yra prijungta prie saugyklos abonemento, ji negali prisijungti prie kito saugyklos abonemento. Šis apribojimas neleidžia užpildyti Dataverse kelių saugojimo paskyrų.
- Duomenų bendrinimas neveiks, jei norint pasiekti "Azure Data Lake" saugyklos abonementą reikia "Azure Private Link" sąrankos, nes ji yra už užkardos. Dataverse šiuo metu nepalaiko ryšio su privačiais galiniais punktais per "Private Link".

### <a name="set-up-powershell"></a>"PowerShell" nustatymas

Norėdami vykdyti "PowerShell" scenarijus, pirmiausia turite atitinkamai nustatyti "PowerShell".

1. Įdiekite naujausią "PowerShell for Graph [Azure Active Directory" versiją](/powershell/azure/active-directory/install-adv2).
   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.
2. Importuokite tris modulius.
    1. "PowerShell" lange įveskite `Install-Module -Name Az.Accounts` ir atlikite veiksmus.
    1. `Install-Module -Name Az.Resources` Pakartokite ir `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigūravimo veiksmai

1. Atsisiųskite du "PowerShell" scenarijus, kuriuos reikia paleisti iš mūsų inžinieriaus "GitHub" [repo](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Norint paleisti šį "PowerShell" scenarijų, reikia *nuomotojo administratoriaus* teisių.
       - Šis "PowerShell" scenarijus sukuria dvi saugos grupes "Azure" prenumeratoje. Vienas skirtas "Reader" grupei, o kitas – bendraautorių grupei ir teiks Microsoft Dataverse paslaugas kaip abiejų šių saugos grupių savininkas.
       - Vykdykite šį "PowerShell" scenarijų naudodami "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
       - Įrašykite abi saugos grupės ID reikšmes, sugeneruotas šio scenarijaus, nes jas naudosime scenarijuje `ByolSetup.ps1`.

        > [!NOTE]
        > Saugos grupės kūrimas gali būti išjungtas nuomotoje. Tokiu atveju reikės neautomatinės sąrankos, o jūsų Azure AD administratorius turėtų įgalinti [saugos grupės kūrimą](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Norint paleisti šį scenarijų, reikia *saugyklos BLOB duomenų savininko* teisių saugyklos abonemento / konteinerio lygiu, arba šis scenarijus sukurs jums. Sėkmingai paleidus scenarijų, jūsų vaidmens priskyrimą galima pašalinti rankiniu būdu.
        - Šis "PowerShell" scenarijus prideda reikiamą "tole" pagrįstą prieigos kontrolę (RBAC) paslaugai Microsoft Dataverse ir visoms Dataverse verslo programoms. Ji taip pat atnaujina su scenarijumi sukurtų saugos grupių prieigos kontrolės sąrašą (ACL) kliento duomenų saugyklų `CreateSecurityGroups.ps1` konteineryje CustomerInsights. Bendraautorių grupė turės *rwx* leidimą, o skaitytojų grupė turės *tik r-x* teises.
        - Vykdykite šį "PowerShell" scenarijų sistemoje "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage, saugyklos abonemento pavadinimas, išteklių grupės pavadinimas ir skaitytuvo bei bendraautoriaus saugos grupės ID reikšmės. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
        - Sėkmingai paleidę scenarijų nukopijuokite išvesties eilutę. Išvesties eilutė atrodo taip: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Įveskite išeigos eilutę, nukopijuotą iš viršaus, **į** aplinkos konfigūravimo veiksmo, skirto Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigūracijos parinktys, skirtos įgalinti duomenų bendrinimą iš savo Azure Data Lake Storage su Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esamo ryšio su Dataverse aplinka šalinimas

Jungiantis prie Dataverse aplinkos, klaidos pranešimas **Ši KOMPAKTINIŲ diskų organizacija jau pridėta prie kito "Customer Insights" egzemplioriaus** reiškia, kad Dataverse aplinka jau naudojama "Customer Insights" aplinkoje. Galite pašalinti esamą ryšį kaip visuotinį aplinkos administratorių Dataverse. Tai gali užtrukti kelias valandas, kad būtų galima užpildyti pakeitimus.

1. Eikite į [Power Apps](https://make.powerapps.com).
1. Pasirinkite aplinką iš aplinkos parinkiklio.
1. Eikite į **sprendimus**
1. Pašalinkite arba panaikinkite sprendimą, pavadintą **Dynamics 365 Customer Insights Kliento kortelės priedu (peržiūra)**.

OR

1. Atidarykite savo Dataverse aplinką.
1. Eikite į **Išplėstiniai nustatymų** > **sprendimai**.
1. **Pašalinkite CustomerInsightsCustomerCard** sprendimą.

Jei ryšio pašalinimas nepavyksta dėl priklausomybių, taip pat turite pašalinti priklausomybes. Daugiau informacijos ieškokite [Remove dependencies](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Išvesties objektai

Kai kurie "Customer Insights" išvesties objektai pasiekiami kaip lentelės.Dataverse Toliau aprašomos numatomos šių lentelių schemos.

- [CustomerProfile](#customerprofile)
- [„AlternateKey”](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [„CustomerMeasure”](#customermeasure)
- [Papildymas](#enrichment)
- [Prognozė](#prediction)
- [Segmento narystė](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Šioje lentelėje pateikiamas vieningasis kliento profilis iš „Customer Insights”. Vieningo kliento profilio schema priklauso nuo objektų ir atributų, naudojamų duomenų suvienijimo procese. Kliento profilio schemoje paprastai yra atributų antrinis rinkinys iš [Kliento profilio „Common Data Model” aprašo](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>„AlternateKey”

Alternatyvaus rakto lentelėje yra suvienodinimo procese dalyvavusių objektų raktų rinkinys.

|Stulpelis  |Tipas  |Aprašymas  |
|---------|---------|---------|
|„DataSourceName”    |Eilutė         | Duomenų šaltinio pavadinimas. Pavyzdžiui: `datasource5`.        |
|EntityName        | String        | "Customer Insights" objekto pavadinimas. Pavyzdžiui: `contact1`.        |
|„AlternateValue”    |String         |Alternatyvusis ID, susietas su kliento ID. Pavyzdys: `cntid_1078`         |
|„KeyRing”           | Kelių eilučių Tekstas        | JSON reikšmė  </br> Pavyzdys: [{„dataSourceName”:„ datasource5 ”,</br>„entityName”:„ contact1”,</br>„preferredKey”:„ cntid_1078”,</br>„keys”:[„ cntid_1078”]}]       |
|CustomerId         | Eilutė        | Vieningojo kliento profilio ID.         |
|„AlternateKeyId”     | GUID         |  Alternatyvų raktą nustatantis GUID pagal msdynci_identifier       |
|„msdynci_identifier” |   Eilutė      |   `DataSourceName|EntityName|AlternateValue`  </br> Pavyzdys: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Šioje lentelėje pateikiamos vartotojų veiklos, galimos „Customer Insights”.

| Stulpelis            | Tipas        | Aprašymas                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Eilutė      | Kliento Profilio ID                                                                      |
| „ActivityId”        | String      | Vidinis kliento veiklos ID (pirminis raktas)                                       |
| „SourceEntityName”  | Eilutė      | Šaltinio objekto pavadinimas                                                                |
| „SourceActivityId”  | Eilutė      | Pirminis raktas iš šaltinio objekto                                                       |
| „ActivityType”      | Eilutė      | Pasirinktinės veiklos semantinis veiklos tipas arba pavadinimas                                        |
| „ActivityTimeStamp” | „DATETIME”    | Veiklos Laiko žyma                                                                      |
| Antraštė             | Eilutė      | Veiklos antraštė arba pavadinimas                                                               |
| Aprašymas       | Eilutė      | Veiklos aprašas                                                                     |
| URL               | Eilutė      | Nuoroda į išorinį URL, būdingą veiklai                                         |
| „SemanticData”      | JSON Eilutė | Apima pagrindinių reikšmių porų sąrašą, skirtą semantinio susiejimo laukams, būdingiems veiklos tipui |
| „RangeIndex”        | Eilutė      | „Unix” laiko žyma, naudojama veiklos laiko planavimo juostai ir efektyvioms diapazono užklausoms rikiuoti |
| „mydynci_unifiedactivityid”   | GUID | Vidinis kliento veiklos ID („ActivityId”) |

### <a name="customermeasure"></a>„CustomerMeasure”

Šioje lentelėje pateikiami kliento atributais pagrįstų matavimų išvesties duomenys.

| Stulpelis             | Tipas             | Aprašymas                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Eilutė           | Kliento profilio ID        |
| Matavimai           | JSON Eilutė      | Pateikiamas matavimų pavadinimų ir reikšmių pagrindinių reikšmių porų sąrašas nurodytam klientui | 
| „msdynci_identifier” | Eilutė           | `Customer_Measure|CustomerId` |
| „msdynci_customermeasureid” | GUID      | Kliento profilio ID |


### <a name="enrichment"></a>Papildymas

Šioje lentelėje pateikiami papildymo proceso rezultatai.

| Stulpelis               | Tipas             |  Aprašymas                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Eilutė           | Kliento profilio ID                                 |
| „EnrichmentProvider”   | Eilutė           | Papildymo tiekėjo pavadinimas                                  |
| „EnrichmentType”       | Eilutė           | Papildymo tipas                                      |
| Reikšmės               | JSON Eilutė      | Papildymo proceso metu sukurtų atributų sąrašas |
| „msdynci_enrichmentid” | GUID             | Nustatantis GUID, sugeneruotas iš „msdynci_identifier” |
| „msdynci_identifier”   | Eilutė           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognozė

Šioje lentelėje pateikiami modelio prognozių rezultatai.

| Stulpelis               | Tipas        | Aprašymas                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Eilutė      | Kliento Profilio ID                                  |
| „ModelProvider”        | Eilutė      | Modelio tiekėjo pavadinimas                                      |
| Modelis                | Eilutė      | Modelio pavadinimas                                                |
| Reikšmės               | JSON Eilutė | Modelio sukurtų atributų sąrašas |
| „msdynci_predictionid” | GUID        | Nustatantis GUID, sugeneruotas iš „msdynci_identifier” | 
| „msdynci_identifier”   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmento narystė

Šioje lentelėje yra klientų profilių segmento narystės informacija.

| Column        | Tipas | Aprašą                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kliento Profilio ID        |
| SegmentProvider      | String       | Programa, kuri publikuoja segmentus.      |
| SegmentMembershipType | String       | Kliento šio segmento narystės įrašo tipas. Palaiko kelis tipus, pvz., klientą, kontaktą arba klientą. Numatytasis: klientas  |
| Segmentai       | JSON Eilutė  | Unikalių segmentų, kurių narys yra kliento profilis, sąrašas      |
| „msdynci_identifier”  | String   | Segmento narystės įrašo unikalusis identifikatorius. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministinis GUID, sukurtas iš`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
