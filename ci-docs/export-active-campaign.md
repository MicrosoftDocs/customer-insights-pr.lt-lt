---
title: Segmentų eksportavimas į "ActiveCampaign"
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „ActiveCampaign“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725410"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentų eksportavimas į „ActiveCampaign“ (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į „ActiveCampaign" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- "ActiveCampaign" [paskyrą](https://www.activecampaign.com/) ir atitinkamus administratoriaus kredencialus.
- ["ActiveCampaign" sąrašo ID](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- ["ActiveCampaign" API raktas](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ir REST galinio punkto pagrindinio kompiuterio pavadinimas.
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių vienam eksportavimui į "ActiveCampaign", o tai gali užtrukti iki 90 minučių. Klientų profilių, kuriuos galite eksportuoti į „ActiveCampaign", skaičius priklauso nuo sutarties su „ActiveCampaign".
- Tik segmentai.

## <a name="set-up-connection-to-activecampaign"></a>Nustatyti ryšį su „ActiveCampaign“

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **"ActiveCampaign**".

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo „ActiveCampaign API" raktą ir REST galinių punktų pagrindinio kompiuterio pavadinimą. REST galinio punkto pagrindinio kompiuterio vardas yra tik pagrindinio kompiuterio vardas be https://.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „ActiveCampaign“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite savo **"ActiveCampaign" sąrašo ID.**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai eksportuokite **vardas**, pavardė **ir** telefoną **,** kad sukurtumėte labiau suasmenintus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
