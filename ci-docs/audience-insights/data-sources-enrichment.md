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
ms.openlocfilehash: eebaaf18795e80dd1ba16a15a23844d685c94c6e
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373069"
---
# <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių praturtinimas (peržiūra)

Naudokite duomenis iš tokių šaltinių kaip "Microsoft" ir kiti partneriai, kad praturtintumėte klientų duomenis prieš suvienodinimą. Duomenų šaltinis sodrinimas padeda sukurti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų suvienodėjus duomenis. Pavyzdžiui, naudojant normalizuotą ir standartizuotą adresų formatą padidėja rungtynių rezultatų kokybė. Palaikomų sodrinimo būdų sąrašą rasite [palaikomų duomenų šaltinis sodrinimo parinktis](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Praturtinkite duomenų šaltinis

Norėdami kurti arba redaguoti praturtinimus, turite turėti bendraautoriaus arba administratoriaus teises. Daugiau informacijos žr. [Teisės](permissions.md).  

1. Eikite į **DataUnify** > **·**. Pasirinkite objektą, kurį norite praturtinti, ir pasirinkite vieną atributą kaip pirminį objekto raktą. Daugiau informacijos ieškokite [Select Primary Key](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.
 
1. Pasirinkite vertikalią daugtaškį šalia duomenų šaltinis, kurį norite praturtinti, ir pasirinkite **Praturtinti**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Duomenų šaltinių sodrinimo puslapis.":::

   Skirtuke **Atraskite** rodomos [palaikomos duomenų šaltinis sodrinimo parinktys](#supported-data-source-enrichments).

1. Pasirinkite **Praturtinti mano duomenis**, kad sukonfigūruotumėte duomenų šaltinis sodrinimą. Išvesties objekto pavadinimas užpildomas automatiškai.

## <a name="supported-data-source-enrichments"></a>Palaikomi duomenų šaltinis sodrinimas

Šiuo metu duomenų šaltiniams galima pateikti šiuos papildymus. Peržiūrėkite išsamius sodrinimo veiksmus, kad sužinotumėte, kaip jį konfigūruoti.

- [Išplėstiniai adresai](enrichment-enhanced-addresses.md)
- ["LiveRamp" tapatybės duomenys](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Tvarkyti esamus duomenų šaltinis sodrinimą

Eikite į skirtuką **Mano papildymai**, kad pamatytumėte visus sukonfigūruotus papildymus.

Norėdami peržiūrėti galimas parinktis, pažymėkite papildymą. Taip pat galite pažymėti elipsę (...) sąrašo elemente ir peržiūrėti parinktis. Jei sukonfigūravote kelis papildymus, galite naudoti ieškos lauką, kad greitai juos rastumėte.

Galite peržiūrėti, redaguoti, paleisti arba panaikinti duomenų šaltinis sodrinimo. Daugiau informacijos ieškokite [Manage existing enrichments](enrichment-hub.md).
