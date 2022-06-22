---
title: Įmonės profilių praturtinimas "Dun & Bradstreet"
description: Bendra informacija apie "Dun & Bradstreet" trečiosios šalies sodrinimą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953901"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Įmonės profilių praturtinimas "Dun & Bradstreet" (Peržiūra)

"Dun & Bradstreet" teikia komercinius duomenis, analizę ir įžvalgas įmonėms. Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis. Sodrinimas apima tokius atributus kaip DUNS numeris, įmonės dydis, vieta, pramonė ir kt.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) licencija.
- [Vieningi įmonių klientų profiliai](customer-profiles.md).
- Sukurtas "Dun & Bradstreet [" projektas](#set-up-your-dun--bradstreet-project).
- Dun & Bradstreet [ryšį](connections.md)[konfigūruoja](#configure-a-connection-for-dun--bradstreet) administratorius.

## <a name="set-up-your-dun--bradstreet-project"></a>"Dun & Bradstreet" projekto nustatymas

Kaip licencijuotas "Dun & Bradstreet" vartotojas, galite sukurti projektą " [Dun & Bradstreet Connect"](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Prisijunkite prie ["Dun & Bradstreet Connect"](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Norėdami gauti kredencialus, [atkurkite slaptažodį](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Atsisiųskite [mūsų csv šablono failą](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), kuris bus naudojamas susieti "Customer Insights" laukus su atitinkamais "Dun & Bradstreet" laukais.

1. Įkelkite failą į **"Dun & Bradstreet" projekto kūrimo patirties įkėlimo duomenų** veiksmą.

1. Pasirinkite horizontalius taškus po atitinkamu **šaltiniu** naujai sukurtame "Dun & Bradstreet" projekte, kad pamatytumėte galimas parinktis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="&quot;Dun & Bradstreet&quot; projekto taškų ekrano nuotrauka.":::

1. Pasirinkite **Gauti S3 informaciją**. Saugokite šią informaciją saugioje vietoje. Jums reikės, kad [nustatytumėte ryšį, kad praturtintumėte](#configure-a-connection-for-dun--bradstreet) "Customer Insights".

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="&quot;Dun & Bradstreet&quot; projekto s3 informacijos pasirinkimo ekrano nuotrauka.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Konfigūruoti "Dun & Bradstreet" ryšį

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti "Dun & Bradstreet Connect" kredencialus.

1. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje Dun & Bradstreet pasirinkite **Nustatyti**.

1. Įveskite ryšio pavadinimą.

1. Pateikite galiojančius "Dun & Bradstreet" kredencialus ir "Dun & Bradstreet" projekto informaciją Regionas *, "Drop" aplanko kelias ir "Drop" aplanko pavadinimą*. Šią informaciją [gausite](#set-up-your-dun--bradstreet-project) iš "Dun & Bradstreet" projekto.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet ryšio konfigūracijos puslapis.":::

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis "Dun & Bradstreet", leidžiate perduoti duomenis už atitikties ribos Dynamics 365 Customer Insights, įskaitant potencialiai neskelbtinus duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "Dun & Bradstreet" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="supported-countries-or-regions"></a>Palaikomos šalys arba regionai

Šiuo metu palaikome šias šalies / regiono parinktis: Kanadą (anglų) arba Jungtines Amerikos Valstijas (anglų k.).

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Praturtinti mano duomenis** apie **"Dun & Bradstreet" plytelių įmonės duomenis**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="&quot;Dun & Bradstreet&quot; plytelių ekrano nuotrauka.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį ir patvirtinkite. Jei jo nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti įmonės duomenimis iš "Dun & Bradstreet". Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Apibrėžkite, kokio tipo laukus iš savo vieningų profilių naudoti įmonės duomenims iš "Dun & Bradstreet" suderinti. Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**.

1. Pasirinkti **Toliau**

1. Susiekite laukus su įmonės duomenimis iš "Dun & Bradstreet". Reikalingi **DUNS numeris** arba **įmonės** pavadinimas ir **šalies** laukai.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet lauko susiejimo sritis.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
