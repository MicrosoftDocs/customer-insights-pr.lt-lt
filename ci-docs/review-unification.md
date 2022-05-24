---
title: Peržiūrėti duomenų suvienijimą
description: Peržiūrėkite duomenų suvienijimo veiksmus, sukurkite vieningus klientų profilius ir peržiūrėkite rezultatus
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8743035"
---
# <a name="review-data-unification"></a>Peržiūrėti duomenų suvienijimą

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis paskutinis suvienijimo proceso veiksmas rodo proceso etapų santrauką ir suteikia galimybę atlikti pakeitimus prieš kuriant vieningą profilį.

:::image type="content" source="media/m3_review.png" alt-text="Klientų profilių peržiūros ir kūrimo ekrano nuotrauka.":::

## <a name="review-the-data-unification-steps"></a>Peržiūrėti duomenų suvienijimo veiksmus

1. Pasirinkite **Redaguoti** bet kuriame duomenų suvienijimo veiksme, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei jus tenkina pasirinkimai, pasirinkite **Kurti klientų profilius**. Puslapis " **Suvienyti** " rodomas kuriant vieningą kliento profilį. Suvienijimo algoritmui užbaigti reikia šiek tiek laiko ir jūs negalite pakeisti konfigūracijos, kol ji nebus baigta.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Kai suvienijimo procesas baigiamas, vieningas kliento profilio objektas, vadinamas *Klientu*, pateikiamas **sekcijos** Profiliai **puslapyje Objektai**. Pirmasis sėkmingas suvienijimo vykdymas sukuria vieningą *kliento* objektą. Visi vėlesni paleidimai išplečia tą objektą.

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
