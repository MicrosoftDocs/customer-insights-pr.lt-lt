---
title: Duomenų eksportavimas iš „Customer Insights“
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 61e95e47489495e367498547687b0065169519e6
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673333"
---
# <a name="exports-preview-overview"></a>Eksportavimų (peržiūros versija) apžvalga

Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai. Eksportavimuose su įvairiomis programomis bendrinami konkretūs duomenys. Jie gali apimti klientų profilius, objektus, schemas ir susiejimo išsamią informaciją. Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md).

Eikite į **Duomenys** > **Eksportavimai**, kad peržiūrėtumėte eksportavimų puslapį. Visi vartotojų vaidmenys gali peržiūrėti sukonfigūruotą eksportą. Komandų juostoje naudokite ieškos lauką, kad rastumėte eksportą pagal jų vardą, ryšio pavadinimą arba ryšio tipą.

## <a name="export-types"></a>Eksportavimo tipai

Yra du pagrindiniai eksportuojami tipai:  

- **Eksportuojant duomenis** galima eksportuoti bet kokio tipo objektą, prieinamą auditorijos įžvalgose. Jūsų pažymėti eksportuoti objektai eksportuojami su visais duomenų laukais, metaduomenimis, schemomis ir susiejimo informacija. 
- **Segmentų eksportavimas** leidžia eksportuoti segmento objektus iš auditorijos įžvalgų. Segmentai atitinka klientų profilių sąrašą. Konfigūruodami eksportavimą, pažymite įtrauktus duomenų laukus, atsižvelgiant į paskirties sistemą, į kurią eksportuojate duomenis. 

### <a name="export-segments"></a>Eksportuokite segmentus

**Segmentų eksportavimas verslo klientų (B2B) arba atskirų klientų (B2B) aplinkose ar (B2C) klientams**  
Dauguma eksportavimo parinkčių palaiko abiejų tipų aplinkas. Norint eksportuoti segmentus į įvairias paskirties sistemas taikomi konkretūs reikalavimai. Bendrai tariant, kliento segmento narys, kliento profilyje yra kontaktinė informacija. Nors paprastai taip būna segmentams, sukurtiems iš atskirų klientų (B2C), segmentams, pagrįstiems verslo klientais (B2B), nebūtina. 

**Segmentų eksporto aplinkos verslo klientams (B2B)**  
- Segmentai verslo paskyrų aplinkose kuriami naudojant *kliento* objektą. Kad klientų segmentai būtų eksportuojami taip, kaip yra, paskirties sistema turi palaikyti klientų segmentus. Taip yra su [„LinkedIn"](export-linkedin-ads.md) kai **apibrėždami** eksportavimą pasirenkate įmonės parinktį.
- Visose kitose paskirties sistemose reikia laukų iš kontakto objekto. Norint užtikrinti, kad klientų segmentai galės nuskaityti duomenis iš susijusių kontaktų, jūsų segmento apraše turi būti pateikti kontakto objekto atributai. Sužinokite daugiau, kaip [konfigūruoti segmentus ir projekto atributus](segment-builder.md).

**Segmentų eksportuojama pavienių klientų aplinkose (B2C)**  
- Segmentai verslo paskyrų aplinkose atskirtiems klientams, kurie yra pagrįsti *vieningu kliento profilio* objektu. Visi segmentai, kurie atitinka paskirties sistemos reikalavimus (pvz., el. pašto adresas), gali būti eksportuojami.

**Segmentų eksporto apribojimai**  
- Trečiųjų šalių paskirties sistemos gali riboti klientų profilių, kuriuos galite eksportuoti, skaičių. 
- Atskiriems klientams, pažymėdami eksportuoti norimą segmentą, matysite faktinį segmento narių skaičių. Jei segmentas yra per didelis, gausite įspėjimą. 
- Verslo klientų segmente matysite klientų skaičių; tačiau kontaktų, kuriuos galima projektuoti, skaičius nerodo. Tam tikrais atvejais eksportuotas segmentas iš tiesų gali turėti daugiau klientų profilių nei tikslinė sistema. Jei viršysite tikslinių sistemų rezultatų apribojimus, eksportą praleisite. 

## <a name="set-up-a-new-export"></a>Naujo eksportavimo sąranka  
Jei norite nustatyti ar redaguoti eksportavimą, turite turėti prieinamų ryšių. Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):
- **Administratoriai** turi prieigą prie visų ryšių. Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.
- **Bendradarbiai** gali turėti prieigą prie konkrečių ryšių. Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius. Eksportavimų sąraše pateikiama, ar bendraautoriai gali redaguoti, ar tik peržiūrėti eksportavimą **Jūsų teisių** stulpelyje. Norėdami gauti daugiau informacijos, eikite į [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Peržiūrintieji** gali peržiūrėti tik esamą eksportą, o ne juos sukuria.

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

1. Vartotojai, neturint redagavimo rinkitės **Peržiūrėti** o ne **Redaguoti** tam, kad pamatytumėte išsamią eksportavimo informaciją.

1. Šoninėje srityje rodoma eksportavimo konfigūracija. Jei neturite redagavimo teisių, reikšmių keisti negalite. Jei norite grįžti prie eksportavimų puslapio, pasirinkite **Uždaryti**.

## <a name="schedule-and-run-exports"></a>Eksportavimų planavimas ir vykdymas

Kiekvienas jūsų konfigūruojamas eksportavimas turi atnaujinimo grafiką. Atnaujinimo metu sistema ieško naujų arba atnaujintų duomenų, kuriuos reikia įtraukti į eksportavimą. Pagal numatytuosius nustatymus, eksportavimai yra vykdomi kaip kiekvieno [suplanuoto sistemos atnaujinimo](system.md#schedule-tab) dalis. Galite tinkinti atnaujinimo grafiką arba išjungti jį, kad eksportavimus vykdytumėte rankiniu būdu.

Eksportavimo grafikai priklauso nuo jūsų aplinkos būsenos. Jei yra vykdomas [priklausomybių](system.md#refresh-policies) naujinimas, kai reikia pradėti suplanuotą eksportavimą, sistema iš pradžių užbaigs naujinimus, o tada paleist eksportavimą. Galite matyti, kada eksportavimas paskutinį kartą buvo atnaujintas, stulpelyje **Atnaujinta**.

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
