---
title: Auditas Dynamics 365 Customer Insights naudojant "Azure Monitor"
description: Sužinokite, kaip siųsti žurnalus monitoriui Microsoft Azure.
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
ms.openlocfilehash: 2e0801c2b6af591e48a7df485a8523903c07617c
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354418"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Prisijungimas Dynamics 365 Customer Insights prie "Azure Monitor" (peržiūra)

Dynamics 365 Customer Insights užtikrina tiesioginę integraciją su "Azure Monitor". "Azure Monitor" išteklių žurnalai leidžia stebėti ir siųsti žurnalus į ["Azure Storage](https://azure.microsoft.com/services/storage/)", ["Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)" arba transliuoti juos į ["Azure Event Hubs"](https://azure.microsoft.com/services/event-hubs/).

"Customer Insights" siunčia šiuos įvykių žurnalus:

- **Audito įvykiai**
  - **APIEvent** - leidžia keisti stebėjimą Dynamics 365 Customer Insights per vartotojo sąsają.
- **Veiklos įvykiai**
  - **WorkflowEvent** – darbo eiga leidžia nustatyti [duomenų šaltinius](data-sources.md), [suvienodinti](data-unification.md) ir [praturtinti](enrichment-hub.md) duomenis ir galiausiai [eksportuoti](export-destinations.md) duomenis į kitas sistemas. Visus šiuos veiksmus galima atlikti atskirai (pvz., sukelti vieną eksportą) arba juos organizuoti (pvz., duomenų atnaujinimas iš duomenų šaltinių, dėl kurių pradedamas suvienijimo procesas, kuris paskatins papildomus sodrinimus ir, kai duomenys bus eksportuojami į kitą sistemą). Daugiau informacijos ieškokite [WorkflowEvent schema](#workflow-event-schema).
  - **APIEvent** – visi API skambina į klientų egzempliorių Dynamics 365 Customer Insights. Daugiau informacijos rasite [APIEvent schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikos parametrų nustatymas

### <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti diagnostiką programoje "Customer Insights", turi būti įvykdytos šios būtinosios sąlygos:

- Turite aktyvią ["Azure" prenumeratą](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Turite administratoriaus](permissions.md#administrator) teises "Customer Insights".
- "Azure" paskirties ištekliuje turite **bendraautoriaus** ir **vartotojo prieigos administratoriaus** vaidmenį. Išteklius gali būti "Azure" saugyklos abonementas, "Azure" įvykių telkinys arba "Azure Log Analytics" darbo sritis. Daugiau informacijos ieškokite [Azure vaidmenų priskyrimų įtraukimas arba šalinimas naudojant "Azure" portalą](/azure/role-based-access-control/role-assignments-portal).
- ["Azure Storage", "Azure Event Hub" arba "Azure Log Analytics" paskirties reikalavimai](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) atitiko.
- Išteklių grupėje, kuriai priklauso išteklius, turite bent **jau skaitytojo** vaidmenį.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostikos nustatymas naudojant "Azure Monitor"

1. Programoje "Customer Insights" pasirinkite **SystemDiagnostics** > **·**, kad pamatytumėte diagnostikos paskirties vietas, sukonfigūruotas šiame egzemplioriuje.

1. Pasirinkite **Įtraukti paskirties vietą**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostikos ryšys](media/diagnostics-pane.png "Diagnostikos ryšys")

1. Pateikite **pavadinimą diagnostikos paskirties** lauke Pavadinimas.

1. Pasirinkite "**Azure" prenumeratos nuomotoją** naudodami paskirties šaltinį ir pasirinkite **prisijungti**.

1. Pasirinkite išteklių **tipą** (saugyklos sąskaita, įvykių telkinys arba žurnalo analizė).

1. **Pasirinkite paskirties ištekliaus prenumeratą**.

1. **Pasirinkite paskirties ištekliaus išteklių grupę**.

1. **Pasirinkite Išteklius**.

1. Patvirtinkite **Duomenų privatumo ir atitikties** patvirtinimą.

1. Pasirinkite **Prisijungti prie sistemos**, kad prisijungtumėte prie paskirties ištekliaus. Žurnalai paskirties vietoje pradeda rodytis po 15 minučių, jei API naudojama ir generuoja įvykius.

### <a name="remove-a-destination"></a>Paskirties vietos šalinimas

1. Eikite į **SystemDiagnostics** > **·**.

1. Sąraše pasirinkite diagnostikos paskirties vietą.

1. Stulpelyje **Veiksmai** pasirinkite piktogramą **Naikinti**.

1. Patvirtinkite naikinimą, kad sustabdytumėte žurnalo peradresavimą. "Azure" prenumeratos ištekliai nebus panaikinti. Stulpelyje Veiksmai **galite pasirinkti saitą**, kad atidarytumėte pasirinkto ištekliaus "Azure" portalą ir panaikintumėte jį ten.

## <a name="log-categories-and-event-schemas"></a>Žurnalo kategorijos ir įvykių schemos

Šiuo metu [palaikomi API įvykiai](apis.md) ir darbo eigos įvykiai, taikomos šios kategorijos ir schemos.
Žurnalo schema atitinka " [Azure Monitor" bendrąją schemą](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategorijos

"Customer Insights" pateikia dvi kategorijas:

- **Audito įvykiai**: [API įvykiai](#api-event-schema), skirti tarnybos konfigūracijos pakeitimams sekti. `POST|PUT|DELETE|PATCH` operacijos patenka į šią kategoriją.
- **Veiklos įvykiai**: [API įvykiai](#api-event-schema) arba [darbo eigos įvykiai](#workflow-event-schema), sugeneruoti naudojant paslaugą.  Pavyzdžiui, `GET` darbo eigos užklausos arba vykdymo įvykiai.

## <a name="configuration-on-the-destination-resource"></a>Paskirties ištekliaus konfigūracija

Atsižvelgiant į jūsų pasirinkimą pagal išteklių tipą, automatiškai bus taikomi šie veiksmai:

### <a name="storage-account"></a>Saugyklos klientas

"Customer Insights" aptarnavimo vadovas gauna **pasirinkto ištekliaus saugyklos sąskaitos mokėtojo** teises ir sukuria du konteinerius pasirinktoje vardų srityje:

- `insight-logs-audit` kuriame yra **audito įvykių**
- `insight-logs-operational` kuriame yra **veiklos įvykių**

### <a name="event-hub"></a>Įvykių telkinys

"Customer Insights" tarnybos vadovas gauna **"Azure Event Hubs" duomenų savininko** teises ištekliui ir sukurs du įvykių centrus pasirinktoje vardų srityje:

- `insight-logs-audit` kuriame yra **audito įvykių**
- `insight-logs-operational` kuriame yra **veiklos įvykių**

### <a name="log-analytics"></a>Žurnalo analizė

"Customer Insights" tarnybos vadovas gauna **ištekliaus "Log Analytics" bendraautoriaus** teises. Žurnalai bus pasiekiami pasirinktoje "Log Analytics" darbo srityje dalyje **LogsTablesLog** > **·** > **Management**. Išplėskite žurnalo **valdymo** sprendimą ir raskite `CIEventsAudit` lenteles `CIEventsOperational`.

- `CIEventsAudit` kuriame yra **audito įvykių**
- `CIEventsOperational` kuriame yra **veiklos įvykių**

**Lange Užklausos** išplėskite **audito** sprendimą ir raskite užklausų pavyzdžius ieškodami `CIEvents`.

## <a name="event-schemas"></a>Įvykių schemos

API įvykiai ir darbo eigos įvykiai turi bendrą struktūrą ir išsamią informaciją, kur jie skiriasi, žr [...](#api-event-schema)[...](#workflow-event-schema).

### <a name="api-event-schema"></a>API įvykio schema

| Laukas             | Duomenų tipas  | Būtina / neprivaloma | Aprašą       | Pavyzdžiui        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Privalomas          | Įvykio išmestų egzempliorių ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Privalomas          | Operacijos, kurią nurodo šis įvykis, pavadinimas.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Privalomas          | Renginio žurnalo kategorija. Arba arba `Operational``Audit`. Visos POST/PUT/PATCH/DELETE HTTP užklausos pažymėtos `Audit`, visa kita su`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Privalomas          | Įvykio būsena. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Pasirinktinai          | Įvykio rezultato būsena. Jei operacija atitinka REST API skambutį, tai HTTP būsenos kodas.        | `200`             |
| `durationMs`      | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.     | `133`     |
| `callerIpAddress` | String    | Pasirinktinai          | Skambinančioojo IP adresas, jei operacija atitinka API skambutį, kuris gaunamas iš viešai prieinamo IP adreso.                                                 | `144.318.99.233`         |
| `identity`        | String    | Pasirinktinai          | JSON objektas, apibūdinantis operaciją atlikusios vartotojo ar programos tapatybę.       | Žiūrėkite [tapatybės](#identity-schema) skyrių.     |  |
| `properties`      | String    | Pasirinktinai          | JSON objektas, turintis daugiau ypatybių konkrečiai įvykių kategorijai.      | Žiūrėkite [ypatybių](#api-properties-schema) skyrių.    |
| `level`           | String    | Privalomas          | Įvykio sunkumo lygis.    | `Informational`, `Warning``Error` arba `Critical`.           |
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
| `Authorization.RequiredRoles` | Operacijai atlikti reikalingi vaidmenys. `Admin` Vaidmuo leidžiamas atlikti visas operacijas.                                                    |
| `Claims`                      | Vartotojo ar programos JSON žiniatinklio atpažinimo ženklo (JWT) pretenzijos. Pretenzijų ypatybės skiriasi priklausomai nuo organizacijos ir Azure Active Directory konfigūracijos. |

#### <a name="api-properties-schema"></a>API ypatybių schema

[API įvykiuose](apis.md) yra šios ypatybės.

| Laukas                        | Aprašą                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Visada `ApiEvent`, pažymėdamas žurnalo įvykį kaip API įvykį.                                                                 |
| `properties.userAgent`       | Naršyklės agentas, siunčiantis užklausą arba `unknown`.                                                                        |
| `properties.method`          | HTTP metodas:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Santykinis užklausos maršrutas.                                                                                          |
| `properties.origin`          | URI, nurodantis, iš kur gaunamas arba `unknown`.                                                                  |
| `properties.operationStatus` | `Success` http būsenos kodas < 400 <br> `ClientError` http būsenos kodas < 500 <br> `Error` http būsenos >= 500 |
| `properties.tenantId`        | Organizacijos ID                                                                                                        |
| `properties.tenantName`      | Organizacijos pavadinimas.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Skambintojo objektyvas.                                                                         |
| `properties.instanceId`      | Kliento įžvalgos`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Darbo eigos įvykio schema

Darbo eigoje yra keli veiksmai. [Prarykite duomenų šaltinius](data-sources.md), [suvienodinkite](data-unification.md), [praturtinkite](enrichment-hub.md) ir [eksportuokite](export-destinations.md) duomenis. Visi šie veiksmai gali būti vykdomi atskirai arba organizuoti su šiais procesais. 

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
| AtributasMeasures | [Segmentai ir priemonės](segments.md)      |
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

| Laukas           | Duomenų tipas  | Būtina / neprivaloma | Aprašą                                                                                                                                                   | Pavyzdžiui                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Laiko žyma | Privalomas          | Renginio laiko žyma (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Privalomas          | Įvykio išmestų egzempliorių ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Privalomas          | Operacijos, kurią nurodo šis įvykis, pavadinimas. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Nuorodą ieškokite [Operacijų tipai](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Privalomas          | Renginio žurnalo kategorija. Visada `Operational` darbo eigos įvykiams                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Privalomas          | Įvykio būsena. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Ilgas      | Pasirinktinai          | Operacijos trukmė milisekundėmis.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Pasirinktinai          | JSON objektas, turintis daugiau ypatybių konkrečiai įvykių kategorijai.                                                                                        | Peržiūrėti poskyrio [darbo eigos ypatybes](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Privalomas          | Įvykio sunkumo lygis.                                                                                                                                  | `Informational`, `Warning` arba `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Darbo eigos ypatybių schema

Darbo eigos įvykiai turi šias ypatybes.

| Laukas              | Workflow | Užduotis | Aprašą            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Taip      | Taip  | Visada `WorkflowEvent`, pažymėdamas įvykį kaip darbo eigos įvykį.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Taip      | Taip  | Darbo eigos vykdymo identifikatorius. Visi darbo eigos ir užduočių įvykiai darbo eigos vykdymo metu turi tą patį `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Taip      | Taip  | Operacijos identifikatorius, žr. (#operation tipai)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Taip      | No   | Tik darbo eiga. Užduočių, kurias suaktyvina darbo eiga, skaičius.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Taip      | No   | Pasirenkama. Tik darbo eigos įvykiai. Vartotojo Azure Active Directory [...](/azure/marketplace/find-tenant-object-id#find-user-object-id), kuris suaktyvino darbo eigą, objektas taip pat `properties.workflowSubmissionKind` žr.                                   |
| `properties.workflowType`                    | Taip      | No   | `full` arba `incremental` atnaujinti.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Taip      | No   | `OnDemand` arba `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Taip      | No   | `Running` arba `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Taip      | Taip  | UTC laiko žyma`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Taip      | Taip  | Kliento įžvalgos`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Taip  | – OperacijosType = `Export`, identifikatorius yra eksporto konfigūracijos guidas. <br> - OperacijaiType = `Enrichment` tai sodrinimo orientyras <br> – OperacijosType `Measures` ir `Segmentation`, identifikatorius yra objekto pavadinimas. |
| `properties.friendlyName`                    | No       | Taip  | Vartotojui patogus eksportavimo arba apdoroto objekto pavadinimas.                                                                                                                                                                                           |
| `properties.error`                           | No       | Taip  | Pasirenkama. Klaidos pranešimas su išsamesne informacija.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Identifikuoja eksportavimo tipą. Daugiau informacijos ieškokite [eksporto paskirties vietų apžvalgoje](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Yra eksportavimo sukonfigūruotų objektų sąrašas.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Taip  | Pasirenkama. Tik "OperationType"`Export`. Išsamus pranešimas eksportui.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Taip  | Pasirenkama. Tik "OperationType"`Segmentation`. Nurodo bendrą segmento narių skaičių.                                                                                                                                                    |
