---
title: Padidėjimo paleidimas iš naujo „Power Query“ pagrįstiems duomenų šaltiniams
description: Atnaujinkite naujus ir atnaujintus „Power Query“ pagrįstų didelių duomenų šaltinių duomenis.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268558"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>„Power Query“ pagrįstų duomenų šaltinių papildantysis naujinimas

Papildantysis duomenų šaltinių naujinimas teikia toliau nurodytus privalumus.

- **Greitesnis naujinimas** – atnaujinami tik pakeisti duomenys. Pavyzdžiui, galite atnaujinti tik pastarąsias penkias istorinio duomenų rinkinio dienas.
- **Didesnis patikimumas** – vykdant smulkesnius atnaujinimus, nereikia ilgai palaikyti ryšių su nepastoviomis šaltinių sistemomis, taip sumažinant ryšio problemų pavojų.
- **Sumažintas išteklių suvartojimas** – atnaujinant tik dalį visų duomenų, skaičiavimo ištekliai naudojami efektyviau ir sumažinamas poveikis aplinkai.

## <a name="configure-incremental-refresh"></a>Konfigūruoti papildantįjį naujinimą

Publikos įžvalgos leidžia padidinti paleidimą iš naujo duomenų šaltiniams importuotiems per „Power Query“, kurie palaiko padidinimo suvartojimą. Pavyzdžiui, „Azure“ SQL duomenų bazių, kurių datos ir laiko laukuose nurodoma, kada paskutinį kartą buvo atnaujinti duomenų įrašai.

1. [Kurkite „Power Query“ pagrįstą naują duomenų šaltinį](connect-power-query.md).

1. Įveskite duomenų šaltinio pavadinimą.

1. Pažymėkite duomenų šaltinį, palaikantį papildantįjį naujinimą, pvz., „Azure“ SQL duomenų bazę.

1. Pažymėkite rinktinus objektus arba lenteles.

1. Atlikite transformavimo veiksmus ir pasirinkite **Pirmyn**.

1. Dialogo lange **Nustatyti papildantįjį naujinimą** pasirinkite **Nustatyti**, kad atidarytumėte **Papildančiojo naujinimo parametrai**. Jei pasirinksite **Praleisti**, duomenų šaltinis atnaujins visą duomenų rinkinį.
   > [!TIP]
   > Taip pat galite taikyti papildantįjį atnaujinimą vėliau, redaguodami esamą duomenų šaltinį.

1. Pasirinkę **Papildančiojo naujinimo parametrai**, sukonfigūruojate papildantįjį naujinimą visiems objektams, kuriuos pasirinkote kurdami duomenų šaltinį.

   > [!div class="mx-imgBorder"]
   > ![Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį naujinimą](media/incremental-refresh-settings.png "Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį naujinimą")

1. Pažymėkite objektą ir nurodykite toliau pateikiamą informaciją.

   - **Pasirinkite pirminį raktą**: pažymėkite objekto arba lentelės pirminį raktą.
   - **Apibrėžkite lauką „paskutinį kartą atnaujinta“**: šiame lauke rodomi tik datos arba laiko tipų atributai. Pasirinkite atributą, nurodantį, kada įrašai buvo paskutinį kartą atnaujinti. Jis bus naudojamas įrašams, patenkantiems į papildančiojo naujinimo skirtąjį laiką, identifikuoti.
   - **Tikrinti, ar yra naujinimų, kas**: nurodykite papildančiojo atnaujinimo laikotarpio trukmę.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte duomenų šaltinio kūrimą. Pradinio duomenų naujinimo metu bus atnaujinti visi duomenys. Paskui papildantysis duomenų naujinimas vykdomas pagal ankstesnio veiksmo metu nustatytus parametrus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]