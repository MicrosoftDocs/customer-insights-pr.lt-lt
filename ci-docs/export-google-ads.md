---
title: Segmentų eksportavimas į „Google Ads“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Google Ads“.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: fd7498ecf17ef8a3a8f22dcc49ae204bef88b47f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196588"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentų eksportavimas į „Google Ads“ (peržiūra)

Eksportuokite unifikuotų klientų profilių segmentus į „Google Ads" auditorijų sąrašą ir naudokite juos norėdami juos naudoti reklamuojant „Google" paiešką, „Gmail" „YouTube“ ir „Google Display Network".

## <a name="prerequisites"></a>Būtinosios sąlygos

- ["Google Ads" paskyra](https://ads.google.com/) ir atitinkami administratoriaus kredencialai.
- ["Google Ads" kliento ID](https://support.google.com/google-ads/answer/1704344).
- Tenkinami Klientų atitikties politikos [reikalavimai](https://support.google.com/adspolicy/answer/6299717).
- Pakartotinės rinkodaros sąrašo [dydžių](https://support.google.com/google-ads/answer/7558048) reikalavimai yra įvykdyti.
- [Sukonfigūruoti segmentai](segments.md).
- Eksportuotuose segmentuose esančiuose vieninguose klientų profiliuose yra laukai, nurodantys el. pašto adresą, telefoną, reklamuotojo mobiliesiems ID, trečiosios šalies vartotojo ID arba adresą.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportuokite iki 1 milijono klientų profilių vienam eksportui į "Google Ads", o tai gali užtrukti iki 30 minučių, nes paslaugų teikėjas turi apribojimų.
- Tik segmentai.
- Atitiktis sistemoje "Google Ads" gali trukti iki 48 valandų.

## <a name="set-up-connection-to-google-ads"></a>Ryšio su „Google Ads“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Google Ads**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite "Google Ads" kliento ID.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Google Ads“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite, ar naudoti esamą auditoriją, ar kurti naują:
   - Jei norite atnaujinti esamą "Google Ads" auditoriją, įveskite ["Google Ads" auditorijos ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Jei norite sukurti naują auditoriją, lauką "Google Audience ID" palikite tuščią. "Customer Insights" automatiškai sukurs naują auditoriją "Google Ads" paskyroje ir naudos eksportuoto segmento pavadinimą.

1. Sekcijoje **Duomenų atitikimas** pasirinkite vieną ar daugiau duomenų laukų, kuriuos norite eksportuoti, ir pasirinkite lauką, kuris nurodo atitinkamus duomenų laukus "Customer Insights".

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
