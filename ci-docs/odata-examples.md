---
title: "\"OData\" užklausų pavyzdžiai, skirti \"Customer Insights\" API"
description: Dažniausiai naudojami atvirųjų duomenų protokolo ("OData") pavyzdžiai, skirti užklausoms dėl "Customer Insights" API pateikti užklausą, kad būtų galima peržiūrėti duomenis.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54ba9f4e9baeb4b7021bb8c20a706bbb6eb1529f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083167"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>"OData" užklausų pavyzdžiai, skirti "Customer Insights" API

Atvirųjų duomenų protokolas (OData) yra duomenų prieigos protokolas, sukurtas remiantis pagrindiniais protokolais, pvz., HTTP. Jis naudoja visuotinai pripažintas metodikas, pvz., REST žiniatinkliui. Yra įvairių tipų bibliotekų ir įrankių, kuriuos galima naudoti "OData" paslaugoms naudoti.

Šiame straipsnyje pateikiami keli dažnai prašomi užklausų pavyzdžiai, kurie padės jums sukurti savo diegimus pagal ["Customer Insights" API](apis.md).

Turite modifikuoti užklausos pavyzdžius, kad jie veiktų tikslinėse aplinkose: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kur {instanceId} yra "Customer Insights" aplinkos GUID, dėl kurio norite pateikti užklausą. Operacija [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) leidžia rasti tą, {InstanceId} prie kurio turite prieigą.
- {CID}: vieningo kliento įrašo GUID. Pavyzdys:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: kliento įrašo pirminio rakto identifikatorius duomenų šaltinis. Pavyzdys: `CNTID_1002`
- {DSname}: eilutė su duomenų šaltinis, kuri patenka į "Customer Insights", objekto pavadinimu. Pavyzdys:`Website_contacts`.
- {SegmentName}: eilutė su segmento išvesties objekto pavadinimu "Customer Insights". Pavyzdys:`Male_under_40`.

## <a name="customer"></a>kliente

Šioje lentelėje yra objekto Klientas *pavyzdinių užklausų* rinkinys.

|Užklausos tipas |Pavyzdžiui  | Pastaba.  |
|---------|---------|---------|
|Vieno kliento ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatyvusis raktas    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatyvūs raktai išlieka vieningame kliento objekte       |
|Pažymėti   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Po    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatyvusis raktas + Į   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Paieška  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Grąžina 10 populiariausių ieškos eilutės rezultatų      |
|Segmento narystė  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Grąžina iš anksto nustatytą segmentavimo objekto eilučių skaičių.      |

## <a name="unified-activity"></a>Vieninga veikla

Šioje lentelėje pateikiamas "UnifiedActivity"*objekto* pavyzdinių užklausų rinkinys.

|Užklausos tipas |Pavyzdžiui  | Pastaba.  |
|---------|---------|---------|
|CID veikla     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Pateikia konkretaus kliento profilio veiklos sąrašus |
|Veiklos laikotarpis    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Kliento profilio veikla per tam tikrą laikotarpį       |
|Veiklos tipas    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Veikla pagal rodomą pavadinimą     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Veiklos rūšiavimas    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Rūšiavimo veiklos didėjimo arba mažėjimo tvarka       |
|Veikla išsiplėtė iš segmento narystės  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Kiti pavyzdžiai

Šioje lentelėje pateikiamas kitų objektų užklausų pavyzdžių rinkinys.

|Užklausos tipas |Pavyzdžiui  | Pastaba.  |
|---------|---------|---------|
|CID priemonės    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Praturtinti CID prekės ženklai    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Praturtinti CID interesai    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Sąlyga + išplėtimas     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Nepalaikomos "OData" užklausos

"Customer Insights" nepalaiko šių užklausų:

- `$filter` dėl nurijusių šaltinio objektų. $filter užklausas galite vykdyti tik "Customer Insights" kuriamuose sistemos objektuose.
- `$expand``$search` iš užklausos. Pavyzdys: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` iš `$select` jei pasirenkamas tik atributų pogrupis. Pavyzdys: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` praturtintas prekės ženklas ar pomėgiai konkrečiam klientui. Pavyzdys: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Užklausos prognozė modelio išvesties objektus per alternatyvusis raktas. Pavyzdys: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
