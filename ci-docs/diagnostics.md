---
title: Diagnostikos žurnalų eksportavimas (peržiūra)
description: Sužinokite, kaip siųsti žurnalus į Microsoft Azure monitorių.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245935"
---
# <a name="export-diagnostic-logs-preview"></a>Diagnostikos žurnalų eksportavimas (peržiūra)

Persiųskite žurnalus iš "Customer Insights" naudodami "Azure Monitor". "Azure Monitor" išteklių žurnalai leidžia stebėti ir siųsti žurnalus į "Azure" saugyklą [...](https://azure.microsoft.com/services/storage/), ["Azure Log Analytics"](/azure/azure-monitor/logs/log-analytics-overview) arba transliuoti juos į ["Azure Event Hubs"](https://azure.microsoft.com/services/event-hubs/).

"Customer Insights" siunčia šiuos įvykių žurnalus:

- **Audito įvykiai**
  - **APIEvent** - įgalina pakeitimų stebėjimą per Dynamics 365 Customer Insights vartotojo sąsają.
- **Operatyviniai renginiai**
  - **"WorkflowEvent"** – leidžia nustatyti [duomenų šaltinius](data-sources.md), [suvienodinti](data-unification.md), [papildyti](enrichment-hub.md) ir [eksportuoti](export-destinations.md) duomenis į kitas sistemas. Šiuos veiksmus galima atlikti atskirai (pvz., suaktyvinti vieną eksportavimą). Jie taip pat gali vykdyti organizuotą orkestravimą (pavyzdžiui, duomenų atnaujinimas iš duomenų šaltinių, kurie suaktyvina suvienijimo procesą, kuris pritrauks papildymus ir eksportuos duomenis į kitą sistemą). Daugiau informacijos ieškokite [WorkflowEvent schema](#workflow-event-schema).
  - **APIEvent** - siunčia visus klientų egzemplioriaus API skambučius į Dynamics 365 Customer Insights. Daugiau informacijos rasite [APIEvent schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikos parametrų nustatymas

### <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi " [Azure" prenumerata](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administratoriaus](permissions.md#admin) teisės programoje "Customer Insights".
- [Bendraautorio ir vartotojo prieigos administratoriaus vaidmuo](/azure/role-based-access-control/role-assignments-portal) "Azure" paskirties ištekliuje. Ištekliai gali būti Azure Data Lake Storage paskyra, "Azure" įvykių telkinys arba "Azure Log Analytics" darbo sritis. Šis leidimas būtinas konfigūruojant diagnostikos parametrus "Customer Insights", tačiau jį galima pakeisti sėkmingai atlikus sąranką.
- [Tenkinami "Azure" saugyklos, "Azure Event Hub" arba "Azure Log Analytics" paskirties reikalavimai](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements).
- Bent jau skaitytuvo **vaidmuo** išteklių grupėje, kuriai priklauso išteklius.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikos nustatymas naudojant "Azure Monitor"

1. Programoje "Customer Insights" eikite į **Administravimo** > **sistema** ir pasirinkite skirtuką **Diagnostika**.

1. Pasirinkite **Pridėti paskirties vietą**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnostikos ryšys.":::

1. Nurodykite pavadinimą **lauke Diagnostikos paskirties vietos** pavadinimas.

1. **Pasirinkite išteklių tipą** (saugyklos paskyra, įvykių telkinys arba žurnalo analizė).

1. Pasirinkite paskirties ištekliaus **prenumeratą**, **išteklių grupę** ir **išteklius**. Žiūrėkite [Paskirties ištekliaus](#configuration-on-the-destination-resource) konfigūracija, kad gautumėte teises ir žurnalo informaciją.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti prie sistemos**, kad prisijungtumėte prie paskirties ištekliaus. Žurnalai paskirties vietoje pradedami rodyti po 15 minučių, jei API naudojama ir generuoja įvykius.

## <a name="configuration-on-the-destination-resource"></a>Paskirties ištekliaus konfigūravimas

Atsižvelgiant į jūsų pasirinktą išteklių tipą, automatiškai atliekami šie keitimai:

### <a name="storage-account"></a>Saugyklos klientas

"Customer Insights" aptarnavimo vykdytojas gauna **pasirinkto ištekliaus saugyklos abonemento bendraautorio** teises ir pasirinktoje vardų srityje sukuria du konteinerius:

- `insight-logs-audit` kuriame pateikiami **audito įvykiai,**
- `insight-logs-operational` kuriuose vyksta **operatyviniai renginiai**

### <a name="event-hub"></a>Įvykių telkinys

"Customer Insights" paslaugos vykdytojas gauna **ištekliaus "Azure Event Hubs" duomenų savininko** teises ir pasirinktoje vardų srityje sukuria du įvykių telkinius:

- `insight-logs-audit` kuriame pateikiami **audito įvykiai,**
- `insight-logs-operational` kuriuose vyksta **operatyviniai renginiai**

### <a name="log-analytics"></a>Žurnalo analizė

"Customer Insights" paslaugos vykdytojas gauna ištekliaus žurnalo **"Analytics" bendraautorio** leidimą. Žurnalai pasiekiami pasirinktoje **"Log Analytics" darbo srities žurnalų skiltyje Žurnalų lentelių** > **·** > **žurnalo valdymas**. Išplėskite žurnalų **valdymo** sprendimą ir raskite lenteles bei `CIEventsAudit` lenteles `CIEventsOperational`.

- `CIEventsAudit` kuriame pateikiami **audito įvykiai,**
- `CIEventsOperational` kuriuose vyksta **operatyviniai renginiai**

Po langu **Užklausos** išplėskite **Audito** sprendimas ir suraskite užklausų pavyzdžius, pateiktus ieškant `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Diagnostikos paskirties vietos šalinimas

1. Eikite į **Administravimo** > **sistema** ir pasirinkite skirtuką **Diagnostika**.

1. Sąraše pasirinkite diagnostikos paskirties vietą.

   > [!TIP]
   > Pašalinus paskirties vietą, žurnalo persiuntimas sustabdomas, bet nepanaikinamas "Azure" prenumeratos išteklius. Norėdami panaikinti "Azure" šaltinį, stulpelyje Veiksmai **pasirinkite saitą**, kad atidarytumėte pasirinkto ištekliaus "Azure" portalą ir panaikintumėte jį ten. Tada ištrinkite diagnostikos paskirties vietą.

1. Stulpelyje **Veiksmai** pasirinkite piktogramą **Ištrinti**.

1. Patvirtinkite ištrynimą, kad pašalintumėte paskirties vietą ir sustabdytumėte žurnalo persiuntimą.

## <a name="log-categories-and-event-schemas"></a>Žurnalų kategorijos ir įvykių schemos

Šiuo metu [palaikomi API įvykiai](apis.md) ir darbo eigos įvykiai ir taikomos šios kategorijos bei schemos.
Žurnalo schema atitinka "Azure Monitor" [bendrąją schemą](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijos

"Customer Insights" pateikia dvi kategorijas:

- **Audito įvykiai**: [API įvykiai](#api-event-schema), skirti stebėti paslaugos konfigūracijos pakeitimus. `POST|PUT|DELETE|PATCH` operacijos patenka į šią kategoriją.
- **Veiklos įvykiai**: [API įvykiai](#api-event-schema) arba [darbo eigos įvykiai](#workflow-event-schema), sugeneruoti naudojant paslaugą.  Pavyzdžiui, `GET` užklausos arba darbo eigos vykdymo įvykiai.

## <a name="event-schemas"></a>Įvykių schemos

API įvykiai ir darbo eigos įvykiai turi bendrą struktūrą, tačiau turi keletą skirtumų. Daugiau informacijos ieškokite [API įvykio schemoje](#api-event-schema) arba [darbo eigos įvykio schemoje](#workflow-event-schema).

### <a name="api-event-schema"></a>API įvykių schema

| Laukas             | DataType  | Būtina / neprivaloma | Aprašą       | Pavyzdžiui        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laiko žyma | Privalomas          | Įvykio laiko žyma (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Privalomas          | Įvykį išmetusio egzemplioriaus resourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Privalomas          | Operacijos, kurią reprezentuoja šis įvykis, pavadinimas.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Privalomas          | Įvykio žurnalo kategorija. Arba arba `Operational``Audit`. Visos POST/PUT/PATCH/DELETE HTTP Užklausos yra pažymėtos `Audit`, visa kita su`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Privalomas          | Renginio statusas. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pasirinktinai          | Įvykio rezultato būsena. Jei operacija atitinka REST API skambutį, tai yra HTTP būsenos kodas.        | `200`             |
| `durationMs`      | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.     | `133`     |
| `callerIpAddress` | String    | Pasirinktinai          | Skambintojo IP adresas, jei operacija atitinka API skambutį, gautą iš viešai prieinamo IP adreso.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pasirinktinai          | JSON objektas, apibūdinantis operaciją atlikusio vartotojo ar programos tapatybę.       | Žiūrėkite [tapatybės](#identity-schema) skyrių.     |  
| `properties`      | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.      | Žiūrėkite [skyrių Ypatybės](#api-properties-schema).    |
| `level`           | String    | Privalomas          | Įvykio sunkumo lygis.    | `Informational`, `Warning`, `Error` arba `Critical`.           |
| `uri`             | String    | Pasirinktinai          | Absoliutus prašymas URI.    |               |

#### <a name="identity-schema"></a>Tapatybės schema

`identity` JSON objektas turi tokią struktūrą

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Laukas                         | Aprašą                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Priskirtas naudotojo arba programos vaidmuo. Daugiau informacijos ieškokite [vartotojo teisėse](permissions.md).                                     |
| `Authorization.RequiredRoles` | Būtini vaidmenys operacijai atlikti. `Admin` vaidmeniui leidžiama atlikti visas operacijas.                                                    |
| `Claims`                      | Vartotojo arba programos JSON žiniatinklio atpažinimo ženklo (JWT) pretenzijos. Pretenzijų ypatybės skiriasi priklausomai nuo organizacijos ir Azure Active Directory konfigūracijos. |

#### <a name="api-properties-schema"></a>API ypatybių schema

[API įvykiai](apis.md) turi šias ypatybes.

| Laukas                        | Aprašą                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Visada `ApiEvent`, pažymėdami žurnalo įvykį kaip API įvykį.                                                                 |
| `properties.userAgent`       | Naršyklės agentas, siunčiantis užklausą arba `unknown`.                                                                        |
| `properties.method`          | HTTP metodas:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Santykinis prašymo kelias.                                                                                          |
| `properties.origin`          | URI, nurodantis, iš kur kilęs gavimas arba `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP būsenos kodui < 400 <br> `ClientError` HTTP būsenos kodui < 500 <br> `Error` HTTP būsenai >= 500 |
| `properties.tenantId`        | Organizacijos ID                                                                                                        |
| `properties.tenantName`      | Organizacijos pavadinimas.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Skambinusiojo objektasId.                                                                         |
| `properties.instanceId`      | Klientų įžvalgos`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbo eigos įvykio schema

Darbo eigoje yra keli veiksmai. [Nurykite duomenų šaltinius](data-sources.md), [suvienodinkite](data-unification.md), [praturtinkite](enrichment-hub.md) ir [eksportuokite](export-destinations.md) duomenis. Visi šie veiksmai gali būti atliekami atskirai arba organizuojami pagal šiuos procesus.

#### <a name="operation-types"></a>Operacijų tipai

| „OperationType“     | Grupuoti                                     |
| ----------------- | ----------------------------------------- |
| Nurijimas         | [Duomenų šaltiniai](data-sources.md)           |
| Duomenų paruošimas   | [Duomenų šaltiniai](data-sources.md)           |
| Susieti               | [Duomenų suvienodinimas](data-unification.md)   |
| Sugretinti             | [Duomenų suvienodinimas](data-unification.md)   |
| Sulieti             | [Duomenų suvienodinimas](data-unification.md)   |
| ProfileStore      | [Klientų profiliai](customer-profiles.md) |
| Paieška            | [Klientų profiliai](customer-profiles.md) |
| Veikla          | [Veiklos](activities.md)                  |
| AtributasPriežiūros | [Segmentai ir priemonės](segments.md)      |
| SubjektasPriemonės    | [Segmentai ir priemonės](segments.md)      |
| Matavimai          | [Segmentai ir priemonės](segments.md)      |
| Segmentacija      | [Segmentai ir priemonės](segments.md)      |
| Papildymas        | [Papildymas](enrichment-hub.md)                                          |
| Duomenų rinkimas      | [Prognozės](predictions-overview.md)                                          |
| "AiBuilder"         | [Prognozės](predictions-overview.md)                                          |
| Įžvalgos          | [Prognozės](predictions-overview.md)                                          |
| Eksportavimas            | [Eksportavimai](export-destinations.md)                                          |
| Modelio valdymas   | [Prognozės](custom-models.md)                                           |
| Ryšys      | [Duomenų suvienodinimas](relationships.md)                                           |

#### <a name="field-description"></a>Lauko aprašymas

| Laukas           | DataType  | Būtina / neprivaloma | Aprašą                                                                                                                                                   | Pavyzdžiui                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laiko žyma | Privalomas          | Įvykio laiko žyma (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Privalomas          | Egzemplioriaus, kuris išskleidė įvykį, resourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Privalomas          | Operacijos, kurią reprezentuoja šis įvykis, pavadinimas. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Žiūrėkite [Operacijų tipai](#operation-types), kad gautumėte nuorodą. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Privalomas          | Įvykio žurnalo kategorija. Darbo eigos įvykiams visada`Operational`                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Privalomas          | Renginio statusas. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.                                                                                        | Žiūrėkite poskyrį [Darbo eigos ypatybės](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Privalomas          | Įvykio sunkumo lygis.                                                                                                                                  | `Informational`, `Warning` arba `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Darbo eigos ypatybių schema

Darbo eigos įvykiai turi šias ypatybes.

| Laukas              | Workflow | Užduotis | Aprašą            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Taip      | Taip  | Visada `WorkflowEvent`, pažymėdami įvykį kaip darbo eigos įvykį.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Taip      | Taip  | Darbo eigos vykdymo identifikatorius. Visi darbo eigos ir užduočių įvykiai darbo eigos vykdyme turi tą patį `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Taip      | Taip  | Operacijos identifikatorius, žr [.](#operation-types)                                                                                                                                                                               |
| `properties.tasksCount`                      | Taip      | No   | Tik darbo eiga. Užduočių, kurias suaktyvina darbo eiga, skaičius.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Taip      | No   | Pasirenkama. Tik darbo eigos įvykiai. Vartotojo Azure Active Directory [...](/azure/marketplace/find-tenant-object-id#find-user-object-id), kuris suaktyvino darbo eigą, objektasId taip pat `properties.workflowSubmissionKind` žr.                                   |
| `properties.workflowType`                    | Taip      | No   | `full` arba `incremental` atnaujinti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Taip      | No   | `OnDemand` arba `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Taip      | No   | `Running` arba `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Taip      | Taip  | Klientų įžvalgos`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Taip  | - OperationType = `Export`, identifikatorius yra eksportavimo konfigūracijos guidas. <br> - OperationType = `Enrichment`, tai sodrinimo gidas <br> - "OperationType" `Measures` ir `Segmentation`, identifikatorius yra objekto pavadinimas. |
| `properties.friendlyName`                    | No       | Taip  | Patogus eksportuoti arba apdorojamo subjekto pavadinimas.                                                                                                                                                                                           |
| `properties.error`                           | No       | Taip  | Pasirenkama. Klaidos pranešimas su daugiau informacijos.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Nurodo eksportavimo tipą. Daugiau informacijos ieškokite [eksporto paskirties vietų](export-destinations.md) apžvalgoje.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Yra eksportavimo sukonfigūruotų objektų sąrašas.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Išsamus pranešimas apie eksportą.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Taip  | Pasirenkama. Tik "OperationType"`Segmentation`. Nurodo bendrą segmento narių skaičių.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]