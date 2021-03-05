---
title: „Customer Insights“ objekto schemos „Common Data Model“
description: Dirbkite su objektais „Common Data Model“.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269294"
---
# <a name="entity-schemas-in-common-data-model"></a>Objektų schemos „Common Data Model”

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[„Common Data Model“](https://docs.microsoft.com/common-data-model/) yra deklaratyvi specifikacija ir standartinių objektų, kurie atitinka verslo ir produktyvumo programose visuotinai naudojamas koncepcijas ir veiklas, aprašas. Šis modelis taip pat taikomas stebėjimo ir analitiniams duomenims. „Common Data Model“ teikiami tinkamai apibrėžti, moduliniai ir plečiami verslo objektai, pvz., Klientas, Verslo vienetas, Atvejis, Kontaktas, Galimas klientas, taip pat veiksmai su pardavėjais, darbuotojais ir klientais, pvz., veiklos ir aptarnavimo lygio sutartys. Kiekvienas gali sukurti ir išplėsti „Common Data Model“, kad užfiksuotų papildomas konkrečias verslo idėjas.

Šis bendrinamas duomenų modulis leidžia programų ir duomenų integruotojams paprasčiau bendradarbiauti pateikiant vieningą duomenų apibrėžimą. „Common Data Model“ yra didžiulė metaduomenų sistema su standartiniais objektais, ryšiais, hierarchijomis, ypatybėmis ir daugiau. Jis kilo iš „Dynamics 365“ programų ir yra atvirojo kodo „GitHub“ su daugiau nei 260 standartinių objektų. Didelė vidinių ir išorinių partnerių sistema prie „Common Data Model“ prisideda su pramonės šaka konkrečiai susijusiomis koncepcijomis.

Šiuo metu „Common Data Model“ įgyvendinamas keliose sistemose ir platformose, įskaitant „Power BI“ duomenų srautus ir „Azure“ duomenų tarnybas. Jį jau palaiko „Common Data Service“, „Dynamics 365“, „Power Apps“, „Power BI“ ir būsimos „Azure“ duomenų tarnybos, tiesiogiai kaupiančios vertę [„Open Data Initiative“](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>„Customer Insights” objektų schemos

Norėdami pateikti 360 laipsnių kliento vaizdą ir padaryti, kad „Customer Insights“ modeliai išplečiamumo tikslu būtų pasiekiami „Common Data Model“, publikavome šias objektų schemas:

| Objektas | Aprašas |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Veikla, atliekama vartotojo, kuris verslui teikia stebėjimo vertę. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Asmuo arba organizacija, kuri užsiima arba gali užsiimti verslo veiklomis. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | KPI apibrėžimas, išskaidytas pagal nulį arba daugiau dimensijų (pvz., mėnesiniai aktyvūs vartotojai, bendra kaina pagal klientą, vidutinė kliento įsigijimo vertė) |
|[Segmentas](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Apibrėžia narių, kuriems būdingi bendri bruožai, grupę. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Nariai, dalyvaujantys duotame segmente. |

Daugiau informacijos žr. dokumentuose apie [„Customer Insights“ objektų schemas „Common Data Model“](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Objektų peržiūra naudojant „Common Data Model“ objekto naršyklę

Galite peržiūrėti objektus [„Common Data Model“ objekto naršyklėje](https://microsoft.github.io/CDM/). Pasirinkite mygtuką **Įkelti „GitHub!“** ir eikite į **foundationCommon** > **crmCommon** > **sprendimai** > **customerInsights**, kur rasite „Customer Insights“ objektų sąrašą ir jų apibrėžimus.
> [!div class="mx-imgBorder"]
> ![CDM objektų naršyklė, rodanti CustomerActivity objektą](media/CDM-entity-navigator.png "CDM objektų naršyklė, rodanti CustomerActivity objektą")


[!INCLUDE[footer-include](../includes/footer-banner.md)]