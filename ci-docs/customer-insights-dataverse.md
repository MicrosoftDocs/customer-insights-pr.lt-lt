---
title: „Customer Insights“ duomenys „Microsoft Dataverse” platformoje
description: Naudokite „Customer Insights” objektus kaip lenteles „Microsoft Dataverse” platformoje.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741375"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje

„Customer Insights” suteikia parinktį padaryti išvesties objektus prieinamus [„Microsoft Dataverse”](/powerapps/maker/data-platform/data-platform-intro). Ši integracija leidžia lengvai dalytis duomenimis ir pasirinktinai kurti naudojant mažo kodo / ne kodo metodą. Išvesties [objektai](#output-entities) yra pasiekiami kaip aplinkos lentelės Dataverse. Galite naudoti duomenis bet kuriai kitai programai, pagrįstai Dataverse lentelėmis. Šios lentelės įgalina scenarijus, pvz., automatizuotas darbo eigas naudojant Power Automate arba kuriant programas su Power Apps. Dabartinis diegimas daugiausia palaiko peržvalgas, kuriose duomenis iš galimų "Customer Insights" objektų galima gauti konkrečiam kliento ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>„Dataverse” aplinkos pridėjimas prie „Customer Insights”

**Esama organizacija**

Administratoriai gali konfigūruoti "Customer Insights", kad [sukurtų "Customer Insights" aplinką, kad galėtų naudoti esamą Dataverse aplinką](create-environment.md). Pateikdamas URL Dataverse aplinkai, jis pridedamas prie naujos "Customer Insights" aplinkos. "Customer Insights" ir Dataverse aplinkos turi būti talpinamos tame pačiame regione. 

Jei nenorite naudoti esamos Dataverse aplinkos, sistema sukuria naują nuomotojo "Customer Insights" duomenų aplinką. 

> [!NOTE]
> Jei jūsų organizacijos jau naudoja Dataverse savo nuomotojuje, svarbu prisiminti, kad [Dataverse aplinkos kūrimą kontroliuoja administratorius](/power-platform/admin/control-environment-creation). Pavyzdžiui, jei nustatote naują "Customer Insights" aplinką naudodami savo organizacijos abonementą ir administratorius išjungė bandomosios Dataverse aplinkos kūrimą visiems, išskyrus administratorius, negalite sukurti naujos bandomosios aplinkos.
> 
> „Customer Insights” sukurtose bandomosiose „Dataverse” aplinkose yra 3 GB saugykla, kuri neįskaičiuota į bendrą nuomotojo pajėgumą. Mokamos prenumeratos turi „Dataverse” teisę į 15 GB duomenų bazę ir 20 GB failų saugyklą.

**Nauja organizacija**

Jei nustatydami "Customer Insights" kuriate naują organizaciją, sistema automatiškai sukuria jums naują Dataverse aplinką jūsų organizacijoje.

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
