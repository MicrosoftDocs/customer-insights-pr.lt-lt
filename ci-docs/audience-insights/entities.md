---
title: Objektai ir duomenų rinkiniai
description: Peržiūrėkite duomenis objektų puslapyje.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049404"
---
# <a name="entities-in-audience-insights"></a>Objektai publikos įžvalgose

[Sukonfigūravę duomenų šaltinius](data-sources.md), eikite į puslapį **Objektai**, kad įvertintumėte apdorotų duomenų kokybę. Objektai yra laikomi duomenų rinkiniais. Daugelis „Dynamics 365 Customer Insights“ pajėgumų yra sukurti aplink šiuos objektus. Jei atidžiai juos peržiūrėsite, lengviau įvertinsite šių galimybių rezultatus.

Puslapyje **Objektai** išvardyti objektai ir yra keletas stulpelių:

- **Pavadinimas**: duomenų objekto pavadinimas. Jei prie objekto pavadinimo rodomas įspėjamasis simbolis, reiškia, kad objekto duomenų nepavyko įkelti.
- **Šaltinis**: duomenų šaltinio, apdorojusio objektą, tipas
- **Sukūrė**: objektą sukūrusio žmogaus vardas, pavardė
- **Sukurta**: objekto sukūrimo data ir laikas
- **Atnaujino**: objektą atnaujinusio žmogaus vardas, pavardė
- **Paskutinį kartą atnaujinta**: data ir laikas, kai objektas buvo atnaujintas paskutinį kartą
- **Paskutinį kartą atnaujinta**: paskutinio atnaujinimo data ir laikas

## <a name="exploring-a-specific-entitys-data"></a>Susipažinimas su konkretaus objekto duomenimis

Pažymėkite objektą, kad susipažintumėte su skirtingais laukais ir įrašais, įtrauktais į šį objektą.

> [!div class="mx-imgBorder"]
> ![Pasirinkti objektą](media/data-manager-entities-data.png "Pasirinkite objektą")

- Skirtuke **Duomenys** rodoma lentelė su išsamia informacija apie atskirus objekto įrašus.

> [!div class="mx-imgBorder"]
> ![Laukų lentelė](media/data-manager-entities-fields.PNG "Laukų lentelė")

- Skirtukas **Atributai** yra pažymėtas pagal numatytuosius parametrus ir rodo lentelę, skirtą peržiūrėti pasirinkto objekto išsamią informaciją, pavyzdžiui, laukų pavadinimus, duomenų tipus ir tipus. Stulpelyje **Tipas** pateikiami su „Common Data Model” susiję tipai, kuriuos sistema nustato automatiškai arba [susieja patys](map-entities.md) vartotojai. Šie semantiniai tipai gali skirtis nuo atributų duomenų tipų, pvz., žemiau esančio lauko *El. paštas* duomenų tipas yra *Tekstas*, bet jo (semantinis) „Common Data Model” tipas gali būti *El. paštas* arba *El. pašto adresas*.

> [!NOTE]
> Abiejose lentelėse parodytas tik objekto duomenų pavyzdys. Norėdami peržiūrėti visą duomenų rinkinį, eikite į puslapį **Duomenų šaltiniai**, pasirinkite objektą, pasirinkite **Redaguoti** ir peržiūrėkite šio objekto duomenis, naudodami rengyklę „Power Query”, kaip paaiškinta skyriuje [Duomenų šaltiniai](data-sources.md).

Jei norite sužinoti daugiau apie į objektą įtrauktus duomenis, stulpelyje **Suvestinė** pateikiamos kai kurios svarbios duomenų charakteristikos, pvz., neapibrėžtos reikšmės, trūkstamos reikšmės, unikalios reikšmės, skaičiai ir pasiskirstymai, taikomi jūsų duomenims.

Norėdami peržiūrėti duomenų suvestinę, pažymėkite diagramos piktogramą.

> [!div class="mx-imgBorder"]
> ![Suvestinės simbolis](media/data-manager-entities-summary.png "Duomenų suvestinės lentelė")

### <a name="next-step"></a>Kitas veiksmas

Norėdami sužinoti kaip *susieti*, *sutapdinti* ir *sulieti* apdorotus duomenis, žr. temą [Suvienodinti](data-unification.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
