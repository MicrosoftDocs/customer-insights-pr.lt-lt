---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft Power Automate” platformoje iš „Dynamics 365 Customer Insights”.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dd90ef4576246b49d4a9c74005196ee9813a6744
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455917"
---
# <a name="power-automate-connector-preview"></a>„Power Automate“ jungtis (peržiūra)

Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Žinomi apribojimai

- Galite atlikti ne daugiau kaip 100 skambučių per 60 sekundžių. Api galinį punktą galite skambinti kelis kartus naudodami parametrą $skip. [Sužinokite daugiau apie parametrą $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>„Power Automate“ paleidikliai

Naudokite paleidinius debesies srautams kurti ir pasikartojančioms užduotims, pvz.: pranešimams ar išplėstiniams veiksmams, automatizuoti. 

- Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio. 
- Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.
- Paleidiklis, pasiekus segmento ribinę reikšmę. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Paleidiklis, pasiekus verslo mato ribinę reikšmę. Palaikomi tik verslo matai be dimensijos. Paleidiklis taikomas tik ribinės vertės viršijimui.
- Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių, ...) yra pabaigtas.
- Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.

[Paleidiklių konfigūravimas „Power Automate“.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

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
