---
title: Duomenų eksportavimas iš „Customer Insights“
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016624"
---
# <a name="exports-preview-overview"></a>Eksportavimų (peržiūros versija) apžvalga

Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai. Eksportavimuose su įvairiomis programomis bendrinami konkretūs duomenys. Jie gali apimti klientų profilius arba objektus, schemas ir žymėjimo duomenis. Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md).

Eikite į **Duomenys** > **Eksportavimai**, kad peržiūrėtumėte eksportavimų puslapį. Visi naudotojo vaidmenys turi prieigą sukonfigūruotiems eksportavimams peržiūrėti. Naudokite komandų juostoje esantį paieškos laukelį eksportavimams rasti pagal pavadinimą, ryšio pavadinimą arba ryšio tipą.

## <a name="set-up-a-new-export"></a>Naujo eksportavimo sąranka

Jei norite nustatyti ar redaguoti eksportavimą, turite turėti prieinamų ryšių. Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):
- Administratoriai turi prieigą prie visų ryšių. Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.
- Bendradarbiai gali turėti prieigą prie konkrečių ryšių. Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Žiūrovai gali tik peržiūrėti esamus eksportavimus, tačiau ne juos kurti.

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**, jei norite sukurti naują eksportavimo paskirties vietą.

1. Srityje **Sąrankos eksportavimas** pasirinkite, kurį ryšį naudoti. [Ryšius](connections.md) tvarko administratoriai. 

1. Jei norite sukurti eksportavimą, pateikite reikiamus duomenis ir pasirinkite **Įrašyti**.

### <a name="edit-an-export"></a>Eksportavimo redagavimas

1. Pažymėkite eksportavimo paskirties vietos, kurią norite redaguoti, vertikalią elipsę.

1. Išskleidžiamajame meniu pasirinkite **Redaguoti**.

1. Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.

## <a name="view-exports-and-export-details"></a>Eksportavimo ir eksportavimo duomenų peržiūra

Sukūrus eksportavimo paskirties vietas jų sąrašas pateikiamas pasirinkus **Duomenys** > **Eksportavimai**. Visi naudotojai mato, kurie duomenys bendrinami ir kokia jų naujausia būsena.

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Naudotojai, neturintys redagavimo teisių, pasirenka **Peržiūrėti**, o ne **Redaguoti**. Peržiūrėkite eksportavimo duomenis.

1. Šioje šoninėje srityje rodoma šio eksportavimo sąranka. Jei neturite redagavimo teisių, reikšmių keisti negalite. Jei norite grįžti prie eksportavimų puslapio, pasirinkite **Uždaryti**.

## <a name="run-exports-on-demand"></a>Pageidaujamų eksportavimų paleidimas

Sukonfigūravus eksportavimą jis bus vykdomas kiekvieno [planinio atnaujinimo metu](system.md#schedule-tab), kol yra veikiantis ryšys.

Jei duomenis norite eksportuoti nelaukdami planuojamo atnaujinimo, eikite į **Duomenys** > **Eksportavimai**. Turite du pasirinkimus:

- Jei norite peržiūrėti visus eksportavimus, komandų juostoje pasirinkite **Vykdyti viską**. 
- Jei norite vykdyti vieną eksportavimą, sąrašo elemente pasirinkite elipsę (...) ir pasirinkite **Vykdyti**.

## <a name="remove-an-export"></a>Eksportavimo pašalinimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pažymėkite norimos pašalinti eksportavimo vertikalią elipsę.

1. Išskleidžiamajame meniu pasirinkite **Pašalinti**.

1. Patvirtinkite pašalinimą pasirinkdami **Pašalinti** patvirtinimo ekrane.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
