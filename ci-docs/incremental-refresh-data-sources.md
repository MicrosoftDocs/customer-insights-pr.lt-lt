---
title: Laipsniškas "Azure Data Lake" duomenų šaltinių atnaujinimas Power Query
description: Atnaujinkite naujus ir atnaujintus didelių duomenų šaltinių duomenis, pagrįstus Power Query arba "Azure" duomenų ežero duomenų šaltiniais.
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
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207147"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Laipsniškas "Azure Data Lake" duomenų šaltinių atnaujinimas Power Query

Laipsniškas duomenų šaltinių, pagrįstų Power Query arba "Azure Data Lake", atnaujinimas suteikia šiuos pranašumus:

- **Greitesnis naujinimas** – atnaujinami tik pakeisti duomenys. Pavyzdžiui, galite atnaujinti tik pastarąsias penkias istorinio duomenų rinkinio dienas.
- **Didesnis patikimumas** – vykdant smulkesnius atnaujinimus, nereikia ilgai palaikyti ryšių su nepastoviomis šaltinių sistemomis, taip sumažinant ryšio problemų pavojų.
- **Sumažintas išteklių suvartojimas** – atnaujinant tik dalį visų duomenų, skaičiavimo ištekliai naudojami efektyviau ir sumažinamas poveikis aplinkai.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Duomenų šaltinių laipsniško atnaujinimo konfigūravimas pagal Power Query

"Customer Insights" leidžia laipsniškai atnaujinti duomenų šaltinius, importuotus per Power Query tą palaikymą, laipsnišką įsisavinimą. Pavyzdžiui, „Azure“ SQL duomenų bazių, kurių datos ir laiko laukuose nurodoma, kada paskutinį kartą buvo atnaujinti duomenų įrašai.

1. [Sukurkite naują duomenų šaltinis pagal Power Query](connect-power-query.md).

1. Pasirinkite duomenų šaltinis, kuris palaiko laipsnišką atnaujinimą, pvz [., "Azure SQL" duomenų bazę](/power-query/connectors/azuresqldatabase).

1. Pažymėkite rinktinus objektus arba lenteles.

1. Atlikite transformavimo veiksmus ir pasirinkite **Pirmyn**.

1. Dialogo lange **Nustatyti papildantįjį naujinimą** pasirinkite **Nustatyti**, kad atidarytumėte **Papildančiojo naujinimo parametrai**. Jei pasirinksite **Praleisti**, duomenų šaltinis atnaujins visą duomenų rinkinį.
   > [!TIP]
   > Taip pat galite taikyti papildantįjį atnaujinimą vėliau, redaguodami esamą duomenų šaltinį.

1. Pasirinkę **Papildančiojo naujinimo parametrai**, sukonfigūruojate papildantįjį naujinimą visiems objektams, kuriuos pasirinkote kurdami duomenų šaltinį.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigūruokite laipsniško atnaujinimo parametrus.":::

1. Pažymėkite objektą ir nurodykite toliau pateikiamą informaciją.

   - **Pasirinkite pirminį raktą**: pažymėkite objekto arba lentelės pirminį raktą.
   - **Apibrėžkite lauką „paskutinį kartą atnaujinta“**: šiame lauke rodomi tik datos arba laiko tipų atributai. Pasirinkite atributą, nurodantį, kada įrašai buvo paskutinį kartą atnaujinti. Jis bus naudojamas įrašams, patenkantiems į papildančiojo naujinimo skirtąjį laiką, identifikuoti.
   - **Tikrinti, ar yra naujinimų, kas**: nurodykite papildančiojo atnaujinimo laikotarpio trukmę.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte duomenų šaltinio kūrimą. Pradinio duomenų naujinimo metu bus atnaujinti visi duomenys. Paskui papildantysis duomenų naujinimas vykdomas pagal ankstesnio veiksmo metu nustatytus parametrus.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>"Azure Data Lake" duomenų šaltinių laipsniško atnaujinimo konfigūravimas

"Customer Insights" leidžia laipsniškai atnaujinti duomenų šaltinius, prijungtus prie Azure Data Lake Storage. Norėdami naudoti objekto laipsnišką įsisavinimą ir atnaujinimą, konfigūruokite tą objektą, kai redaguodami duomenų šaltinis duomenų šaltinis arba naujesnę versiją. Objekto duomenų aplanke turi būti šie aplankai:

- **"FullData"**: aplankas su duomenų failais, kuriuose yra pradinių įrašų
- **IncrementalData**: aplankas su datos / laiko hierarchijos aplankais **yyyyy/mm/dd/hh** formatu, kuriame yra laipsniški naujinimai. **hh** reiškia utc valandą atnaujinimų ir turi **aplankus Upserts** ir **Deletes**. **"Upserts"** yra duomenų failų su esamų įrašų arba naujų įrašų naujinimais. **Naikinime** yra duomenų failai su įrašais, kuriuos reikia pašalinti.

1. Įtraukdami arba redaguodami duomenų šaltinis, pereikite į objekto **sritį Atributai**.

1. Peržiūrėkite atributus. Įsitikinkite, kad sukurtas arba paskutinį kartą atnaujintas datos atributas nustatytas naudojant *dateTime* **Data formatą** *ir Calendar.Date* **semantinį tipą**. Jei reikia, redaguokite atributą ir pasirinkite **Atlikta**.

1. **Srityje Pasirinkti objektus** redaguokite. Pažymėtas žymimasis laukelis Laipsniškas **nurijimas**.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį atnaujinimą.":::

   1. Pereikite į šakninį aplanką, kuriame yra .csv arba .parketo failai, kad gautumėte visus duomenis, papildomus duomenų priedus ir laipsniškus duomenų naikinimus.
   1. Įveskite visų duomenų ir abiejų prieaugio failų (\. csv arba \. parketo) plėtinį.
   1. Jei naudojate .csv failus, pasirinkite stulpelių skyriklį ir, jei norite, kad pirmoji failo eilutė būtų stulpelio antraštė.
   1. Pasirinkite **Įrašyti**.

1. Dalyje **Paskutinį kartą atnaujinta** pasirinkite datos laiko žymos atributą.

1. **Jei pirminis raktas** nepasirinktas, pasirinkite pirminį raktą. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.

1. Pasirinkite **Uždaryti**, kad įrašytumėte ir uždarytumėte sritį.

1. Tęskite duomenų šaltinis pridėjimą arba redagavimą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
