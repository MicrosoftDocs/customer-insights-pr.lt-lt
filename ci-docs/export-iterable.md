---
title: Segmentų eksportavimas į Iterable (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724556"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentų eksportavimas į Iterable (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "Iterable" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Iterable abonementas [ir](https://iterable.com/) atitinkami administratoriaus kredencialai.
- Iterable [API raktas](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių iki "Iterable", o tai gali užtrukti iki 30 minučių. Klientų profilių, kuriuos galite eksportuoti į Iterable, skaičius priklauso nuo jūsų sutarties su Iterable.
- Tik segmentai.

## <a name="set-up-connection-to-iterable"></a>Nustatykite ryšį su Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Iterable**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite iterable API raktą, kad galėtumėte toliau prisijungti.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. **Lauke Ryšys eksportui** pasirinkite ryšį iš Iterable skyriaus. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Iterable sukurtas sąrašas gaus tą patį pavadinimą kaip ir jūsų segmento pavadinimas Dynamics 365 Customer Insights.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
