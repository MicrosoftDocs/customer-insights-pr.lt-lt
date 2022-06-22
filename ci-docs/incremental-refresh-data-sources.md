---
title: Papildomas atnaujinimas, skirtas Power Query "Azure Data Lake" duomenų šaltiniams
description: Atnaujinkite naujus ir atnaujintus didelių duomenų šaltinių duomenis pagal Power Query arba "Azure" duomenų ežero duomenų šaltinius.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012035"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Papildomas atnaujinimas, skirtas Power Query "Azure Data Lake" duomenų šaltiniams

Šiame straipsnyje aptariama, kaip konfigūruoti papildomą duomenų šaltinių atnaujinimą pagal Power Query "Azure Data Lake" arba "Azure Data Lake".

Papildantysis duomenų šaltinių naujinimas teikia toliau nurodytus privalumus.

- **Greitesnis naujinimas** – atnaujinami tik pakeisti duomenys. Pavyzdžiui, galite atnaujinti tik pastarąsias penkias istorinio duomenų rinkinio dienas.
- **Didesnis patikimumas** – vykdant smulkesnius atnaujinimus, nereikia ilgai palaikyti ryšių su nepastoviomis šaltinių sistemomis, taip sumažinant ryšio problemų pavojų.
- **Sumažintas išteklių suvartojimas** – atnaujinant tik dalį visų duomenų, skaičiavimo ištekliai naudojami efektyviau ir sumažinamas poveikis aplinkai.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Konfigūruoti papildomą duomenų šaltinių atnaujinimą pagal Power Query

"Customer Insights" leidžia palaipsniui atnaujinti duomenų šaltinius, importuotus naudojant Power Query tą palaiko laipsnišką nurijimą. Pavyzdžiui, „Azure“ SQL duomenų bazių, kurių datos ir laiko laukuose nurodoma, kada paskutinį kartą buvo atnaujinti duomenų įrašai.

1. [Sukurkite naują duomenų šaltinis pagal Power Query](connect-power-query.md).

1. Pasirinkite duomenų šaltinis, palaikantį papildomą atnaujinimą, pvz [., "Azure SQL" duomenų bazę](/power-query/connectors/azuresqldatabase).

1. Pažymėkite rinktinus objektus arba lenteles.

1. Atlikite transformavimo veiksmus ir pasirinkite **Pirmyn**.

1. Dialogo lange **Nustatyti papildantįjį naujinimą** pasirinkite **Nustatyti**, kad atidarytumėte **Papildančiojo naujinimo parametrai**. Jei pasirinksite **Praleisti**, duomenų šaltinis atnaujins visą duomenų rinkinį.
   > [!TIP]
   > Taip pat galite taikyti papildantįjį atnaujinimą vėliau, redaguodami esamą duomenų šaltinį.

1. Pasirinkę **Papildančiojo naujinimo parametrai**, sukonfigūruojate papildantįjį naujinimą visiems objektams, kuriuos pasirinkote kurdami duomenų šaltinį.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigūruokite papildančius atnaujinimo parametrus.":::

1. Pažymėkite objektą ir nurodykite toliau pateikiamą informaciją.

   - **Pasirinkite pirminį raktą**: pažymėkite objekto arba lentelės pirminį raktą.
   - **Apibrėžkite lauką „paskutinį kartą atnaujinta“**: šiame lauke rodomi tik datos arba laiko tipų atributai. Pasirinkite atributą, nurodantį, kada įrašai buvo paskutinį kartą atnaujinti. Jis bus naudojamas įrašams, patenkantiems į papildančiojo naujinimo skirtąjį laiką, identifikuoti.
   - **Tikrinti, ar yra naujinimų, kas**: nurodykite papildančiojo atnaujinimo laikotarpio trukmę.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte duomenų šaltinio kūrimą. Pradinio duomenų naujinimo metu bus atnaujinti visi duomenys. Paskui papildantysis duomenų naujinimas vykdomas pagal ankstesnio veiksmo metu nustatytus parametrus.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Konfigūruoti papildomą "Azure Data Lake" duomenų šaltinių atnaujinimą

"Customer Insights" leidžia palaipsniui atnaujinti duomenų šaltinius, prijungtus prie Azure Data Lake Storage. Norėdami naudoti papildomą objekto nurijimą ir atnaujinimą, konfigūruokite tą objektą įtraukdami "Azure Data Lake" duomenų šaltinis arba vėlesnę versiją redaguodami duomenų šaltinis. Objekto duomenų aplanke turi būti šie aplankai:

- **FullData**: aplankas su duomenų failais, kuriuose yra pradinių įrašų
- **IncrementalData**: aplankas su datos / laiko hierarchijos aplankais **yyyy / mm / dd / hh** formatu, kuriame yra papildomi naujinimai. **hh** nurodo atnaujinimų UTC valandą ir yra **aplankai Upserts** ir **Deletes**. **"Upserts** " yra duomenų failų su esamų įrašų arba naujų įrašų naujinimais. **Naikinamuose yra duomenų failų su įrašais**, kuriuos reikia pašalinti.

1. Įtraukdami arba redaguodami duomenų šaltinis, eikite į objekto **sritį Atributai**.

1. Peržiūrėkite atributus. Įsitikinkite, kad sukurtas arba paskutinis atnaujintas datos atributas nustatytas su *dateTime* **duomenų formatu** ir *Calendar.Date* **semantiniu tipu**. Jei reikia, redaguokite atributą ir pasirinkite **Atlikta**.

1. **Srityje Pasirinkti objektus** redaguokite objektą. Pažymėtas žymės langelis **Papildomas nurijimas**.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį atnaujinimą.":::

   1. Raskite šakninį aplanką, kuriame yra .csv arba .parquet failai, kad gautumėte išsamius duomenis, papildomus duomenų papildymus ir papildomus duomenų naikinimus.
   1. Įveskite visų duomenų plėtinį ir abu papildomus failus (\. csv arba \. parketą).
   1. Pasirinkite **Įrašyti**.

1. Dalyje **Paskutinis atnaujintas** pasirinkite datos laiko žymos atributą.

1. Jei pirminis **raktas** nepasirinktas, pasirinkite pirminį raktą. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.

1. Pasirinkite **Uždaryti**, kad įrašytumėte ir uždarytumėte sritį.

1. Toliau pridėkite arba redaguokite duomenų šaltinis.

[!INCLUDE [footer-include](includes/footer-banner.md)]
