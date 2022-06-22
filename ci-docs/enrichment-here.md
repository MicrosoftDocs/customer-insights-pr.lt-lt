---
title: Papildymas trečiųjų šalių pratinimas „HERE Technologies“
description: Bendra informacija apie „HERE Technologies“ trečiosios šalies papildymą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953683"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tinkintų profilių papildymas su „HERE Technologies“ (peržiūra)

„HERE Technologies“ yra vietos platformos bendrovė, kuri pateikia vietos centro duomenis ir paslaugas. HERE Technologies duomenų praturtinimo paslaugos pagerina vietos nustatymo informacijos apie jūsų klientus tikslumą. Tai suteikia adreso normalizavimą, platumos ir ilgumos ištraukimą ir dar daugiau.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "HERE Technologies" prenumerata. Norėdami gauti prenumeratą, [užsiregistruokite čia](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) arba [tiesiogiai susisiekite su "HERE Technologies"](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Sužinokite daugiau apie vietos papildymą su „HERE Technologies“.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- ČIA [ryšį](connections.md)[konfigūruoja](#configure-the-connection-for-here-technologies) administratorius.

## <a name="configure-the-connection-for-here-technologies"></a>„HERE Technologies“ ryšio konfigūravimas

Turite būti "Customer Insights" administratorius [ir](permissions.md#admin) turėti aktyvų "HERE Technologies" API raktą.

1. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje HERE Technologijos pasirinkite **Nustatyti**.

1. Įveskite ryšio pavadinimą ir galiojantį HERE Technologies API raktą.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="„HERE Technologies“ ryšio konfigūravimo puslapis.":::

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „HERE Technologies“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „HERE Technologies“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje **Vieta** iš HERE Technologies pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/HERE-tile.png" alt-text="„HERE Technologies“ plytelė.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei jo nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti "HERE Technologies" duomenimis. Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Nurodykite, kokio tipo laukus iš vieningų profilių naudoti gretinimui: pirminį ir (arba) antrinį adresą. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, namų adresui ir įmonės adresui. Pasirinkite **Toliau**.

1. Susiekite laukus su "HERE Technologies" duomenimis. **Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą. Jei norite didesnio rungtynių tikslumo, pridėkite daugiau laukų.

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientų **, praturtintų pagal lauką**, skaičius suteikia detalizuotą kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
