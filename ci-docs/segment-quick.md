---
title: Kurkite paprastus segmentus su greitais segmentais
description: Sukurkite paprastus klientų segmentus, kad sugrupuotumėte juos pagal įvairius atributus.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171161"
---
# <a name="create-simple-segments-with-quick-segments"></a>Kurkite paprastus segmentus su greitais segmentais

Spartieji segmentai leidžia jums greitai sukurti paprastus segmentus naudojant vieną operatorių, kad įžvalgos būtų greitesnės. Sparčiuosius segmentus galima naudoti tik atskirų **klientų aplinkose**.

## <a name="create-a-new-segment-with-quick-segments"></a>Naujo segmento su greitais segmentais kūrimas

1. Eikite į **Segmentai**.

1. Pasirinkite **Naujas** > **kurti iš**.
   - Pažymėkite parinktį **Profiliai**, kad sukurtumėte segmentą, pagrįstą *vieningojo klientu* objektu.
   - Pažymėkite parinktį **Matavimai**, kad sukurtumėte segmentą pagal anksčiau jūsų sukurtus matavimus.
   - Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.

1. Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**. Remiantis jūsų pasirinkimu, sistema pateikia skirtingas vertes.
   - Kategoriniuose laukuose rodomi 10 geriausių klientų skaičių. Pasirinkite **Reikšmė** ir pažymėkite **Peržiūra**.
   - Skaitinio atributo atveju sistema rodo, kokia atributo reikšmė patenka į kiekvieno kliento procentilį. Pasirinkite **operatorių** ir **reikšmę**, tada pažymėktie **Peržiūra**.

1. Sistema pateikia apskaičiuotą segmento **dydį**. Pasirinkite, ar generuoti apibrėžtą segmentą, ar grįžti atgal ir pasirinkti kitą lauką.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Sparčiojo segmento pavadinimas ir įvertinimas.":::

1. Pateikite segmento **pavadinimo** ir **išvesties objekto pavadinimą**. Pasirinktinai pridėkite [žymų](work-with-tags-columns.md#manage-tags).

1. Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą. Rodomas puslapis **Segmentai**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Paskesni veiksmai

[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [klientų kortelių integravimu](customer-card-add-in.md) naudoti segmentus kitose programose.

[!INCLUDE [footer-include](includes/footer-banner.md)]
