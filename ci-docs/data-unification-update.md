---
title: Suvienijimo parametrų naujinimas
description: Atnaujinkite pasikartojančias taisykles, atitikties taisykles arba vieningus laukus suvienijimo parametruose.
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
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245604"
---
# <a name="update-the-unification-settings"></a>Suvienijimo parametrų naujinimas

Norėdami peržiūrėti arba pakeisti suvienijimo parametrus sukūrus vieningąjį profilį, atlikite šiuos veiksmus.

1. Eikite į **Duomenų** > **suvienodinimas**.

   :::image type="content" source="media/m3_unified.png" alt-text="Duomenų suvienodinimo puslapio ekrano kopija suvienodinus duomenis.":::

   > [!TIP]
   > Plytelė Atitikimo **sąlygos** rodoma tik tada, jei buvo pasirinkti keli objektai.

1. Pasirinkite, ką norite atnaujinti:
   - [Šaltinio laukai](#edit-source-fields), skirti objektams ar atributams įtraukti arba atributų tipams keisti.
   - [Pasikartojantys įrašai](#manage-deduplication-rules), skirti tvarkyti dubliavimo taisykles arba suliejimo nuostatas.
   - [Atitikimo sąlygos](#manage-match-rules), kad būtų galima atnaujinti dviejų ar daugiau objektų atitikties taisykles.
   - [Vieningi klientų laukai](#manage-unified-fields), skirti laukams sujungti arba neįtraukti. Taip pat galite sugrupuoti susijusius profilius į grupes.

1. Atlikę pakeitimus, pasirinkite kitą parinktį:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Puslapio Duomenys suvienodinti su paryškintomis parinktimis Suvienodinti ekrano kopija.":::

   - [Vykdykite atitikimo sąlygas](#run-matching-conditions), kad greitai įvertintumėte atitikimo sąlygų (dubliavimo ir atitikties taisyklių) kokybę neatnaujindami vieningo profilio. Parinktis **Vykdyti tik atitikimo sąlygas** nerodoma vienam objektui.
   - [Suvienodinkite klientų profilius](#run-updates-to-the-unified-customer-profile), kad būtų vykdomos atitikties sąlygos, ir atnaujinkite vieningą kliento profilio objektą nedarydami įtakos priklausomybėms (pvz., papildymams, segmentams ar matams). Priklausomi procesai nevykdomi, bet bus atnaujinti, kaip [apibrėžta atnaujinimo grafike](schedule-refresh.md).
   - [Suvienodinti klientų profilius ir priklausomybes](#run-updates-to-the-unified-customer-profile), kad būtų vykdomos atitikties sąlygos, ir atnaujinkite vieningą kliento profilio objektą bei visas priklausomybes (pvz., papildymus, segmentus ar matus). Visi procesai automatiškai paleidžiami iš naujo.

## <a name="edit-source-fields"></a>Šaltinio laukų redagavimas

Negalite pašalinti atributo arba objekto, jei jie jau buvo suvienodinti.

1. Pasirinkite **Redaguoti** plytelėje Šaltinio **laukai**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Šaltinio laukų puslapio, kuriame rodomas pirminių raktų, susietų ir neuždarytų laukų skaičius, ekrano kopija":::

   Rodomas susietų ir neuždengtų laukų skaičius.

1. Pasirinkite **Pasirinkti objektus ir laukus**, kad įtrauktumėte kitų atributų arba objektų. Naudokite iešką arba slinkite, kad rastumėte ir pažymėtumėte dominančius atributus ir objektus. Pasirinkite **Taikyti**.

1. Pasirinktinai galite pakeisti pirminį objekto raktą, atributų tipus ir įjungti **arba išjungti išmanųjį susiejimą**. Daugiau informacijos ieškokite [Atributų](map-entities.md#select-primary-key-and-semantic-type-for-attributes) pirminio rakto ir semantinio tipo pasirinkimas.

1. Pasirinkite **Pirmyn**, kad atliktumėte dublikatų taisyklių keitimus, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Kopijavimo taisyklių valdymas

1. Pasirinkite **Redaguoti** plytelėje **Pasikartojantys įrašai**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Besidubliuojančių įrašų puslapio, kuriame rodomas besidubliuojančių įrašų skaičius, ekrano nuotrauka" lightbox="media/m3_duplicates_edit.png":::

   Rastų pasikartojančių įrašų skaičius rodomas dalyje **Dublikatai**. Stulpelyje **Dubliuojami** įrašai rodoma, kurie objektai turėjo pasikartojančius įrašus ir pasikartojančių įrašų procentą.

1. Jei įtraukėte papildytą objektą, pasirinkite **Naudoti papildytus objektus**. Daugiau informacijos ieškokite [Duomenų šaltinių](data-sources-enrichment.md) papildymas.

1. Norėdami valdyti dubliavimo taisykles, pasirinkite bet kurią iš šių parinkčių:
   - **Naujos taisyklės** kūrimas: pasirinkite **Įtraukti taisyklę** po atitinkamu objektu. Daugiau informacijos ieškokite [Dubliavimo taisyklių apibrėžimas](remove-duplicates.md#define-deduplication-rules).
   - **Keisti taisyklės sąlygas**: pasirinkite taisyklę, tada – **Redaguoti**. Keiskite laukus, įtraukite arba pašalinkite sąlygas arba įtraukite ar pašalinkite išimtis.
   - **Peržiūra**: pasirinkite taisyklę ir peržiūrėkite taisyklę, tada **Peržiūra**, kad peržiūrėtumėte paskutinius šios taisyklės vykdymo rezultatus.
   - **Išjungti taisyklę**: pažymėkite taisyklę, tada **Išjunkite**, kad išsaugotumėte dubliavimo taisyklę, neįtraukdami jos į atitikties procesą.
   - **Kopijuoti taisyklę**: pažymėkite taisyklę, tada **Dubliuoti**, kad sukurtumėte panašią taisyklę su pakeitimais.
   - **Naikinti taisyklę**: pažymėkite taisyklę, tada – **Naikinti**.

1. Norėdami pakeisti suliejimo nuostatas, pasirinkite objektą. Nuostatas galite keisti tik sukūrę taisyklę.
   1. Pasirinkite **Redaguoti suliejimo nuostatas** ir pakeiskite **parinktį Įrašyti, kad išsaugotumėte**.
   1. Norėdami pakeisti atskirų objekto atributų suliejimo nuostatas, pasirinkite **Išsamiau** ir atlikite reikiamus keitimus.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Išplėstinių suliejimo nuostatų, kuriose rodomas naujausias el. paštas ir išsamiausias adresas, ekrano nuotrauka":::

   1. Pasirinkite **Atlikta**.

1. Pasirinkite **Pirmyn**, kad atliktumėte atitinkamų sąlygų keitimus, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į Naujinti [suvienijimo parametrus](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Sugretinimo taisyklių valdymas

Galite konfigūruoti iš naujo ir tiksliai nustatyti daugumą atitikties parametrų. Negalite pridėti arba panaikinti objektų. Atitikties taisyklės netaikomos vienam objektui.

1. Pasirinkite **Redaguoti** plytelėje Atitikimo **sąlygos**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Atitikties taisyklių ir sąlygų puslapio su statistika ekrano nuotrauka." lightbox="media/m3_match_edit.png":::

   Puslapyje rodoma atitikties tvarka ir apibrėžtos taisyklės bei ši statistika:
   - **Unikalūs šaltinio įrašai** rodo atskirų šaltinio įrašų, apdorotų paskutiniame sugretinimo vykdyme, skaičių.
   - **Suderinti ir nesuderinti įrašai** išryškina, kiek unikalių įrašų lieka apdorojus gretinimo taisykles.
   - **Tik suderinti įrašai** rodo atitikmenų skaičių visose jūsų sugretintose porose.

1. Norėdami peržiūrėti visų taisyklių rezultatus ir jų balus, pasirinkite **Peržiūrėti paskutinį bėgimą**. Rodomi rezultatai, įskaitant alternatyvius kontaktų ID. Galite atsisiųsti rezultatus.

1. Norėdami peržiūrėti konkrečios taisyklės rezultatus ir balus, pasirinkite taisyklę, tada – **Peržiūra**. Rodomi rezultatai. Galite atsisiųsti rezultatus.

1. Norėdami peržiūrėti tam tikros taisyklės sąlygos rezultatus, pasirinkite taisyklę ir tada **Redaguoti**. Redagavimo srityje pasirinkite **Peržiūra** su sąlyga. Galite atsisiųsti rezultatus.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafinis nesuderintų ir suderintų įrašų atvaizdavimas, įskaitant duomenų sąrašą.":::

1. Jei įtraukėte papildytą objektą, pasirinkite **Naudoti papildytus objektus**. Daugiau informacijos ieškokite [Duomenų šaltinių](data-sources-enrichment.md) papildymas.

1. Norėdami valdyti taisykles, pasirinkite bet kurią iš šių parinkčių:
   - **Naujos taisyklės** kūrimas: pasirinkite **Įtraukti taisyklę** po atitinkamu objektu. Daugiau informacijos ieškokite [Atitikties porų taisyklių apibrėžimas](match-entities.md#define-rules-for-match-pairs).
   - **Pakeiskite taisyklių** tvarką, jei apibrėžėte kelias taisykles: vilkite ir numeskite taisykles į norimą tvarką. Daugiau informacijos ieškokite [Atitikties tvarkos](match-entities.md#specify-the-match-order) nurodymas.
   - **Keisti taisyklės sąlygas**: pasirinkite taisyklę, tada – **Redaguoti**. Keiskite laukus, įtraukite arba pašalinkite sąlygas arba įtraukite ar pašalinkite išimtis.
   - **Išjungti taisyklę**: pasirinkite taisyklę, tada – **Išjungti**, kad išlaikytumėte atitikties taisyklę, neįtraukdami jos į susiejimo procesą.
   - **Kopijuoti taisyklę**: pažymėkite taisyklę, tada **Dubliuoti**, kad sukurtumėte panašią taisyklę su pakeitimais.
   - **Naikinti taisyklę**: pažymėkite taisyklę, tada – **Naikinti**.

1. Pasirinkite **Pirmyn**, kad atliktumėte vieningųjų laukų keitimus, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Vieningųjų laukų valdymas

1. Pasirinkite **Redaguoti** vieningųjų **klientų laukų** plytelėje.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Vieningųjų kliento laukų ekrano kopija":::

1. Peržiūrėkite sujungtus ir neįtrauktus laukus ir, jei reikia, atlikite visus pakeitimus. Įtraukite arba redaguokite "CustomerID" raktą arba grupės profilius į grupes. Daugiau informacijos ieškokite [Suvienodinti klientų laukus](merge-entities.md).

1. Pasirinkite **Pirmyn**, kad peržiūrėtumėte suvienijimo parametrus ir [atnaujintumėte vieningąjį profilį bei priklausomybes](#run-updates-to-the-unified-customer-profile), arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-the-unification-settings), kad atliktumėte daugiau keitimų.

## <a name="run-matching-conditions"></a>Bėgimo atitikimo sąlygos

Vykdyti atitikimo sąlygas vykdomos tik dubliavimo ir atitikties taisyklės ir atnaujinami *objektai Deduplication_**" ir *"ConflationMatchPair* ".

1. Puslapyje Duomenų **suvienodinimas** > **pasirinkite** **Vykdyti tik** atitikimo sąlygas.

   Pasikartojančių **įrašų** ir **atitikimo sąlygų** plytelėse rodoma **būsena Eilė arba** **Atnaujinimas**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kai atitikimo procesas bus baigtas, **pasirinkite Redaguoti** plytelėje Atitikimo sąlygos.**·**

   :::image type="content" source="media/match-KPIs.png" alt-text="Apkarpyta Atitikties puslapio pagrindinės metrikos su skaičiais ir išsamia informacija ekrano kopija.":::

1. Norėdami atlikti keitimus, žiūrėkite [Kopijavimo taisyklių](#manage-deduplication-rules) valdymas arba [Atitikties taisyklių](#manage-match-rules) valdymas.

1. Dar kartą paleiskite atitikties procesą arba [paleiskite kliento profilio](#run-updates-to-the-unified-customer-profile) naujinimus.

## <a name="run-updates-to-the-unified-customer-profile"></a>Vieningojo kliento profilio naujinimų vykdymas

1. Puslapyje Duomenų **suvienodinimas** > **pasirinkite**:

   - **Klientų profilių** suvienodinimas: vykdo atitikimo sąlygas ir naujina vieningą kliento profilio objektą, nedarydamas įtakos priklausomybėms (pvz., papildymams, segmentams ar matams). Priklausomi procesai nevykdomi, bet bus atnaujinti, kaip [apibrėžta atnaujinimo grafike](schedule-refresh.md).

   - **Klientų profilių ir priklausomybių** suvienodinimas: vykdo atitikimo sąlygas ir atnaujina vieningąjį profilį bei visas priklausomybes. Visi procesai automatiškai paleidžiami iš naujo. Užbaigus visus tolesnius procesus, kliento profilis atspindi atnaujintus duomenis.

   Laukų **Dublikatas įrašai**, **Atitikimo sąlygos** ir **vieningųjų klientų** parinktys rodo **būseną Eilė arba** **Atnaujinimas**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Sėkmingo vykdymo rezultatai rodomi puslapyje "Unify"**,** kuriame rodomas suvienodintų klientų profilių skaičius.
