---
title: Duomenų šaltinis praturtėjimas
description: Praturtinkite duomenų šaltinius prieš pradėdami duomenų suvienijimo procesą.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800291"
---
# <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių praturtinimas (peržiūra)

Naudokite duomenis iš šaltinių, pvz., "Microsoft" ir kitų partnerių, kad praturtintumėte savo klientų duomenis prieš duomenų suvienijimą. Duomenų šaltinis praturtinimai padeda užtikrinti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų suvienijus duomenis. Pavyzdžiui, naudojant normalizuotą ir standartizuotą adresų formatą, padidėja rungtynių rezultatų kokybė. Remiamų sodrinimo galimybių sąrašą rasite [palaikomuose duomenų šaltinis sodrinimo galimybių](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Praturtinkite duomenų šaltinis

Norėdami kurti arba redaguoti praturtinimus, turite turėti bendraautoriaus arba administratoriaus teises. Daugiau informacijos žr. [Teisės](permissions.md).  

1. Eikite į **"Data** > **Unify"**. Pasirinkite objektą, kurį norite praturtinti, ir pasirinkite vieną atributą kaip pirminį objekto raktą. Daugiau informacijos ieškokite [Select primary key](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite vertikalią elipsę (&vellip;) šalia duomenų šaltinis norite praturtinti, ir pasirinkite **Praturtinti**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Duomenų šaltinių praturtinimo puslapis.":::

   Skirtuke **Atrasti** rodomos [palaikomos duomenų šaltinis sodrinimo parinktys](#supported-data-source-enrichments).

1. Pasirinkite **Praturtinti mano duomenis**, kad sukonfigūruotumėte duomenų šaltinis praturtinimą. Išvesties objekto pavadinimas užpildomas automatiškai.

## <a name="supported-data-source-enrichments"></a>Remiami duomenų šaltinis praturtėjimas

Šiuo metu duomenų šaltiniuose galima rasti toliau nurodytų sodrinimo priemonių. Peržiūrėkite išsamius sodrinimo veiksmus, kad sužinotumėte, kaip jį konfigūruoti.

- [Išplėstiniai adresai](enrichment-enhanced-addresses.md)
- [Išplėstiniai įmonės duomenys](enrichment-enhanced-company-data.md)
- [Tapatybės duomenys iš "LiveRamp"](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Valdykite esamus duomenų šaltinis praturtinimus

Eikite į skirtuką **Mano papildymai**, kad pamatytumėte visus sukonfigūruotus papildymus.

Norėdami peržiūrėti galimas parinktis, pažymėkite papildymą. Taip pat galite pasirinkti vertikalią elipsę (&vellip;) sąrašo elemente, kad pamatytumėte parinktis. Jei sukonfigūravote kelis papildymus, galite naudoti ieškos lauką, kad greitai juos rastumėte.

Galite peržiūrėti, redaguoti, paleisti arba panaikinti duomenų šaltinis sodrinimą. Daugiau informacijos ieškokite [Manage existing enrichgs](enrichment-hub.md).
