---
title: Praturtinkite klientų profilius tapatybės duomenimis iš "LiveRamp" (peržiūra)
description: Praturtinkite klientų profilius "LiveRamp" duomenimis.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237822"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Praturtinkite klientų profilius tapatybės duomenimis iš "LiveRamp" (peržiūra)

"LiveRamp" teikia deterministinę autonominės tapatybės skiriamąją gebą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su "AbiliTec" tapatybės grafiku ir gauti "AbiliTec ID". Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikome klientų profilių praturtinimą "LiveRamp" duomenimis tik Jungtinėse Amerikos Valstijose.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "LiveRamp" prenumerata. Norėdami gauti prenumeratą, susisiekite su savo "LiveRamp" paskyros komanda arba [dynamics@liveramp.com](mailto:dynamics@liveramp.com) norėdami gauti daugiau informacijos.

- Aktyvi "AbiliTec" prenumerata su kliento ID ir slapta prieiga prie API. Daugiau informacijos rasite [AbiliTec API kūrėjų telkinyje](https://developers.liveramp.com/abilitec-api/).

- "LiveRamp [" ryšį](connections.md)[sukonfigūruoja](#configure-the-connection-for-liveramp) administratorius.

## <a name="configure-the-connection-for-liveramp"></a>Konfigūruokite "LiveRamp" ryšį

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti aktyvų "LiveRamp" kliento ID ir slaptą.

1. Konfigūruojant papildymą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir **pasirinkite Nustatyti** "LiveRamp" plytelėje.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigūracijos sritis, skirta nustatyti ryšį su &quot;LiveRamp AbiliTec&quot; paslauga.":::

1. Įveskite ryšio pavadinimą ir galiojantį "LiveRamp" kliento ID bei paslaptį.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis** plytelėje **Tapatybė** iš "LiveRamp".

   :::image type="content" source="media/liveramp-tile.png" alt-text="Tapatybės plytelė papildymo apžvalgos puslapyje.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei ryšio nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti tapatybės duomenimis iš "LiveRamp". *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Apibrėžkite, kokio tipo laukus iš savo vieningųjų profilių naudoti tapatybės duomenims iš "LiveRamp" suderinti. Reikia bent vieno iš laukų **Pavadinimas ir adresas**, **El. paštas** arba **Telefonas**. Norėdami gauti didesnį atitikties tikslumą, įtraukite kitus laukus. Pasirinkite **Toliau**.

1. Susiekite laukus su identifikavimo duomenimis iš "LiveRamp".

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="&quot;LiveRamp&quot; papildymo duomenų susiejimo parinktys.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lauku **praturtintų** klientų skaičius leidžia detalizuoti kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Naudokite "AbiliTec" ID, kad sujungtumėte klientų profilius į asmenį pagrįstą rodinį.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
