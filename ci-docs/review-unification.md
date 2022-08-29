---
title: Duomenų suvienijimo peržiūra
description: Peržiūrėkite duomenų suvienijimo veiksmus, kurkite vieningus klientų profilius ir peržiūrėkite rezultatus
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303977"
---
# <a name="review-data-unification"></a>Duomenų suvienijimo peržiūra

Peržiūrėkite keitimų suvestinę, sukurkite vieningą profilį ir peržiūrėkite rezultatus.

## <a name="review-and-create-customer-profiles"></a>Peržiūrėti ir kurti klientų profilius

Šis paskutinis suvienijimo proceso veiksmas rodo proceso veiksmų suvestinę ir suteikia galimybę atlikti pakeitimus prieš kuriant vieningąjį profilį.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Peržiūrėkite ir kurkite klientų profilius ekrano kopija.":::

1. Pasirinkite **Redaguoti** atliekant bet kurį duomenų suvienijimo veiksmą, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Kurti klientų profilius** (arba **Kurti paskyros profilius** nuo B iki B). Puslapis " **Suvienodinti** " rodomas, kai kuriamas vieningas kliento profilis.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Puslapio &quot;Unify&quot; su plytelėmis, kuriose rodoma eilė arba atnaujinimas, ekrano nuotrauka.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Suvienijimo algoritmo užbaigimas užtrunka šiek tiek laiko ir jūs negalite pakeisti konfigūracijos, kol ji nebus baigta.

## <a name="view-the-results-of-data-unification"></a>Duomenų suvienijimo rezultatų peržiūra

Po suvienijimo **puslapyje Duomenų** > **suvienodinimas** rodomas suvienodintų klientų profilių (arba B–B paskyros profilių) skaičius. Kiekvieno suvienijimo proceso veiksmo rezultatai rodomi kiekvienoje plytelėje. Pavyzdžiui, **laukuose** Šaltinis rodomas susietų atributų (laukų) skaičius, o **Pasikartojančių įrašų** skaičius rodo rastų pasikartojančių įrašų skaičių.

:::image type="content" source="media/m3_unified.png" alt-text="Duomenų suvienodinimo puslapio ekrano kopija suvienodinus duomenis.":::

> [!TIP]
> Plytelė Atitikimo **sąlygos** rodoma tik tada, jei buvo pasirinkti keli objektai.

Rekomenduojame peržiūrėti rezultatus, ypač rungtynių taisyklių [kokybę](data-unification-update.md#manage-match-rules), ir, jei reikia, jas patikslinti.

Jei reikia, [pakeiskite suvienijimo parametrus](data-unification-update.md) ir iš naujo paleiskite vieningą profilį.

### <a name="verify-output-entities-from-data-unification"></a>Išvesties objektų tikrinimas iš duomenų suvienijimo

Eikite į **Duomenų** > **objektai**, kad patikrintumėte išvesties objektus.

Vieningas kliento profilio objektas, vadinamas *Klientu*, rodomas sekcijoje **Profiliai**. Pirmasis sėkmingas suvienijimo vykdymas sukuria vieningą *kliento* objektą. Visi vėlesni važiavimai išplečia tą objektą.

Kopijavimo ir sujungimo objektai sukuriami ir rodomi **skyriuje Sistema**. Kiekvienam šaltinio objektui sukuriamas besidubliuojantis objektas su pavadinimu **Deduplication_DataSource_Entity**. Objekte **ConflationMatchPairs** yra informacijos apie kelių objektų atitikmenis.

Dublikatų naikinimo išvesties objektas turi šią informaciją:
- ID/Raktai
  - Laukai Pirminis raktas ir Alternatyvus ID. Alternatyvųjį ID lauką sudaro visi alternatyvūs įrašo ID.
  - Dublikatų naikinimo grupės ID lauke rodoma grupė arba klasteris, nustatytas objektu, grupuojantis visus panašius įrašus pagal nurodytus dublikatų naikinimo laukus. Jis naudojamas sistemos apdorojimo tikslais. Jei nėra nurodytų neautomatiniu būdu nurodomų dublikatų naikinimo taisyklių ir taikomos sistemos apibrėžtos dublikatų naikinimo taisyklės, šis laukas gali būti nerandamas dublikatų naikinimo išvesties objektui.
  - „Deduplication_WinnerId”: Šiame lauke yra nustatytų grupių arba grupių laimėtojo ID. Jei „Deduplication_WinnerId” reikšmė yra tokia pati kaip įrašo pirminio rakto reikšmė, tai reiškia, kad įrašas yra nugalėtojas.
- Laukai, naudojami dublikatų naikinimo taisyklėms apibrėžti.
- Taisyklių ir Rezultato laukeliai žymi gretinimo algoritmo grąžintą rezultatą ir, kurios iš dublikatų naikinimo taisyklių buvo taikomos.

## <a name="next-step"></a>Kitas veiksmas

- Jei naudojate nuo B iki B, pasirinktinai atlikite [kontaktinį suvienijimą](data-unification-contacts.md).

- Jei naudojate "B-to-C", sukonfigūruokite [veiklą](activities.md), [papildymus](enrichment-hub.md), [ryšius](relationships.md) ar [priemones](measures.md), kad gautumėte daugiau įžvalgų apie savo klientus.

[!INCLUDE[footer-include](includes/footer-banner.md)]
