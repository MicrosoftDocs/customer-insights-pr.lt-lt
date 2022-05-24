---
title: API OData pavyzdžiai Dynamics 365 Customer Insights
description: Dažniausiai naudojami atvirųjų duomenų protokolo (OData) pavyzdžiai, kaip pateikti užklausą "Customer Insights" API, kad būtų galima peržiūrėti duomenis.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740071"
---
# <a name="odata-query-examples"></a>OData užklausų pavyzdžiai

Atvirųjų duomenų protokolas (OData) yra duomenų prieigos protokolas, pagrįstas pagrindiniais protokolais, tokiais kaip HTTP. Jis naudoja visuotinai priimtas metodikas, tokias kaip POILSIS žiniatinklyje. Yra įvairių rūšių bibliotekų ir įrankių, kuriuos galima naudoti "OData" paslaugoms naudoti.

Šiame straipsnyje išvardijamos kelios dažnai prašomos pavyzdinės užklausos, padedančios kurti savo diegimus pagal ["Customer Insights" API](apis.md).

Turite modifikuoti užklausų pavyzdžius, kad jie veiktų tikslinėse aplinkose: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kur {instanceId} yra "Customer Insights" aplinkos, kurią norite užklausti, GUID. Operacija [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) leidžia rasti prieigą prie {InstanceId} jūsų.
- {CID}: Vieningo kliento įrašo GUID. Pavyzdys:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Kliento įrašo pirminio rakto identifikatorius duomenų šaltinis. Pavyzdys: `CNTID_1002`
- {DSname}: Eilutė su duomenų šaltinis objekto pavadinimu, kuris praryjamas "Customer Insights". Pavyzdys:`Website_contacts`.
- {SegmentName}: Eilutė su "Customer Insights" segmento išvesties objekto pavadinimu. Pavyzdys:`Male_under_40`.

## <a name="customer"></a>kliente

Šioje lentelėje yra kliento objekto užklausų pavyzdžių *rinkinys*.


|Užklausos tipas |Pavyzdžiui  | Pastaba.  |
|---------|---------|---------|
|Vieno kliento ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Alternatyvusis raktas    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Alternatyvūs raktai išlieka vieningame kliento objekte       |
|Pažymėti   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Po    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatyvusis raktas + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Paieška  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Pateikia 10 geriausių ieškos eilutės rezultatų      |
|Segmento narystė  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Grąžina iš anksto nustatytą segmentavimo objekto eilučių skaičių.      |

## <a name="unified-activity"></a>Vieninga veikla

Šioje lentelėje yra objekto UnifiedActivity *užklausų pavyzdžių* rinkinys.

|Užklausos tipas |Pavyzdžiui  | Pastaba.  |
|---------|---------|---------|
|CID veikla     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Išvardija konkretaus kliento profilio veiklas |
|Veiklos laikotarpis    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Kliento profilio veikla per tam tikrą laikotarpį       |
|Veiklos tipas    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Veikla pagal rodomą pavadinimą     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Veiklos rūšiavimas    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Veiklos rūšiavimas didėjimo tvarka arba mažėjimo tvarka       |
|Veikla išplėsta nuo segmento narystės  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Kiti pavyzdžiai

Šioje lentelėje yra kitų objektų užklausų pavyzdžių rinkinys.

|Užklausos tipas |Pavyzdžiui  | Pastaba.  |
|---------|---------|---------|
|CID priemonės    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Praturtinti CID prekių ženklai    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Praturtinti CID interesai    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Sąlyga + išplėsti     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
