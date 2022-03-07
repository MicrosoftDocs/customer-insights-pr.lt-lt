---
title: Objektai ir duomenų rinkiniai
description: Peržiūrėkite duomenis objektų puslapyje.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 00c5ee50fb9f0906622c91699852ffba0acb5c15
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900437"
---
# <a name="entities-in-audience-insights"></a>Objektai publikos įžvalgose

[Sukonfigūravę duomenų šaltinius](data-sources.md), eikite į puslapį **Objektai**, kad įvertintumėte apdorotų duomenų kokybę. Objektai yra laikomi duomenų rinkiniais. Daugelis „Dynamics 365 Customer Insights“ pajėgumų yra sukurti aplink šiuos objektus. Jei atidžiai juos peržiūrėsite, lengviau įvertinsite šių galimybių rezultatus.

**Puslapyje Objektai** išvardijami objektai ir įtraukiami šie stulpeliai:

- **Pavadinimas** : duomenų objekto pavadinimas. Jei prie objekto pavadinimo rodomas įspėjamasis simbolis, reiškia, kad objekto duomenų nepavyko įkelti.
- **Šaltinis** : objekto nurijimo duomenų šaltinis tipas.
- **Atnaujinta** : paskutinio objekto atnaujinimo laikas.
- **Būsena** : išsami informacija apie paskutinį objekto naujinimą.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Susipažinkite su konkretaus objekto duomenimis

1. Publikos įžvalgose, eikite į **Duomenys** > **Objektai**.
1. Puslapyje **Objektai** pasirinkite objektą, kad atidarytumėte išsamios informacijos puslapį.  
1. Ištirkite skirtingus to objekto laukus ir įrašus.

- Skirtukas **Atributai** yra pažymėtas pagal numatytuosius parametrus ir rodo lentelę, skirtą peržiūrėti pasirinkto objekto išsamią informaciją, pavyzdžiui, laukų pavadinimus, duomenų tipus ir tipus. Stulpelyje **Tipas** pateikiami su „Common Data Model” susiję tipai, kuriuos sistema nustato automatiškai arba [susieja patys](map-entities.md) vartotojai. Šie tipai yra semantiniai, kurie gali skirtis nuo atributų duomenų tipų. Pavyzdžiui, toliau pateikto lauko *Elektroninis paštas* duomenų tipas yra *Tekstas*, tačiau jo (semantinis) „Common Data Model” tipas gali būti *Elektroninis laiškas* arba *Elektroninio pašto adresas*.

> [!div class="mx-imgBorder"]
> ![Laukų lentelė.](media/data-manager-entities-fields.PNG "Laukų lentelė")

> [!NOTE]
> Šiame puslapyje rodomas tik jūsų objekto duomenų pavyzdys. Norėdami peržiūrėti visą duomenų rinkinį, eikite į puslapį **Duomenų šaltiniai**, pasirinkite objektą, pasirinkite **Redaguoti** ir peržiūrėkite šio objekto duomenis, naudodami rengyklę „Power Query”, kaip paaiškinta skyriuje [Duomenų šaltiniai](data-sources.md).

Jei norite sužinoti daugiau apie į objektą įtrauktus duomenis, stulpelyje **Suvestinė** pateikiamos kai kurios svarbios duomenų charakteristikos, pvz., neapibrėžtos reikšmės, trūkstamos reikšmės, unikalios reikšmės, skaičiai ir pasiskirstymai, taikomi jūsų duomenims. Norėdami peržiūrėti duomenų suvestinę, pažymėkite diagramos piktogramą.

> [!div class="mx-imgBorder"]
> ![Suvestinės simbolis.](media/data-manager-entities-summary.png "Duomenų suvestinės lentelė")

- Skirtuke **Duomenys** rodoma lentelė su išsamia informacija apie atskirus objekto įrašus. Pateikta informacija priklauso nuo objekto duomenų tipo.

> [!div class="mx-imgBorder"]
> ![Pasirinkite objektą.](media/data-manager-entities-data.png "Pasirinkti objektą")

- **Skirtukas Ataskaitos** (galimas kai kuriems objektams) leidžia vizualizuoti duomenis sukuriant ataskaitą ir apima šiuos stulpelius:

  - **Ataskaitos pavadinimas** : ataskaitos pavadinimas.
  - **Sukurta** : objekto sukūrusio asmens vardas.
  - **Sukurta** : objekto sukūrimo data ir laikas.
  - **Redagavo** : objekto modifikavusio asmens vardas.
  - **Redaguota** : objekto modifikavimo data ir laikas. 

## <a name="entity-specific-information"></a>Konkretaus objekto informacija

Šiame skyriuje pateikiama informacija apie kai kuriuos sistemos sukurtus objektus.

### <a name="corrupted-data-sources"></a>Pažeisti duomenų šaltiniai

Pažeisto duomenų šaltinio laukuose gali būti pažeistų duomenų. Įrašai su pažeistais laukais yra rodomi sistemos sukurtuose objektuose. Žinodami apie pažeistus įrašus galite identifikuoti, kuriuos duomenis reikia peržiūrėti ir atnaujinti šaltinio sistemoje. Kitą kartą atnaujinus duomenų šaltinį, pataisyti įrašai įtraukiami į „Customer Insights” ir perduodami tolesniems procesams. 

Pavyzdžiui, stulpelyje „gimimo diena” nustatytas duomenų tipas „data”. Kliento įraše jo gimimo diena įvesta kaip „01/01/19777”. Sistema pažymės šį įrašą kaip pažeistą. Dabar kas nors galės pakeisti gimimo datą šaltinio sistemoje į „1977”. Automatiškai atnaujinus duomenų šaltinius laukas turi galiojantį formatą, o įrašas bus pašalintas iš pažeisto objekto. 

Eikite į **Duomenys** > **Objektai** ir ieškokite pažeistų objektų **Sistemos** skyriuje. Pažeistų objektų pavadinimų suteikimo schema: „DataSourceName_EntityName_corrupt”.

„Customer Insights” vis tiek apdoroja pažeistus įrašus. Tačiau jie gali sukelti problemų dirbant su vieningais duomenimis.

Toliau nurodyti įtrauktų duomenų patikrinimai, skirti pažeistiems įrašams aptikti: 

- Lauko reikšmė neatitinka jo stulpelio duomenų tipo.
- Laukuose yra simbolių, dėl kurių stulpeliai neatitinka numatytos schemos. Pavyzdžiui: neteisingai suformatuotos citatos, nepakeistos citatos arba naujų eilučių simboliai.
- Jei yra datetime/date/datetimeoffset stulpelių, jų formatas turi būti nurodytas modelyje, jei jis neatitinka standartinio ISO formato.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
