---
title: Objektų schemos „Common Data Model”
description: Dirbkite su objektais „Common Data Model“.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: cc65314f1b083694b60ac0a2625bea906be7272b
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183503"
---
# <a name="entity-schemas-in-common-data-model"></a>Objektų schemos „Common Data Model”

[„Common Data Model“](/common-data-model/) yra deklaratyvi specifikacija ir standartinių objektų, kurie atitinka verslo ir produktyvumo programose visuotinai naudojamas koncepcijas ir veiklas, aprašas. Šis modelis taip pat taikomas stebėjimo ir analitiniams duomenims. „Common Data Model“ teikiami tinkamai apibrėžti, moduliniai ir plečiami verslo objektai, pvz., Klientas, Verslo vienetas, Atvejis, Kontaktas, Galimas klientas, taip pat veiksmai su pardavėjais, darbuotojais ir klientais, pvz., veiklos ir aptarnavimo lygio sutartys. Kiekvienas gali sukurti ir išplėsti „Common Data Model“, kad užfiksuotų papildomas konkrečias verslo idėjas.

Šis bendrinamas duomenų modulis leidžia programų ir duomenų integruotojams paprasčiau bendradarbiauti pateikiant vieningą duomenų apibrėžimą. „Common Data Model“ yra didžiulė metaduomenų sistema su standartiniais objektais, ryšiais, hierarchijomis, ypatybėmis ir daugiau. Jis kilo iš „Dynamics 365“ programų ir yra atvirojo kodo „GitHub“ su daugiau nei 260 standartinių objektų. Didelė vidinių ir išorinių partnerių sistema prie „Common Data Model“ prisideda su pramonės šaka konkrečiai susijusiomis koncepcijomis.

Daug sistemų ir platformų šiandien įdiegia „Common Data Model“, įskaitant „Power BI“ duomenų srautus ir „Azure“ duomenų tarnybas. Tai jau palaikoma „Microsoft Dataverse”, „Dynamics 365”, „Power Apps”, „Power BI” ir būsimose „Azure” duomenų tarnybose, tiesiogiai kaupiant duomenis [Atvirų duomenų iniciatyvai](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>„Customer Insights” objektų schemos

Norėdami pateikti 360 laipsnių kliento vaizdą ir padaryti, kad „Customer Insights“ modeliai išplečiamumo tikslu būtų pasiekiami „Common Data Model“, publikavome šias objektų schemas:

| Objektas | Aprašas |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Veikla, atliekama vartotojo, kuris verslui teikia stebėjimo vertę. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Asmuo arba organizacija, kuri užsiima arba gali užsiimti verslo veiklomis. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | KPI apibrėžimas, išskaidytas pagal nulį arba daugiau dimensijų (pvz., mėnesiniai aktyvūs vartotojai, bendra kaina pagal klientą, vidutinė kliento įsigijimo vertė) |
|[Segmentas](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Apibrėžia narių, kuriems būdingi bendri bruožai, grupę. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Nariai, dalyvaujantys duotame segmente. |

Daugiau informacijos žr. dokumentuose apie [„Customer Insights“ objektų schemas „Common Data Model“](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Objektų peržiūra naudojant „Common Data Model“ objekto naršyklę

Peržiūrėkite objektus ["Common Data Model" objektų žvalgyklėje](https://microsoft.github.io/CDM/). Norėdami gauti "Customer Insights" objektų ir jų aprašų sąrašą, pasirinkite objektą iš skyriaus "Insights Application".

:::image type="content" source="media/CDM-entity-navigator.png" alt-text="CDM objektų naršyklė, rodanti „CustomerActivity” objektą.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
