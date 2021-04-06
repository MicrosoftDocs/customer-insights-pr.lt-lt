---
title: Eksportuoti „Customer Insights“ duomenis į „DotDigital“
description: Sužinokite, kaip konfigūruoti jungtį su „DotDigital“.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598027"
---
# <a name="connector-for-dotdigital-preview"></a>Jungtis „DotDigital“ (peržiūra)

Eksportuokite suvienodintų klientų profilio segmentus į „DotDigital“ adresų knygas ir naudokite juos kampanijos, el. pašto reklamavimui ir siekiant kurti tinkintus segmentus su „DotDigital“. 

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„DotDigital“ paskyrą](https://dotdigital.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių adreso knygų „DotDigital“ ir atitinkamų ID. ID gali būti prieinamas URL, kurį pasirinkote ir atvėrėte adresų knygoje. Dėl daugiau informacijos, žr. [„DotDigital“ adresų knygos](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="connect-to-dotdigital"></a>Prisijunkite prie „DotDigital“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Skyriuje **„DotDigital“** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigūravimo juosta „DotDigital“ eksportavimui.":::

1. Įveskite savo **„DotDigital“ vartotojo vardą ir slaptažodį**.

1. Įveskite savo **[„DotDigital“ adreso knygos ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Sujungti** siekiant pradėti sujungimą su „DotDigital“.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius kitiems pasirenkamiems laukeliams, tokius kaip **Vardas**, **Pavardė**, **Vardas ir pavardė**, **Lytis** ir **Pašto kodas**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „DotDigital“.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab). „DotDigital“ galite dabar surasti savo segmentus skyriuje [„DotDigital“ adresų knygose](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „DotDigital“.
- Eksportavimas į „DotDigital“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų dėl apribojimų tiekėjo pusėje. 
- Profilių skaičius, kurį galite eksportuoti į „DotDigital“ priklauso ir yra apribotas jūsų sutartimi su „DotDigital“.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „DotDigital“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „DotDigital“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]