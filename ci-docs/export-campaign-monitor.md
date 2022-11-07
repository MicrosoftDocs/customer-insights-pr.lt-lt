---
title: Segmentų eksportavimas į „Campaign Monitor“ (peržiūros versija)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Campaign Monitor“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724694"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentų eksportavimas į „Campaign Monitor“ (peržiūros versija)

Eksportuokite vieningų klientų profilių segmentus į „Campaign Monitor“ ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Campaign Monitor" paskyra](https://www.campaignmonitor.com/) ir atitinkami administratoriaus kredencialai.
- [Kampanijos monitoriaus sąrašo ID](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Sugeneruotas [API raktas](https://www.campaignmonitor.com/api/getting-started/) iš **paskyros nustatymų** kampanijos monitoriuje, kad gautumėte API sąrašo ID.
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių vienam eksportavimui į "Campaign Monitor", o tai gali užtrukti iki 20 minučių. Klientų profilių, kuriuos galite eksportuoti į "Campaign Monitor", skaičius priklauso nuo jūsų sutarties su "Campaign Monitor".
- Tik segmentai.

## <a name="set-up-connection-to-campaign-monitor"></a>Ryšio su „Campaign Monitor“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Kampanijos monitorius**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Campaign Monitor“.

1. Pažymėkite **Autentifikuoti naudojant „Campaign Monitor“** ir pateikite savo „Campaign Monitor“ administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Campaign Monitor“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite **kampanijos monitoriaus sąrašo ID.**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. To reikia norint segmentus eksportuoti į „Campaign Monitor“.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
