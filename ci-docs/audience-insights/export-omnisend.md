---
title: „Customer Insights“ duomenų eksportavimas į „Omnisend“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Omnisend“.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124523"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentų eksportavimas į „Omnisend“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „Omnisend“ ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Omnisend“ paskyrą](https://www.omnisend.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Vieno eksportavimo į „Omnisend” metu galite eksportuoti iki 1 milijono profilių ir tai gali užtrukti iki 4 valandų.
- Eksportavimas į „Omnisend“ apsiriboja segmentais.
- Profilių, kuriuos galite eksportuoti į „Omnisend”, skaičius priklauso nuo jūsų sutarties su „Omnisend”.

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

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. To reikia norint eksportuoti segmentus į „Omnisend“. Pasirinktinai galite eksportuoti Vardą, Pavardę, Adresą, Šalį/Regioną, Valstiją, Miestą ir Pašto kodą, jei norite sukurti labiau personalizuotus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „Omnisend“, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galima slaptus duomenis, pavyzdžiui, Asmeninius duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, kad „Omnisend“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.
