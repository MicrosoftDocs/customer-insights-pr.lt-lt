---
title: „Customer Insights“ duomenys „Microsoft Dataverse” platformoje
description: Naudokite „Customer Insights” objektus kaip lenteles „Microsoft Dataverse” platformoje.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9855ff6908001dd18bc19a286fc56620d0a127e5
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645228"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Dirbkite su „Customer Insights“ duomenimis „Microsoft Dataverse” platformoje

„Customer Insights” suteikia parinktį padaryti išvesties objektus prieinamus [„Microsoft Dataverse”](/powerapps/maker/data-platform/data-platform-intro.md). Šis integravimas leidžia lengvai bendrinti duomenis ir pasirinktinai kurti naudojant „mažai kodų” / „jokių kodų” principą. Išvesties objektai bus prieinami kaip „Dataverse” lentelės. Šios lentelės įgalina scenarijus, pavyzdžiui, [automatizuotas darbo eigas per „Power Automate”](/power-automate/getting-started), [modeliu pagrįstas programas](/powerapps/maker/model-driven-apps/) ir [drobės programas](/powerapps/maker/canvas-apps/) per „Power Apps”. Galite naudoti duomenis bet kuriai kitai taikomajai programai, pagrįstai „Dataverse” lentelėmis. Dabartinis diegimas daugiausia palaiko peržvalgas, kuriose duomenys iš prieinamų auditorijos įžvalgos objektų gali būti iškviečiami nurodytam kliento ID.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>„Dataverse” aplinkos pridėjimas prie „Customer Insights”

**Organizacijos su esamomis „Dataverse” aplinkomis**

Organizacijos, kurios jau naudoja „Dataverse”, gali [naudoti vieną iš jų esamų „Dataverse” aplinkų](create-environment.md), kai administratorius nustato auditorijos įžvalgas. Pateikiant URL į „Dataverse” aplinką, jis pridedamas prie naujos auditorijos įžvalgų aplinkos. Norint užtikrinti geriausią galimą efektyvumą, „Customer Insights” ir „Dataverse” aplinkos turi būti nuomojamos tame pačiame regione.

**Nauja organizacija**

Jei kuriate naują organizaciją nustatydami „Customer Insights”, automatiškai gausite naują „Dataverse” aplinką.

> [!NOTE]
> Jei jūsų organizacijos jau naudoja „Dataverse” savo nuomotojui, svarbu prisiminti, kad [„Dataverse” aplinkos kūrimą valdo administratorius](/power-platform/admin/control-environment-creation.md). Pavyzdžiui, jei naudodami jūsų organizacijos abonementą nustatote naują auditorijos įžvalgų aplinką, o administratorius išjungė „Dataverse” bandomosios versijos aplinkų kūrimą visiems, išskyrus administratorius, naujos bandomosios aplinkos sukurti nepavyks.
> 
> „Customer Insights” sukurtose bandomosiose „Dataverse” aplinkose yra 3 GB saugykla, kuri neįskaičiuota į bendrą nuomotojo pajėgumą. Mokamos prenumeratos turi „Dataverse” teisę į 15 GB duomenų bazę ir 20 GB failų saugyklą.

## <a name="output-entities"></a>Išvesties objektai

Kai kurie išvesties objektai iš auditorijos įžvalgų pateikiami kaip lentelės „Dataverse” platformoje. Toliau aprašomos numatomos šių lentelių schemos.

- [CustomerProfile](#customerprofile)
- [„AlternateKey”](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [„CustomerMeasure”](#customermeasure)
- [Papildymas](#enrichment)
- [Prognozė](#prediction)


### <a name="customerprofile"></a>CustomerProfile

Šioje lentelėje pateikiamas vieningasis kliento profilis iš „Customer Insights”. Vieningojo kliento profilio schema priklauso nuo objektų ir atributų, panaudotų suliejimo procese. Kliento profilio schemoje paprastai yra atributų antrinis rinkinys iš [Kliento profilio „Common Data Model” aprašo](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>„AlternateKey”

Alternatyvaus rakto lentelėje yra suvienodinimo procese dalyvavusių objektų raktų rinkinys.

|Stulpelis  |Tipas  |Aprašymas  |
|---------|---------|---------|
|„DataSourceName”    |Eilutė         | Duomenų šaltinio pavadinimas. Pavyzdžiui: `datasource5`.        |
|EntityName        | Eilutė        | Objekto pavadinimas auditorijos įžvalgose. Pavyzdžiui: `contact1`.        |
|„AlternateValue”    |Eilutė         |Alternatyvusis ID, susietas su kliento ID. Pavyzdys: `cntid_1078`         |
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
| „msdynci_identifier”   | Eilutė      |  `Model|ModelProvider|CustomerId`                      |
