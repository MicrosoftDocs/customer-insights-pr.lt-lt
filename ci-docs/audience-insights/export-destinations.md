---
title: Duomenų eksportavimas iš „Customer Insights“
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253050"
---
# <a name="exports-preview-overview"></a>Eksportavimų (peržiūros versija) apžvalga

Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai. Eksportavimuose su įvairiomis programomis bendrinami konkretūs duomenys. Jie gali apimti klientų profilius arba objektus, schemas ir žymėjimo duomenis. Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md).

Eikite į **Duomenys** > **Eksportavimai**, kad peržiūrėtumėte eksportavimų puslapį. Visi naudotojo vaidmenys turi prieigą sukonfigūruotiems eksportavimams peržiūrėti. Naudokite komandų juostoje esantį paieškos laukelį eksportavimams rasti pagal pavadinimą, ryšio pavadinimą arba ryšio tipą.

## <a name="set-up-a-new-export"></a>Naujo eksportavimo sąranka

Jei norite nustatyti ar redaguoti eksportavimą, turite turėti prieinamų ryšių. Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):
- Administratoriai turi prieigą prie visų ryšių. Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.
- Bendradarbiai gali turėti prieigą prie konkrečių ryšių. Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius. Eksportavimų sąraše pateikiama, ar bendraautoriai gali redaguoti, ar tik peržiūrėti eksportavimą **Jūsų teisių** stulpelyje. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Žiūrovai gali tik peržiūrėti esamus eksportavimus, tačiau ne juos kurti.

### <a name="define-a-new-export"></a>Naujo eksportavimo apibrėžimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą** naujo eksportavimo sukūrimui.

1. Srityje **Sąrankos eksportavimas** pasirinkite, kurį ryšį naudoti. [Ryšius](connections.md) tvarko administratoriai. 

1. Jei norite sukurti eksportavimą, pateikite reikiamus duomenis ir pasirinkite **Įrašyti**.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Apibrėžti naują eksportavimą, pagrįstą esamu eksportavimu

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Eksportavimų sąraše pasirinkite eksportavimą, kurio dublikatą norite sukurti.

1. Komandų juostoje pasirinkite **Kurti dublikatą**, kad atidarytumėte sritį **Nustatyti eksportavimą** su išsamia pasirinkto eksportavimo informacija.

1. Peržiūrėkite ir pritaikykite eksportavimą bei pasirinkite **Įrašyti**, kad sukurtumėte naują eksportavimą.

### <a name="edit-an-export"></a>Eksportavimo redagavimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Eksportavimų sąraše pasirinkite eksportavimą, kurį norite redaguoti.

1. Pasirinkite **Redaguoti** komandų juostoje.

1. Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.

## <a name="view-exports-and-export-details"></a>Eksportavimų ir išsamios eksportavimo informacijos peržiūra

Sukurtų eksportavimo paskirties vietų sąrašas yra pateikiamas **Duomenys** > **Eksportavimai**. Visi naudotojai mato, kurie duomenys bendrinami ir kokia jų naujausia būsena.

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Naudotojai, neturintys redagavimo teisių, pasirenka **Peržiūrėti**, o ne **Redaguoti**. Peržiūrėkite eksportavimo duomenis.

1. Šoninėje srityje rodoma eksportavimo konfigūracija. Jei neturite redagavimo teisių, reikšmių keisti negalite. Jei norite grįžti prie eksportavimų puslapio, pasirinkite **Uždaryti**.

## <a name="schedule-and-run-exports"></a>Eksportavimų planavimas ir vykdymas

Kiekvienas jūsų konfigūruojamas eksportavimas turi atnaujinimo grafiką. Atnaujinimo metu sistema ieško naujų arba atnaujintų duomenų, kuriuos reikia įtraukti į eksportavimą. Pagal numatytuosius nustatymus, eksportavimai yra vykdomi kaip kiekvieno [suplanuoto sistemos atnaujinimo](system.md#schedule-tab) dalis. Galite tinkinti atnaujinimo grafiką arba išjungti jį, kad eksportavimus vykdytumėte rankiniu būdu.

Eksportavimo grafikai priklauso nuo jūsų aplinkos būsenos. Jei progrese yra [priklausomybių](system.md#refresh-policies) atnaujinimų, kai turėtų prasidėti suplanuotas eksportavimas, sistema pirmiausia užbaigs priklausomybes ir tada vykdys eksportavimą. Galite matyti, kada eksportavimas paskutinį kartą buvo atnaujintas, stulpelyje **Atnaujinta**.

### <a name="schedule-exports"></a>Eksportavimų grafikas

Vienu metu galite apibrėžti pasirinktinius atskirų arba kelių eksportavimų atnaujinimo grafikus. Šiuo metu apibrėžtas grafikas pateikiamas eksportavimo sąrašo stulpelyje **Grafikas**. Teisė keisti grafiką yra tokia pat, kaip ir [redaguojant ir apibrėžiant eksportavimus](export-destinations.md#set-up-a-new-export). 

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite norimą suplanuoti eksportavimą.

1. Pasirinkite **Grafikas** komandų juostoje.

1. Srityje **Eksportavimo grafikas** nustatykite **Vykdymo grafiką** į **Įjungta**, kad eksportavimas būtų vykdomas automatiškai. Nustatykite į **Išjungta**, kad jį atnaujintumėte rankiniu būdu.

1. Automatiškai atnaujintiems eksportavimams pasirinkite **Pasikartojimo** reikšmę ir nurodykite jos išsamią informaciją. Nustatytas laikas taikomas visiems pasikartojimo atvejams. Tai yra laikas, kai eksportavimas turėtų pradėti atsinaujinti.

1. Taikykite ir suaktyvinkite pakeitimus pažymėdami **Įrašyti**.

Redaguodami kelių eksportavimų grafiką, turite pasirinkti skiltyje **Išsaugoti arba perrašyti grafikus**:
- **Išlaikyti atskirus grafikus**: Išlaiko anksčiau apibrėžtą pasirinktų eksportavimų grafiką ir juos tik išjungia arba įjungia.
- **Apibrėžti naują grafiką visiems pasirinktiems eksportavimams**: Perrašo esamus pasirinktų eksportavimų grafikus.

### <a name="run-exports-on-demand"></a>Pageidaujamų eksportavimų paleidimas

Jei duomenis norite eksportuoti nelaukdami planuojamo atnaujinimo, eikite į **Duomenys** > **Eksportavimai**.

- Jei norite peržiūrėti visus eksportavimus, komandų juostoje pasirinkite **Vykdyti viską**. Šis veiksmas paleis tik eksportavimus, turinčius aktyvų grafiką.
- Norėdami vykdyti vieną eksportavimą, pažymėkite jį sąraše ir pasirinkite **Vykdyti** komandų juostoje. Taip vykdote eksportavimus, neturinčius aktyvaus grafiko. 

## <a name="remove-an-export"></a>Eksportavimo pašalinimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pažymėkite norimą pašalinti eksportavimą.

1. Pasirinkite **Šalinti** komandų juostoje.

1. Patvirtinkite pašalinimą pasirinkdami **Pašalinti** patvirtinimo ekrane.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
