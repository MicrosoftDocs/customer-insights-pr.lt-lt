---
title: Papildykite klientų profilius vietos duomenimis iš „Azure” žemėlapių
description: Bendroji informacija apie „Azure“ žemėlapių pirmosios šalies papildymą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953638"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Klientų profilių papildymas „Azure” žemėlapiais (peržiūros versija)

"Azure Maps" teikia į vietovę orientuotus duomenis ir paslaugas, kad būtų galima teikti patirtį, pagrįstą geoerdviniais duomenimis, naudojant įmontuotą vietos nustatymo informaciją. „Azure” žemėlapių duomenų papildymo paslaugos pagerina vietos informacijos apie klientus tikslumą. Taip teikiamos funkcijos, pavyzdžiui, adreso normalizavimas ir platumos ir ilgumos išskleidimas į „Dynamics 365 Customer Insights”.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "Azure Maps" prenumerata. Norėdami gauti prenumeratą, [prisiregistruokite arba gaukite nemokamą bandomąją versiją](https://azure.microsoft.com/services/azure-maps/).

- "Azure Maps" [ryšį](connections.md)[konfigūruoja](#configure-the-connection-for-azure-maps) administratorius.

## <a name="configure-the-connection-for-azure-maps"></a>„Azure” žemėlapių ryšio konfigūravimas

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti aktyvų "Azure Maps" API raktą.

1. Pasirinkite **Įtraukti ryšį** kai konfigūruojate papildymą arba eikite į **Administratorius** > **Ryšiai** ir pasirinkite **Nustatyti**, esantį „Azure“ žemėlapių plytelėje.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure žemėlapių ryšio konfigūravimo puslapis.":::

1. Įveskite ryšio pavadinimą ir galiojantį "Azure Maps" API raktą.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights“ perduoti duomenis „Azure” žemėlapiams, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights“ atitikties ribos, įskaitant galimai jautrius duomenis, pavyzdžiui, Asmens. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "Azure" žemėlapiai atitiktų visus privatumo ar saugos įsipareigojimus, kuriuos galite turėti. Daugiau informacijos pateikta [„Microsoft” privatumo nuostatose](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje Vieta **iš žemėlapių** pasirinkite **Praturtinti mano duomenis** Microsoft Azure.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure žemėlapių raktas.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei ryšio nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti "Microsoft" duomenimis. Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Nurodykite, kokio tipo laukus iš vieningų profilių naudoti gretinimui: pirminį ir (arba) antrinį adresą. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, namų adresui ir įmonės adresui. Pasirinkite **Toliau**.

1. Susiekite laukus su vietos duomenimis iš "Azure" žemėlapių. **Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą. Jei norite didesnio rungtynių tikslumo, pridėkite daugiau laukų.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Maps atributų susiejimas.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Peržiūrėkite **išplėstinius nustatymus**, kurie suteikia maksimalų lankstumą, kad būtų galima tvarkyti išplėstinio naudojimo atvejus. Tačiau šių numatytųjų reikšmių paprastai keisti nereikia.

   - **Adresų** tipas: geriausios adreso atitikties deklaracijos, net jei jos neišsamios. Jei norite gauti tik pilnus adresus&mdash;pavyzdžiui, adresus, kuriuose yra namų numeris&mdash;išvalykite visus žymės langelius, išskyrus **Taškų adresus**.
   - **Kalba**: adresai grąžinami kalba pagal adreso sritį. Jei norite taikyti standartizuotą adreso kalbą, pasirinkite kalbą iš išplečiamojo meniu. Pavyzdžiui, pasirinkus **anglų kalbą** grąžinama **Kopenhaga, Danija**, o ne **København, Danmark**.
   - **Maksimalus rezultatų** skaičius: rezultatų skaičius pagal adresą.

1. Pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientų **, praturtintų pagal lauką**, skaičius suteikia detalizuotą kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
