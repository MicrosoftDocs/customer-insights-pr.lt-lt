---
title: Praturtinkite klientų profilius vietos duomenimis iš "Azure" žemėlapių (peržiūra)
description: Bendroji informacija apie „Azure“ žemėlapių pirmosios šalies papildymą.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238052"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Praturtinkite klientų profilius vietos duomenimis iš "Azure" žemėlapių (peržiūra)

"Azure" žemėlapiai teikia į vietą orientuotus duomenis ir paslaugas, kad būtų galima teikti funkcijas, pagrįstas geoerdviniais duomenimis, naudojant įtaisytąsias vietos įžvalgas. „Azure” žemėlapių duomenų papildymo paslaugos pagerina vietos informacijos apie klientus tikslumą. Taip teikiamos funkcijos, pavyzdžiui, adreso normalizavimas ir platumos ir ilgumos išskleidimas į „Dynamics 365 Customer Insights”.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "Azure" žemėlapių prenumerata. Norėdami gauti prenumeratą, [prisiregistruokite arba gaukite nemokamą bandomąją versiją](https://azure.microsoft.com/services/azure-maps/).

- "Azure" žemėlapių [ryšį](connections.md)[sukonfigūruoja](#configure-the-connection-for-azure-maps) administratorius.

## <a name="configure-the-connection-for-azure-maps"></a>„Azure” žemėlapių ryšio konfigūravimas

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti aktyvų "Azure Maps" API raktą.

1. Pasirinkite **Įtraukti ryšį** kai konfigūruojate papildymą arba eikite į **Administratorius** > **Ryšiai** ir pasirinkite **Nustatyti**, esantį „Azure“ žemėlapių plytelėje.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure žemėlapių ryšio konfigūravimo puslapis.":::

1. Įveskite ryšio pavadinimą ir galiojantį "Azure Maps" API raktą.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis** plytelėje **Vieta** iš Microsoft Azure žemėlapių.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure žemėlapių raktas.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei ryšio nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti "Microsoft" duomenimis. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Apibrėžkite, kokio tipo laukus iš savo vieningųjų profilių naudoti atitikčiai: pirminį ir (arba) antrinį adresą. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, namų ir įmonės adreso atveju. Pasirinkite **Toliau**.

1. Susiekite laukus su vietos duomenimis iš "Azure" žemėlapių. **Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą. Norėdami gauti didesnį atitikties tikslumą, įtraukite daugiau laukų.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps atributų susiejimas.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Peržiūrėkite **išplėstinius nustatymus**, kurie suteikia maksimalų lankstumą tvarkant išplėstinius naudojimo atvejus. Tačiau šių numatytųjų reikšmių paprastai keisti nereikia.

   - **Adresų** tipas: grąžinama geriausia adreso atitiktis, net jei ji neišsami. Jei norite gauti tik pilnus adresus&mdash;pavyzdžiui, adresus, kuriuose yra namų numeris&mdash;išvalykite visus žymės langelius, išskyrus **Taškų adresus**.
   - **Kalba**: adresai grąžinami kalba pagal adreso sritį. Jei norite taikyti standartizuotą adreso kalbą, pasirinkite kalbą iš išplečiamojo meniu. Pavyzdžiui, pasirinkus **anglų kalbą**, grįžta **Kopenhaga, Danija**, o ne **København, Danmark**.
   - **Maksimalus rezultatų** skaičius: rezultatų skaičius vienam adresui.

1. Pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lauku **praturtintų** klientų skaičius leidžia detalizuoti kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
