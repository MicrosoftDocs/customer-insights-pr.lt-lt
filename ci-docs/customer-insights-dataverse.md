---
title: Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje
description: Sužinokite, kaip prijungti "Customer Insights" ir Microsoft Dataverse suprasti išvesties objektus, kurie eksportuojami į Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153414"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje

"Customer Insights" suteikia galimybę išvesties objektus padaryti pasiekiamus kaip [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Ši integracija leidžia lengvai dalytis duomenimis ir pasirinktinai kurti naudojant žemo kodo / kodo nebuvimo metodą. Išvesties [objektai](#output-entities) galimi kaip lentelės aplinkoje Dataverse. Duomenis galite naudoti bet kuriai kitai programai, pagrįstoms Dataverse lentelėmis. Šiose lentelėse įgalinami tokie scenarijai kaip automatizuotos darbo eigos arba Power Automate programų kūrimas naudojant Power Apps.

Prisijungę prie savo Dataverse aplinkos taip pat galite nuryti [duomenis iš vietinis duomenų šaltinių naudodami Power Platform duomenų srautus ir šliuzus](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Klientų įžvalgos ir Dataverse aplinkos turi būti priglobtos tame pačiame regione.
- Aplinkoje turite atlikti visuotinio administratoriaus vaidmenį Dataverse. Patikrinkite, ar ši [Dataverse aplinka susieta su](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) tam tikromis saugos grupėmis, ir įsitikinkite, kad esate įtraukti į tas saugos grupes.
- Jokia kita "Customer Insights" aplinka dar nėra susieta su aplinka, Dataverse prie kurios norite prisijungti. Sužinokite, [kaip pašalinti esamą ryšį su Dataverse aplinka](#remove-an-existing-connection-to-a-dataverse-environment).
- Aplinka Microsoft Dataverse gali prisijungti tik prie vienos saugyklos paskyros. Tai taikoma tik tuo atveju, jei sukonfigūruojate aplinką, kad ji [naudotų jūsų Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse saugojimo pajėgumų teisė

"Customer Insights" prenumerata suteikia jums teisę į papildomą pajėgumą, susijusį su jūsų organizacijos esama [Dataverse saugyklos talpa](/power-platform/admin/capacity-storage). Pridėta talpa priklauso nuo jūsų prenumeratos naudojamų profilių skaičiaus.

**Pavyzdys:**

Darant prielaidą, kad gausite 15 GB duomenų bazės saugyklą ir 20 GB failų saugyklą 100 000 klientų profilių. Jei jūsų prenumeratoje yra 300 000 klientų profilių, bendra saugyklos talpa bus 45 GB (3 x 15 GB) duomenų bazės saugykla ir 60 GB failų saugykla (3 x 20 GB). Panašiai, jei turite B2B prenumeratą su 30K paskyromis, bendra saugyklos talpa būtų 45 GB (3 x 15 GB) duomenų bazės saugykla ir 60 GB failų saugykla (3 x 20 GB).

Jūsų organizacijoje žurnalo pajėgumas nėra laipsniškas ir fiksuotas.

Daugiau informacijos apie išsamias pajėgumo teises rasite ["Dynamics 365" licencijavimo vadove](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Aplinkos prijungimas Dataverse prie "Customer Insights"

Šis **Microsoft Dataverse** veiksmas leidžia susieti "Customer Insights" su aplinka Dataverse kuriant ["Customer Insights" aplinką](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="duomenų bendrinimas su Microsoft Dataverse automatiškai įgalinta naujų internetinių aplinkų funkcija.":::

Administratoriai gali konfigūruoti "Customer Insights", kad sujungtų esamą Dataverse aplinką. Pateikdamas URL Dataverse aplinkai, jis prisijungia prie naujos "Customer Insights" aplinkos. Nustatę ryšį tarp "Customer Insights" ir Dataverse, nekeiskite organizacijos aplinkos pavadinimo Dataverse. Organizacijos pavadinimas naudojamas URL, Dataverse o pakeistas pavadinimas nutraukia ryšį su "Customer Insights".

Jei nenorite naudoti esamos Dataverse aplinkos, sistema sukuria naują nuomotojo "Customer Insights" duomenų aplinką. [Power Platform administratoriai gali valdyti, kas gali kurti aplinkas](/power-platform/admin/control-environment-creation). Kai nustatote naują "Customer Insights" aplinką ir administratorius išjungė aplinkų Dataverse kūrimą visiems, išskyrus administratorius, gali būti, kad negalėsite sukurti naujos aplinkos.

**Įgalinkite duomenų bendrinimą** su Dataverse pasirinkdami žymimąjį laukelį duomenų bendrinimas.

Jei naudojate savo "Data Lake Storage" paskyrą, jums taip pat reikia leidimų **identifikatoriaus**. Jei reikia daugiau informacijos, kaip gauti leidimo identifikatorių, peržiūrėkite šį skyrių.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Įgalinkite duomenų bendrinimą su Dataverse savo Azure Data Lake Storage (peržiūra)

Norint įgalinti duomenų bendrinimą su Microsoft Dataverse tuo, kai aplinka [naudoja jūsų paskyrą Azure Data Lake Storage,](own-data-lake-storage.md) reikia papildomos konfigūracijos. Vartotojas, nustatantis "Customer Insights" aplinką, turi turėti bent **"Storage Blob Data Reader"** teises *paskyros "CustomerInsights"* konteineryje Azure Data Lake Storage.

1. "Azure" prenumeratoje sukurkite dvi saugos grupes – vieną **skaitytuvo** saugos grupę ir vieną **bendraautorių** saugos grupę ir nustatykite paslaugą Microsoft Dataverse kaip abiejų saugos grupių savininkę.
2. Tvarkykite prieigos kontrolės sąrašą (ACL), esantį "CustomerInsights" konteineryje savo saugyklos paskyroje, naudodami šias saugos grupes. Įtraukite paslaugą Microsoft Dataverse ir visas Dataverse verslo programas, pvz., "Dynamics 365 Marketing", **į skaitytuvo** saugos grupę su **tik** skaitymo teisėmis. Į bendraautorių *saugos grupę įtraukite* **tik** programą "Customer Insights", kad suteiktumėte **skaitymo ir rašymo** teises rašyti profilius ir įžvalgas.

### <a name="limitations"></a>Apribojimai

Naudojant su Dataverse savo Azure Data Lake Storage paskyra taikomi du apribojimai:

- Yra asmeninis susiejimas tarp Dataverse organizacijos ir Azure Data Lake Storage paskyros. Kai organizacija prijungiama Dataverse prie saugyklos abonemento, ji negali prisijungti prie kito saugyklos abonemento. Šis apribojimas neleidžia, kad a Dataverse neužpildytų kelių saugyklos paskyrų.
- Duomenų bendrinimas neveiks, jei norint pasiekti paskyrą Azure Data Lake Storage reikia "Azure Private Link" sąrankos, nes ji yra už užkardos. Dataverse šiuo metu nepalaiko ryšio su privačiais galiniais taškais per "Private Link".

### <a name="set-up-powershell"></a>"PowerShell" nustatymas

Norėdami vykdyti "PowerShell" scenarijus, pirmiausia turite atitinkamai nustatyti "PowerShell".

1. Įdiekite naujausią "PowerShell for Graph"[Azure Active Directory versiją](/powershell/azure/active-directory/install-adv2).
   1. Savo kompiuteryje pasirinkite klaviatūroje pasirinkite "Windows" klavišą ir ieškokite **Windows PowerShell** bei pasirinkite **Paleisti kaip administratorių**.
   1. „PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.
2. Importuokite tris modulius.
    1. "PowerShell" lange įveskite `Install-Module -Name Az.Accounts` ir atlikite veiksmus.
    1. Pakartokite ir `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigūravimo veiksmai

1. Atsisiųskite du "PowerShell" scenarijus, kuriuos turite paleisti iš mūsų inžinieriaus ["GitHub" atpirkimo sandorio](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Jums reikia *nuomotojo administratoriaus* teisių, kad galėtumėte paleisti šį "PowerShell" scenarijų.
       - Šis "PowerShell" scenarijus sukuria dvi saugos grupes jūsų "Azure" prenumeratoje. Vienas skirtas skaitytojų grupei, o kitas – bendraautorių grupei ir teiks Microsoft Dataverse paslaugas kaip abiejų šių saugos grupių savininkas.
       - Vykdykite šį "PowerShell" scenarijų sistemoje "Windows PowerShell", pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
       - Įrašykite abi saugos grupės ID reikšmes, sugeneruotas naudojant šį scenarijų, nes naudosime jas scenarijuje `ByolSetup.ps1`.

        > [!NOTE]
        > Saugos grupės kūrimas gali būti išjungtas jūsų nuomotojuje. Tokiu atveju reikės rankinio nustatymo, o jūsų Azure AD administratorius turėtų įjungti [saugos grupės kūrimą](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Jums reikia *"Storage Blob Data Owner"* leidimų saugyklos abonemento / konteinerio lygiu, kad galėtumėte paleisti šį scenarijų, kitaip šis scenarijus sukurs jums vieną. Sėkmingai paleidus scenarijų, jūsų vaidmens priskyrimą galima pašalinti rankiniu būdu.
        - Šis "PowerShell" scenarijus prideda reikiamą vaidmenimis pagrįstą prieigos valdiklį Microsoft Dataverse paslaugai ir visoms Dataverse verslo programoms. Ji taip pat atnaujina su scenarijumi sukurtų `CreateSecurityGroups.ps1` saugos grupių prieigos valdymo sąrašą (ACL) konteineryje CustomerInsights. Bendraautorių grupė turės *rwx* leidimą, o skaitytojų grupė turės *tik r-x* leidimą.
        - Vykdykite šį "PowerShell" scenarijų "Windows PowerShell" pateikdami "Azure" prenumeratos ID, kuriame yra jūsų Azure Data Lake Storage, saugyklos abonemento pavadinimas, išteklių grupės pavadinimas ir "Reader" bei "Contributor" saugos grupės ID reikšmės. Atidarykite "PowerShell" scenarijų redaktoriuje, kad peržiūrėtumėte papildomą informaciją ir įdiegtą logiką.
        - Nukopijuokite išvesties eilutę sėkmingai paleidę scenarijų. Išvesties eilutė atrodo taip: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Įveskite iš viršaus nukopijuotą išvesties eilutę į **aplinkos konfigūravimo veiksmo** lauką Leidimų identifikatorius Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigūravimo parinktys, leidžiančios įgalinti duomenų bendrinimą iš savo Azure Data Lake Storage su Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Esamo ryšio su Dataverse aplinka šalinimas

Jungiantis prie Dataverse aplinkos, klaidos pranešimas **Ši CDS organizacija jau prijungta prie kito "Customer Insights" egzemplioriaus** reiškia, kad Dataverse aplinka jau naudojama "Customer Insights" aplinkoje. Esamą ryšį galite pašalinti kaip visuotinis aplinkos administratorius Dataverse. Pakeitimų užpildymas gali užtrukti kelias valandas.

1. Eikite į [Power Apps](https://make.powerapps.com).
1. Pasirinkite aplinką iš aplinkos parinkiklio.
1. Eikite į **"Sprendimai"**
1. Pašalinkite arba panaikinkite sprendimą, pavadintą **Dynamics 365 Customer Insights Kliento kortelės papildinys (peržiūra)**.

OR

1. Atidarykite savo Dataverse aplinką.
1. Eikite į **Išplėstiniai nustatymų** > **sprendimai**.
1. Pašalinkite **"CustomerInsightsCustomerCard"** sprendimą.

Jei ryšio pašalinimas nepavyksta dėl priklausomybių, turite pašalinti ir priklausomybes. Norėdami gauti daugiau informacijos, žiūrėkite [Priklausomybių](/power-platform/alm/removing-dependencies) šalinimas.

## <a name="output-entities"></a>Išvesties objektai

Kai kurie išvesties objektai iš "Customer Insights" pasiekiami kaip lentelės Dataverse. Toliau aprašomos numatomos šių lentelių schemos.

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
|EntityName        | String        | Objekto pavadinimas programoje "Customer Insights". Pavyzdžiui: `contact1`.        |
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

Šioje lentelėje pateikiama klientų profilių segmento narystės informacija.

| Column        | Tipas | Aprašą                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kliento Profilio ID        |
| Segmentprovider      | String       | Programa, skelbianti segmentus.      |
| SegmentasMembershipType | String       | Kliento tipas šio segmento narystės įrašas. Palaiko kelių tipų, pvz., Klientas, Kontaktas arba Paskyra. Numatytasis nustatymas: klientas  |
| Segmentai       | JSON Eilutė  | Unikalių segmentų, kurių narys yra kliento profilis, sąrašas      |
| „msdynci_identifier”  | String   | Unikalus segmento narystės įrašo identifikatorius. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministinis GUID, sugeneruotas iš`msdynci_identifier`          |

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
