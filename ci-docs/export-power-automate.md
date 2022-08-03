---
title: Power Automate jungtis (peržiūra) | "Microsoft" dokumentai
description: Kurkite srautus „Microsoft Power Automate” platformoje iš „Dynamics 365 Customer Insights”.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196128"
---
# <a name="power-automate-connector-preview"></a>„Power Automate“ jungtis (peržiūra)

Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Microsoft Power Automate“](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Žinomi apribojimai

- Ne daugiau kaip 100 skambučių per 60 sekundžių. Naudokite [parametrą](/connectors/customerinsights/#get-items-from-an-entity) $skip, kad kelis kartus iškviestumėte API galinį punktą.

## <a name="power-automate-triggers"></a>„Power Automate“ paleidikliai

Naudokite paleidinius debesies srautams kurti ir pasikartojančioms užduotims, pvz.: pranešimams ar išplėstiniams veiksmams, automatizuoti. Naudokite paleidiklius, kai:

- Nepavyksta atnaujinti duomenų šaltinis.
- Duomenų šaltinis atnaujinimas pavyksta.
- Segmente peržengiama riba. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Verslo priemonėje peržengiama riba. Palaikomi tik verslo matai be dimensijos. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Baigtas visas suplanuotas atnaujinimas. Šis paleidiklis neveikia rankiniu būdu pradėtiems atnaujinimams.
- Baigiamas suvienijimo proceso atnaujinimas.

[Paleidiklių konfigūravimas „Power Automate“.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>„Power Automate“ veiksmai

„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius. Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Kurti Power Automate srautą

1. Eikite į **Administravimas** > **Ryšiai**.

1. Plytelėje **„Power Automate”** pasirinkite **Nustatyti**.

1. Atsidaro „Power Automate“ jungtis programoje „Customer Insights“. **Prisijunkite** prie „Power Automate“.

1. Pasirinkite vieną iš galimų paleidiklių ir įtraukite daugiau veiksmų į naują srautą. Daugiau informacijos [žr. Debesies srauto kūrimas Power Automate](/power-automate/get-started-logic-flow).

Pavyzdžiai, kaip naudoti srautus: 
- Jei nepavyksta atnaujinti duomenų šaltinio kanale, praneškite Microsoft Teams kanale. 
- Duomenų savininkams nusiuntus ribinę segmento ribinę vertę, el. laišką siųskite duomenų savininkams.

[!INCLUDE [footer-include](includes/footer-banner.md)]
