---
title: Segmentų eksportavimas į „Omnisend“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Omnisend“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196174"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentų eksportavimas į „Omnisend“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „Omnisend“ ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Omnisend" paskyrą](https://www.omnisend.com/) ir atitinkamus administratoriaus kredencialus.
- " [Omnisend" API raktas](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Sukonfigūruoti segmentai](segments.md) "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono klientų profilių vienam eksportui į "Omnisend", o tai gali užtrukti iki keturių valandų. Klientų profilių, kuriuos galite eksportuoti į „Omnisend", skaičius priklauso nuo sutarties su „Omnisend".
- Tik segmentai.

## <a name="set-up-connection-to-omnisend"></a>Ryšio su „Omnisend“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Omnisend**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo „Omnisend“ API raktą.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „Omnisend“ skyriaus. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai eksportuokite vardas, pavardė, adresą **,** šalį / regioną **,** **valstiją**, miestą **ir** pašto kodą **,** kad sukurtumėte labiau suasmenintus el. laiškus.**·** **·** Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
