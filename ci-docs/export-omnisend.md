---
title: „Customer Insights“ duomenų eksportavimas į „Omnisend“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Omnisend“.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 70bd94ea5e4060094c3d215e3fc263a98df51229
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643648"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentų eksportavimas į „Omnisend“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „Omnisend“ ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Omnisend“ paskyrą](https://www.omnisend.com/) ir atitinkamus administratoriaus kredencialus.
-   Sukonfigūravote [segmentus](segments.md) programoje "Customer Insights".
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportuojant į „Omnisend" galima eksportuoti iki 1 milijonai klientų profilių, o užbaigti gali trukti iki 4 valandų.
- Eksportavimas į „Omnisend“ apsiriboja segmentais.
- Klientų profilių, kuriuos galite eksportuoti į „Omnisend", skaičius priklauso nuo sutarties su „Omnisend".

## <a name="set-up-connection-to-omnisend"></a>Ryšio su „Omnisend“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **„Omnisend“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo [„Omnisend“ API raktą](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ryšio su „Omnisend“ inicijavimui.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „Omnisend“ skyriaus. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. To reikia norint eksportuoti segmentus į „Omnisend“. Pasirinktinai galite eksportuoti Vardą, Pavardę, Adresą, Šalį/Regioną, Valstiją, Miestą ir Pašto kodą, jei norite sukurti labiau personalizuotus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „Omnisend“, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galima slaptus duomenis, pavyzdžiui, Asmeninius duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, kad „Omnisend“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.
