---
title: Duomenų šaltinių papildymas (peržiūra)
description: Praturtinkite duomenų šaltinius prieš pradėdami duomenų suvienijimo procesą.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207193"
---
# <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių papildymas (peržiūra)

Naudokite duomenis iš šaltinių, pvz., "Microsoft" ir kitų partnerių, kad praturtintumėte savo klientų duomenis prieš suvienodindami duomenis. Duomenų šaltinis papildymai padeda užtikrinti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų suvienijus duomenis. Pavyzdžiui, naudojant normalizuotą ir standartizuotą adresų formatą, padidėja atitikties rezultatų kokybė. Palaikomų papildymų sąrašą rasite [palaikomos duomenų šaltinis papildymo parinktys](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Praturtinkite duomenų šaltinis

Turite turėti bendraautorio arba administratoriaus [teises](permissions.md), kad galėtumėte kurti arba redaguoti papildymus.  

1. Eikite į **Duomenų** > **suvienodinimas**. Pasirinkite objektą, kurį norite papildyti, ir pasirinkite vieną atributą kaip pirminį [objekto raktą](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite praturtinti, ir pasirinkite **Praturtinti**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Duomenų šaltinių puslapis su paryškintu papildymu":::

   Skirtuke **Atrasti** rodomos [palaikomos duomenų šaltinis papildymo parinktys](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Duomenų šaltinių papildymo puslapis.":::

1. Pasirinkite **Papildyti mano duomenis**, kad sukonfigūruotumėte duomenų šaltinis papildymą. Išvesties objekto pavadinimas užpildomas automatiškai.

## <a name="supported-data-source-enrichments"></a>Palaikomi duomenų šaltinis papildymai

Toliau nurodyti papildymai šiuo metu yra prieinami duomenų šaltiniams. Peržiūrėkite išsamius papildymo veiksmus, kad sužinotumėte, kaip jį konfigūruoti.

- [Išplėstiniai adresai](enrichment-enhanced-addresses.md)
- [Išplėstiniai įmonės duomenys](enrichment-enhanced-company-data.md)
- [Tapatybės duomenys iš "LiveRamp"](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Esamų duomenų šaltinis papildymų valdymas

Eikite į **Duomenys** > **Papildymas**. Skirtuke **Mano papildymai** peržiūrėkite sukonfigūruotus papildymus, jų būseną, papildytų klientų skaičių ir paskutinį kartą, kai duomenys buvo atnaujinti. Galite rūšiuoti papildymų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte norimą tvarkyti papildymą.

Norėdami peržiūrėti galimas parinktis, pažymėkite papildymą. Taip pat galite pasirinkti vertikalią daugtaškį (&vellip;) sąrašo elemente, kad pamatytumėte parinktis.

Galite peržiūrėti, redaguoti, paleisti arba naikinti duomenų šaltinis papildymą. Daugiau informacijos ieškokite [Esamų papildymų](enrichment-hub.md#manage-existing-enrichments) valdymas.
