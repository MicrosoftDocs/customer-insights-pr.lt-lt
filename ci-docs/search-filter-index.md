---
title: Klientų profilių ieškos ir filtro indekso valdymas
description: Greitai raskite vieningų klientų profilių informaciją ir filtruokite nurodytus atributus.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187919"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Klientų profilių ieškos ir filtro indekso valdymas

Kliento duomenų suvienodinimo rezultatas yra *kliento* objektas, kuris pateikia vieningą rodinį į bendrą klientų bazę. Kad vartotojai galėtų greitai [rasti informaciją apie konkretų klientą arba klientų](customer-profiles.md) grupę, administratorius turi sukonfigūruoti **puslapio Klientai** ieškos **ir** filtravimo **galimybes**.

   :::image type="content" source="media/search-filter.png" alt-text="Ieškos filtras":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Atributų, kuriuose galima ieškoti, ir indeksuotų laukų apibrėžimas

Jei pirmą kartą kaip administratorius apibrėžia atributus, kuriuose galima ieškoti, pirmiausia apibrėžkite indeksuotus laukus. Patariame pasirinkti visus atributus, pagal kuriuos naudotojai gali ieškoti ir filtruoti klientus **klientų** puslapyje. Galima nurodyti tik atributus, esančius objekte *Klientas*, sukurtame duomenų suvienijimo proceso metu.

1. Eikite į **Klientai ir pasirinkite** Paieškos ir filtro **indeksas**.

1. Pasirinkite **+ Pridėti**.

1. Pasirinkite sąrašo atributus, kuriuos norite įtraukti kaip indeksuotus laukus, ir spustelėkite **Taikyti**.

1. Norėdami įtraukti daugiau atributų, pasirinkite **Įtraukti**. Norėdami pašalinti pasirinktą atributą, pasirinkite atributą, tada **Naikinti**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Ieškos ir filtro indekso puslapis.":::

1. Pasirinkite **Vykdyti**, kai būsite pasirengę taikyti paieškos ir filtro nustatymus. Apdoroję pakeitimus, peržiūrėkite juos kliento kortelėse, esančiose [puslapyje](customer-profiles.md) Klientas.

## <a name="define-filtering-options-for-a-given-attribute"></a>Nurodyto atributo filtravimo parinkčių apibrėžimas

Nustatykite laukus, kuriuos galima naudoti klientams **filtruoti puslapyje Klientai**.

1. Eikite į **Klientai ir pasirinkite** Paieškos ir filtro **indeksas**.

1. Pasirinkite atributą ir **Pridėti filtrą**. Apibrėžkite rezultatų skaičių ir tvarką, kuria jie bus tvarkomi. Atsižvelgiant į atributo duomenų tipą, rodoma viena iš šių sričių.

   - Eilutės tipo atributai: nurodykite norimų rezultatų **skaičių srityje Eilučių filtras** ir užsakymo strategiją, pagal kurią jie bus tvarkomi.

   - Skaitinio tipo atributai: nurodykite intervalus, įtrauktus į **sritį Skaičių filtras**, ir užsakymo strategiją, pagal kurią jie bus tvarkomi.

   - Datos tipo atributai: nurodykite intervalus, įtrauktus į **sritį Datos filtras**, ir užsakymo strategiją, pagal kurią jie bus tvarkomi.

1. Pasirinkite **Gerai**. Pakartokite su visais atributais, pagal kuriuos norite filtruoti.

1. Pasirinkite **Vykdyti**, kai būsite pasirengę taikyti paieškos ir filtro nustatymus. Apdoroję pakeitimus, peržiūrėkite juos kliento kortelėse, esančiose [puslapyje](customer-profiles.md) Klientas.

## <a name="view-indexed-customer-fields"></a>Indeksuotų klientų laukų peržiūra

Puslapyje **Ieškos ir filtro indeksas** rodoma ši informacija:

- **Pavadinimas**: nurodo atributo pavadinimą taip, kaip jis rodomas objekte *Klientas*.
- **Duomenų tipas**: nurodo, ar duomenų tipas yra eilutė, skaičius ar data.
- **Įtrauktas į iešką**: nurodo, ar šis atributas gali būti naudojamas ieškant klientų **klientų** puslapyje per **ieškos** lauką.
- **Pridėti filtrą**: nuspręsti, kaip šis atributas gali būti naudojamas filtruojant **klientų** puslapyje.

## <a name="next-steps"></a>Paskesni veiksmai

Peržiūrėkite [vienigų profilių puslapį](customer-profiles.md) ieškokite profilių arba naudokite indeksuotus laukus, kad pamatytumėte visų vieningųjų profilių antrinį rinkinį.

[!INCLUDE [footer-include](includes/footer-banner.md)]
