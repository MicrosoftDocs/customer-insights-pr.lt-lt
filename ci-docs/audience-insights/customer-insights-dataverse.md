---
title: "\"Customer Insights\" duomenys Microsoft Dataverse"
description: Naudokite "Customer Insights" objektus kaip lenteles Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866944"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Darbas su "Customer Insights" duomenimis Microsoft Dataverse

"Customer Insights" pateikia parinktį, kad išvesties objektai būtų pasiekiami [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Šis integravimas leidžia lengvai bendrinti duomenis ir pasirinktinai kurti naudojant „mažai kodų” / „jokių kodų” principą. Išvesties objektai bus pasiekiami kaip lentelės Dataverse. Šios lentelės įgalina scenarijus, pvz., [automatines darbo eigas per Power Automate](/power-automate/getting-started), [modeliu pagrįstas programas](/powerapps/maker/model-driven-apps/) ir [drobės programas per](/powerapps/maker/canvas-apps/) Power Apps. Duomenis galite naudoti bet kuriai kitai programai, pagrįstai Dataverse lentelėmis. Dabartinis diegimas daugiausia palaiko peržvalgas, kuriose duomenys iš prieinamų auditorijos įžvalgos objektų gali būti iškviečiami nurodytam kliento ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse aplinkos pridėjimas prie "Customer Insights"

**Organizacijos su esamomis Dataverse aplinkomis**

Organizacijos, kurios jau naudoja Dataverse gali [naudoti vieną iš esamų Dataverse aplinkų, kai](create-environment.md) administratorius nustato auditorijos įžvalgas. Pateikdamas URL Dataverse aplinkoje, jis pridedamas prie naujos auditorijos įžvalgų aplinkos. Siekiant užtikrinti geriausią įmanomą našumą, "Customer Insights" ir Dataverse aplinkos turi būti laikomos tame pačiame regione.

**Nauja organizacija**

Jei nustatydami "Customer Insights" sukursite naują organizaciją, automatiškai gausite naują Dataverse aplinką.

> [!NOTE]
> Jei jūsų organizacijos jau naudoja Dataverse savo nuomotojuje, svarbu prisiminti, kad [Dataverse aplinkos kūrimą valdo administratorius](/power-platform/admin/control-environment-creation.md) . Pavyzdžiui, jei nustatote naują auditorijos įžvalgų aplinką naudodami organizacijos abonementą ir administratorius uždraudė kurti Dataverse bandomąsias aplinkas visiems, išskyrus administratorius, negalite sukurti naujos bandomosios aplinkos.
> 
> "Dataverse" bandomosiose aplinkose, sukurtose "Customer Insights", yra 3 GB saugyklos vietos, kuri nebus įskaičiuota į bendrą nuomotojo turintį pajėgumą. Mokamos prenumeratos gauna Dataverse teisę į 15 GB duomenų bazę ir 20 GB failų saugyklą.

## <a name="output-entities"></a>Išvesties objektai

Kai kurie išvesties objektai iš auditorijos įžvalgų galimi kaip lentelės Dataverse. Toliau aprašomos numatomos šių lentelių schemos.

- [CustomerProfile](#customerprofile)
- [„AlternateKey”](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [„CustomerMeasure”](#customermeasure)
- [Papildymas](#enrichment)
- [Prognozė](#prediction)
- [Segmento narystė](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Šioje lentelėje pateikiamas vieningasis kliento profilis iš „Customer Insights”. Vieningojo kliento profilio schema priklauso nuo objektų ir atributų, panaudotų suliejimo procese. Kliento profilio schemoje paprastai yra atributų antrinis rinkinys iš [Kliento profilio „Common Data Model” aprašo](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>„AlternateKey”

Alternatyvaus rakto lentelėje yra suvienodinimo procese dalyvavusių objektų raktų rinkinys.

|Stulpelis  |Tipas  |Aprašymas  |
|---------|---------|---------|
|„DataSourceName”    |Eilutė         | Duomenų šaltinio pavadinimas. Pavyzdžiui: `datasource5`.        |
|EntityName        | Eilutė        | Objekto pavadinimas auditorijos įžvalgose. Pavyzdžiui: `contact1`.        |
|„AlternateValue”    |Eilutė         |Alternatyvusis ID, susietas su kliento ID. Pavyzdys: `cntid_1078`         |
|„KeyRing”           | Kelių eilučių Tekstas        | JSON reikšmė  </br> Pavyzdys: [{"dataSourceName":" datasource5 ",</br>„entityName”:„ contact1”,</br>„preferredKey”:„ cntid_1078”,</br>"raktai":[" cntid_1078"]}]       |
|CustomerId         | String        | Vieningojo kliento profilio ID.         |
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

Šioje lentelėje yra kliento profilių segmentų narystės informacija.

| Column        | Tipas | Aprašą                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kliento Profilio ID        |
| SegmentasProvider      | String       | Programa, kuri publikuoja segmentus. Numatytoji reikšmė: auditorijos įžvalgos         |
| SegmentAsMembershipType | String       | Kliento tipas šis segmento narystės įrašas. Palaiko kelis tipus, pvz., Klientas, Kontaktas arba Abonementas. Numatytasis: klientas  |
| Segmentai       | JSON Eilutė  | Unikalių segmentų, kurių narys yra kliento profilis, sąrašas      |
| „msdynci_identifier”  | String   | Unikalusis segmento narystės įrašo identifikatorius. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministinis GUID, sugeneruotas iš`msdynci_identifier`          |
