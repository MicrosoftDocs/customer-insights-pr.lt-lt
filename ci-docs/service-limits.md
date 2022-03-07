---
title: „Dynamics 365 Customer Insights“ aptarnavimo apribojimai
description: Supraskite apribojimus ir suvaržymus.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483689"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>„Customer Insights“ galimybių aptarnavimo apribojimai

Straipsnis aprašo inkorporuotus apribojimus „Customer Insights“ paslaugoms, kurios yra sukurtos siekiant užtikrinti paslaugų patikimumą ir stabilumą. Bet kokios pakeitimų užklausos gali būti pateiktos per [Idėjų forumą](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Auditorijos įžvalgos

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Paslaugų limitai „Dynamics 365 Customer Insights“ publikos įžvalgų pajėgume

| Plotas  | Apribojimai  | Pastabos |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentai ir priemonės | 100 segmentų ar priemonių. | Bendras aktyvių [segmentų](audience-insights/segments.md) ir [priemonių](audience-insights/measures.md) skaičius bendrai negali viršyti 100.  |
| Ryšiai | 20 gylio lygių santykiuose objektų keliuose. | Kuriant [segmentus](audience-insights/segments.md) ar [priemones](audience-insights/measures.md) naudojant kūrėjo sąsają, objekto keliai gali turėti iki 20 ryšių perėjimų tarp pradinio ir tikslinio objekto.  |


## <a name="engagement-insights"></a>Įtraukimo įžvalgos

### <a name="workspace-and-event-quotas"></a>Darbo srities ir įvykių kvotos

"Engagement" įžvalgos – tai labai keičiamo mastelio programa, kuri gali palaikyti milijonai įvykių per antrą. Viešosios peržiūros metu įvykiai turi ribinę apimtį. Taip pat ribojamas organizacijos darbo sričių skaičius.

### <a name="engagement-insights-limits"></a>Įtraukimo įžvalgos (apribojimai)

- Maksimalus įvykio apimtis darbo srityje = 100 įvykių per antrą

- Maksimalus darbo sričių skaičius organizacijai = 100

Kai įvykiai viršija ribinę verčių ribą, ataskaitose, pagrįstose tais įvykiais, gali būti prarasti duomenys. Galite [susisiekti su palaikymo tarnyba](https://go.microsoft.com/fwlink/?linkid=2145734), jei norite pateikti užklausą dėl garso padidinimo prieš viršydami apribojimus. Dirbsime su jumis, kad nustatytumėte, ar reikia padidinti kiekį ir palaikyti užklausą.


[!INCLUDE[footer-include](includes/footer-banner.md)]