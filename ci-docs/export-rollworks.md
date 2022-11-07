---
title: Segmentų eksportavimas į „RollWorks“ (peržiūros versija)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „RollWorks“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725135"
---
# <a name="export-segments-to-rollworks-preview"></a>Segmentų eksportavimas į „RollWorks“ (peržiūros versija)

Eksportuokite vieningų klientų profilių segmentus į „RollWorks“ ir naudokite juos reklamai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [RollWorks" paskyra](https://www.rollworks.com/) ir atitinkami administratoriaus kredencialai.
- " [RollWorks" reklamuotojo ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 250 000 klientų profilių vienam eksportavimui į "RollWorks", o tai gali užtrukti iki 10 minučių. Klientų profilių, kuriuos galite eksportuoti į "RollWorks", skaičius priklauso nuo jūsų sutarties su "RollWorks".
- Tik segmentai.

## <a name="set-up-connection-to-rollworks"></a>Ryšio su „RollWorks“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **RollWorks**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį.  Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pažymėkite **Autentifikuoti naudojant „RollWorks“** ir pateikite savo „RollWorks“ administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „RollWorks“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite savo **"RollWorks" reklamuotojo ID.**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
