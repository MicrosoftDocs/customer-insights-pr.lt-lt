---
title: Kliento, abonemento arba kontaktų suvienijimo parametrų naujinimas
description: Atnaujinkite pasikartojančias taisykles, atitikties taisykles arba vieningus laukus kliento arba abonemento suvienijimo parametruose.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304345"
---
# <a name="update-unification-settings"></a>Suvienijimo parametrų naujinimas

Norėdami peržiūrėti arba pakeisti suvienijimo parametrus sukūrus vieningąjį profilį, atlikite šiuos veiksmus.

1. Eikite į **Duomenų** > **suvienodinimas**.

   Atskiriems klientams (nuo B iki C) **puslapyje Suvienodinti** rodomas suvienodintų klientų profilių ir plytelių skaičius kiekvienam suvienijimo veiksmui.

   :::image type="content" source="media/m3_unified.png" alt-text="Duomenų suvienodinimo puslapio ekrano kopija suvienodinus duomenis." lightbox="media/m3_unified.png":::

   Verslo paskyrų (nuo B iki B) **puslapyje Suvienodinti rodomas suvienodintų** paskyros profilių ir plytelių skaičius kiekvienam paskyros suvienijimo veiksmui. Jei kontaktai buvo suvienodinti, rodomas suvienodintų kontaktų profilių ir plytelių skaičius kiekvienam kontakto suvienijimo veiksmui. Pasirinkite atitinkamą plytelę dalyje **Suvienodinti paskyras** arba **Suvienodinti kontaktus (peržiūra),** atsižvelgdami į tai, ką norite naujinti.

   :::image type="content" source="media/b2b_unified.png" alt-text="Puslapio Duomenų suvienodinimas ekrano nuotrauka suvienodinus paskyrą ir kontaktinius duomenis." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Plytelė Atitikimo **sąlygos** rodoma tik tada, jei buvo pasirinkti keli objektai.

1. Pasirinkite, ką norite atnaujinti:
   - [Šaltinio laukai](#edit-source-fields), skirti objektams ar atributams įtraukti arba atributų tipams keisti.
   - [Pasikartojantys įrašai](#manage-deduplication-rules), skirti tvarkyti dubliavimo taisykles arba suliejimo nuostatas.
   - [Atitikimo sąlygos](#manage-match-rules), kad būtų galima atnaujinti dviejų ar daugiau objektų atitikties taisykles.
   - [Vieningi klientų laukai](#manage-unified-fields), skirti laukams sujungti arba neįtraukti. Taip pat galite sugrupuoti susijusius profilius į grupes.
   - [Semantiniai laukai](#manage-semantic-fields-for-unified-contacts), skirti valdyti vieningų kontaktų laukų semantinius tipus.
   - [Ryšiai](#manage-contact-and-account-relationships), skirti kontakto ir abonemento ryšiui valdyti.

1. Atlikę pakeitimus, pasirinkite kitą parinktį:

   - [Vykdykite atitikimo sąlygas](#run-matching-conditions), kad greitai įvertintumėte atitikimo sąlygų (dubliavimo ir atitikties taisyklių) kokybę neatnaujindami vieningo profilio. Parinktis **Vykdyti tik atitikimo sąlygas** nerodoma vienam objektui.
   - [Suvienodinkite profilius](#run-updates-to-the-unified-profile), kad būtų vykdomos atitikties sąlygos, ir atnaujinkite vieningą profilio objektą nedarydami įtakos priklausomybėms (pvz., papildymams, segmentams ar matams). Priklausomi procesai nevykdomi, bet bus atnaujinti, kaip [apibrėžta atnaujinimo grafike](schedule-refresh.md).
   - [Suvienodinkite profilius ir priklausomybes](#run-updates-to-the-unified-profile), kad paleistumėte atitikimo sąlygas, atnaujintumėte vieningą profilio objektą ir atnaujintumėte visas priklausomybes (pvz., papildymus, segmentus ar matus). Visi procesai automatiškai paleidžiami iš naujo. B-to-B suvienijimas vykdomas tiek abonemento, tiek kontaktų objektuose, atnaujinančiuose vieninguosius profilius.

## <a name="edit-source-fields"></a>Šaltinio laukų redagavimas

Negalite pašalinti atributo arba objekto, jei jie jau buvo suvienodinti.

1. Pasirinkite **Redaguoti** plytelėje Šaltinio **laukai**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Šaltinio laukų puslapio, kuriame rodomas pirminių raktų, susietų ir neuždarytų laukų skaičius, ekrano kopija":::

   Rodomas susietų ir neuždengtų laukų skaičius.

1. Norėdami įtraukti kitų atributų arba objektų, pasirinkite **Pasirinkti objektus ir laukus**.

1. Pasirinktinai galite pakeisti pirminį objekto raktą, atributų tipus ir įjungti **arba išjungti išmanųjį susiejimą**. Daugiau informacijos ieškokite [Šaltinio laukų](map-entities.md) pasirinkimas.

1. Pasirinkite **Pirmyn**, kad pakeistumėte dubliavimo taisykles, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-unification-settings).

## <a name="manage-deduplication-rules"></a>Kopijavimo taisyklių valdymas

1. Pasirinkite **Redaguoti** plytelėje **Pasikartojantys įrašai**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Besidubliuojančių įrašų puslapio, kuriame rodomas besidubliuojančių įrašų skaičius, ekrano nuotrauka" lightbox="media/m3_duplicates_edit.png":::

   Rastų pasikartojančių įrašų skaičius rodomas dalyje **Dublikatai**. Stulpelyje **Dubliuojami** įrašai rodoma, kurie objektai turėjo pasikartojančius įrašus ir pasikartojančių įrašų procentą.

1. Norėdami naudoti papildytąjį objektą, pasirinkite **Naudoti papildytuosius objektus**. Daugiau informacijos ieškokite [Duomenų šaltinių papildymas](data-sources-enrichment.md).

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

   1. Pasirinkite **Atlikta**.

1. Pasirinkite **Pirmyn**, kad atliktumėte atitinkamų sąlygų keitimus, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į Naujinti [suvienijimo parametrus](#update-unification-settings).

## <a name="manage-match-rules"></a>Sugretinimo taisyklių valdymas

Galite konfigūruoti iš naujo ir tiksliai nustatyti daugumą atitikties parametrų. Negalite pridėti arba panaikinti objektų. Atitikties taisyklės netaikomos vienam objektui.

1. Pasirinkite **Redaguoti** plytelėje Atitikimo **sąlygos**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Atitikties taisyklių ir sąlygų puslapio su statistika ekrano nuotrauka." lightbox="media/m3_match_edit.png":::

   Puslapyje rodoma atitikties tvarka ir apibrėžtos taisyklės bei ši statistika:
   - **Unikalaus šaltinio įrašai** rodo atskirų šaltinio įrašų, kurie buvo apdoroti paskutinio atitikties vykdymo metu, skaičių.
   - **Suderinti ir nesuderinti įrašai** paryškina, kiek unikalių įrašų lieka apdorojus atitikties taisykles.
   - **Suderinti įrašai rodo tik** rungtynių skaičių visose rungtynių porose.

1. Norėdami peržiūrėti visų taisyklių rezultatus ir jų balus, pasirinkite **Peržiūrėti paskutinį bėgimą**. Rodomi rezultatai, įskaitant alternatyvius kontaktų ID. Galite atsisiųsti rezultatus.

1. Norėdami peržiūrėti konkrečios taisyklės rezultatus ir balus, pasirinkite taisyklę, tada – **Peržiūra**. Rodomi rezultatai. Galite atsisiųsti rezultatus.

1. Norėdami peržiūrėti tam tikros taisyklės sąlygos rezultatus, pasirinkite taisyklę ir tada **Redaguoti**. Redagavimo srityje pasirinkite **Peržiūra** su sąlyga. Galite atsisiųsti rezultatus.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Grafinis nesuderintų ir suderintų įrašų atvaizdavimas, įskaitant duomenų sąrašą.":::

1. Jei įtraukėte papildytą objektą, pasirinkite **Naudoti papildytus objektus**. Daugiau informacijos ieškokite [Duomenų šaltinių papildymas](data-sources-enrichment.md).

1. Norėdami valdyti taisykles, pasirinkite bet kurią iš šių parinkčių:
   - **Naujos taisyklės** kūrimas: pasirinkite **Įtraukti taisyklę** po atitinkamu objektu. Daugiau informacijos ieškokite [Atitikties porų taisyklių apibrėžimas](match-entities.md#define-rules-for-match-pairs).
   - **Pakeiskite taisyklių** tvarką, jei apibrėžėte kelias taisykles: vilkite ir numeskite taisykles į norimą tvarką. Daugiau informacijos ieškokite [Atitikties tvarkos](match-entities.md#specify-the-match-order) nurodymas.
   - **Keisti taisyklės sąlygas**: pasirinkite taisyklę, tada – **Redaguoti**. Keiskite laukus, įtraukite arba pašalinkite sąlygas arba įtraukite ar pašalinkite išimtis.
   - **Išjungti taisyklę**: pasirinkite taisyklę, tada – **Išjungti**, kad išlaikytumėte atitikties taisyklę, neįtraukdami jos į susiejimo procesą.
   - **Kopijuoti taisyklę**: pažymėkite taisyklę, tada **Dubliuoti**, kad sukurtumėte panašią taisyklę su pakeitimais.
   - **Naikinti taisyklę**: pažymėkite taisyklę, tada – **Naikinti**.

1. Pasirinkite **Pirmyn**, kad atliktumėte vieningųjų laukų keitimus, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-unification-settings).

## <a name="manage-unified-fields"></a>Vieningųjų laukų valdymas

1. Pasirinkite **Redaguoti** vieningųjų **klientų laukų** plytelėje.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Vieningųjų kliento laukų ekrano kopija":::

1. Peržiūrėkite sujungtus ir neįtrauktus laukus ir, jei reikia, atlikite visus pakeitimus. Įtraukite arba redaguokite "CustomerID" raktą arba grupės profilius į grupes. Daugiau informacijos ieškokite [Suvienodinti klientų laukus](merge-entities.md).

1. Klientams arba paskyroms pasirinkite **Pirmyn**, kad peržiūrėtumėte ir [atnaujintumėte vieningą profilį ir priklausomybes](#run-updates-to-the-unified-profile). Arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Atnaujinti suvienijimo parametrus](#update-unification-settings), kad atliktumėte daugiau pakeitimų.

   Kontaktams pasirinkite **Pirmyn**, kad tvarkytumėte semantinius laukus. Arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Atnaujinti suvienijimo parametrus](#update-unification-settings), kad atliktumėte daugiau pakeitimų.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Vieningų kontaktų semantinių laukų valdymas

1. Pasirinkite **Redaguoti** **semantinių laukų** plytelėje.

1. Norėdami pakeisti vieningojo lauko semantinį tipą, pasirinkite naują tipą. Daugiau informacijos ieškokite [Vieningų kontaktų semantinių laukų apibrėžimas](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Pasirinkite **Pirmyn**, kad tvarkytumėte abonemento ir kontakto ryšį, arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-unification-settings), kad atliktumėte daugiau keitimų.

## <a name="manage-contact-and-account-relationships"></a>Kontaktų ir paskyros ryšių valdymas

1. Pasirinkite **Redaguoti** plytelėje **Ryšiai**.

1. Norėdami pakeisti kontakto ir abonemento ryšį, pakeiskite bet kurią iš šių duomenų:

   - **Išorinis raktas iš kontakto objekto**: pasirinkite atributą, kuris sujungia kontakto objektą su klientu.
   - **Norėdami kliento objekto**: pasirinkite su kontaktu susietą kliento objektą.

1. Pasirinkite **Pirmyn**, kad peržiūrėtumėte suvienijimo parametrus ir [atnaujintumėte vieningąjį profilį bei priklausomybes](#run-updates-to-the-unified-profile), arba pasirinkite **Įrašyti ir uždaryti** ir grįžkite į [Naujinti suvienijimo parametrus](#update-unification-settings), kad atliktumėte daugiau pakeitimų.

## <a name="run-matching-conditions"></a>Bėgimo atitikimo sąlygos

Vykdyti atitikimo sąlygas vykdomos tik dubliavimo ir atitikties taisyklės ir atnaujinami *objektai Deduplication_**" ir *"ConflationMatchPair* ".

1. Puslapyje Duomenų **suvienodinimas** > **pasirinkite** **Vykdyti tik** atitikimo sąlygas.

   Pasikartojančių **įrašų** ir **atitikimo sąlygų** plytelėse rodoma **būsena Eilė arba** **Atnaujinimas**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kai atitikimo procesas bus baigtas, **pasirinkite Redaguoti** plytelėje Atitikimo sąlygos.**·**

   :::image type="content" source="media/match-KPIs.png" alt-text="Apkarpyta Atitikties puslapio pagrindinės metrikos su skaičiais ir išsamia informacija ekrano kopija.":::

1. Norėdami atlikti keitimus, žiūrėkite [Kopijavimo taisyklių](#manage-deduplication-rules) valdymas arba [Atitikties taisyklių](#manage-match-rules) valdymas.

1. Dar kartą paleiskite atitikties procesą arba [paleiskite profilio](#run-updates-to-the-unified-profile) naujinimus.

## <a name="run-updates-to-the-unified-profile"></a>Vieningojo profilio naujinimų vykdymas

- Norėdami vykdyti atitikimo sąlygas ir atnaujinti vieningą profilio objektą *nedarydami* įtakos priklausomybėms (pvz., klientų kortelėms, papildymams, segmentams ar matams), pasirinkite **Suvienodinti klientų profilius**. Jei naudojate paskyras, pasirinkite **Suvienodinti paskyras** > **Suvienodinti profilius**. Kontaktams pasirinkite **Suvienodinti kontaktus (peržiūra)** > **Suvienodinti profilius**. Priklausomi procesai nevykdomi, bet bus atnaujinti, kaip [apibrėžta atnaujinimo grafike](schedule-refresh.md).
- Norėdami vykdyti atitikimo sąlygas, atnaujinti vieningąjį profilį ir paleisti visas priklausomybes, pasirinkite **Suvienodinti klientų profilius ir priklausomybes**. Visi procesai automatiškai paleidžiami iš naujo. Jei naudojate paskyras ir kontaktus, pasirinkite **Suvienodinti paskyras** > **Suvienodinti profilius ir priklausomybes**. Sutampančios sąlygos vykdomos tiek abonementams, tiek kontaktams, naujinantiems tiek vieningus profilius, tiek visas kitas priklausomybes.

Visose plytelėse, išskyrus **šaltinio laukus**, rodoma **eilė arba** **atnaujinimas**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Sėkmingo vykdymo rezultatai rodomi puslapyje "Unify"**,** kuriame rodomas suvienodintų profilių skaičius.
