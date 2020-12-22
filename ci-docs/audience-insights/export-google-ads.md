---
title: Eksportuoti „Customer Insights“ duomenis į „Google Ads“
description: Sužinokite, kaip konfigūruoti jungtį su „Google Ads“.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568472"
---
# <a name="connector-for-google-ads-preview"></a>Jungtis „Google Ads“ (peržiūra)

Eksportuoti suvienodintų kliento profilių segmentus į „Google Ads“ publikos sąrašą ir naudoti juos reklamavimui „Google Search“, „Gmail“, „YouTube“ ir „Google Display Network“. 

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Google Ads“ paskyrą](https://ads.google.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių publikų „Google Ads“ ir atitinkamų ID. Dėl daugiau informacijos, žr. [„Google Ads“ publikos](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Turite [konfigūruoti segmentus](segments.md)
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelius rodančius el. pašto adresą, vardą ir pavardę

## <a name="connect-to-google-ads"></a>Prisijungti prie „Google Ads“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Skyriuje **„Google Ads“** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

1. Įveskite savo **[„Google Ads“ kliento ID](https://support.google.com/google-ads/answer/1704344)**.

1. Įveskite savo **[„Google Ads“ patvirtinto kūrėjo žymą](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Įveskite savo **[„Google Ads“ publikos ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ir pasirinkite **Sujungti** tam, kad pradėtumėte sujungimą su „Google Ads“.

1. Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportuoti momentinę nuotrauką „Google Ads“ jungčiai":::

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius **Vardo** ir **Pavardės** laukeliams.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Google Ads“.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab). „Google Ads“ galite dabar surasti savo segmentus skyriuje [„Google Ads“ publikos](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „Google Ads“.
- Eksportavimas į „Google Ads“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 5 minučių dėl apribojimų tiekėjo pusėje. 
- Suderinamumas „Google Ads“ gali trukti iki 48 valandų.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Google Ads“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Google Ads“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
