---
title: LiveRamp tapatybės duomenų praturtinimas
description: Praturtinkite klientų profilius "LiveRamp" duomenimis.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954005"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Klientų profilių praturtinimas tapatybės duomenimis iš "LiveRamp" (peržiūra)

LiveRamp teikia deterministinę autonominę tapatybės skiriamąją gebą ir kliento duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su AbiliTec tapatybės grafiku ir gauti AbiliTec ID. Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikome klientų profilių praturtinimą "LiveRamp" duomenimis tik Jungtinėse Amerikos Valstijose.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "LiveRamp" prenumerata. Norėdami gauti prenumeratą, susisiekite su "LiveRamp" abonemento komanda arba norėdami gauti [dynamics@liveramp.com](mailto:dynamics@liveramp.com) daugiau informacijos.

- Aktyvi "AbiliTec" prenumerata su kliento ID ir slapta prieiga prie API. Daugiau informacijos ieškokite [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- "LiveRamp [" ryšį](connections.md)[konfigūruoja](#configure-the-connection-for-liveramp) administratorius.

## <a name="configure-the-connection-for-liveramp"></a>Konfigūruoti "LiveRamp" ryšį

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti aktyvų "LiveRamp" kliento ID ir paslaptį.

1. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje LiveRamp pasirinkite **Nustatyti**.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfigūracijos sritis, skirta nustatyti ryšį su LiveRamp AbiliTec tarnyba.":::

1. Įveskite ryšio pavadinimą ir galiojantį "LiveRamp" kliento ID bei paslaptį.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis "LiveRamp", leidžiate perduoti duomenis už atitikties ribos, įskaitant potencialiai neskelbtinus Dynamics 365 Customer Insights duomenis, pvz., asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "LiveRamp" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Norėdami gauti daugiau informacijos, peržiūrėkite ["Microsoft" privatumo patvirtinimą](https://go.microsoft.com/fwlink/?linkid=396732). Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje **"LiveRamp**" pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Tapatybės plytelė sodrinimo apžvalgos puslapyje.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei jo nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti tapatybės duomenimis iš "LiveRamp". Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Nurodykite, kokio tipo laukus iš jūsų vieningų profilių naudoti derinant tapatybės duomenis iš "LiveRamp". Reikalingas bent vienas iš laukų **Pavadinimas ir adresas**, **El. paštas** arba **Telefonas**. Jei norite didesnio rungtynių tikslumo, pridėkite kitų laukų. Pasirinkite **Toliau**.

1. Susiekite laukus su identifikavimo duomenimis iš "LiveRamp".

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="&quot;LiveRamp&quot; sodrinimo duomenų susiejimo parinktys.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientų **, praturtintų pagal lauką**, skaičius suteikia detalizuotą kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Naudokite AbiliTec ID, kad konsoliduotumėte klientų profilius į asmenį pagrįstą rodinį.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
