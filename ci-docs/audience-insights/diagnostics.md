---
title: Auditas Dynamics 365 Customer Insights naudojant "Azure Monitor"
description: Sužinokite, kaip siųsti žurnalus į Monitorių Microsoft Azure.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523679"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prisijungimo peradresavimas Dynamics 365 Customer Insights naudojant "Azure Monitor" (peržiūra)

Dynamics 365 Customer Insights užtikrina tiesioginę integraciją su "Azure Monitor". "Azure Monitor" išteklių žurnalai leidžia stebėti ir siųsti žurnalus į ["Azure Storage](https://azure.microsoft.com/services/storage/)", ["Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)" arba transliuoti juos į ["Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/)".

"Customer Insights" siunčia šiuos įvykių žurnalus:

- **Audito įvykiai**
  - **APIEvent** - leidžia stebėti keitimus, atliktus Dynamics 365 Customer Insights per vartotojo sąsają.
- **Veiklos įvykiai**
  - **WorkflowEvent** - darbo eiga leidžia nustatyti [duomenų šaltinius](data-sources.md), [suvienyti](data-unification.md) ir praturtinti [ir](enrichment-hub.md) galiausiai [eksportuoti](export-destinations.md) duomenis į kitas sistemas. Visi šie veiksmai gali būti atliekami atskirai (pvz., suaktyvinti vieną eksportą) arba surežisuoti (pvz., duomenų atnaujinimas iš duomenų šaltinių, dėl kurių pradedamas suvienijimo procesas, kuris pritrauks papildomų papildymų ir kai bus atliktas duomenų eksportas į kitą sistemą). Daugiau informacijos ieškokite [WorkflowEvent schemoje](#workflow-event-schema).
  - **APIEvent** – visi API skambučiai į klientų egzempliorių.Dynamics 365 Customer Insights Daugiau informacijos ieškokite [APIEvent schemoje](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Nustatyti diagnostikos parametrus

### <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti diagnostiką "Customer Insights", turi būti įvykdytos šios būtinosios sąlygos:

- Turite aktyvią ["Azure" prenumeratą](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- "Customer Insights" turite [administratoriaus](permissions.md#admin) teises.
- "Azure" paskirties ištekliuje turite **bendraautoriaus** ir **vartotojo prieigos administratoriaus** vaidmenį. Ištekliai gali būti "Azure Storage" abonementas, "Azure" įvykių centras arba "Azure Log Analytics" darbo sritis. Daugiau informacijos ieškokite [Įtraukti arba pašalinti "Azure" vaidmenų priskyrimus naudojant "Azure" portalą](/azure/role-based-access-control/role-assignments-portal).
- [Įvykdyti "Azure Storage", "Azure Event Hub" arba "Azure Log Analytics" paskirties reikalavimai](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements).
- Išteklių grupėje, **kuriai priklauso išteklius, turite bent skaitytojo** vaidmenį.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikos nustatymas naudojant "Azure Monitor"

1. Dalyje "Customer Insights" pasirinkite **SystemDiagnostics** > **·**, kad pamatytumėte diagnostikos paskirties vietas, sukonfigūruotas šiuo egzemplioriumi.

1. Pasirinkite **Įtraukti paskirties vietą**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikos ryšys](media/diagnostics-pane.png "Diagnostikos ryšys")

1. Lauke Diagnostikos paskirties **vietos pavadinimas pateikite** pavadinimą.

1. Pasirinkite **"Azure" prenumeratos nuomotoją** naudodami paskirties šaltinį ir pasirinkite **prisijungti**.

1. Pasirinkite ištekliaus **tipą** (saugyklos abonementas, įvykių koncentratorius arba žurnalo analizė).

1. Pasirinkite **paskirties ištekliaus prenumeratą**.

1. Pasirinkite **paskirties ištekliaus išteklių grupę**.

1. Pasirinkite **Išteklius**.

1. Patvirtinkite **Duomenų privatumo ir atitikties** patvirtinimą.

1. Norėdami prisijungti prie paskirties ištekliaus, pasirinkite **Prisijungti prie sistemos**. Žurnalai paskirties vietoje pradedami rodyti po 15 minučių, jei naudojama API ir generuoja įvykius.

### <a name="remove-a-destination"></a>Paskirties vietos šalinimas

1. Eikite į **"SystemDiagnostics** > **"**.

1. Sąraše pasirinkite diagnostikos paskirties vietą.

1. Stulpelyje **Veiksmai** pasirinkite piktogramą **Naikinti**.

1. Patvirtinkite naikinimą, kad sustabdytumėte žurnalo peradresavimą. "Azure" prenumeratos išteklius nebus panaikintas. Stulpelyje Veiksmai **galite pasirinkti saitą**, kad atidarytumėte pasirinkto ištekliaus "Azure" portalą ir ten jį panaikintumėte.

## <a name="log-categories-and-event-schemas"></a>Žurnalo kategorijos ir įvykių schemos

Šiuo metu [palaikomi API įvykiai](apis.md) ir darbo eigos įvykiai, taikomos šios kategorijos ir schemos.
Žurnalo schema atitinka [bendrąją schemą "Azure Monitor"](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijos

"Customer Insights" pateikia dvi kategorijas:

- **Audito įvykiai**: [API įvykiai](#api-event-schema), skirti tarnybos konfigūracijos pakeitimams sekti. `POST|PUT|DELETE|PATCH` Operacijos patenka į šią kategoriją.
- **Veiklos įvykiai**: [API įvykiai](#api-event-schema) arba [darbo eigos įvykiai](#workflow-event-schema), sugeneruoti naudojant paslaugą.  Pavyzdžiui, `GET` darbo eigos užklausos arba vykdymo įvykiai.

## <a name="configuration-on-the-destination-resource"></a>Paskirties ištekliaus konfigūracija

Atsižvelgiant į jūsų pasirinktą išteklių tipą, automatiškai bus taikomi šie veiksmai:

### <a name="storage-account"></a>Saugyklos klientas

"Customer Insights" tarnybos vykdytojas gauna pasirinkto ištekliaus **saugyklos abonemento bendraautoriaus** teises ir sukuria du konteinerius pasirinktoje vardų srityje:

- `insight-logs-audit` kuriuose yra **audito įvykių**
- `insight-logs-operational` apima veiklos **įvykius**

### <a name="event-hub"></a>Įvykių telkinys

"Customer Insights" tarnybos vadovas gauna ištekliaus **"Azure Event Hubs" duomenų savininko** teises ir pagal pasirinktą vardų sritį sukurs du įvykių centrus:

- `insight-logs-audit` kuriuose yra **audito įvykių**
- `insight-logs-operational` apima veiklos **įvykius**

### <a name="log-analytics"></a>Žurnalo analizė

"Customer Insights" tarnybos vykdytojas **gauna "Log Analytics Contributor"** teises ištekliuje. Žurnalai bus pasiekiami dalyje **LogsTablesLog** > **·** > **Management** pasirinktoje Log Analytics darbo srityje. Išplėskite žurnalo **valdymo** sprendimą ir raskite `CIEventsAudit``CIEventsOperational` lenteles.

- `CIEventsAudit` kuriuose yra **audito įvykių**
- `CIEventsOperational` apima veiklos **įvykius**

**Lange Užklausos** išplėskite **audito** sprendimą ir raskite pavyzdines užklausas, pateiktas ieškant `CIEvents`.

## <a name="event-schemas"></a>Įvykių schemos

API įvykiai ir darbo eigos įvykiai turi bendrą struktūrą ir išsamią informaciją, kur jie skiriasi, žr [...](#api-event-schema)[...](#workflow-event-schema).

### <a name="api-event-schema"></a>API įvykio schema

| Laukas             | DataType  | Būtina / neprivaloma | Aprašą       | Pavyzdžiui        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Privalomas          | Įvykį išmesusio egzemplioriaus ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Privalomas          | Operacijos, kuriai atstovauja šis įvykis, pavadinimas.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Privalomas          | Renginio žurnalo kategorija. `Operational` Arba `Audit`. Visos POST/PUT/PATCH/DELETE HTTP užklausos pažymėtos `Audit`, visa kita su`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Privalomas          | Įvykio būsena. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pasirinktinai          | Įvykio rezultatų būsena. Jei operacija atitinka REST API iškvietimą, tai http būsenos kodas.        | `200`             |
| `durationMs`      | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.     | `133`     |
| `callerIpAddress` | String    | Pasirinktinai          | Skambintojo IP adresas, jei operacija atitinka API skambutį, gautą iš viešai prieinamo IP adreso.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pasirinktinai          | JSON objektas, apibūdinantis operaciją atlikusio vartotojo ar programos tapatybę.       | Žiūrėkite [skyrių Tapatybė](#identity-schema).     |  
| `properties`      | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.      | Ypatybių [skyriuje](#api-properties-schema).    |
| `level`           | String    | Privalomas          | Įvykio sunkumo lygis.    | `Informational`, `Warning`,, `Error` arba `Critical`.           |
| `uri`             | String    | Pasirinktinai          | Absoliutus prašymas URI.    |               |

#### <a name="identity-schema"></a>Tapatybės schema

`identity` JSON objektas turi šią struktūrą

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
| `Authorization.UserRole`      | Priskirtas vartotojo arba programos vaidmuo. Daugiau informacijos ieškokite [user rightss](permissions.md).                                     |
| `Authorization.RequiredRoles` | Operacijai atlikti reikiami vaidmenys. `Admin` vaidmuo leidžiamas visoms operacijoms atlikti.                                                    |
| `Claims`                      | Vartotojo ar programos JSON žiniatinklio atpažinimo ženklo (JWT) pretenzijos. Pretenzijų ypatybės skiriasi priklausomai nuo organizacijos ir Azure Active Directory konfigūracijos. |

#### <a name="api-properties-schema"></a>API ypatybių schema

[API įvykiai](apis.md) turi šias ypatybes.

| Laukas                        | Aprašą                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Visada `ApiEvent` pažymėkite žurnalo įvykį KAIP API įvykį.                                                                 |
| `properties.userAgent`       | Naršyklės agentas, siunčiantis užklausą arba `unknown`.                                                                        |
| `properties.method`          | HTTP metodas:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Santykinis užklausos maršrutas.                                                                                          |
| `properties.origin`          | URI nurodo, iš kur atsiranda paėmimas, arba `unknown`.                                                                  |
| `properties.operationStatus` | `Success` http būsenos kodas < 400 <br> `ClientError` http būsenos kodas < 500 <br> `Error` http būsenai > = 500 |
| `properties.tenantId`        | Organizacijos ID                                                                                                        |
| `properties.tenantName`      | Organizacijos pavadinimas.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Skambinančiojo objectId.                                                                         |
| `properties.instanceId`      | Klientų įžvalgos`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbo eigos įvykių schema

Darbo eigoje yra keli veiksmai. [Nurykite duomenų šaltinius](data-sources.md), [suvienodinkite](data-unification.md), [praturtinkite](enrichment-hub.md) ir [eksportuokite](export-destinations.md) duomenis. Visi šie veiksmai gali būti atliekami atskirai arba organizuoti su šiais procesais. 

#### <a name="operation-types"></a>Operacijų tipai

| „OperationType“     | Grupuoti                                     |
| ----------------- | ----------------------------------------- |
| Nurijimas         | [Duomenų šaltiniai](data-sources.md)           |
| DataPreparation   | [Duomenų šaltiniai](data-sources.md)           |
| Susieti               | [Duomenų suvienodinimas](data-unification.md)   |
| Sugretinti             | [Duomenų suvienodinimas](data-unification.md)   |
| Sulieti             | [Duomenų suvienodinimas](data-unification.md)   |
| ProfileStore      | [Klientų profiliai](customer-profiles.md) |
| Paieška            | [Klientų profiliai](customer-profiles.md) |
| Veikla          | [Veiklos](activities.md)                  |
| AttributeMeasures | [Segmentai ir priemonės](segments.md)      |
| EntityMeasures    | [Segmentai ir priemonės](segments.md)      |
| Matavimai          | [Segmentai ir priemonės](segments.md)      |
| Segmentacija      | [Segmentai ir priemonės](segments.md)      |
| Papildymas        | [Papildymas](enrichment-hub.md)                                          |
| Duomenų rinkimas      | [Prognozės](predictions-overview.md)                                          |
| AiBuilder         | [Prognozės](predictions-overview.md)                                          |
| Įžvalgos          | [Prognozės](predictions-overview.md)                                          |
| Eksportavimas            | [Eksportavimai](export-destinations.md)                                          |
| ModelValdymas   | [Prognozės](custom-models.md)                                           |
| Ryšys      | [Duomenų suvienodinimas](relationships.md)                                           |

#### <a name="field-description"></a>Lauko aprašymas

| Laukas           | DataType  | Būtina / neprivaloma | Aprašą                                                                                                                                                   | Pavyzdžiui                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Privalomas          | Įvykio išmesto egzemplioriaus ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Privalomas          | Operacijos, kuriai atstovauja šis įvykis, pavadinimas. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Nuorodą rasite [Operacijų tipuose](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Privalomas          | Renginio žurnalo kategorija. Visada `Operational` darbo eigos įvykiams                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Privalomas          | Įvykio būsena. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.                                                                                        | Žiūrėti antrinę sekciją [Darbo eigos ypatybės](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Privalomas          | Įvykio sunkumo lygis.                                                                                                                                  | `Informational`, `Warning` arba `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbo eigos ypatybių schema

Darbo eigos įvykiai turi šias ypatybes.

| Laukas              | Workflow | Užduotis | Aprašą            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Taip      | Taip  | Visada `WorkflowEvent`, pažymėkite įvykį kaip darbo eigos įvykį.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Taip      | Taip  | Vykdomos darbo eigos identifikatorius. Visi darbo eigos ir užduočių įvykiai, susiję su darbo eigos vykdymu, yra vienodi `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Taip      | Taip  | Operacijos identifikatorius, žr [...](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Taip      | No   | Tik darbo eiga. Užduočių, kurias suaktyvina darbo eiga, skaičius.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Taip      | No   | Pasirenkama. Tik darbo eigos įvykiai. Vartotojo Azure Active Directory [...](/azure/marketplace/find-tenant-object-id#find-user-object-id), kuris suaktyvino darbo eigą, objektID taip pat `properties.workflowSubmissionKind` žr.                                   |
| `properties.workflowType`                    | Taip      | No   | `full` arba `incremental` atnaujinti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Taip      | No   | `OnDemand` arba `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Taip      | No   | `Running` arba `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Taip      | Taip  | Klientų įžvalgos`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Taip  | - OperationType = `Export`, identifikatorius yra eksportavimo konfigūracijos vadovas. <br> - OperacijaType = `Enrichment`, tai sodrinimo vadovas <br> - OperacijaType `Measures` ir `Segmentation`, identifikatorius yra objekto pavadinimas. |
| `properties.friendlyName`                    | No       | Taip  | Vartotojui patogus eksportavimo arba apdoroto objekto pavadinimas.                                                                                                                                                                                           |
| `properties.error`                           | No       | Taip  | Pasirenkama. Klaidos pranešimas su išsamesne informacija.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Identifikuoja eksportavimo tipą. Daugiau informacijos ieškokite [eksporto paskirties vietų apžvalgoje](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Yra sukonfigūruotų eksportavimo objektų sąrašas.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Išsamus eksporto pranešimas.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Taip  | Pasirenkama. Tik "OperationType"`Segmentation`. Nurodo bendrą segmento narių skaičių.                                                                                                                                                    |
