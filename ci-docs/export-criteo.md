---
title: Segmentų eksportavimas į Criteo (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195346"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentų eksportavimas į Criteo (peržiūra)

Eksportuokite vieningų klientų profilių segmentus, kad sukurtumėte kampanijas, teiktumėte rinkodarą el. paštu ir naudotumėte konkrečias klientų grupes naudodami "Criteo".

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Criteo Dynamics Retargeting" paskyra](https://www.criteo.com/login/) ir atitinkami administratoriaus kredencialai.
- [Sukonfigūruoti segmentai](segments.md).
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono klientų profilių vienam eksportui į Criteo, o tai gali užtrukti iki 30 minučių. Klientų profilių, kuriuos galite eksportuoti į Criteo, skaičius priklauso nuo jūsų sutarties su Criteo.
- Tik segmentai.

## <a name="set-up-connection-to-criteo"></a>Ryšio su Criteo nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Criteo**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį.

1. Pasirinkite **Autentifikuoti naudojant Criteo** ir pateikite savo administratoriaus vartotojo vardą bei "Criteo" kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. **Lauke Ryšys eksportavimui** pasirinkite ryšį iš skyriaus Criteo. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai eksportuokite **reklamuotojo ID** ir **vardą**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
