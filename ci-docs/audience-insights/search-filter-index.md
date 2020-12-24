---
title: Ieškokite ir filtruokite kliento profilius
description: Greitai raskite vieningų klientų profilių informaciją ir filtruokite nurodytus atributus.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406424"
---
# <a name="customer-profiles-search--filter-index"></a>Klientų profiliai: ieškos ir filtro rodyklė

Kliento duomenų suvienodinimo rezultatas yra kliento profilio objektas, kuris jūsų bendroje klientų bazėje teikia vieningą rodinį. Norėdami greitai [rasti informaciją apie tam tikrą klientą arba klientų grupę](customer-profiles.md), galite sukonfigūruoti **ieškos** ir **filtro** galimybes **klientų** puslapyje. Skaitydami toliau sužinosite, kaip administratoriai gali redaguoti **ieškos ir filtrų rodyklės** puslapyje esančius atributus, pasiekiamus norint ieškoti ir filtruoti.

> [!div class="mx-imgBorder"]
> ![Ieškos filtras](media/search-filter.png "Ieškos filtras")

## <a name="add-fields-and-specify-attributes"></a>Įtraukti laukus ir nurodyti atributus

Jei pirmą kartą nustatote ieškomus atributus kaip administratorius, pirmiausia turite apibrėžti indeksuotus laukus. Patariame pasirinkti visus atributus, pagal kuriuos naudotojai gali ieškoti ir filtruoti klientus **klientų** puslapyje. Galite nurodyti tik per duomenų suvienijimo procesą sukurtus, klientų profilio objekte esančius atributus.

1. Atidarykite puslapį **Klientai** ir pasirinkite **Ieškos ir filtro rodyklė**.

> [!NOTE]
> Iš šių semantikos tipų, kaip apibrėžta struktūros puslapyje, sukursime numatytąją ieškos rodyklės konfigūraciją.
> - Asmens vardas, pavardė, vidurinis vardas, pilnas vardas
> - Organizacijos pavadinimas
> - El. pašto adresas
> - Telefono numeris
> - Vietos informacija

2. Pasirinkite **+ Įtraukti**, kad nurodytumėte indeksuotus laukus.

3. Pasirinkite sąraše esančius atributus, kuriuos norite įtraukti kaip indeksuotus laukus. Bet kada galite įtraukti daugiau atributų, pasirinkę **Įtraukti**. Taip pat galite pašalinti bet kokius pasirinktus atributus pažymėdami simbolį **Šalinti**.

## <a name="explore-the-indexed-customer-fields-table"></a>Susipažinkite su indeksuotų klientų laukų lentele

Ši informacija yra pateikta lentelėje.

- **Pavadinimas**: nurodo atributo pavadinimą, kai jis atsiranda kliento profilio objekte.
- **Duomenų tipas**: nurodo, ar duomenų tipas yra eilutė, skaičius ar data.
- **Įtrauktas į iešką**: nurodo, ar šis atributas gali būti naudojamas ieškant klientų **klientų** puslapyje per **ieškos** lauką.
- **Pridėti filtrą**: nuspręsti, kaip šis atributas gali būti naudojamas filtruojant **klientų** puslapyje.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Duoto atributo filtravimo parametrų redagavimas

**Filtro** meniu, esantis **klientų** puslapyje, gali turėti įvairius atributų lygius (pavyzdžiui, filtruoti klientus galima pagal skirtingas amžiaus grupes).

1. Pasirinkite **pridėti filtrą** duotam atributui **ieškos ir filtro rodyklės** puslapyje. Galite apibrėžti rezultatų skaičių ir eiliškumą, pagal kurį jie bus tvarkomi. Atsižvelgiant į atributo duomenų tipą, pasirodo viena iš toliau nurodytų sričių.

- Eilutės tipo atributai: nurodykite norimų rezultatų skaičių srityje **Eilutės filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.

- Skaičiaus tipo atributai: nurodykite intervalus, įtrauktus srityje **Numerių filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.

- Datos tipo atributai: nurodykite intervalus, įtrauktus srityje **Datos filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.

2. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

3. Kai būsite pasirengę taikyti savo parametrus, pasirinkite **vykdyti**.