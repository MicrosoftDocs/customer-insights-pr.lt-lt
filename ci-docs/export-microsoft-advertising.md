---
title: Segmentų eksportavimas į „Microsoft Advertising“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Microsoft Advertising“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196542"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentų eksportavimas į „Microsoft Advertising“ (peržiūra)

Eksportuokite „Customer Insights” segmentus į „Microsoft Advertising”, kad sukurtumėte Klientų atitikmenų auditorijas. Naudokite šias auditorijas savo reklamos kampanijoms.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Microsoft Advertising" paskyra](https://ads.microsoft.com/) ir atitinkami administratoriaus kredencialai.
- "Microsoft Advertising" kliento ID ir paskyros ID. Raskite Kliento ID (`cid`) ir Paskyros ID (`aid`) URL parametruose, kai esate prisijungę prie "Microsoft Advertising".
- Kliento atitikties naudojimo sąlygos yra priimtinos.
- [Sukonfigūruoti segmentai](segments.md) "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 500 000 klientų profilių vienam eksportui į "Microsoft Advertising", o tai gali užtrukti iki 10 minučių.
- Tik segmentai.

## <a name="set-up-connection-to-microsoft-advertising"></a>Ryšio su "Microsoft Advertising" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **"Microsoft Advertising"**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Numatytasis parametras yra administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Įveskite "Microsoft" reklamos kliento ID**.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį.

1. Pažymėkite **Autentifikuoti naudojant „Microsoft Advertising“** ir pateikite savo „Microsoft Advertising“ administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „Microsoft Advertising“ skyriaus. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite segmentus eksportavimui. Klientų atitikmens auditorijos yra automatiškai sukuriamos „Microsoft Advertising” su eksportavimui pasirinktų segmentų pavadinimu. Kiekviename segmente bus sukurta atskira Klientų atitikmens auditorija.

1. Įveskite savo **„Microsoft Advertising” Kliento ID ir Paskyros ID**.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** su kliento el. pašto adresu.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
