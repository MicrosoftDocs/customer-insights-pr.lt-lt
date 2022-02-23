---
title: Paslaugų apribojimai Dynamics 365 Customer Insights
description: Supraskite apribojimus ir suvaržymus.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791991"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>„Customer Insights“ galimybių aptarnavimo apribojimai

Straipsnis aprašo inkorporuotus apribojimus „Customer Insights“ paslaugoms, kurios yra sukurtos siekiant užtikrinti paslaugų patikimumą ir stabilumą. Bet kokios pakeitimų užklausos gali būti pateiktos per [Idėjų forumą](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Auditorijos įžvalgos

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Paslaugų apribojimai Dynamics 365 Customer Insights auditorijos įžvalgų galimybėse

| Plotas  | Apribojimai  | Pastabos |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentai, priemonės ir prognozės | 300  | Bendras [segmentų](audience-insights/segments.md), [matų ir prognozių skaičius](audience-insights/measures.md) kartu negali viršyti [...](audience-insights/predictions.md) 300.  |
| Ryšiai | 20 gylio lygių santykiuose objektų keliuose. | Kuriant [segmentus](audience-insights/segments.md) ar [priemones](audience-insights/measures.md) naudojant kūrėjo sąsają, objekto keliai gali turėti iki 20 ryšių perėjimų tarp pradinio ir tikslinio objekto.  |


## <a name="engagement-insights"></a>Įtraukimo įžvalgos

### <a name="workspace-and-event-quotas"></a>Darbo srities ir įvykių kvotos

"Engagement" įžvalgos – tai labai keičiamo mastelio programa, kuri gali palaikyti milijonai įvykių per antrą. Viešosios peržiūros metu įvykiai turi ribinę apimtį. Taip pat ribojamas organizacijos darbo sričių skaičius.

### <a name="engagement-insights-limits"></a>Įtraukimo įžvalgos (apribojimai)

- Maksimalus įvykio apimtis darbo srityje = 100 įvykių per antrą

- Maksimalus darbo sričių skaičius organizacijai = 100

Kai įvykiai viršija ribinę verčių ribą, ataskaitose, pagrįstose tais įvykiais, gali būti prarasti duomenys. Galite [susisiekti su palaikymo tarnyba](https://go.microsoft.com/fwlink/?linkid=2145734), jei norite pateikti užklausą dėl garso padidinimo prieš viršydami apribojimus. Dirbsime su jumis, kad nustatytumėte, ar reikia padidinti kiekį ir palaikyti užklausą.


[!INCLUDE[footer-include](includes/footer-banner.md)]
