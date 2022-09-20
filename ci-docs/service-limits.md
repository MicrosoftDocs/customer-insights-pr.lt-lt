---
title: "\"Customer Insights\" paslaugų apribojimai"
description: Supraskite "Customer Insights SaaS" paslaugos apribojimus ir apribojimus.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463229"
---
# <a name="service-limits-in-customer-insights"></a>"Customer Insights" paslaugų apribojimai

 "Customer Insights" turi įtaisytąsias ribas, skirtas užtikrinti paslaugos patikimumą ir stabilumą. Bet kokios pakeitimų užklausos gali būti pateiktos per [Idėjų forumą](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Plotas  | Apribojimai  | Pastabos |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentai, matai ir prognozės | 300  | Bendras segmentų [,](segments.md) matų [ir](measures.md) [prognozių](predictions-overview.md) skaičius kartu negali viršyti 300.  |
| Ryšiai | 20 gylio lygių santykiuose objektų keliuose. | Kuriant [segmentus](segments.md) ar [priemones](measures.md) naudojant kūrėjo sąsają, objekto keliai gali turėti iki 20 ryšių perėjimų tarp pradinio ir tikslinio objekto.  |
|Duomenų įsisavinimas| Tuo pačiu metu atliekami duomenų šaltinių vertinimai Power Query yra riboti. | "Customer Insights" turi tuos pačius [atnaujinimo apribojimus, kaip ir "Dataflows" PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Sąžiningas darbų planavimas

"Customer Insights" yra SaaS paslauga, kuri naudoja bendrinamus "Azure" išteklius. Klientai paprastai turi kintamo intensyvumo darbo krūvius ir skirtingus tvarkaraščius. Siekdami užtikrinti sąžiningą prieigą prie pagrindinių išteklių, užtikriname, kad sistemos procesai būtų vykdomi sąžiningai. Sistemos procesų pavyzdžiai yra užduotys, susijusios su duomenų suvienijimu, segmentų naujinimais arba matų skaičiavimu. Sąžiningas planavimas apsaugo jus nuo išteklių eiliškumo, jei yra prašomų darbų šuolis. Tuo pačiu metu "Customer Insights" negarantuoja, kad visos užduotys, kurias rikiuojate į eilę, bus apdorojamos lygiagrečiai.

[!INCLUDE [footer-include](includes/footer-banner.md)]
