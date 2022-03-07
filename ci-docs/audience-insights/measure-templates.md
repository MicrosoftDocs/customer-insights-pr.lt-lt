---
title: Kurti priemones iš šablonų
description: Apibrėžti priemones, naudojant šablonus bendro naudojimo atvejams.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359962"
---
# <a name="use-a-template-to-build-a-measure"></a>Šablono naudojimas priemonei kurti

Norėdami juos sukurti, galite naudoti iš anksto apibrėžtus dažniausiai naudojamų [priemonių](measures.md) šablonus. Išsamūs šablonų aprašymai ir interaktyvioji patirtis padeda efektyviai matuoti kūrimą. Šablonai kuriami pagal žymimys duomenis iš objekto *„Unified Activity“*. Prieš kurdami priemonę pagal šabloną įsitikinkite, kad sukonfigūravote [kleinto veiklą](activities.md).

Norėdami kurti pasirinktines priemones, žr [...](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Galimi priemonių šablonai: 
- Vidutinė operacijų vertė (ATV)
- Bendra operacijos vertė
- Vidutinės dienos pajamos
- Vidutinės metų pajamos
- Operacijų skaičius
- Gauti lojalumo taškai
- Panaudoti lojalumo taškai
- Lojalumo taškų balansas
- Aktyvaus kliento veiklos trukmė
- Lojalumo narystės trukmė
- Laikas nuo paskutinio pirkimo

## <a name="build-a-new-measure-using-a-template"></a>Naujos priemonės kūrimas naudojant šabloną

1. Eikite į **priemones**.

1. Pasirinkite **Naujas** ir pasirinkite **Rinktis šabloną**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Kai kuriate naują priemonę su šablono paryškinimo parinktimi, išskleidžiamajame meniu yra šiek tiek pasislėpęs.":::

1. Raskite jūsų poreikius atitinkantį šabloną ir pasirinkite **Rinktis šabloną**.

1. Peržiūrėkite reikiamus duomenis ir pasirinkite **Darbo pradžia**, jei turite visus duomenis.

1. Srityje **Pavadinimo redagavimas** nustatykite savo priemonės pavadinimą ir išvesties objektą. 

1. Pasirinkite **Atlikta**.

1. Skiltyje **Laikotarpio nustatymas** apibrėžkite naudojamų duomenų laiko tarpą. Pasirinkite, ar norite, kad nauja priemonė apimtų visą duomenų rinkinį pažymėdami "Visas laikas" arba, jei norite, kad **priemonė sufokusuos** konkretų laiko **periodą**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrano nuotrauka, kurioje rodoma laikotarpio skiltis konfigūruojant priemonę iš šablono.":::

1. Kitoje skiltyje pasirinkite **Pridėti duomenis** ir pasirinkite veiklas bei pažymėkite attitinkamus duomenis iš savo objekto *Unified Activity*.

    1. 1 veiksmas iš 2: skiltyje **Veiklos tipas** pasirinkite norimo naudoti objekto tipą. Skiltyje **Veiklos** pasirinkite objektus, kuriuos norite žymėti.
    1. 2 veiksmas iš 2: pasirinkite formulės reikalaujamo komponento atributą iš objekto *Unified Activity*. Pvz., jei operacijos vertė vidutinė, tai operacijos vertę vaiduojantis atributas. **Veiklos laiko žymai** pasirinkite atributą iš objekto „Unified Activity“, kuriame vaizduojama veiklos data ir laikas.
   
1. Sėkmingai pažymėjė duomenis būseną galite matyti kaip **Baigta** kartu su pažymėtų veiklų ir atributų pavadinimu.

1. Dabar galite pasirinkti **Vykdyti** ir apskaičiuoti priemonės rezultatus. Jei paiešką vėliau norėsite susiaurinti, pasirinkite **Išsaugoti juodarštį**.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Ši funkcija galima tik priemonėms, sukurtoms aplinkose su atskirais klientais kaip pirmine tiksline auditorija.

---
