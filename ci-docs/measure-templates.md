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
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170783"
---
# <a name="create-measures-from-templates"></a>Priemonių kūrimas naudojant šablonus

Norėdami juos sukurti, naudokite iš anksto nustatytus dažniausiai naudojamų [matų](measures.md) šablonus. Šablonai kuriami pagal žymimys duomenis iš objekto *„Unified Activity“*. Prieš kurdami priemonę pagal šabloną įsitikinkite, kad sukonfigūravote [kleinto veiklą](activities.md).

Matų šablonai palaikomi tik atskirų klientų **aplinkose**. Norėdami sukurti pasirinktinius matus arba kurti priemones nuo B iki B, žiūrėkite [Priemonių kūrimo priemonės naudojimas](measure-builder.md).

Galimi priemonių šablonai:
- Vidutinė operacijų vertė (ATV)
- Bendra operacijos vertė
- Vidutinės dienos pajamos
- Vidutinės mėnesio pajamos
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

1. Sekcijoje **Nustatyti laikotarpį** apibrėžkite duomenų laiko tarpą. Pasirinkite, ar norite, kad nauja priemonė apimtų visą duomenų rinkinį pažymėdami "Visas laikas" arba, jei norite, kad **priemonė sufokusuos** konkretų laiko **periodą**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrano nuotrauka, kurioje rodoma laikotarpio skiltis konfigūruojant priemonę iš šablono.":::

1. Kitoje skiltyje pasirinkite **Pridėti duomenis** ir pasirinkite veiklas bei pažymėkite attitinkamus duomenis iš savo objekto *Unified Activity*.

    1. 1 veiksmas iš 2: skiltyje **Veiklos tipas** pasirinkite norimo naudoti objekto tipą. Dalyje **Veikla** pasirinkite objektus, kuriuos norite susieti, tada pasirinkite **Pirmyn**.
    1. 2 veiksmas iš 2: pasirinkite formulės reikalaujamo komponento atributą iš objekto *Unified Activity*. Pvz., jei operacijos vertė vidutinė, tai operacijos vertę vaiduojantis atributas. Dalyje **Veiklos laiko žyma** pasirinkite atributą iš vieningosios veiklos *objekto*, kuris nurodo veiklos datą ir laiką.
    1. Pasirinkite **Įrašyti**.

    Kai duomenų susiejimas sėkmingas, būsena rodo **Baigta** ir rodomas susietos veiklos ir atributų pavadinimas.

1. Pasirinkite **Vykdyti**, kad apskaičiuotumėte mato rezultatus. Pasirinkite **Įrašyti juodraštį**, jei norite išlaikyti dabartinę konfigūraciją ir paleisti matą vėliau. Rodomas **puslapis Matai**.

## <a name="next-step"></a>Tolesnis veiksmas

Naudokite esamas priemones, kad sukurtumėte [klientų segmentą](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
