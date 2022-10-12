---
title: Objektai programoje „Customer Insights“.
description: Peržiūrėkite duomenis objektų puslapyje.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610108"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
