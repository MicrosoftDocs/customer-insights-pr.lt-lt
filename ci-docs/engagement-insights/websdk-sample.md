---
title: Žiniatinklio SDK pavyzdžio paleidimas
description: Sužinokite, kaip pritaikyti asmeniniams poreikiams ir paleisti žiniatinklio SDK pavyzdį.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225341"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Paleiskite žiniatinklio SDK „Dynamics 365 Customer Insights“ pavyzdį, kad būtų galima naudoti įtraukimo įžvalgų galimybes

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Įtraukimo įžvalgų galimybių žiniatinklio SDK biblioteka yra „JavaScript" biblioteka su kodo pavyzdžiu, kurį galite naudoti svetainėje.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Įdiegti [„Visual Studio“ kodą ](https://code.visualstudio.com/).
- [Įdiekite „Live Server" plėtinį](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) esantį „Visual Studio“ kode ir susipažinkite su tai, kaip paleisti „Live Server".
- Turite turėti įtraukimo [įžvalgų darbo sritį](create-workspace.md).

## <a name="run-sample"></a>Vykdyti pavyzdį

1. [Atsisiųskite žiniatinklio SDK pavyzdį](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Išarchyvuokite suspaustą failą `ei_websdk_sample.zip`.

1. Atidarykite išspaustą aplanką „Visual Studio“ kodą.

1. Eikite į savo darbo srities įtraukimo įžvalgų portalą. Pasirinkite **Administravimo** > **darbo sritis**, tada – **Diegimo vadovas**. Vykdykite pirmą parinktį ir pasirinkite **Kopijuoti kodą** kad nukopijuotumėte „JavaScript" kodo fragmentą.

1. Į failą `ei_websdk_sample.html` įklijuokite kodo fragmentas, kurį ką tik nukopijavote po šia eilute:

   - < – ĮKLIJUOKITE „JAVASCRIPT" KODO FRAGMENTAS IŠ ĮTRAUKIMO ĮŽVALGŲ PORTALO ČIA PO ŠIA EILUTE -->

1. Būsenos `ei_websdk_sample.html` juostoje pasirinkdami „Live Server“ „Visual Studio“ kodą atidarykite failą **„Go Live“** iš būsenos juostos.

1. Atidarius puslapį, rodinio įvykis turi būti automatiškai išsiųstas. Spustelėjus bet kurį puslapio mygtuką, veiksmas bus siunčiamas. Mygtukas **Sekti įvykius** taip pat siųs pasirinktinius įvykius. Jei pažymėsite mygtuką **Eiti į „Bing"** prieš pereidami prie „Bing" svetainės, siųsite veiksmo įvykį.

1. Peržiūrėkite įvykius, kurie vyksta pereidami prie savo darbo srities. Ši darbo sritis susieta su prarijimo raktu, įvestu 4 veiksme.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
