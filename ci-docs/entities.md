---
title: Objektai programoje „Customer Insights“.
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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183577"
---
# <a name="entities-in-customer-insights"></a>Objektai programoje „Customer Insights“.

[Sukonfigūravę duomenų šaltinius](data-sources.md), eikite į puslapį **Objektai**, kad įvertintumėte apdorotų duomenų kokybę. Objektai yra laikomi duomenų rinkiniais. Daugelis „Dynamics 365 Customer Insights“ pajėgumų yra sukurti aplink šiuos objektus. Jei atidžiai juos peržiūrėsite, lengviau įvertinsite šių galimybių rezultatus.

Kai dirbate su "Customer Insights", praturtindami savo duomenis arba kurdami segmentus, matus ir veiklas, objektai, sukurti iš šių veiksmų, rodomi **puslapyje Objektai**.

## <a name="view-a-list-of-entities"></a>Objektų sąrašo peržiūra

Eikite į **Duomenų** > **objektai** ir peržiūrėkite objektų sąrašą. Toliau pateikta informacija rodoma apie kiekvieną objektą.

- **Pavadinimas**: duomenų objekto pavadinimas. Jei prie objekto pavadinimo rodomas įspėjamasis simbolis, reiškia, kad objekto duomenų nepavyko įkelti.
- **Šaltinis**: objektą prarijusių duomenų šaltinis tipas.
- **Atnaujinta**: laikas, kada objektas buvo paskutinį kartą atnaujintas.
- **Būsena**: išsami informacija apie paskutinį objekto naujinimą.

## <a name="explore-a-specific-entitys-data"></a>Susipažinkite su konkretaus objekto duomenimis

1. Eikite į **Duomenų** > **objektai**.
1. Pasirinkite objektą, kad atidarytumėte išsamios informacijos puslapį.  
1. Naršykite skirtingus to objekto laukus ir įrašus.

- Skirtukas **Atributai pasirenkamas pagal numatytuosius** nustatymus ir jame rodoma pasirinkto objekto išsami informacija, pvz., laukų pavadinimai, duomenų tipai ir tipai. Stulpelyje **Tipas** pateikiami su „Common Data Model” susiję tipai, kuriuos sistema nustato automatiškai arba [susieja patys](map-entities.md) vartotojai. Šie tipai yra semantiniai, kurie gali skirtis nuo atributų duomenų tipų. Pavyzdžiui, toliau pateiktame lauke *El. paštas* yra duomenų tipas *Eilutė,* bet jo (semantinis) "Common Data Model" tipas gali būti *El. paštas*, El. paštasAddress *arba* *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Laukų lentelė.":::

   > [!NOTE]
   > Šiame puslapyje rodomas tik objekto duomenų pavyzdys. Norėdami peržiūrėti visą duomenų rinkinį, eikite į **puslapį Duomenų šaltiniai**, pasirinkite objektą, pasirinkite **Redaguoti**, tada peržiūrėkite šio objekto duomenis naudodami Power Query redaktorių, kaip paaiškinta dalyje [Duomenų šaltiniai](data-sources.md).

   Norėdami sužinoti daugiau apie objekte nuskaitytus duomenis, **stulpelyje Suvestinė** pateikiamos kai kurios svarbios duomenų charakteristikos, pvz., neapibrėžtos reikšmės, trūkstamos reikšmės, unikalios reikšmės, skaičiai ir paskirstymai, kad ir kas būtų taikoma jūsų duomenims. Norėdami peržiūrėti duomenų suvestinę, pažymėkite diagramos piktogramą.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Duomenų suvestinė lentelė.":::

- Skirtuke **Duomenys** rodoma išsami informacija apie atskirus objekto įrašus. Pateikta išsami informacija priklauso nuo objekto duomenų tipo.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Pasirinkite objektą.":::

- Skirtukas **Ataskaitos** (pasiekiamas kai kuriems objektams) leidžia vizualizuoti duomenis sukuriant ataskaitą, kurioje yra šie stulpeliai:

  - **Ataskaitos pavadinimas**: Ataskaitos pavadinimas.
  - **Sukūrė**: subjektą sukūrusio asmens vardas ir pavardė.
  - **Sukurta**: objekto sukūrimo data ir laikas.
  - **Redagavo**: subjektą modifikavusio asmens vardas ir pavardė.
  - **Redaguota**: objekto modifikavimo data ir laikas.

## <a name="entity-specific-information"></a>Konkretaus objekto informacija

Šiame skyriuje pateikiama informacija apie kai kuriuos sistemos sukurtus objektus.

### <a name="corrupted-data-sources"></a>Pažeisti duomenų šaltiniai

Pažeisto duomenų šaltinio laukuose gali būti pažeistų duomenų. Įrašai su pažeistais laukais yra rodomi sistemos sukurtuose objektuose. Žinodami apie pažeistus įrašus galite identifikuoti, kuriuos duomenis reikia peržiūrėti ir atnaujinti šaltinio sistemoje. Kitą kartą atnaujinus duomenų šaltinį, pataisyti įrašai įtraukiami į „Customer Insights” ir perduodami tolesniems procesams. 

Pavyzdžiui, stulpelyje „gimimo diena” nustatytas duomenų tipas „data”. Kliento įraše jo gimimo diena įvesta kaip „01/01/19777”. Sistema pažymės šį įrašą kaip pažeistą. Dabar kas nors galės pakeisti gimimo datą šaltinio sistemoje į „1977”. Automatiškai atnaujinus duomenų šaltinius laukas turi galiojantį formatą, o įrašas bus pašalintas iš pažeisto objekto.

Eikite į **Duomenys** > **Objektai** ir ieškokite pažeistų objektų **Sistemos** skyriuje. Pažeistų objektų pavadinimų suteikimo schema: „DataSourceName_EntityName_corrupt”. Pasirinkite sugadintą objektą, kad identifikuotumėte sugadintus laukus ir priežastį atskiro įrašo lygiu.

   :::image type="content" source="media/corruption-reason.png" alt-text="Korupcijos priežastis.":::

„Customer Insights” vis tiek apdoroja pažeistus įrašus. Tačiau jie gali sukelti problemų dirbant su vieningais duomenimis.

Toliau nurodyti įtrauktų duomenų patikrinimai, skirti pažeistiems įrašams aptikti:

- Lauko reikšmė neatitinka jo stulpelio duomenų tipo.
- Laukuose yra simbolių, dėl kurių stulpeliai neatitinka numatytos schemos. Pavyzdžiui: neteisingai suformatuotos citatos, nepakeistos citatos arba naujų eilučių simboliai.
- Jei yra datos / datos / datos nustatymo stulpelių, jų formatas turi būti nurodytas modelyje, jei jis neatitinka standartinio ISO formato.

[!INCLUDE [footer-include](includes/footer-banner.md)]
