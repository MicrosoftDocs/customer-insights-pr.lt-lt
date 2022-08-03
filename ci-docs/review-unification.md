---
title: Duomenų suvienijimo peržiūra
description: Peržiūrėkite duomenų suvienijimo veiksmus, kurkite vieningus klientų profilius ir peržiūrėkite rezultatus
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
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139594"
---
# <a name="review-data-unification"></a>Duomenų suvienijimo peržiūra

Šis paskutinis suvienijimo proceso veiksmas rodo proceso veiksmų suvestinę ir suteikia galimybę atlikti pakeitimus prieš kuriant vieningąjį profilį.

:::image type="content" source="media/m3_review.png" alt-text="Peržiūrėkite ir kurkite klientų profilius ekrano kopija.":::

## <a name="review-the-data-unification-steps"></a>Duomenų suvienijimo veiksmų peržiūra

1. Pasirinkite **Redaguoti** atliekant bet kurį duomenų suvienijimo veiksmą, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Kurti klientų profilius**. Puslapis " **Suvienodinti** " rodomas, kai kuriamas vieningas kliento profilis. Visose plytelėse, išskyrus **šaltinio laukus**, rodoma **būsena Eilė arba** **Atnaujinimas**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Puslapio &quot;Unify&quot; su plytelėmis, kuriose rodoma eilė arba atnaujinimas, ekrano nuotrauka.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Suvienijimo algoritmo užbaigimas užtrunka šiek tiek laiko ir jūs negalite pakeisti konfigūracijos, kol ji nebus baigta. Kai suvienijimo procesas baigiamas, suvienodintas kliento profilio objektas, vadinamas *Klientu, pateikiamas* sekcijos **Profiliai** puslapyje **Objektai**. Pirmasis sėkmingas suvienijimo vykdymas sukuria vieningą *kliento* objektą. Visi vėlesni važiavimai išplečia tą objektą.

## <a name="review-the-results-of-data-unification"></a>Duomenų suvienijimo rezultatų peržiūra

Suvienijimo puslapyje Duomenų **suvienodinimas** > **rodomas** suvienodintų klientų profilių skaičius. Kiekvieno suvienijimo proceso veiksmo rezultatai rodomi kiekvienoje plytelėje. Pavyzdžiui, **laukuose** Šaltinis rodomas susietų atributų (laukų) skaičius, o **Pasikartojančių įrašų** skaičius rodo rastų pasikartojančių įrašų skaičių.

:::image type="content" source="media/m3_unified.png" alt-text="Duomenų suvienodinimo puslapio ekrano kopija suvienodinus duomenis.":::

> [!TIP]
> Plytelė Atitikimo **sąlygos** rodoma tik tada, jei buvo pasirinkti keli objektai.

Rekomenduojame peržiūrėti rezultatus, ypač rungtynių taisyklių [kokybę](data-unification-update.md#manage-match-rules), ir, jei reikia, jas patikslinti.

Jei reikia, [pakeiskite suvienijimo parametrus](data-unification-update.md) ir iš naujo paleiskite vieningą profilį.

## <a name="next-step"></a>Kitas veiksmas

Konfigūruokite veiklą, papildymą [,](activities.md) ryšius [ar](enrichment-hub.md) priemones [, kad gautumėte daugiau įžvalgų apie savo klientus.](relationships.md)[...](measures.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
