---
title: Segmentų eksportavimas į "MoEngage"
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į "MoEngage".
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199216"
---
# <a name="export-segments-to-moengage-preview"></a>Segmentų eksportavimas į "MoEngage" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "MoEngage" ir naudokite juos el. pašto rinkodarai "MoEngage".

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

- ["MoEngage" paskyra](https://www.moengage.com/) ir atitinkami administratoriaus kredencialai.
- "MoEngage API" klavišas iš "MoEngage" nustatymų > API.
- [Sukonfigūruoti segmentai](segments.md) "Customer Insights".

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 100 000 klientų profilių vienam eksportui į "MoEngage", o tai gali užtrukti iki 15 minučių. Klientų profilių, kuriuos galite eksportuoti į "MoEngage", skaičius priklauso nuo jūsų sutarties su "MoEngage".
- Tik segmentai.

## <a name="set-up-connection-to-moengage"></a>Ryšio su "MoEngage" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **MoEngage**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo ["MoEngage Data API ID" ir API raktą](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį su "MoEngage".

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. **Lauke Ryšys eksportui** pasirinkite ryšį iš skyriaus MoEngage. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius veiksmus su kitais pasirinktiniais laukais.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Sukursime vieną ar daugiau segmentų tuo pačiu pavadinimu kaip ir pasirinkti segmentai "MoEngage" dalyje **Segmentai Pasirinktiniai** > **segmentai**.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
