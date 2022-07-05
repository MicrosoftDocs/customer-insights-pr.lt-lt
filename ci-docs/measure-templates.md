---
title: Priemonių kūrimas naudojant šablonus
description: Apibrėžkite priemones naudodami šablonus įprastiems naudojimo atvejams.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: f6bcdfc45a49c36f22d6ebc6e919f43b27f899d8
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051693"
---
# <a name="create-measures-from-templates"></a>Priemonių kūrimas naudojant šablonus

Norėdami juos sukurti, galite naudoti iš anksto nustatytus dažniausiai naudojamų [priemonių](measures.md) šablonus. Išsamūs šablonų aprašymai ir interaktyvioji patirtis padeda efektyviai matuoti kūrimą. Šablonai kuriami pagal žymimys duomenis iš objekto *„Unified Activity“*. Prieš kurdami priemonę pagal šabloną įsitikinkite, kad sukonfigūravote [kleinto veiklą](activities.md).

Norėdami sukurti pasirinktinius matus, žiūrėkite [Priemonių kūrimo priemonės naudojimas priemonėms kurti nuo pradžių](measure-builder.md).

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

1. Eikite į **"Measures"**.

1. Pasirinkite **Naujas** ir pasirinkite **Rinktis šabloną**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Kai kuriate naują priemonę su šablono paryškinimo parinktimi, išskleidžiamajame meniu yra šiek tiek pasislėpęs.":::

1. Raskite jūsų poreikius atitinkantį šabloną ir pasirinkite **Rinktis šabloną**.

1. Peržiūrėkite reikiamus duomenis ir pasirinkite **Darbo pradžia**, jei turite visus duomenis.

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Priemonės pavadinimas. Nurodykite priemonės pavadinimą. Pasirinktinai prie priemonės pridėkite [žymų](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

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
