---
title: Aptarnavimo apribojimai "Customer Insights"
description: Suprasti "Customer Insights SaaS" tarnybos apribojimus ir apribojimus.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940678"
---
# <a name="service-limits-in-customer-insights"></a>Aptarnavimo apribojimai "Customer Insights"

Straipsnis aprašo inkorporuotus apribojimus „Customer Insights“ paslaugoms, kurios yra sukurtos siekiant užtikrinti paslaugų patikimumą ir stabilumą. Bet kokios pakeitimų užklausos gali būti pateiktos per [Idėjų forumą](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Plotas  | Apribojimai  | Pastabos |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentai, priemonės ir prognozės | 300  | Bendras segmentų, [matų](segments.md)[ir](measures.md) [prognozių](predictions.md) skaičius kartu negali viršyti 300.  |
| Ryšiai | 20 gylio lygių santykiuose objektų keliuose. | Kuriant [segmentus](segments.md) ar [priemones](measures.md) naudojant kūrėjo sąsają, objekto keliai gali turėti iki 20 ryšių perėjimų tarp pradinio ir tikslinio objekto.  |

## <a name="fair-scheduling-of-jobs"></a>Sąžiningas užduočių planavimas

"Customer Insights" yra "SaaS" paslauga, naudojanti bendrinamus "Azure" išteklius. Klientai paprastai turi kintamo intensyvumo darbo krūvius ir skirtingais tvarkaraščiais. Siekdami užtikrinti sąžiningą prieigą prie pagrindinių išteklių, užtikriname, kad sistemos procesai būtų vykdomi sąžiningai. Sistemos procesų pavyzdžiai yra užduotys, susijusios su duomenų suvienijimu, segmentų naujinimais arba matavimo skaičiavimu. Sąžiningas planavimas apsaugo jus nuo eilių dėl išteklių, jei yra prašomų užduočių šuolis. Tuo pačiu metu "Customer Insights" negarantuoja, kad visos užduotys, kurias laukiate eilėje, bus apdorojamos lygiagrečiai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
