---
title: Eksportavimų (peržiūros versija) apžvalga
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 07/25/2022
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
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245337"
---
# <a name="exports-preview-overview"></a>Eksportavimų (peržiūros versija) apžvalga

 Eksportas leidžia bendrinti konkrečius duomenis su įvairiomis programomis. Jie gali apimti klientų profilius, objektus, schemas ir susiejimo išsamią informaciją. Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md). Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai.

## <a name="export-types"></a>Eksportavimo tipai

Yra du pagrindiniai eksportuojami tipai:  

- **Duomenų eksportavimas**: eksportuokite bet kokio tipo objektus, pasiekiamus "Customer Insights". Jūsų pažymėti eksportuoti objektai eksportuojami su visais duomenų laukais, metaduomenimis, schemomis ir susiejimo informacija.
- **Segmento eksportavimas**: segmento objektų eksportavimas iš "Customer Insights". Segmentai atitinka klientų profilių sąrašą. Konfigūruodami eksportavimą, pasirenkate įtrauktus duomenų laukus, atsižvelgdami į tikslinę sistemą, į kurią eksportuojate duomenis.

### <a name="export-segments"></a>Eksportuokite segmentus

**Segmentų eksportavimas verslo klientų (B2B) arba atskirų klientų (B2B) aplinkose ar (B2C) klientams**  
Dauguma eksportavimo parinkčių palaiko abiejų tipų aplinkas. Segmentų eksportavimas į įvairias tikslines sistemas turi specifinius reikalavimus. 

**Segmentų eksportuojama pavienių klientų aplinkose (B2C)**  
- Segmentai verslo paskyrų aplinkose atskirtiems klientams, kurie yra pagrįsti *vieningu kliento profilio* objektu. Visi segmentai, kurie atitinka paskirties sistemos reikalavimus (pvz., el. pašto adresas), gali būti eksportuojami.

**Segmentų eksporto aplinkos verslo klientams (B2B)**  
- Segmentai verslo paskyrų aplinkose kuriami naudojant *kliento* objektą. Kad klientų segmentai būtų eksportuojami taip, kaip yra, paskirties sistema turi palaikyti klientų segmentus. Taip yra su [„LinkedIn"](export-linkedin-ads.md) kai **apibrėždami** eksportavimą pasirenkate įmonės parinktį.
- Visose kitose paskirties sistemose reikia laukų iš kontakto objekto. Norint užtikrinti, kad klientų segmentai galės nuskaityti duomenis iš susijusių kontaktų, jūsų segmento apraše turi būti pateikti kontakto objekto atributai. Sužinokite daugiau, kaip [konfigūruoti segmentus ir projekto atributus](segment-builder.md).

**Segmentų eksporto apribojimai**  
- Trečiųjų šalių paskirties sistemos gali riboti klientų profilių, kuriuos galite eksportuoti, skaičių. 
- Atskiriems klientams, pažymėdami eksportuoti norimą segmentą, matysite faktinį segmento narių skaičių. Jei segmentas yra per didelis, gausite įspėjimą. 
- Verslo klientų segmente matysite klientų skaičių; tačiau kontaktų, kuriuos galima projektuoti, skaičius nerodo. Tam tikrais atvejais eksportuotas segmentas iš tiesų gali turėti daugiau klientų profilių nei tikslinė sistema. Jei viršijamos tikslinės sistemos ribos, eksportas praleidžiamas.

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
