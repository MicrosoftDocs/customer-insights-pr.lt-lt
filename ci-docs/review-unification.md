---
title: Peržiūrėti duomenų suvienijimą
description: Peržiūrėkite duomenų suvienijimo veiksmus, sukurkite vieningus klientų profilius ir peržiūrėkite rezultatus
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844096"
---
# <a name="review-data-unification"></a>Peržiūrėti duomenų suvienijimą

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis paskutinis suvienijimo proceso veiksmas rodo proceso etapų santrauką ir suteikia galimybę atlikti pakeitimus prieš kuriant vieningą profilį.

:::image type="content" source="media/m3_review.png" alt-text="Klientų profilių peržiūros ir kūrimo ekrano nuotrauka.":::

## <a name="review-the-data-unification-steps"></a>Peržiūrėti duomenų suvienijimo veiksmus

1. Pasirinkite **Redaguoti** bet kuriame duomenų suvienijimo veiksme, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei jus tenkina pasirinkimai, pasirinkite **Kurti klientų profilius**. Puslapis " **Suvienyti** " rodomas kuriant vieningą kliento profilį. Visose plytelėse, išskyrus **šaltinio laukus**, rodoma **eilėje** arba **atnaujinimo** būsena.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Puslapio &quot;Unify&quot; su plytelėmis, kuriose rodoma eilėje arba atnaujinama, ekrano nuotrauka.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Suvienijimo algoritmui užbaigti reikia šiek tiek laiko ir jūs negalite pakeisti konfigūracijos, kol ji nebus baigta. Kai suvienijimo procesas baigiamas, vieningas kliento profilio objektas, vadinamas *Klientu*, pateikiamas **sekcijos** Profiliai **puslapyje Objektai**. Pirmasis sėkmingas suvienijimo vykdymas sukuria vieningą *kliento* objektą. Visi vėlesni paleidimai išplečia tą objektą.

## <a name="review-the-results-of-data-unification"></a>Peržiūrėti duomenų suvienijimo rezultatus

Po suvienijimo **puslapyje "Data** > **Unify** " rodomas vieningų klientų profilių skaičius. Kiekvieno suvienijimo proceso etapo rezultatai rodomi kiekvienoje plytelėje. Pavyzdžiui, **šaltinio laukuose** rodomas susietų atributų (laukų) skaičius, o **įrašų** dublikatų skaičius rodo rastų įrašų dublikatų skaičių.

:::image type="content" source="media/m3_unified.png" alt-text="Puslapio Duomenų suvienodinimas po to, kai duomenys suvienijami, ekrano nuotrauka.":::

> [!TIP]
> Plytelė **Atitikimo sąlygos** rodoma tik tuo atveju, jei buvo pasirinkti keli objektai.

Rekomenduojame peržiūrėti rezultatus, ypač rungtynių [taisyklių](data-unification-update.md#manage-match-rules) kokybę, ir prireikus juos patobulinti.

Jei reikia, [pakeiskite suvienijimo parametrus](data-unification-update.md) ir iš naujo paleiskite vieningą profilį.

## <a name="next-step"></a>Kitas veiksmas

Konfigūruokite [veiklas](activities.md), [sodrinimą](enrichment-hub.md), [ryšius](relationships.md) ar [priemones](measures.md), kad gautumėte daugiau įžvalgų apie savo klientus.

[!INCLUDE[footer-include](includes/footer-banner.md)]
