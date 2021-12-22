---
title: Auditas Dynamics 365 Customer Insights naudojant "Azure Monitor"
description: Sužinokite, kaip siųsti žurnalus Microsoft Azure monitoriui.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920872"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prisijungimas naudojant Dynamics 365 Customer Insights "Azure Monitor" (Preview)

Dynamics 365 Customer Insights suteikia tiesioginę integraciją su "Azure Monitor". "Azure Monitor" išteklių žurnalai leidžia stebėti ir siųsti žurnalus į ["Azure](https://azure.microsoft.com/services/storage/) Storage", ["Azure Log Analytics"](/azure/azure-monitor/logs/log-analytics-overview) arba transliuoti juos į ["Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/) " .

„Customer Insights“ siunčia šiuos įvykių žurnalus:

- **Audito įvykiai**
  - **APIEvent** – leidžia sekti keitimus naudojant vartotojo Dynamics 365 Customer Insights sąsają.
- **Veiklos renginiai**
  - **WorkflowEvent** – darbo eiga leidžia nustatyti [duomenų šaltinius](data-sources.md), [suvienodinti](data-unification.md), [praturtinti](enrichment-hub.md) bei galiausiai [eksportuoti](export-destinations.md) duomenis į kitas sistemas. Visus šiuos veiksmus galima atlikti atskirai (pvz., sukelti vieną eksportą) arba organizuoti (pvz., atnaujinti duomenis iš duomenų šaltinių, kurie sukelia suvienijimo procesą, kuris paskatins papildomus sodrinimus ir, kai bus atliktas duomenų eksportas į kitą sistemą). Daugiau informacijos ieškokite [WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** – visi API skambučiai klientams į Dynamics 365 Customer Insights. Daugiau informacijos ieškokite [APIEvent Schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikos parametrų nustatymas

### <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti diagnostiką programoje "Customer Insights", reikia įvykdyti šias būtinas sąlygas:

- Turite aktyvią ["Azure" prenumeratą](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- "Customer [Insights](permissions.md#administrator)" turite administratoriaus teises.
- **"Azure" paskirties išteklių bendraautoriaus** ir **vartotojo prieigos administratoriaus** vaidmuo. Išteklius gali būti "Azure" saugyklos abonementas, "Azure Event Hub" arba "Azure Log Analytics" darbo sritis. Daugiau informacijos ieškokite [Add arba remove Azure role assignments using the Azure portal](/azure/role-based-access-control/role-assignments-portal).
- [Atitiko](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) "Azure Storage", "Azure Event Hub" arba "Azure Log Analytics" paskirties reikalavimus.
- **Išteklių grupėje, kuriai priklauso išteklius, turite bent** skaitytojo vaidmenį.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikos nustatymas naudojant "Azure Monitor"

1. Programoje "Customer Insights" pasirinkite **Sistemos** > **diagnostika,** kad pamatytumėte diagnostikos paskirties vietas, sukonfigūruotas šį egzempliorių.

1. Pasirinkite **Įtraukti paskirties vietą**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikos ryšys](media/diagnostics-pane.png "Diagnostikos ryšys")

1. Pateikite pavadinimą **diagnostikos paskirties** lauke.

1. Pasirinkite **·** "Azure" prenumeratos nuomotoją naudodami paskirties išteklių ir **pasirinkite prisijungti**.

1. Pasirinkite **išteklių tipą** (saugyklos abonementas, įvykių telkinys arba žurnalo analizė).

1. Pasirinkite **paskirties** ištekliaus prenumeratą.

1. Pasirinkite **paskirties ištekliaus išteklių** grupę.

1. Pasirinkite **išteklių**.

1. Patvirtinkite **duomenų privatumo ir atitikties** patvirtinimą.

1. Pasirinkite **Jungtis prie** sistemos, kad prisijungtumėte prie paskirties išteklių. Žurnalai paskirties vietoje pradedami rodyti po 15 minučių, jei NAUDOJAMA API ir generuoja įvykius.

### <a name="remove-a-destination"></a>Paskirties vietos šalinimas

1. Eikite į **Sistemos** > **diagnostika**.

1. Sąraše pasirinkite diagnostikos paskirties vietą.

1. **Stulpelyje Veiksmai** pasirinkite **piktogramą** Naikinti.

1. Patvirtinkite naikinimą, kad sustabdytumėte žurnalo persiuntimą. "Azure" prenumeratos ištekliai nebus panaikinti. Galite pasirinkti **saitą** stulpelyje Veiksmai, kad atidarytumėte pasirinkto ištekliaus "Azure" portalą ir ten jį panaikintumėte.

## <a name="log-categories-and-event-schemas"></a>Žurnalo kategorijos ir įvykių schemos

Šiuo metu [palaikomi API įvykiai](apis.md) ir darbo eigos įvykiai ir taikomos šios kategorijos bei schemos.
Žurnalo schema atitinka ["Azure Monitor" bendrąją schemą](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijos

"Customer Insights" pateikia dvi kategorijas:

- **Audito įvykiai** : [API](#api-event-schema) įvykiai, skirti tarnybos konfigūracijos pokyčiams sekti. `POST|PUT|DELETE|PATCH` operacijos patenka į šią kategoriją.
- **Veiklos įvykiai**: [API įvykiai](#api-event-schema) arba [darbo eigos įvykiai](#workflow-event-schema) sugeneruoti naudojant tarnybą.  Pavyzdžiui, `GET` darbo eigos užklausos arba vykdymo įvykiai.

## <a name="configuration-on-the-destination-resource"></a>Paskirties ištekliaus konfigūracija

Atsižvelgiant į jūsų pasirinktą išteklių tipą, automatiškai bus taikomi šie veiksmai:

### <a name="storage-account"></a>Saugyklos klientas

"Customer Insights" tarnybos vadovas **gauna pasirinkto ištekliaus saugyklos abonemento bendraautoriaus** teises ir sukuria du konteinerius po pasirinkta vardų sritimi:

- `insight-logs-audit` audito įvykių **susodinimą**
- `insight-logs-operational` su **veiklos įvykiais**

### <a name="event-hub"></a>Įvykių telkinys

"Customer Insights" tarnybos vadovas gauna **ištekliaus "Azure Event Hubs" duomenų savininko** teises ir sukurs du įvykių centrus po pasirinkta vardų sritimi:

- `insight-logs-audit` audito įvykių **susodinimą**
- `insight-logs-operational` su **veiklos įvykiais**

### <a name="log-analytics"></a>Žurnalo analizė

"Customer Insights" tarnybos vadovas gauna **išteklių "Log Analytics" bendraautoriaus** teises. Žurnalus bus galima **rasti** > **·** > **pasirinktoje** "Log Analytics" darbo srityje dalyje Žurnalų lentelių žurnalo valdymas. Išplėskite **žurnalo valdymo** sprendimą ir raskite `CIEventsAudit``CIEventsOperational` lenteles ir lenteles.

- `CIEventsAudit` audito įvykių **susodinimą**
- `CIEventsOperational` su **veiklos įvykiais**

Lange **Užklausos** išplėskite **audito** sprendimą ir raskite užklausų pavyzdį, pateiktą ieškant `CIEvents`.

## <a name="event-schemas"></a>Įvykių schemos

API įvykiai ir darbo eigos įvykiai turi bendrą struktūrą ir išsamią informaciją, kur jie skiriasi, [žr.](#api-event-schema)[...](#workflow-event-schema)

### <a name="api-event-schema"></a>API įvykių schema

| Laukas             | DataType  | Būtina / pasirinktinai | Aprašą       | Pavyzdžiui        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Privalomas          | Įvykio išskleidimo egzemplioriaus ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Privalomas          | Operacijos, kuriai atstovauja šis įvykis, pavadinimas.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Privalomas          | Įvykio žurnalo kategorija. Arba, `Operational``Audit` arba. Visos POST/PUT/PATCH/DELETE HTTP užklausos pažymėtos `Audit`, visa kita su`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Privalomas          | Įvykio būsena. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pasirinktinai          | Įvykio rezultato būsena. Jei operacija atitinka REST API iškvietimą, tai yra HTTP būsenos kodas.        | `200`             |
| `durationMs`      | Ilgas      | Pasirinktinai          | Operacijos milisekundėmis trukmė.     | `133`     |
| `callerIpAddress` | String    | Pasirinktinai          | Skambintojo IP adresas, jei operacija atitinka API skambutį, kuris gaunamas iš viešai prieinamo IP adreso.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pasirinktinai          | JSON objektas, apibūdinantis vartotojo ar programos, kuri atliko operaciją, tapatybę.       | [Žiūrėkite](#identity-schema) tapatybės skyrių.     |  |
| `properties`      | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.      | [Skyriuje](#api-properties-schema) Ypatybės.    |
| `level`           | String    | Privalomas          | Įvykio sunkumo lygis.    | `Informational`, `Warning``Error`, arba `Critical`.           |
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
| `Authorization.UserRole`      | Priskirtas vartotojo arba programos vaidmuo. Daugiau informacijos ieškokite [user permissions](permissions.md).                                     |
| `Authorization.RequiredRoles` | Reikalingi vaidmenys operacijai atlikti. `Admin` Vaidmuo leidžiamas atlikti visas operacijas.                                                    |
| `Claims`                      | Vartotojo ar programos JSON žiniatinklio atpažinimo ženklo (JWT) pretenzijos. Pretenzijos ypatybės skiriasi priklausomai nuo organizacijos ir Azure Active Directory konfigūracijos. |

#### <a name="api-properties-schema"></a>API ypatybių schema

[API įvykiai](apis.md) turi šias ypatybes.

| Laukas                        | Aprašą                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Visada `ApiEvent`, pažymėdami žurnalo įvykį kaip API įvykį.                                                                 |
| `properties.userAgent`       | Naršyklės agentas, siunčiantis užklausą arba `unknown`.                                                                        |
| `properties.method`          | HTTP metodas:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Santykinis užklausos kelias.                                                                                          |
| `properties.origin`          | URI nurodo, iš kur gaunamas paėmimas arba `unknown`.                                                                  |
| `properties.operationStatus` | `Success` http būsenos kodas < 400 <br> `ClientError` http būsenos kodas < 500 <br> `Error` for HTTP būsenos >= 500 |
| `properties.tenantId`        | Organizacijos ID                                                                                                        |
| `properties.tenantName`      | Organizacijos pavadinimas.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Skambinančiojo objectId.                                                                         |
| `properties.instanceId`      | Klientų įžvalgos`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbo eigos įvykių schema

Darbo eigoje yra keli žingsniai. [Duomenų šaltinių praryjimas](data-sources.md), [suvienodinkite,](data-unification.md)[praturtinkite](enrichment-hub.md) ir [eksportuokite](export-destinations.md) duomenis. Visi šie veiksmai gali būti atlikti atskirai arba surežisuoti su šiais procesais. 

#### <a name="operation-types"></a>Operacijų tipai

| „OperationType“     | Grupuoti                                     |
| ----------------- | ----------------------------------------- |
| Nurijimas         | [Duomenų šaltiniai](data-sources.md)           |
| DataPreparas   | [Duomenų šaltiniai](data-sources.md)           |
| Susieti               | [Duomenų suvienodinimas](data-unification.md)   |
| Sugretinti             | [Duomenų suvienodinimas](data-unification.md)   |
| Sulieti             | [Duomenų suvienodinimas](data-unification.md)   |
| ProfileStore      | [Klientų profiliai](customer-profiles.md) |
| Paieška            | [Klientų profiliai](customer-profiles.md) |
| Veikla          | [Veiklos](activities.md)                  |
| Atributų išmatai | [Segmentai ir priemonės](segments.md)      |
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

#### <a name="field-description"></a>Lauko aprašymas

| Laukas           | DataType  | Būtina / pasirinktinai | Aprašą                                                                                                                                                   | Pavyzdžiui                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Privalomas          | Įvykio išskleidė egzemplioriaus ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Privalomas          | Operacijos, kuriai atstovauja šis įvykis, pavadinimas. `{OperationType}.[WorkFlow|Task][Started|Completed]`. [Nuorodų ieškokite Operacijų](#operation-types) tipai. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Privalomas          | Įvykio žurnalo kategorija. Darbo `Operational` eigos įvykiams visada                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Privalomas          | Įvykio būsena. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ilgas      | Pasirinktinai          | Operacijos milisekundėmis trukmė.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pasirinktinai          | JSON objektas, turintis daugiau savybių konkrečiai įvykių kategorijai.                                                                                        | Peržiūrėti poskyrio [darbo eigos ypatybes](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Privalomas          | Įvykio sunkumo lygis.                                                                                                                                  | `Informational`, `Warning` arba `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbo eigos ypatybių schema

Darbo eigos įvykiai turi šias ypatybes.

| Laukas              | Workflow | Užduotis | Aprašą            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Taip      | Taip  | Visada `WorkflowEvent` pažymėkite įvykį kaip darbo eigos įvykį.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Taip      | Taip  | Darbo eigos vykdymo identifikatorius. Visi darbo eigos ir užduočių įvykiai darbo eigos vykdymo metu turi tą patį `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Taip      | Taip  | Operacijos identifikatorius žr. (#operation tipai)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Taip      | No   | Tik darbo eiga. Darbo eigos suaktyvintų užduočių skaičius.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Taip      | No   | Pasirenkama. Tik darbo eigos įvykiai. Azure Active Directory [Vartotojo, kuris suaktyvino darbo eigą, objectId](/azure/marketplace/find-tenant-object-id#find-user-object-id) taip pat `properties.workflowSubmissionKind` žr.                                   |
| `properties.workflowType`                    | Taip      | No   | `full` arba `incremental` atnaujinti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Taip      | No   | `OnDemand` arba `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Taip      | No   | `Running` arba `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Taip      | Taip  | Klientų įžvalgos`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Taip  | - OperationType = `Export`, identifikatorius yra eksportavimo konfigūracijos guid. <br> - OperationType = `Enrichment`, tai sodrinimo pagrindas <br> - OperationType `Measures` ir `Segmentation`, identifikatorius yra objekto pavadinimas. |
| `properties.friendlyName`                    | No       | Taip  | Vartotojui patogus eksportavimo arba apdorojamo objekto pavadinimas.                                                                                                                                                                                           |
| `properties.error`                           | No       | Taip  | Pasirenkama. Klaidos pranešimas su daugiau informacijos.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Taip  | Pasirenkama. `Export` Skirta tik OperacijaiType. Identifikuoja eksportavimo tipą. Daugiau informacijos ieškokite [export destinations .](export-destinations.md)                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Taip  | Pasirenkama. `Export` Skirta tik OperacijaiType. Yra sukonfigūruotų eksportavimo objektų sąrašas.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Taip  | Pasirenkama. `Export` Skirta tik OperacijaiType. Išsamus pranešimas eksportui.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Taip  | Pasirenkama. `Segmentation` Skirta tik OperacijaiType. Nurodo bendrą segmento narių skaičių.                                                                                                                                                    |
