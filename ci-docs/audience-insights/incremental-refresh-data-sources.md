---
title: Laipsniškas duomenų šaltinių atnaujinimas Power Query
description: Atnaujinti naujus ir atnaujintus duomenis dideliems duomenų šaltiniams pagal Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353692"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Laipsniškas duomenų šaltinių atnaujinimas, pagrįstas Power Query

Šiame straipsnyje aptariama, kaip konfigūruoti papildomą duomenų šaltinių atnaujinimą pagal Power Query.

Papildantysis duomenų šaltinių naujinimas teikia toliau nurodytus privalumus.

- **Greitesnis naujinimas** – atnaujinami tik pakeisti duomenys. Pavyzdžiui, galite atnaujinti tik pastarąsias penkias istorinio duomenų rinkinio dienas.
- **Didesnis patikimumas** – vykdant smulkesnius atnaujinimus, nereikia ilgai palaikyti ryšių su nepastoviomis šaltinių sistemomis, taip sumažinant ryšio problemų pavojų.
- **Sumažintas išteklių suvartojimas** – atnaujinant tik dalį visų duomenų, skaičiavimo ištekliai naudojami efektyviau ir sumažinamas poveikis aplinkai.

## <a name="configure-incremental-refresh"></a>Konfigūruoti papildantįjį naujinimą

Auditorijos įžvalgos leidžia palaipsniui atnaujinti duomenų šaltinius, importuotus per Power Query tą palaikymo padidėjimą. Pavyzdžiui, „Azure“ SQL duomenų bazių, kurių datos ir laiko laukuose nurodoma, kada paskutinį kartą buvo atnaujinti duomenų įrašai.

1. [Sukurkite naują duomenų šaltinis pagal Power Query](connect-power-query.md).

1. Pateikite **duomenų šaltinis pavadinimą**.

1. Pasirinkite duomenų šaltinis, palaikančią laipsnišką atnaujinimą, pvz [., "Azure SQL" duomenų bazę](/power-query/connectors/azuresqldatabase).

1. Pažymėkite rinktinus objektus arba lenteles.

1. Atlikite transformavimo veiksmus ir pasirinkite **Pirmyn**.

1. Dialogo lange **Nustatyti papildantįjį naujinimą** pasirinkite **Nustatyti**, kad atidarytumėte **Papildančiojo naujinimo parametrai**. Jei pasirinksite **Praleisti**, duomenų šaltinis atnaujins visą duomenų rinkinį.
   > [!TIP]
   > Taip pat galite taikyti papildantįjį atnaujinimą vėliau, redaguodami esamą duomenų šaltinį.

1. Pasirinkę **Papildančiojo naujinimo parametrai**, sukonfigūruojate papildantįjį naujinimą visiems objektams, kuriuos pasirinkote kurdami duomenų šaltinį.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį atnaujinimą.":::

1. Pažymėkite objektą ir nurodykite toliau pateikiamą informaciją.

   - **Pasirinkite pirminį raktą**: pažymėkite objekto arba lentelės pirminį raktą.
   - **Apibrėžkite lauką „paskutinį kartą atnaujinta“**: šiame lauke rodomi tik datos arba laiko tipų atributai. Pasirinkite atributą, nurodantį, kada įrašai buvo paskutinį kartą atnaujinti. Jis bus naudojamas įrašams, patenkantiems į papildančiojo naujinimo skirtąjį laiką, identifikuoti.
   - **Tikrinti, ar yra naujinimų, kas**: nurodykite papildančiojo atnaujinimo laikotarpio trukmę.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte duomenų šaltinio kūrimą. Pradinio duomenų naujinimo metu bus atnaujinti visi duomenys. Paskui papildantysis duomenų naujinimas vykdomas pagal ankstesnio veiksmo metu nustatytus parametrus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
