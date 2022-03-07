---
title: Objektai ir duomenų rinkiniai
description: Peržiūrėkite duomenis objektų puslapyje.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355308"
---
# <a name="entities-in-audience-insights"></a>Objektai publikos įžvalgose

[Sukonfigūravę duomenų šaltinius](data-sources.md), eikite į puslapį **Objektai**, kad įvertintumėte apdorotų duomenų kokybę. Objektai yra laikomi duomenų rinkiniais. Daugelis „Dynamics 365 Customer Insights“ pajėgumų yra sukurti aplink šiuos objektus. Jei atidžiai juos peržiūrėsite, lengviau įvertinsite šių galimybių rezultatus.

Puslapyje **Objektai** išvardijami objektai ir pateikiami šie stulpeliai:

- **Pavadinimas**: duomenų objekto pavadinimas. Jei prie objekto pavadinimo rodomas įspėjamasis simbolis, reiškia, kad objekto duomenų nepavyko įkelti.
- **Šaltinis**: objektą nurijusios duomenų šaltinis tipas.
- **Atnaujinta**: laikas, kada objektas paskutinį kartą buvo atnaujintas.
- **Būsena**: Išsami informacija apie paskutinį objekto atnaujinimą.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Susipažinkite su konkretaus objekto duomenimis

1. Publikos įžvalgose, eikite į **Duomenys** > **Objektai**.
1. **Puslapyje Objektai** pasirinkite objektą, kad atidarytumėte išsamios informacijos puslapį.  
1. Naršykite skirtingus į tą objektą įtrauktus laukus ir įrašus.

- Skirtukas **Atributai** yra pažymėtas pagal numatytuosius parametrus ir rodo lentelę, skirtą peržiūrėti pasirinkto objekto išsamią informaciją, pavyzdžiui, laukų pavadinimus, duomenų tipus ir tipus. Stulpelyje **Tipas** pateikiami su „Common Data Model” susiję tipai, kuriuos sistema nustato automatiškai arba [susieja patys](map-entities.md) vartotojai. Šie tipai yra semantiniai, kurie gali skirtis nuo atributų duomenų tipų. Pavyzdžiui, toliau pateikto lauko *Elektroninis paštas* duomenų tipas yra *Tekstas*, tačiau jo (semantinis) „Common Data Model” tipas gali būti *Elektroninis laiškas* arba *Elektroninio pašto adresas*.

> [!div class="mx-imgBorder"]
> ![Laukų lentelė.](media/data-manager-entities-fields.PNG "Laukų lentelė")

> [!NOTE]
> Šiame puslapyje rodomas tik objekto duomenų pavyzdys. Norėdami peržiūrėti visą duomenų rinkinį, eikite į **puslapį Duomenų šaltiniai**, pasirinkite objektą, pasirinkite **Redaguoti**, tada peržiūrėkite šio objekto duomenis su Power Query redaktoriumi, kaip paaiškinta duomenų [šaltiniuose](data-sources.md).

Jei norite sužinoti daugiau apie į objektą įtrauktus duomenis, stulpelyje **Suvestinė** pateikiamos kai kurios svarbios duomenų charakteristikos, pvz., neapibrėžtos reikšmės, trūkstamos reikšmės, unikalios reikšmės, skaičiai ir pasiskirstymai, taikomi jūsų duomenims. Norėdami peržiūrėti duomenų suvestinę, pažymėkite diagramos piktogramą.

> [!div class="mx-imgBorder"]
> ![Suvestinės simbolis.](media/data-manager-entities-summary.png "Duomenų suvestinės lentelė")

- Skirtuke **Duomenys** rodoma lentelė su išsamia informacija apie atskirus objekto įrašus. Pateikta išsami informacija priklauso nuo objekto duomenų tipo.

> [!div class="mx-imgBorder"]
> ![Pasirinkite objektą.](media/data-manager-entities-data.png "Pasirinkti objektą")

- Skirtukas **Ataskaitos** (galimas kai kuriems objektams) leidžia vizualizuoti duomenis kuriant ataskaitą ir apima šiuos stulpelius:

  - **Ataskaitos pavadinimas**: Ataskaitos pavadinimas.
  - **Sukūrė**: subjektą sukūrusio asmens vardas.
  - **Sukurta**: objekto sukūrimo data ir laikas.
  - **Redagavo**: subjektą modifikavusio asmens vardas.
  - **Redaguota**: objekto modifikavimo data ir laikas. 

## <a name="entity-specific-information"></a>Konkretaus objekto informacija

Šiame skyriuje pateikiama informacija apie kai kuriuos sistemos sukurtus objektus.

### <a name="corrupted-data-sources"></a>Pažeisti duomenų šaltiniai

Pažeisto duomenų šaltinio laukuose gali būti pažeistų duomenų. Įrašai su pažeistais laukais yra rodomi sistemos sukurtuose objektuose. Žinodami apie pažeistus įrašus galite identifikuoti, kuriuos duomenis reikia peržiūrėti ir atnaujinti šaltinio sistemoje. Kitą kartą atnaujinus duomenų šaltinį, pataisyti įrašai įtraukiami į „Customer Insights” ir perduodami tolesniems procesams. 

Pavyzdžiui, stulpelyje „gimimo diena” nustatytas duomenų tipas „data”. Kliento įraše jo gimimo diena įvesta kaip „01/01/19777”. Sistema pažymės šį įrašą kaip pažeistą. Dabar kas nors galės pakeisti gimimo datą šaltinio sistemoje į „1977”. Automatiškai atnaujinus duomenų šaltinius laukas turi galiojantį formatą, o įrašas bus pašalintas iš pažeisto objekto. 

Eikite į **Duomenys** > **Objektai** ir ieškokite pažeistų objektų **Sistemos** skyriuje. Pažeistų objektų pavadinimų suteikimo schema: „DataSourceName_EntityName_corrupt”. Pasirinkite sugadintą objektą, kad nustatytumėte visus sugadintus laukus ir priežastį atskirame įrašų lygyje.
> [!div class="mx-imgBorder"]
> ![Korupcijos priežastis.](media/corruption-reason.png "Korupcijos priežastis")

„Customer Insights” vis tiek apdoroja pažeistus įrašus. Tačiau jie gali sukelti problemų dirbant su vieningais duomenimis.

Toliau nurodyti įtrauktų duomenų patikrinimai, skirti pažeistiems įrašams aptikti: 

- Lauko reikšmė neatitinka jo stulpelio duomenų tipo.
- Laukuose yra simbolių, dėl kurių stulpeliai neatitinka numatytos schemos. Pavyzdžiui: neteisingai suformatuotos citatos, nepakeistos citatos arba naujų eilučių simboliai.
- Jei yra datos/ datos / datetimeoffset stulpelių, jų formatas turi būti nurodytas modelyje, jei jis neatitinka standartinio ISO formato.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
