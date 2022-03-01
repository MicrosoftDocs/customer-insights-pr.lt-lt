---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft“ programoje „Power Automate“ iš „Dynamics 365 Customer Insights“.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406377"
---
# <a name="power-automate-connector-preview"></a>„Power Automate“ jungtis (peržiūra)

Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>„Power Automate“ paleidikliai

Galite naudoti įvairius paleidiklius, leidžiančius kurti srautus, automatizuojančius pasikartojančias užduotis, pvz., pranešimus ar sudėtingesnius veiksmus. 

- Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio. 
- Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.
- Paleidiklis, pasiekus segmento ribinę reikšmę. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Paleidiklis, pasiekus verslo mato ribinę reikšmę. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių,...) yra pabaigtas.
- Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.

[Paleidiklių konfigūravimas „Power Automate“](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>„Power Automate“ veiksmai
„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius. Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Sukurkite „Power Automate“ eigą publikso įžvalgose

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Puslapyje **Sistema** pasirinkite skirtuką **Būsena**.

1. Skyriuje **Duomenų šaltiniai** pasirinkite **Srautai**, o išplečiamajame sąraše pasirinkite **Kurti srautą**.
   > [!div class="mx-imgBorder"]
   > ![„Power Automate“ jungtis, rodanti srauto kūrimo veiksmą](media/power-automate-connector-create-flow.png "„Power Automate“ jungtis, rodanti srauto kūrimo veiksmą")

1. Programoje „Power Automate“ pasirinkite vieną iš galimų paleidiklių, kad sukurtumėte pageidaujamą srautą. Jei kuriate pirmąjį srautą, pirmiausia turite patvirtinti savo tapatybę su „Power Automate“ jungtimi.
