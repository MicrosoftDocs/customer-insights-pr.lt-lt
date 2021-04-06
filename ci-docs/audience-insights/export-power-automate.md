---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft Power Automate” platformoje iš „Dynamics 365 Customer Insights”.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597935"
---
# <a name="power-automate-connector-preview"></a>„Power Automate“ jungtis (peržiūra)

Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>„Power Automate“ paleidikliai

Naudokite paleidinius debesies srautams kurti ir pasikartojančioms užduotims, pvz.: pranešimams ar išplėstiniams veiksmams, automatizuoti. 

- Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio. 
- Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.
- Paleidiklis, pasiekus segmento ribinę reikšmę. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Paleidiklis, pasiekus verslo mato ribinę reikšmę. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių,...) yra pabaigtas.
- Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.

[Paleidiklių konfigūravimas „Power Automate“](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>„Power Automate“ veiksmai
„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius. Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Kurti Power Automate srautą

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.

1. Plytelėje **„Power Automate”** pasirinkite **Nustatyti**.

1. Atsidaro „Power Automate“ jungtis programoje „Customer Insights“. **Prisijunkite** prie „Power Automate“.

1. Pasirinkite vieną iš galimų paleidiklių ir įtraukite daugiau veiksmų į naują srautą. Daugiau informacijos [žr. Debesies srauto kūrimas Power Automate](/power-automate/get-started-logic-flow).

Pavyzdžiai, kaip naudoti srautus: 
- Jei nepavyksta atnaujinti duomenų šaltinio kanale, praneškite Microsoft Teams kanale. 
- Duomenų savininkams nusiuntus ribinę segmento ribinę vertę, el. laišką siųskite duomenų savininkams.



[!INCLUDE[footer-include](../includes/footer-banner.md)]