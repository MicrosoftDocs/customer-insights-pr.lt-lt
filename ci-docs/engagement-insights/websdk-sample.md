---
title: Žiniatinklio SDK pavyzdžio paleidimas
description: Sužinokite, kaip pritaikyti asmeniniams poreikiams ir paleisti žiniatinklio SDK pavyzdį.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036613"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Paleiskite žiniatinklio SDK „Dynamics 365 Customer Insights“ pavyzdį, kad būtų galima naudoti įtraukimo įžvalgų galimybes

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Įtraukimo įžvalgų galimybių žiniatinklio SDK biblioteka yra „JavaScript" biblioteka su kodo pavyzdžiu, kurį galite naudoti svetainėje.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Įdiegti [„Visual Studio“ kodą ](https://code.visualstudio.com/).
- [Įdiekite „Live Server" plėtinį](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) esantį „Visual Studio“ kode ir susipažinkite su tai, kaip paleisti „Live Server".
- Turite turėti [nurijimo raktą](instrument-website.md).

## <a name="run-sample"></a>Vykdyti pavyzdį

1. [Atsisiųskite žiniatinklio SDK pavyzdį](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Išarchyvuokite suspaustą failą `ei_websdk_sample.zip`.

1. Atidarykite išspaustą aplanką „Visual Studio“ kodą.

1. Faile `ei_websdk_sample.html` pakeiskite eilutę „INGESTION_KEY” su jūsų prarijimo raktu iš įsitraukimo įžvalgų galimybių portalo ir eilutę „PAVADINIMAS“ su bendru pavadinimu, kuriuo norite pradėti SDK. Įsitikinkite, kad keičiate visus atvejus.

1. Būsenos `ei_websdk_sample.html` juostoje pasirinkdami „Live Server“ „Visual Studio“ kodą atidarykite failą **„Go Live“** iš būsenos juostos.

1. Atidarius puslapį, rodinio įvykis turi būti automatiškai išsiųstas. Spustelėjus bet kurį puslapio mygtuką, veiksmas bus siunčiamas. Mygtukas **Sekti įvykius** taip pat siųs pasirinktinius įvykius. Jei pažymėsite mygtuką **Eiti į „Bing"** prieš pereidami prie „Bing" svetainės, siųsite veiksmo įvykį.

1. Peržiūrėkite įvykius, kurie vyksta pereidami prie savo darbo srities. Ši darbo sritis susieta su prarijimo raktu, įvestu 4 veiksme.


[!INCLUDE[footer-include](../includes/footer-banner.md)]