---
title: 'Klientų profiliai: ieškos ir filtro rodyklė'
description: Greitai raskite vieningų klientų profilių informaciją ir filtruokite nurodytus atributus.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: fc076e341f744ac2922dcacdf5f20ae8ecbdbaa0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050819"
---
# <a name="customer-profiles-search--filter-index"></a>Klientų profiliai: ieškos ir filtro rodyklė

Kliento duomenų suvienodinimo rezultatas yra kliento profilio objektas, kuris jūsų bendroje klientų bazėje teikia vieningą rodinį. Norėdami greitai [rasti informaciją apie tam tikrą klientą arba klientų grupę](customer-profiles.md), galite sukonfigūruoti **ieškos** ir **filtro** galimybes **klientų** puslapyje. Skaitydami toliau sužinosite, kaip administratoriai gali redaguoti **ieškos ir filtrų rodyklės** puslapyje esančius atributus, pasiekiamus norint ieškoti ir filtruoti.

   :::image type="content" source="media/search-filter.png" alt-text="Ieškos filtras":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Įtraukti laukus ir nurodyti atributus

Jei pirmą kartą nustatote ieškomus atributus kaip administratorius, pirmiausia turite apibrėžti indeksuotus laukus. Patariame pasirinkti visus atributus, pagal kuriuos naudotojai gali ieškoti ir filtruoti klientus **klientų** puslapyje. Galite nurodyti tik per duomenų suvienijimo procesą sukurtus, klientų profilio objekte esančius atributus.

1. Atidarykite puslapį **Klientai** ir pasirinkite **Ieškos ir filtro rodyklė**.

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

3. Kai būsite pasirengę taikyti savo parametrus, pasirinkite **vykdyti**. Apdorotus pakeitimus rasite [kliento kortelėse, esančiose Kliento puslapyje](customer-profiles.md). 

## <a name="next-steps"></a>Kiti veiksmai

Peržiūrėkite [vienigų profilių puslapį](customer-profiles.md) ieškokite profilių arba naudokite indeksuotus laukus, kad pamatytumėte visų vieningųjų profilių antrinį rinkinį.


[!INCLUDE [footer-include](includes/footer-banner.md)]
