---
title: Segmentų eksportavimas į „Autopilot“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Autopilot“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724767"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentų eksportavimas į „Autopilot“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „Autopilot” kontaktų sąrašus ir naudokite juos el. pašto rinkodarai naudojant „Autopilot”.

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

- Autopiloto abonementas [ir](https://www.autopilothq.com/) atitinkami administratoriaus kredencialai.
- Autopiloto [API raktas](https://autopilot.docs.apiary.io/#)
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 100 000 klientų profilių vienam eksportavimui į "Autopilot", o tai gali užtrukti iki kelių valandų. Klientų profilių, kuriuos galite eksportuoti į "Autopilot", skaičius priklauso nuo jūsų sutarties su "Autopilot".
- Tik segmentai.

## <a name="set-up-connection-to-autopilot"></a>Ryšio su „Autopilot“ sąranka

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Autopilotas**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite „Autopilot“ API raktą.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Autopilot“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai eksportuokite kitus laukus, pvz., **vardas** ir **pavardė**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti laikydamiesi žinomų apribojimų.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
