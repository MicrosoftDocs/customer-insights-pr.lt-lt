---
title: „Customer Insights“ duomenų eksportavimas į „Microsoft Advertising“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Microsoft Advertising“.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031482"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentų eksportavimas į „Microsoft Advertising“ (peržiūra)

Eksportuokite „Customer Insights” segmentus į „Microsoft Advertising”, kad sukurtumėte Klientų atitikmenų auditorijas. Naudokite šias auditorijas savo reklamos kampanijoms.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   [„Microsoft Advertising“ paskyra](https://ads.microsoft.com/) ir atitinkami administratoriaus kredencialai.
-   Priėmėte „Customer Match” naudojimo sąlygas. 
-   [Sukonfigūruoti segmentai](segments.md) auditorijos įžvalgose.
-   Vieningieji klientų profiliai, esantys eksportuotuose segmentuose, ir turintys lauką su el. pašto adresu.

## <a name="known-limitations"></a>Žinomi apribojimai

- Vienu metu į „Microsoft Advertising“ galima eksportuoti iki 500 tūkstančių profilių.
- Eksportavimas į „Microsoft Advertising“ apsiriboja segmentais.
- Iki 500 tūkstančių profilių eksportavimas į „Microsoft Advertising“ gali užtrukti iki 10 minučių. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Ryšio su „Microsoft Advertising” nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtrauktti ryšį** ir pasirinkite **„Microsoft Advertising“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Numatytasis parametras yra administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ryšio su „Microsoft Advertising“ inicijavimui.

1. Pažymėkite **Autentifikuoti naudojant „Microsoft Advertising“** ir pateikite savo „Microsoft Advertising“ administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „Microsoft Advertising“ skyriaus. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pasirinkite segmentus eksportavimui. Klientų atitikmens auditorijos yra automatiškai sukuriamos „Microsoft Advertising” su eksportavimui pasirinktų segmentų pavadinimu. Kiekviename segmente bus sukurta atskira Klientų atitikmens auditorija. 

1. Įveskite savo **„Microsoft Advertising” Kliento ID ir Paskyros ID**. Galite rasti Kliento ID (`cid`) ir Paskyros ID (`aid`) URL parametruose, kai esate prisijungę prie „Microsoft Advertising”.

1. Skyriaus **Duomenų gretinimas** lauke **El. paštas** pasirinkite savo vieningojo kliento profilio lauką su kliento el. pašto adresu. To reikia norint eksportuoti segmentus į „Microsoft Advertising“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „Microsoft Advertising“, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai slaptus duomenis, pavyzdžiui, Asmeninius duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, jog „Microsoft Advertising“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ Administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu tam, kad sustabdytų šios funkcijos naudojimą.
