---
title: Duomenų šaltinis praturtėjimas
description: Praturtinkite duomenų šaltinius prieš atlikdami duomenų suvienijimo procesą.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376589"
---
# <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių sodrinimas (peržiūra)

Naudokite duomenis iš tokių šaltinių kaip "Microsoft" ir kiti partneriai, kad praturtintumėte savo klientų duomenis prieš duomenų suvienodinimą. Duomenų šaltinis praturtėjimas padeda užtikrinti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų, kai suvienodinsite duomenis. Pavyzdžiui, naudojant normalizuotą ir standartizuotą adresų formatą, padidėja rungtynių rezultatų kokybė. Palaikomų sodrinimo darbų sąrašą rasite [palaikomose duomenų šaltinis sodrinimo parinktyse](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Praturtinkite duomenų šaltinis

Norėdami kurti arba redaguoti sodrinimus, turite turėti bendraautoriaus arba administratoriaus teises. Daugiau informacijos žr. [Teisės](permissions.md).  

1. Eikite į **"DataUnify** > **"**. Pasirinkite objektą, kurį norite praturtinti, ir pasirinkite vieną atributą kaip pagrindinį objekto raktą. Daugiau informacijos ieškokite [Select primary key](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.
 
1. Pasirinkite vertikalią daugtaškį šalia norimo praturtinti duomenų šaltinis ir pasirinkite **Praturtinti**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Duomenų šaltinių sodrinimo puslapis.":::

   Skirtuke **Atrasti** rodomos [palaikomos duomenų šaltinis sodrinimo parinktys](#supported-data-source-enrichments).

1. Norėdami konfigūruoti duomenų šaltinis sodrinimą, pasirinkite **Praturtinti mano duomenis**. Išeigos objekto pavadinimas užpildomas automatiškai.

## <a name="supported-data-source-enrichments"></a>Palaikomi duomenų šaltinis praturtėjimas

Šiuo metu duomenų šaltiniuose galimi šie turtintuvai. Peržiūrėkite išsamius sodrinimo veiksmus, kad sužinotumėte, kaip jį konfigūruoti.

- [Išplėstiniai adresai](enrichment-enhanced-addresses.md)
- [Išplėstiniai įmonės duomenys](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Tvarkyti esamus duomenų šaltinis sodrinimus

Eikite į skirtuką **Mano papildymai**, kad pamatytumėte visus sukonfigūruotus papildymus.

Norėdami peržiūrėti galimas parinktis, pažymėkite papildymą. Taip pat galite pažymėti elipsę (...) sąrašo elemente ir peržiūrėti parinktis. Jei sukonfigūravote kelis papildymus, galite naudoti ieškos lauką, kad greitai juos rastumėte.

Galite peržiūrėti, redaguoti, vykdyti arba naikinti duomenų šaltinis sodrinimo duomenų šaltinis. Daugiau informacijos ieškokite [Manage existing enrichments](enrichment-hub.md).
