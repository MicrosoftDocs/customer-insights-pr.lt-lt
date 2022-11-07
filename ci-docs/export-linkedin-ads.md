---
title: Segmentų eksportavimas į „LinkedIn Ads” (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „LinkedIn Ads”.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725318"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentų eksportavimas į „LinkedIn Ads” (peržiūra)

Eksportuokite vieningųjų klientų profilius į „LinkedIn Ads”, kad sukurtumėte „matched audiences”. Naudokite „matched audiences”, kad būtų galima taikyti pagal įmonę ir pagal kontaktus.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Paskyra [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) ir atitinkami administratoriaus kredencialai.
- Paskyros [LinkedIn Campaign Manager ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Eksportuojamiems segmentams reikia bent vieno konkretaus lauko, atsižvelgiant į tai, ar "LinkedIn" pasirenkate [taikymą pagal](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) kontaktą, ar [pagal įmonę](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). Galimi laukai išvardyti **atliekant duomenų atitikimo** veiksmą konfigūruojant [eksportavimą](#configure-an-export).

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 100 000 klientų profilių vienam eksportavimui į "LinkedIn Ads", o tai gali užtrukti iki 10 minučių.
- Tik segmentai. Segmente turi būti bent 300 unikalių profilių.

## <a name="set-up-connection-to-linkedin-ads"></a>Ryšio su "LinkedIn Ads" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **LinkedIn Ads**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite savo LinkedIn Campaign Manager paskyros ID.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pažymėkite **Autentifikuoti naudojant „LinkedIn“** ir pateikite savo „LinkedIn Campaign Manager“ administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „LinkedIn Ads“ skyriaus. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite, ar norite eksportuoti duomenis [taikymui pagal kontaktą](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ar [taikymui pagal įmonę](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) „LinkedIn” platformoje.

1. Jei tai kontaktas, skyriuje **Duomenų gretinimas** pažymėkite bent vieną lauką, kuriame pateikiamas kliento el. pašto adresas „Apple Ad ID", „Google Ad ID", „Google" vartotojo ID arba pirmasis pavardė. Jei pasirinksite taiką pagal įmonę, pažymėkite bent vieną lauką, kuriame pateikiamas įmonės pavadinimas, el. pašto domenas, „LinkedIn" puslapio URL, akcijų simbolis arba svetainė.

1. Pasirinktinai įtraukite laukų, kad toliau apibrėžtumėte eksportą. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. „Matched Audiences” bus automatiškai sukurtos „LinkedIn Campaign Manager” platformoje su eksportavimui pasirinktų segmentų pavadinimu. Kiekviename segmente bus sukurta atskira „matched audience”.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
