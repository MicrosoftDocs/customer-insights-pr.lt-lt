---
title: "\"Customer Insights\" duomenų eksportavimas į \"HubSpot\""
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į "HubSpot".
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588933"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmentų eksportavimas į "HubSpot" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "HubSpot" ir naudokite juos el. pašto rinkodarai.

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

- " [HubSpot" abonementą](https://www.hubspot.com/) ir atitinkamus administratoriaus kredencialus.
- [API raktas](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) iš HubSpot.
- [Sukonfigūruoti segmentai](segments.md) "Customer Insights".

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 100'000 klientų profilių vienam eksportui į "HubSpot", o tai gali užtrukti iki 15 minučių. Klientų profilių, kuriuos galite eksportuoti į "HubSpot", skaičius priklauso nuo jūsų sutarties su "HubSpot" ir yra ribojamas.
- Tik segmentai.

## <a name="set-up-connection-to-hubspot"></a>Ryšio su "HubSpot" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **"HubSpot"**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Kai būsite paraginti, įveskite "HubSpot" kredencialus.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį su "HubSpot".

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus "HubSpot". Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius veiksmus su kitais pasirinktiniais laukais.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
