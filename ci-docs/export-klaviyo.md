---
title: Segmentų eksportavimas į "Klaviyo" (peržiūra)
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Klaviyo“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 075e6758f2c6992a1185756f9beecf852fdd0a96
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724608"
---
# <a name="export-segments-to-klaviyo-preview"></a>Segmentų eksportavimas į "Klaviyo" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į „Klaviyo" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- ["Klaviyo" paskyra](https://www.klaviyo.com/) ir atitinkami administratoriaus kredencialai.
- Klaviyo [API raktas](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- Klaviyo [sąrašo ID](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių vienam eksportui į "Klaviyo", o tai gali užtrukti iki 20 minučių. Klientų profilių, kuriuos galite eksportuoti į "Klaviyo", skaičius priklauso nuo jūsų sutarties su "Klaviyo".
- Tik segmentai.

## <a name="set-up-connection-to-klaviyo"></a>Nustatyti ryšį su „Klaviyo“

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Klaviyo**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite savo "Klaviyo" API raktą kad tęstumėte prisijungimą.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Autentifikuoti su „Klaviyo”** ir pateikite savo „Klaviyo” administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „Klaviyo“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite savo **Klaviyo sąrašo ID.**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
