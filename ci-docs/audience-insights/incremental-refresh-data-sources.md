---
title: Padidėjimo paleidimas iš naujo „Power Query“ pagrįstiems duomenų šaltiniams
description: Atnaujinkite naujus ir atnaujintus „Power Query“ pagrįstų didelių duomenų šaltinių duomenis.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900278"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>„Power Query“ pagrįstų duomenų šaltinių papildantysis naujinimas

Šiame straipsnyje aptariama, kaip konfigūruoti papildomą duomenų šaltinių atnaujinimą pagal "Power Query".

Papildantysis duomenų šaltinių naujinimas teikia toliau nurodytus privalumus.

- **Greitesnis naujinimas** – atnaujinami tik pakeisti duomenys. Pavyzdžiui, galite atnaujinti tik pastarąsias penkias istorinio duomenų rinkinio dienas.
- **Didesnis patikimumas** – vykdant smulkesnius atnaujinimus, nereikia ilgai palaikyti ryšių su nepastoviomis šaltinių sistemomis, taip sumažinant ryšio problemų pavojų.
- **Sumažintas išteklių suvartojimas** – atnaujinant tik dalį visų duomenų, skaičiavimo ištekliai naudojami efektyviau ir sumažinamas poveikis aplinkai.

## <a name="configure-incremental-refresh"></a>Konfigūruoti papildantįjį naujinimą

Publikos įžvalgos leidžia padidinti paleidimą iš naujo duomenų šaltiniams importuotiems per „Power Query“, kurie palaiko padidinimo suvartojimą. Pavyzdžiui, „Azure“ SQL duomenų bazių, kurių datos ir laiko laukuose nurodoma, kada paskutinį kartą buvo atnaujinti duomenų įrašai.

1. [Kurkite „Power Query“ pagrįstą naują duomenų šaltinį](connect-power-query.md).

1. Nurodykite **duomenų** šaltinis pavadinimą.

1. Pasirinkite duomenų šaltinis, palaikančią papildomą atnaujinimą, pvz., ["Azure SQL" duomenų bazę](/power-query/connectors/azuresqldatabase).

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
