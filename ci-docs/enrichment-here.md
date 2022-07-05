---
title: Praturtinkite klientų profilius naudodami HERE Technologijas (peržiūra)
description: Bendra informacija apie „HERE Technologies“ trečiosios šalies papildymą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052061"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Praturtinkite klientų profilius naudodami HERE Technologijas (peržiūra)

„HERE Technologies“ yra vietos platformos bendrovė, kuri pateikia vietos centro duomenis ir paslaugas. HERE Technologies duomenų papildymo paslaugos pagerina vietos nustatymo informacijos apie jūsų klientus tikslumą. Tai suteikia adreso normalizavimą, platumos ir ilgumos ištraukimą ir dar daugiau.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi HERE Technologies prenumerata. Norėdami gauti prenumeratą, [prisiregistruokite čia](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) arba [tiesiogiai susisiekite su HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Sužinokite daugiau apie vietos papildymą su „HERE Technologies“.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [ryšį](connections.md)[sukonfigūruoja](#configure-the-connection-for-here-technologies) administratorius.

## <a name="configure-the-connection-for-here-technologies"></a>„HERE Technologies“ ryšio konfigūravimas

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti aktyvų HERE Technologies API raktą.

1. Pasirinkite **Įtraukti ryšį** konfigūruojant papildymą arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje HERE Technologijos pasirinkite **Nustatyti**.

1. Įveskite ryšio pavadinimą ir galiojantį HERE Technologies API raktą.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="„HERE Technologies“ ryšio konfigūravimo puslapis.":::

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „HERE Technologies“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „HERE Technologies“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Praturtinti mano duomenis** plytelėje **Vieta** iš HERE technologijos.

   :::image type="content" source="media/HERE-tile.png" alt-text="„HERE Technologies“ plytelė.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Kreipkitės į administratorių, jei jis nepasiekiamas.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį ar segmentą, kurį norite papildyti here Technologies duomenimis. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Apibrėžkite, kokio tipo laukus iš savo vieningųjų profilių naudoti atitikčiai: pirminį ir (arba) antrinį adresą. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, namų ir įmonės adreso atveju. Pasirinkite **Toliau**.

1. Susiekite savo laukus su here Technologies duomenimis. **Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą. Norėdami pasiekti didesnį atitikties tikslumą, įtraukite daugiau laukų.

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lauku **praturtintų** klientų skaičius leidžia detalizuoti kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
