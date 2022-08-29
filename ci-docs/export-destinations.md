---
title: Eksportavimų (peržiūros versija) apžvalga
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304069"
---
# <a name="exports-preview-overview"></a>Eksportavimų (peržiūros versija) apžvalga

 Eksportas leidžia bendrinti konkrečius duomenis su įvairiomis programomis. Jie gali apimti klientų profilius, objektus, schemas ir susiejimo išsamią informaciją. Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md). Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai.

## <a name="export-types"></a>Eksportavimo tipai

Yra du pagrindiniai eksportuojami tipai:  

- **Duomenų eksportavimas** leidžia eksportuoti bet kokio tipo objektus, pasiekiamus "Customer Insights". Jūsų pažymėti eksportuoti objektai eksportuojami su visais duomenų laukais, metaduomenimis, schemomis ir susiejimo informacija.
- **Segmentų eksportavimas** leidžia eksportuoti segmento objektus iš "Customer Insights". Individualiems vartotojams (nuo B iki C) segmentai yra klientų profilių sąrašas. Įmonėms (nuo B iki B) [segmentai gali reikšti abonementų arba kontaktų sąrašą](segment-builder.md#create-a-new-segment-with-segment-builder). Konfigūruodami eksportavimą, pasirenkate įtrauktus duomenų laukus, atsižvelgdami į tikslinę sistemą, į kurią eksportuojate duomenis.

### <a name="export-segments"></a>Eksportuokite segmentus

**Segmentų eksportavimas verslo klientų (B2B) arba atskirų klientų (B2B) aplinkose ar (B2C) klientams**  
Dauguma eksportavimo parinkčių palaiko abiejų tipų aplinkas. Segmentų eksportavimas į įvairias tikslines sistemas turi specifinius reikalavimus. 

**Segmentų eksportuojama pavienių klientų aplinkose (B2C)**  
- Segmentai verslo paskyrų aplinkose atskirtiems klientams, kurie yra pagrįsti *vieningu kliento profilio* objektu. Visi segmentai, kurie atitinka paskirties sistemos reikalavimus (pvz., el. pašto adresas), gali būti eksportuojami.

**Segmentuokite eksportą verslo sąskaitų aplinkoje (nuo B iki B)**  
- Segmentai, susiję su verslo paskyrų aplinkomis, yra sukurti pagal kliento objektą *arba kontaktų* objektą *.* Kad klientų segmentai būtų eksportuojami taip, kaip yra, paskirties sistema turi palaikyti klientų segmentus. Taip yra su [„LinkedIn"](export-linkedin-ads.md) kai **apibrėždami** eksportavimą pasirenkate įmonės parinktį.
- Visose kitose paskirties sistemose reikia laukų iš kontakto objekto.
- Naudojant du segmentų tipus (kontaktus ir paskyras), "Customer Insights" automatiškai nustato, kokio tipo segmentus galima eksportuoti pagal tikslinę sistemą. Pavyzdžiui, į kontaktą orientuotoje tikslinėje sistemoje, pvz., "Mailchimp", "Customer Insights" leidžia pasirinkti tik eksportuotinus kontaktų segmentus.

**Segmentų eksporto apribojimai**  
- Trečiųjų šalių paskirties sistemos gali riboti klientų profilių, kuriuos galite eksportuoti, skaičių. 
- Atskiriems klientams, pažymėdami eksportuoti norimą segmentą, matysite faktinį segmento narių skaičių. Gausite įspėjimą, jei segmentas yra per didelis. 
- Verslo paskyrose matysite paskyrų arba kontaktų skaičių, atsižvelgiant į segmentą. Gausite įspėjimą, jei segmentas yra per didelis. Jei viršysite tikslinių sistemų rezultatų apribojimus, eksportą praleisite.

## <a name="set-up-a-new-export"></a>Naujo eksportavimo sąranka

Norėdami nustatyti arba redaguoti eksportavimą, jums reikia tinkamų jums prieinamų ryšių. Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):
- **Administratoriai** turi prieigą prie visų ryšių. Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.
- **Bendradarbiai** gali turėti prieigą prie konkrečių ryšių. Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius. Eksportavimų sąraše pateikiama, ar bendraautoriai gali redaguoti, ar tik peržiūrėti eksportavimą **Jūsų teisių** stulpelyje. Norėdami gauti daugiau informacijos, eikite į [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Peržiūrintieji** gali peržiūrėti tik esamą eksportą, o ne juos sukuria.

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą** naujo eksportavimo sukūrimui.

1. Srityje Eksportavimo **nustatymas** pasirinkite, kurį [ryšį](connections.md) naudoti.

1. Jei norite sukurti eksportavimą, pateikite reikiamus duomenis ir pasirinkite **Įrašyti**. Norėdami gauti reikiamą informaciją, peržiūrėkite konkretaus eksportavimo "Customer Insights" dokumentaciją.

## <a name="manage-existing-exports"></a>Esamo eksportavimo valdymas

Eikite į **Duomenų** > **eksportavimas**, kad peržiūrėtumėte eksportą, jo ryšio pavadinimą, ryšio tipą ir būseną. Visi vartotojų vaidmenys gali peržiūrėti sukonfigūruotą eksportą. Galite rūšiuoti eksportų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte norimą tvarkyti eksportą.

Pasirinkite eksportavimą, kad peržiūrėtumėte galimus veiksmus.

:::image type="content" source="media/exports_showmore.png" alt-text="Eksporto puslapis.":::

- **Peržiūrėti** arba **Redaguoti** eksportavimą. Vartotojai, neturint redagavimo rinkitės **Peržiūrėti** o ne **Redaguoti** tam, kad pamatytumėte išsamią eksportavimo informaciją.
- **Vykdykite** eksportavimą, kad eksportuotumėte naujausius duomenis.
- **Sukurkite eksportavimo dublikatą**.
- **[Suplanuokite](#schedule-and-run-exports)** eksportą.
- **Atjunkite jungtį**, kad pašalintumėte šio eksportavimo ryšį. "Detach" nepašalina ryšio, bet išjungia eksportą. Naudotame **stulpelyje Ryšys** rodo, kad nėra ryšio.
- **Pašalinkite** eksportą.

## <a name="schedule-and-run-exports"></a>Eksportavimų planavimas ir vykdymas

Kiekvienas jūsų konfigūruojamas eksportavimas turi atnaujinimo grafiką. Atnaujinimo metu sistema ieško naujų arba atnaujintų duomenų, kuriuos reikia įtraukti į eksportavimą. Pagal numatytuosius nustatymus, eksportavimai yra vykdomi kaip kiekvieno [suplanuoto sistemos atnaujinimo](schedule-refresh.md) dalis. Galite tinkinti atnaujinimo grafiką arba išjungti jį, kad eksportavimus vykdytumėte rankiniu būdu.

Eksportavimo grafikai priklauso nuo jūsų aplinkos būsenos. Jei yra vykdomas [priklausomybių](system.md#refresh-processes) naujinimas, kai reikia pradėti suplanuotą eksportavimą, sistema iš pradžių užbaigs naujinimus, o tada paleist eksportavimą. Stulpelyje **Atnaujinta** rodoma, kada eksportavimas buvo paskutinį kartą atnaujintas.

### <a name="schedule-exports"></a>Eksportavimų grafikas

Apibrėžkite pasirinktinius atskirų eksportų arba kelių eksportų atnaujinimo tvarkaraščius vienu metu. Šiuo metu apibrėžtas grafikas pateikiamas eksportavimo sąrašo stulpelyje **Grafikas**. Teisė keisti tvarkaraštį yra tokia pati kaip [eksporto redagavimas ir apibrėžimas](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite norimą suplanuoti eksportavimą.

1. Pasirinkite **Grafikas**.

1. Srityje **Eksportavimo grafikas** nustatykite **Vykdymo grafiką** į **Įjungta**, kad eksportavimas būtų vykdomas automatiškai. Nustatykite į **Išjungta**, kad jį atnaujintumėte rankiniu būdu.

1. Automatiškai atnaujintiems eksportavimams pasirinkite **Pasikartojimo** reikšmę ir nurodykite jos išsamią informaciją. Nustatytas laikas taikomas visiems pasikartojimo atvejams. Tai yra laikas, kai eksportavimas turėtų pradėti atsinaujinti.

1. Pasirinkite **Įrašyti**.

Redaguodami kelių eksportų tvarkaraštį, pasirinkite skiltyje **Išlaikyti arba nepaisyti tvarkaraščių**:

- **Išsaugokite atskirus tvarkaraščius**: palikite anksčiau apibrėžtą pasirinktų eksportų tvarkaraštį ir tik išjunkite arba įgalinkite juos.
- **Apibrėžti naują grafiką visiems pasirinktiems eksportavimams**: Perrašo esamus pasirinktų eksportavimų grafikus.

### <a name="run-exports-on-demand"></a>Pageidaujamų eksportavimų paleidimas

Jei duomenis norite eksportuoti nelaukdami planuojamo atnaujinimo, eikite į **Duomenys** > **Eksportavimai**.

- Jei norite peržiūrėti visus eksportavimus, komandų juostoje pasirinkite **Vykdyti viską**. Vykdomi tik tie eksportavimai, kurie turi aktyvų tvarkaraštį. Norėdami vykdyti neaktyvų eksportavimą, vykdykite vieną eksportavimą.
- Norėdami vykdyti vieną eksportavimą, pažymėkite jį sąraše ir pasirinkite **Vykdyti** komandų juostoje.

## <a name="troubleshooting"></a>Trikčių šalinimas

### <a name="segment-not-eligible-for-export"></a>Segmentas, neatitinkantis eksporto reikalavimų

**Problema** Verslo paskyrų aplinkoje jūsų eksportas nepavyksta su klaidos pranešimu: "Šis segmentas neatitinka šios eksportavimo paskirties vietos reikalavimų: "{segmento} pavadinimas". Pasirinkite tik "ContactProfile" tipo segmentus ir bandykite dar kartą."

**Pertvarkymo** "Customer Insights" aplinkos verslo paskyroms buvo atnaujintos, kad, be sąskaitų segmentų, būtų palaikomi kontaktų segmentai. Dėl šio pokyčio eksportas, kuriam reikia kontaktinės informacijos, veikia tik su segmentais pagal kontaktus.

1. [Sukurkite segmentą pagal kontaktus](segment-builder.md), kuris atitinka anksčiau naudotą segmentą.

1. Paleidę tą kontaktų segmentą, redaguokite atitinkamą eksportavimą ir pasirinkite naują segmentą.

1. Pasirinkite **Įrašyti**, kad įrašytumėte konfigūraciją, arba **Įrašyti ir paleisti**, kad iš karto išbandytumėte šį eksportavimą.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
