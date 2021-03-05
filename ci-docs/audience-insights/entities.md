---
title: Objektai ir duomenų rinkiniai
description: Peržiūrėkite duomenis objektų puslapyje.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269386"
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
> ![Pasirinkite objektą](media/data-manager-entities-data.png "Pasirinkite objektą")

- Skirtukas **Duomenys** yra pasirinktas pagal numatytuosius nustatymus ir jame rodoma lentelė, kurioje išvardyta išsami informacija apie atskirus objekto įrašus.

> [!div class="mx-imgBorder"]
> ![Laukų lentelė](media/data-manager-entities-fields.PNG "Laukų lentelė")

- Skirtuke **Laukai** pateikiama lentelė, kurioje galima peržiūrėti išsamią pasirinkto objekto informaciją, pvz., laukų pavadinimus, duomenų tipus ir tipus. Stulpelyje **Tipas** pateikiami su „Common Data Model” susiję tipai, kuriuos sistema nustato automatiškai arba [susieja patys](map-entities.md) vartotojai. Šie semantiniai tipai gali skirtis nuo atributų duomenų tipų, pvz., žemiau esančio lauko *El. paštas* duomenų tipas yra *Tekstas*, bet jo (semantinis) „Common Data Model” tipas gali būti *El. paštas* arba *El. pašto adresas*.

> [!NOTE]
> Abiejose lentelėse parodytas tik objekto duomenų pavyzdys. Norėdami peržiūrėti visą duomenų rinkinį, eikite į puslapį **Duomenų šaltiniai**, pasirinkite objektą, pasirinkite **Redaguoti** ir peržiūrėkite šio objekto duomenis, naudodami rengyklę „Power Query”, kaip paaiškinta skyriuje [Duomenų šaltiniai](data-sources.md).

Jei norite sužinoti daugiau apie į objektą įtrauktus duomenis, stulpelyje **Suvestinė** pateikiamos kai kurios svarbios duomenų charakteristikos, pvz., neapibrėžtos reikšmės, trūkstamos reikšmės, unikalios reikšmės, skaičiai ir pasiskirstymai, taikomi jūsų duomenims.

Norėdami peržiūrėti duomenų suvestinę, pažymėkite diagramos piktogramą.

> [!div class="mx-imgBorder"]
> ![Suvestinės simbolis](media/data-manager-entities-summary.png "Duomenų suvestinės lentelė")

### <a name="next-step"></a>Kitas veiksmas

Norėdami sužinoti kaip *susieti*, *sutapdinti* ir *sulieti* apdorotus duomenis, žr. temą [Sujungimas](data-unification.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]