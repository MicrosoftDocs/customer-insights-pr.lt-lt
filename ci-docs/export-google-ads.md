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
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725088"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentų eksportavimas į „Google Ads“ (peržiūra)

Eksportuokite unifikuotų klientų profilių segmentus į „Google Ads" auditorijų sąrašą ir naudokite juos norėdami juos naudoti reklamuojant „Google" paiešką, „Gmail" „YouTube“ ir „Google Display Network".

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Google Ads" paskyros](https://ads.google.com/) ir atitinkamų administratoriaus kredencialų.
- " [Google Ads" kliento ID](https://support.google.com/google-ads/answer/1704344).
- Klientų atitikties politikos [reikalavimai](https://support.google.com/adspolicy/answer/6299717) yra įvykdyti.
- Tenkinami pakartotinės rinkodaros sąrašų dydžių [reikalavimai](https://support.google.com/google-ads/answer/7558048).
- [Sukonfigūruoti segmentai](segments.md).
- Suvienodintuose klientų profiliuose eksportuotuose segmentuose yra laukų, nurodančių el. pašto adresą, telefoną, reklamuotojo mobiliesiems ID, trečiosios šalies naudotojo ID arba adresą.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Eksportuokite iki 1 milijono klientų profilių vienam eksportavimui į "Google Ads", o tai gali užtrukti iki 30 minučių dėl teikėjo apribojimų.
- Tik segmentai.
- Atitiktis sistemoje "Google Ads" gali trukti iki 48 valandų.

## <a name="set-up-connection-to-google-ads"></a>Ryšio su „Google Ads“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **"Google Ads**".

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite "Google Ads" kliento ID.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Google Ads“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite, ar naudoti esamą auditoriją, ar kurti naują:
   - Jei norite atnaujinti esamą "Google Ads" auditoriją, įveskite ["Google Ads" auditorijos ID.](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns)
   - Jei norite sukurti naują auditoriją, palikite "Google" auditorijos ID lauką tuščią. "Customer Insights" automatiškai sukurs naują auditoriją jūsų "Google Ads" paskyroje ir naudos eksportuoto segmento pavadinimą.

1. Sekcijoje **Duomenų atitikimas** pasirinkite vieną ar daugiau duomenų laukų, kuriuos norite eksportuoti, ir pasirinkite lauką, kuris atitinka atitinkamus "Customer Insights" duomenų laukus.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
