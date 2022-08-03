---
title: Praturtinkite klientų profilius tapatybės duomenimis iš "LiveRamp" (peržiūra)
description: Praturtinkite klientų profilius "LiveRamp" duomenimis.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196358"
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

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate Dynamics 365 Customer Insights perduoti duomenis į "LiveRamp", leidžiate perduoti duomenis už atitikties ribos Dynamics 365 Customer Insights ribų, įskaitant galimai neskelbtinus duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, bet jūs esate atsakingi už tai, kad užtikrintumėte, jog "LiveRamp" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Norėdami gauti daugiau informacijos, peržiūrėkite ["Microsoft" privatumo patvirtinimą](https://go.microsoft.com/fwlink/?linkid=396732). Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

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
