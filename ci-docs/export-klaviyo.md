---
title: „Customer Insights“ duomenų eksportavimas į „Klaviyo“
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Klaviyo“.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aa6d43884e5e57af4627b7d5a857d3043abcd026
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643773"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Segmentų sąrašų eksportavimas į "Klaviyo" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į „Klaviyo" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Klaviyo“ paskyrą](https://www.klaviyo.com/) ir atitinkamus administratoriaus kredencialus.
-   Sukonfigūravote [segmentus](segments.md) programoje "Customer Insights".
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Į „Klaviyo‟ iš viso galima eksportuoti iki 100 000 eksportuojamų klientų profilių.
- Eksportavimas į „Klaviyo“ ribojamas segmentais.
- Iki 1 milijono klientų profilių eksportavimas į „Klaviyo“ gali užtrukti iki 20 minučių. 
- Klientų profilių, kuriuos galite eksportuoti į „Klaviyo“, skaičius priklauso ir yra apribotas pagal sutartį su „Klaviyo“.

## <a name="set-up-connection-to-klaviyo"></a>Nustatyti ryšį su „Klaviyo“

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **„Klaviyo“** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite savo ["Klaviyo" API raktą](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) kad tęstumėte prisijungimą. 

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** siekiant pradėti jungtį su „Klaviyo“.

1. Pasirinkite **Autentifikuoti su „Klaviyo”** ir pateikite savo „Klaviyo” administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „Klaviyo“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo [**Klaviyo sąrašo ID**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Būtina eksportuoti segmentus į „Klaviyo“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis į "Klaviyo", leidžiate perduoti duomenis už tos sienos ribų Dynamics 365 Customer Insights“, įskaitant galimai jautrius duomenis, tokius kaip asmens duomenis. „Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Klaviyo“ privatumo arba saugos apsauga. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
