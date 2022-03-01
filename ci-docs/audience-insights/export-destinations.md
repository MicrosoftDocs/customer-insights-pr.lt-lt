---
title: Eksportavimo paskirties vietos
description: Eksportuoti duomenis ir tvarkyti eksportavimo paskirties vietas.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643873"
---
# <a name="export-destinations-preview"></a>Eksportavimo paskirties vietos (peržiūra)

Puslapyje **Eksportavimo paskirties vietos** rodomos visos vietos, į kurias nustatėte eksportuoti duomenis. Taip pat galite įtraukti naujų eksportavimo paskirties vietų. Taip pat, jis rodo šiuo metu galimas eksportavimo parinktis. Gaukite trumpą apžvalgą, aprašą ir sužinokite, ką galite daryti su kiekviena išplečiamumo parinktimi. Eksportuokite vieninguosius profilius, priemones ir segmentus į palaikomas programas, tinkamas jūsų verslui.

Eikite į **Administratorius** > **Eksportuoti paskirties vietas** , kad rastumėte toliau nurodytas išplečiamumo parinktis.

- [„Dynamics 365“ klientų kortelių priedai](customer-card-add-in.md)
- [„Facebook“ reklamos tvarkytuvo jungtis](export-facebook.md)
- [„Power Automate“ jungtis](export-power-automate.md)
- [„Power Apps“ jungtis](export-power-apps.md)
- [„Power BI“ jungtis](export-power-bi.md)
- [„DotDigital“](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [„Dynamics 365 Marketing“](export-dynamics365-marketing.md)
- [„Azure“ didelių dvejetainių objektų saugykla](export-azure-blob-storage.md)
- [„LiveRamp&reg;“ jungtis](export-liveramp.md)
- [„Microsoft Teams“ robotas](export-teams-bot.md)
- [„Mailchimp“](export-mailchimp.md)
- [„Customer Insights“ API](apis.md)

## <a name="add-a-new-export-destination"></a>Naujos eksportavimo vietos įtraukimas

Norėdami įtraukti eksportavimo paskirties vietas, turite [administratoriaus teises](permissions.md). Jei eksportuojate į „Microsoft“ tarnybas, daroma prielaida, kad abi tarnybos yra toje pačioje organizacijoje.

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Įjunkite skirtuką **Mano eksportavimo paskirties vietos**.

1. Pasirinkite **Įtraukti paskirties vietą**, kad sukurtumėte naują eksportavimo paskirties vietą.

1. Srityje **Įtraukti paskirties vietą** išplečiamajame sąraše pasirinkite eksportavimo paskirties vietos **Tipą**.

1. Nurodykite reikiamą informaciją ir pasirinkite **Toliau**, kad sukurtumėte eksportavimo paskirties vietą.

Taip pat galite pasirinkti **Nustatyti** plytelėje, esančioje skirtuke **Atrasti**.

## <a name="view-export-destinations"></a>Eksportavimo paskirties vietos peržiūra

Sukūręs eksportavimo paskirties vietas jas rasite skirtuke **Mano eksportavimo paskirties vietos** esančioje lentelėje. Šioje lentelėje yra trys stulpeliai:

- **Rodomas pavadinimas**: pavadinimas, įvestas kuriant paskirties vietą.
- **Tipas**: eksportavimo paskirties vietos tipas, kurį nustatėte kurdami paskirties vietą.
- **Sukurta**: data, kada buvo sukurta paskirties vieta.

## <a name="edit-an-export-destination"></a>Eksportavimo paskirties vietos redagavimas

1. Pažymėkite eksportavimo paskirties vietos, kurią norite redaguoti, vertikalią elipsę.

   > [!div class="mx-imgBorder"]
   > ![Vertikali elipsė](media/export-destinations-page-ellipsis.png "Vertikali elipsė")

1. Išplečiamajame meniu pasirinkite **Redaguoti**.

1. Pakeiskite reikšmes, kurias reikia atnaujinti, ir pasirinkite **Įrašyti**.

## <a name="export-data-on-demand"></a>Duomenų eksportavimas pareikalavus

Sukonfigūravus eksporto paskirties vietos jungtį eksportavimas bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

Jei norite eksportuoti duomenis nelaukdami suplanuoto naujinimo, eikite į skirtuką **Mano eksportavimo paskirties vietos** dalyje **Administratorius** > **Eksportavimo paskirties vietos**.

> [!div class="mx-imgBorder"]
> ![Vertikali elipsė](media/export-destinations-page-ellipsis.png "Vertikali elipsė")

- Virš sąrašo pasirinkite **Eksportuoti**, kad tuo pačiu metu būtų paleistas eksportavimas į visas eksportavimo paskirties vietas.
- Pasirinkite elipsę (...) po sąrašo elementu, tada pasirinkite parinktį **Eksportuoti**, kad būtų paleistas eksportavimas į vieną eksportavimo paskirties vietą.

## <a name="remove-an-export-destination"></a>Eksportavimo paskirties vietos pašalinimas

Norėdami pašalinti eksportavimo paskirties vietą, pradėkite nuo pagrindinio puslapio **Eksportavimo paskirties vietos**.

1. Pažymėkite norimos pašalinti eksportavimo paskirties vietos vertikalią elipsę.

   > [!div class="mx-imgBorder"]
   > ![Vertikali elipsė](media/export-destinations-page-ellipsis.png "Vertikali elipsė")

2. Išskleidžiamajame meniu pasirinkite **Pašalinti**.

3. Patvirtinkite pašalinimą pasirinkdami **Pašalinti** patvirtinimo ekrane.
