---
title: Auditas Dynamics 365 Customer Insights naudojant "Azure Monitor"
description: Sužinokite, kaip siųsti žurnalus į monitorių Microsoft Azure.
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
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643034"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prisijungimas persiunčiant naudojant Dynamics 365 Customer Insights "Azure Monitor" (peržiūra)

Dynamics 365 Customer Insights suteikia tiesioginę integraciją su "Azure Monitor". "Azure Monitor" išteklių žurnalai leidžia stebėti ir siųsti žurnalus į ["Azure Storage](https://azure.microsoft.com/services/storage/)", ["Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)" arba transliuoti juos į ["Azure Event Hubs"](https://azure.microsoft.com/services/event-hubs/).

"Customer Insights" siunčia šiuos įvykių žurnalus:

- **Audito įvykiai**
  - **APIEvent** - leidžia keitimų stebėjimą Dynamics 365 Customer Insights atlikti per vartotojo sąsają.
- **Veiklos įvykiai**
  - **WorkflowEvent** - Darbo eiga leidžia nustatyti [duomenų šaltinius](data-sources.md), [suvienyti ir](data-unification.md) praturtinti [ir](enrichment-hub.md) galiausiai [eksportuoti](export-destinations.md) duomenis į kitas sistemas. Visus šiuos veiksmus galima atlikti atskirai (pvz., pradėti vieną eksportą) arba organizuoti (pvz., duomenų atnaujinimas iš duomenų šaltinių, dėl kurių pradedamas suvienijimo procesas, kuris paskatins sustiprinimą, o atlikus jį bus galima papildomai praturtinti ir, kai tai bus padaryta, duomenis eksportuoti į kitą sistemą). Daugiau informacijos ieškokite [WorkflowEvent schema](#workflow-event-schema).
  - **APIEvent** - visi API skambučiai klientų egzemplioriui į Dynamics 365 Customer Insights. Daugiau informacijos ieškokite [APIEvent schema.](#api-event-schema)

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikos parametrų nustatymas

### <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti diagnostiką programoje "Customer Insights", turi būti įvykdytos šios būtinosios sąlygos:

- Turite aktyvią ["Azure" prenumeratą](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Turite administratoriaus](permissions.md#admin) teises "Customer Insights".
- "Azure" **paskirties ištekliuose yra bendraautoriaus** ir **vartotojo prieigos administratoriaus** vaidmuo. Išteklius gali būti "Azure Storage" abonementas, "Azure Event Hub" arba "Azure Log Analytics" darbo sritis. Daugiau informacijos ieškokite ["Azure" vaidmenų priskyrimų įtraukimas arba šalinimas naudojant "Azure" portalą](/azure/role-based-access-control/role-assignments-portal).
- [Įvykdyti "Azure Storage", "Azure Event Hub" arba "Azure Log Analytics" paskirties vietos reikalavimai](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements).
- Išteklių grupėje, kuriai priklauso išteklius, turite bent **skaitytojo** vaidmenį.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikos nustatymas naudojant "Azure Monitor"

1. "Customer Insights" pasirinkite **SystemDiagnostics** > **·**, kad pamatytumėte diagnostikos paskirties vietas, sukonfigūruotas šiuo egzemplioriumi.

1. Pasirinkite **Įtraukti paskirties vietą**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikos ryšys](media/diagnostics-pane.png "Diagnostikos ryšys")

1. Pateikite pavadinimą lauke **Diagnostikos paskirties pavadinimas**.

1. Pasirinkite **"Azure" prenumeratos nuomotoją** su paskirties ištekliais ir pasirinkite **prisijungti**.

1. Pasirinkite ištekliaus **tipą** (saugyklos abonementas, įvykių telkinys arba žurnalo analizė).

1. Pasirinkite **paskirties ištekliaus prenumeratą**.

1. Pasirinkite **paskirties ištekliaus išteklių grupę**.

1. Pasirinkite **išteklius**.

1. **Patvirtinkite duomenų privatumo ir atitikties** patvirtinimą.

1. Pasirinkite **Prisijungti prie sistemos**, kad prisijungtumėte prie paskirties ištekliaus. Žurnalai pradeda rodyti paskirties vietoje po 15 minučių, jei API yra naudojama ir generuoja įvykius.

### <a name="remove-a-destination"></a>Paskirties vietos šalinimas

1. Eikite į **SystemDiagnostics** > **·**.

1. Sąraše pasirinkite diagnostikos paskirties vietą.

1. Stulpelyje **Veiksmai** pasirinkite piktogramą **Naikinti**.

1. Patvirtinkite naikinimą, kad sustabdytumėte žurnalo persiuntimą. "Azure" prenumeratos išteklius nebus panaikintas. Stulpelyje **Veiksmai** galite pasirinkti saitą, kad atidarytumėte pasirinkto ištekliaus "Azure" portalą ir ten jį panaikintumėte.

## <a name="log-categories-and-event-schemas"></a>Žurnalo kategorijos ir įvykių schemos

Šiuo metu [palaikomi API įvykiai](apis.md) ir darbo eigos įvykiai, taikomos šios kategorijos ir schemos.
Žurnalo schema atitinka " [Azure Monitor" bendrąją schemą](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijos

"Customer Insights" pateikia dvi kategorijas:

- **Audito įvykiai**: [API įvykiai](#api-event-schema), skirti tarnybos konfigūracijos pakeitimams sekti. `POST|PUT|DELETE|PATCH` Operacijos patenka į šią kategoriją.
- **Veiklos įvykiai**: [API įvykiai](#api-event-schema) arba [darbo eigos įvykiai](#workflow-event-schema), sugeneruoti naudojant paslaugą.  Pavyzdžiui, `GET` darbo eigos užklausos arba vykdymo įvykiai.

## <a name="configuration-on-the-destination-resource"></a>Paskirties ištekliaus konfigūracija

Atsižvelgiant į jūsų pasirinkimą pagal ištekliaus tipą, automatiškai bus taikomi šie veiksmai:

### <a name="storage-account"></a>Saugyklos klientas

"Customer Insights" tarnybos vykdytojas gauna **saugyklos abonemento bendraautoriaus** teises pasirinktame ištekliuje ir sukuria du konteinerius pasirinktoje vardų srityje:

- `insight-logs-audit` kuriuose yra **audito įvykių**
- `insight-logs-operational` su **veiklos įvykiais**

### <a name="event-hub"></a>Įvykių telkinys

"Customer Insights" tarnybos vykdytojas gauna **"Azure" įvykių centrų duomenų savininko** teises į ištekliaus ir sukurs du įvykių centrus pasirinktoje vardų srityje:

- `insight-logs-audit` kuriuose yra **audito įvykių**
- `insight-logs-operational` su **veiklos įvykiais**

### <a name="log-analytics"></a>Žurnalo analizė

"Customer Insights" tarnybos vykdytojas gauna ištekliaus **žurnalo analizės bendraautoriaus** teises. Žurnalai bus pasiekiami pasirinktos Log Analytics darbo srities dalyje **LogsTablesLog** > **·** > **Management**. Išplėskite žurnalo **valdymo** sprendimą ir raskite lenteles `CIEventsAudit` ir `CIEventsOperational` lenteles.

- `CIEventsAudit` kuriuose yra **audito įvykių**
- `CIEventsOperational` su **veiklos įvykiais**

**Lange Užklausos** išplėskite **audito** sprendimą ir raskite užklausų pavyzdžius, pateiktus ieškant `CIEvents`.

## <a name="event-schemas"></a>Įvykių schemos

API įvykiai ir darbo eigos įvykiai turi bendrą struktūrą ir išsamią informaciją, kur jie skiriasi, žr [...](#api-event-schema)[...](#workflow-event-schema).

### <a name="api-event-schema"></a>API įvykių schema

| Laukas             | DataType  | Būtina/Pasirinktinai | Aprašą       | Pavyzdžiui        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Privalomas          | Įvykio išstūmimo egzemplioriaus ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Privalomas          | Šio įvykio atstovaujamos operacijos pavadinimas.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Privalomas          | Renginio žurnalo kategorija. `Operational` Arba `Audit`. Visos POST/PUT/PATCH/DELETE HTTP užklausos yra pažymėtos `Audit`, visa kita su`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Privalomas          | Įvykio būsena. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pasirinktinai          | Įvykio rezultato būsena. Jei operacija atitinka REST API skambutį, tai yra HTTP būsenos kodas.        | `200`             |
| `durationMs`      | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.     | `133`     |
| `callerIpAddress` | String    | Pasirinktinai          | Skambinančiojo IP adresas, jei operacija atitinka API skambutį, gautą iš viešai prieinamo IP adreso.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pasirinktinai          | JSON objektas, apibūdinantis operaciją atlikusio vartotojo ar programos tapatybę.       | [Skyrių Tapatybė.](#identity-schema)     |  
| `properties`      | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.      | [Žr](#api-properties-schema).    |
| `level`           | String    | Privalomas          | Įvykio sunkumo lygis.    | `Informational`, `Warning` arba `Error``Critical`.           |
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
| `Authorization.UserRole`      | Priskirtas vartotojo arba programos vaidmuo. Daugiau informacijos ieškokite [user permissions](permissions.md).                                     |
| `Authorization.RequiredRoles` | Operacijai atlikti reikalingi vaidmenys. `Admin` Vaidmuo leidžiamas atlikti visas operacijas.                                                    |
| `Claims`                      | Vartotojo arba programos JSON žiniatinklio atpažinimo ženklo (JWT) pretenzijos. Pretenzijų ypatybės skiriasi priklausomai nuo Azure Active Directory organizacijos ir konfigūracijos. |

#### <a name="api-properties-schema"></a>API ypatybių schema

[API įvykiai](apis.md) turi šias ypatybes.

| Laukas                        | Aprašą                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Visada `ApiEvent`, žurnalo įvykio žymėjimas kaip API įvykis.                                                                 |
| `properties.userAgent`       | Naršyklės agentas, siunčiantis užklausą arba `unknown`.                                                                        |
| `properties.method`          | HTTP metodas:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Santykinis užklausos kelias.                                                                                          |
| `properties.origin`          | URI nurodo, iš kur gaunamas ėminys arba .`unknown`                                                                  |
| `properties.operationStatus` | `Success` HTTP būsenos kodui < 400 <br> `ClientError` HTTP būsenos kodui < 500 <br> `Error` HTTP būsenos > = 500 |
| `properties.tenantId`        | Organizacijos ID                                                                                                        |
| `properties.tenantName`      | Organizacijos pavadinimas.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Skambinančiojo objektas.                                                                         |
| `properties.instanceId`      | "Customer Insights" `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbo eigos įvykių schema

Darbo eigoje yra keli veiksmai. [Duomenų šaltinių](data-sources.md) nurijimas, [duomenų suvienodinimas](data-unification.md), [praturtinimas](enrichment-hub.md) ir [eksportavimas](export-destinations.md). Visi šie veiksmai gali būti vykdomi atskirai arba organizuojami naudojant šiuos procesus. 

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
| ModelManagement   | [Prognozės](custom-models.md)                                           |
| Ryšys      | [Duomenų suvienodinimas](relationships.md)                                           |

#### <a name="field-description"></a>Lauko aprašas

| Laukas           | DataType  | Būtina/Pasirinktinai | Aprašą                                                                                                                                                   | Pavyzdžiui                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Privalomas          | Egzemplioriaus, išplatinusio įvykį, resourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Privalomas          | Šio įvykio atstovaujamos operacijos pavadinimas. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Nuorodos ieškokite [Operations Types](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Privalomas          | Renginio žurnalo kategorija. Visada `Operational` darbo eigos įvykiams                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Privalomas          | Įvykio būsena. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.                                                                                        | Žiūrėkite poskyrį [Darbo eigos ypatybės](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Privalomas          | Įvykio sunkumo lygis.                                                                                                                                  | `Informational`, `Warning` arba `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbo eigos ypatybių schema

Darbo eigos įvykiai turi šias ypatybes.

| Laukas              | Workflow | Užduotis | Aprašą            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Taip      | Taip  | Visada `WorkflowEvent` pažymėkite įvykį kaip darbo eigos įvykį.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Taip      | Taip  | Vykdomos darbo eigos identifikatorius. Visi darbo eigos ir užduoties įvykiai, susiję su darbo eigos vykdymu, turi tą patį `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Taip      | Taip  | Operacijos identifikatorius [žr](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Taip      | No   | Tik darbo eiga. Užduočių, kurias suaktyvina darbo eiga, skaičius.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Taip      | No   | Pasirenkama. Tik darbo eigos įvykiai. Vartotojo Azure Active Directory [...](/azure/marketplace/find-tenant-object-id#find-user-object-id), suaktyvinusio darbo eigą, objectId taip pat `properties.workflowSubmissionKind` žr.                                   |
| `properties.workflowType`                    | Taip      | No   | `full` arba `incremental` atnaujinti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Taip      | No   | `OnDemand` arba `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Taip      | No   | `Running` arba `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Taip      | Taip  | "Customer Insights" `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Taip  | - OperationType = `Export`, identifikatorius yra eksporto konfigūracijos vadovas. <br> - OperationType = `Enrichment`, tai yra sodrinimo vadovas <br> - OperationType `Measures` ir `Segmentation`, identifikatorius yra objekto pavadinimas. |
| `properties.friendlyName`                    | No       | Taip  | Patogus eksportuoti arba apdorojamo objekto pavadinimas.                                                                                                                                                                                           |
| `properties.error`                           | No       | Taip  | Pasirenkama. Klaidos pranešimas su daugiau informacijos.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Taip  | Pasirenkama. Tik "OperationType `Export` ". Identifikuoja eksportavimo tipą. Daugiau informacijos ieškokite [eksporto paskirties vietų apžvalgoje](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Taip  | Pasirenkama. Tik "OperationType `Export` ". Yra sukonfigūruotų eksportuojamų objektų sąrašas.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Taip  | Pasirenkama. Tik "OperationType `Export` ". Išsamus pranešimas apie eksportą.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Taip  | Pasirenkama. Tik "OperationType `Segmentation` ". Nurodo bendrą segmento narių skaičių.                                                                                                                                                    |
