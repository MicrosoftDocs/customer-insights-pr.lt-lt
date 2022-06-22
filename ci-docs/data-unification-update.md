---
title: Atnaujinti suvienijimo parametrus
description: Atnaujinkite pasikartojančias taisykles, gretinimo taisykles arba vieningus suvienijimo parametrų laukus.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 590a2996cf8b2b1c6def59b78583169ec1910b59
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844050"
---
# <a name="update-the-unification-settings"></a>Atnaujinti suvienijimo parametrus

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Norėdami peržiūrėti arba pakeisti visus suvienijimo parametrus, kai sukuriamas vieningas profilis, atlikite šiuos veiksmus.

1. Eikite į **"Data** > **Unify"**.

   :::image type="content" source="media/m3_unified.png" alt-text="Puslapio Duomenų suvienodinimas po to, kai duomenys suvienijami, ekrano nuotrauka.":::

   > [!TIP]
   > Plytelė **Atitikimo sąlygos** rodoma tik tuo atveju, jei buvo pasirinkti keli objektai.

1. Pasirinkite, ką norite atnaujinti:
   - [Šaltinio laukai](#edit-source-fields) objektams ar atributams įtraukti arba atributų tipams keisti.
   - [Dubliuoti įrašus](#manage-deduplication-rules), kad būtų galima valdyti deduplication taisykles arba suliejimo nuostatas.
   - [Atitikimo sąlygos](#manage-match-rules), skirtos atnaujinti dviejų ar daugiau objektų atitikimo taisykles.
   - [Vieningi kliento laukai](#manage-unified-fields), skirti sujungti arba neįtraukti laukų. Taip pat galite grupuoti susijusius profilius į klasterius.

1. Atlikę keitimus, pasirinkite kitą parinktį:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Puslapio Duomenų suvienodinimas su paryškintomis parinktimis &quot;Unify&quot; ekrano nuotrauka.":::

   - [Paleiskite atitikimo sąlygas](#run-matching-conditions), kad greitai įvertintumėte savo atitikimo sąlygų kokybę (deduplication ir atitikties taisykles), neatnaujindami vieningo profilio. Parinktis **Vykdyti gretinimo sąlygas nerodoma tik** vienam objektui.
   - [Suvienodinkite klientų profilius](#run-updates-to-the-unified-customer-profile), kad būtų vykdomos gretinimo sąlygos, ir atnaujinkite vieningą kliento profilio objektą nedarydami poveikio priklausomybėms (pvz., sodrinimui, segmentams ar matams). Priklausomi procesai nevykdomi, bet bus atnaujinti, kaip [nurodyta atnaujinimo grafike](system.md#schedule-tab).
   - [Suvienodinti klientų profilius ir priklausomybes](#run-updates-to-the-unified-customer-profile), kad būtų vykdomos gretinimo sąlygos, ir atnaujinti vieningą kliento profilio objektą bei visas priklausomybes (pvz., sodrinimą, segmentus ar priemones). Visi procesai paleidžiami automatiškai.

## <a name="edit-source-fields"></a>Redaguoti šaltinio laukus

Negalite pašalinti atributo ar objekto, jei jie jau buvo suvienyti.

1. Plytelėje **Šaltinis laukuose** pasirinkite **Redaguoti**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Šaltinio laukų puslapio, kuriame rodomas pirminių raktų, susietų ir nesusietų laukų skaičius, ekrano nuotrauka":::

   Rodomas susietų ir nesusietų laukų skaičius.

1. Pasirinkite **Pasirinkti objektus ir laukus**, kad įtrauktumėte kitų atributų ar objektų. Naudokite iešką arba slinkite, kad rastumėte ir pažymėtumėte dominančius atributus ir objektus. Pasirinkite **Taikyti**.

1. Pasirinktinai galite keisti pirminį objekto raktą, atributų tipus ir perjungti **išmanųjį susiejimą** įjungdami arba išjungdami. Daugiau informacijos ieškokite [Select primary key and semantic type for attributes](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pasirinkite Pirmyn **, jei norite keisti deduplikacijos taisykles, arba pasirinkite** Įrašyti ir uždaryti **ir grįžkite į** Naujinti suvienijimo parametrus [.](#update-the-unification-settings)

## <a name="manage-deduplication-rules"></a>Tvarkyti deduplication taisykles

1. Plytelėje Įrašų dublikatas **pasirinkite** **Redaguoti**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Puslapio Dubliuoti įrašus, kuriame rodomas dubliuotų įrašų skaičius, ekrano nuotrauka" lightbox="media/m3_duplicates_edit.png":::

   Rastų įrašų dublikatų skaičius rodomas dalyje **Dublikatai**. Stulpelyje **Įrašai deduplicated** rodoma, kurie objektai turėjo pasikartojančius įrašus ir dubliuotų įrašų procentinę dalį.

1. Jei įtraukėte praturtintą objektą, pasirinkite **Naudoti praturtintus** objektus. Daugiau informacijos ieškokite [Enrichment for data sources](data-sources-enrichment.md).

1. Norėdami valdyti deduplication taisykles, pasirinkite bet kurią iš šių parinkčių:
   - **Sukurkite naują taisyklę**: atitinkamame objekte pasirinkite **Įtraukti taisyklę**. Daugiau informacijos ieškokite [Define deduplication rules](remove-duplicates.md#define-deduplication-rules).
   - **Keisti taisyklės sąlygas**: pasirinkite taisyklę, tada **Redaguokite**. Keiskite laukus, įtraukite arba pašalinkite sąlygas arba įtraukite arba pašalinkite išimtis.
   - **Peržiūra**: pasirinkite taisyklę, tada **Peržiūrėkite**, kad peržiūrėtumėte paskutinius šios taisyklės vykdymo rezultatus.
   - **Išjunkite taisyklę**: pasirinkite taisyklę ir tada **Išjunkite**, kad išlaikytumėte deduplikacijos taisyklę, tuo pačiu neįtraukdami jos į gretinimo procesą.
   - **Dubliuokite taisyklę**: pasirinkite taisyklę ir tada **Dubliuokite**, kad sukurtumėte panašią taisyklę su pakeitimais.
   - **Panaikinkite taisyklę**: pasirinkite taisyklę ir **panaikinkite**.

1. Norėdami pakeisti suliejimo nuostatas, pasirinkite objektą. Nuostatas galite keisti tik tada, jei sukuriama taisyklė.
   1. Pasirinkite **Redaguoti suliejimo nuostatas** ir pakeiskite **parinktį Įrašas, kad išlaikytumėte**.
   1. Norėdami pakeisti atskirų objekto atributų suliejimo nuostatas, pasirinkite **Išsamiau** ir atlikite reikiamus pakeitimus.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Išplėstinių suliejimo nuostatų, rodančių naujausią el. laišką ir išsamiausią adresą, ekrano nuotrauka":::

   1. Pasirinkite **Atlikta**.

1. Pasirinkite Pirmyn **, jei norite keisti gretinimo sąlygas, arba pasirinkite** Įrašyti ir uždaryti **ir grįžkite** į [Naujinti suvienijimo parametrus](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Sugretinimo taisyklių valdymas

Galite konfigūruoti iš naujo ir tiksliai nustatyti daugumą atitikties parametrų. Negalite įtraukti arba naikinti objektų. Atitikties taisyklės netaikomos vienam objektui.

1. Plytelėje **Gretinimo sąlygos** pasirinkite **Redaguoti**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Puslapio Rungtynių taisyklės ir sąlygos su statistika ekrano nuotrauka." lightbox="media/m3_match_edit.png":::

   Puslapyje rodoma atitikties tvarka ir apibrėžtos taisyklės bei ši statistika:
   - **Unikalūs šaltinio įrašai** rodo atskirų šaltinio įrašų, apdorotų paskutiniame sugretinimo vykdyme, skaičių.
   - **Suderinti ir nesuderinti įrašai** išryškina, kiek unikalių įrašų lieka apdorojus gretinimo taisykles.
   - **Tik suderinti įrašai** rodo atitikmenų skaičių visose jūsų sugretintose porose.

1. Norėdami peržiūrėti visų taisyklių rezultatus ir jų rezultatus, pasirinkite **Peržiūrėti paskutinį paleidimą**. Rodomi rezultatai, įskaitant alternatyvius kontaktų ID. Rezultatus galite atsisiųsti.

1. Norėdami peržiūrėti tam tikros taisyklės rezultatus ir balus, pasirinkite taisyklę, tada **Peržiūrėkite**. Rezultatai rodomi. Rezultatus galite atsisiųsti.

1. Norėdami peržiūrėti tam tikros taisyklės sąlygos rezultatus, pasirinkite taisyklę ir tada **Redaguokite**. Srityje Redagavimas pagal sąlygą pasirinkite **Peržiūra**. Rezultatus galite atsisiųsti.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafinis nesuderintų ir suderintų įrašų, įskaitant duomenų sąrašą, atvaizdavimas.":::

1. Jei įtraukėte praturtintą objektą, pasirinkite **Naudoti praturtintus** objektus. Daugiau informacijos ieškokite [Enrichment for data sources](data-sources-enrichment.md).

1. Norėdami valdyti taisykles, pasirinkite bet kurią iš šių parinkčių:
   - **Sukurkite naują taisyklę**: atitinkamame objekte pasirinkite **Įtraukti taisyklę**. Daugiau informacijos ieškokite [Define rules for match pair.](match-entities.md#define-rules-for-match-pairs)
   - **Pakeiskite taisyklių** tvarką, jei nustatėte kelias taisykles: Vilkite ir numeskite taisykles norima tvarka. Daugiau informacijos ieškokite [Nurodykite atitikties tvarką](match-entities.md#specify-the-match-order).
   - **Keisti taisyklės sąlygas**: pasirinkite taisyklę, tada **Redaguokite**. Keiskite laukus, įtraukite arba pašalinkite sąlygas arba įtraukite arba pašalinkite išimtis.
   - **Išjunkite taisyklę**: pasirinkite taisyklę ir tada **Išjunkite**, kad išlaikytumėte atitikties taisyklę, tuo pačiu neįtraukdami jos į gretinimo procesą.
   - **Dubliuokite taisyklę**: pasirinkite taisyklę ir tada **Dubliuokite**, kad sukurtumėte panašią taisyklę su pakeitimais.
   - **Panaikinkite taisyklę**: pasirinkite taisyklę ir **panaikinkite**.

1. Pasirinkite Pirmyn **, jei norite keisti vieningus laukus, arba pasirinkite** Įrašyti ir uždaryti **ir grįžkite į** Naujinti suvienijimo parametrus [.](#update-the-unification-settings)

## <a name="manage-unified-fields"></a>Tvarkyti vieningus laukus

1. Plytelėje Vieningi **kliento laukai** pasirinkite **Redaguoti**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Vieningų klientų laukų ekrano nuotrauka":::

1. Peržiūrėkite kombinuotus ir neįtrauktus laukus ir, jei reikia, atlikite pakeitimus. Įtraukite arba redaguokite CustomerID raktą arba grupės profilius į grupes. Daugiau informacijos ieškokite [Unify customer fields](merge-entities.md).

1. Pasirinkite **Pirmyn**, kad peržiūrėtumėte suvienijimo parametrus ir [atnaujintumėte vieningą profilį ir priklausomybes](#run-updates-to-the-unified-customer-profile), arba pasirinkite Įrašyti ir uždaryti **ir grįžkite** į [Naujinti suvienijimo parametrus](#update-the-unification-settings), kad atliktumėte daugiau pakeitimų.

## <a name="run-matching-conditions"></a>Vykdyti gretinimo sąlygas

Vykdyti gretinimo sąlygas vykdomos tik deduplication ir atitikties taisyklės ir atnaujinami *objektai Deduplication_** ir *ConflationMatchPair*.

1. **Puslapyje Duomenų** > **suvienodinimas** pasirinkite **Vykdyti tik** gretinimo sąlygas.

   Plytelėse **Dubliuoti įrašus** ir **Gretinti sąlygas** rodoma **eilėje** arba **Atnaujinimo** būsena.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kai atitikimo procesas bus baigtas, plytelėje **Gretinimo sąlygos** pasirinkite **Redaguoti**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Apkarpyta Atitikties puslapio pagrindinės metrikos su skaičiais ir išsamia informacija ekrano kopija.":::

1. Norėdami atlikti keitimus, žr [...](#manage-deduplication-rules)[...](#manage-match-rules).

1. Dar kartą paleiskite atitikties procesą arba [paleiskite kliento profilio](#run-updates-to-the-unified-customer-profile) naujinimus.

## <a name="run-updates-to-the-unified-customer-profile"></a>Vykdyti vieningo kliento profilio naujinimus

1. **Puslapyje Duomenų** > **suvienodinimas** pasirinkite:

   - **Suvienodinti klientų profilius**: paleidžia gretinimo sąlygas ir atnaujina vieningą kliento profilio objektą nedarydami poveikio priklausomybėms (pvz., sodrinimui, segmentams ar priemonėms). Priklausomi procesai nevykdomi, bet bus atnaujinti, kaip [nurodyta atnaujinimo grafike](system.md#schedule-tab).

   - **Suvienykite klientų profilius ir priklausomybes**: paleidžia gretinimo sąlygas ir atnaujina vieningą profilį bei visas priklausomybes. Visi procesai paleidžiami automatiškai. Pasibaigus visiems tolesniems procesams, kliento profilis atspindi atnaujintus duomenis.

   Plytelėse **Įrašų dublikatai**, **Gretinimo sąlygos** ir **Vieningi klientų laukai** rodomi **eilėje** arba **atnaujinimo** būsena.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Sėkmingo vykdymo rodymo **puslapyje "Unify** " rezultatai, rodantys vieningų klientų profilių skaičių.
