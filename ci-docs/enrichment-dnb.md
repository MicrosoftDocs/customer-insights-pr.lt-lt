---
title: Praturtinkite įmonės profilius naudodami Dun & Bradstreet (peržiūra)
description: Bendra informacija apie "Dun &Bradstreet" trečiosios šalies sodrinimą.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237914"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Praturtinkite įmonės profilius naudodami Dun & Bradstreet (peržiūra)

"Dun &Bradstreet" teikia komercinius duomenis, analizę ir įžvalgas įmonėms. Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis. Papildymai apima tokius atributus kaip DUNS numeris, įmonės dydis, vieta, pramonė ir kt.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi ["Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) " licencija.
- [Vieningi klientų profiliai](customer-profiles.md) įmonėms.
- Sukurtas "Dun &Bradstreet [" projektas](#set-up-your-dun--bradstreet-project).
- "Dun & Bradstreet [" ryšį](connections.md)[sukonfigūruoja](#configure-a-connection-for-dun--bradstreet) administratorius.

## <a name="set-up-your-dun--bradstreet-project"></a>Nustatykite savo Dun & Bradstreet projektą

Kaip licencijuotas "Dun & Bradstreet" vartotojas, galite sukurti projektą " [Dun &Bradstreet Connect"](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prisijunkite prie ["Dun & Bradstreet Connect"](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Norėdami gauti kredencialus, [atkurkite slaptažodį](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Atsisiųskite [csv šablono failą](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), kuris bus naudojamas klientų įžvalgų laukams susieti su atitinkamais Laukais Dun & Bradstreet.

1. Įkelkite failą į **"Dun & Bradstreet" projekto kūrimo patirties žingsnį Įkelti duomenis**.

1. Pasirinkite horizontalius taškus po atitinkamu **šaltiniu** naujai sukurtame Dun & Bradstreet projekte, kad pamatytumėte galimas parinktis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="&quot;Dun & Bradstreet&quot; projekto taškų ekrano kopija.":::

1. Pasirinkite **Gauti išsamią informaciją apie** S3. Saugokite šią informaciją saugioje vietoje. Jums jo reikės norint [nustatyti papildymo](#configure-a-connection-for-dun--bradstreet) ryšį "Customer Insights".

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="S3 informacijos pasirinkimo &quot;Dun & Bradstreet&quot; projekte ekrano kopija.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Sukonfigūruokite "Dun & Bradstreet" ryšį

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti "Dun & Bradstreet Connect" kredencialus.

1. Konfigūruojant papildymą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje Dun & Bradstreet pasirinkite **Nustatyti**.

1. Įveskite ryšio pavadinimą.

1. Pateikite galiojančius "Dun & Bradstreet" kredencialus ir "Dun & Bradstreet" projekto informaciją apie *regioną, aplanko "Drop" kelią ir aplanko "Drop" pavadinimą*. Šią informaciją [gaunate](#set-up-your-dun--bradstreet-project) iš "Dun & Bradstreet" projekto.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun &Bradstreet ryšio konfigūracijos puslapis.":::

## <a name="supported-countries-or-regions"></a>Palaikomos šalys arba regionai

Šiuo metu palaikome šias šalies / regiono parinktis: Kanada (anglų k.) arba Jungtinės Amerikos Valstijos (anglų k.).

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Praturtinti mano duomenis** plytelėje **Dun & Bradstreet įmonės duomenys**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="&quot;Dun & Bradstreet&quot; plytelių ekrano kopija.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį ir patvirtinkite. Jei ryšio nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti įmonės duomenimis iš "Dun & Bradstreet". *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Apibrėžkite, kokio tipo laukus iš savo vieningųjų profilių naudoti įmonės duomenims iš Dun & Bradstreet suderinti. Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**.

1. Pasirinkti **Toliau**

1. Susiekite savo laukus su įmonės duomenimis iš Dun & Bradstreet. Reikalingi **laukai DUNS numeris** arba **Įmonės** pavadinimas ir **Šalis**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet lauko žemėlapių sudarymo sritis.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
