---
title: Eksportuoti „Customer Insights“ duomenis į „Marketo“
description: Sužinokite, kaip konfigūruoti jungtį su „Marketo“.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570413"
---
# <a name="connector-for-marketo-preview"></a>Jungtis „Marketo“ (peržiūra)

Eksportuokite suvienodintų klientų profilio segmentus siekiant sugeneruoti kampanijas, pateikti el. pašto reklamavimą ir naudoti konkrečias klientų grupes su „Marketo“.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Marketo“ paskyrą](https://login.marketo.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių sąrašų „Marketo“ ir atitinkamų ID. Dėl daugiau informacijos, žr. [„Marketo“ sąrašus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Turite [konfigūruoti segmentus](segments.md).
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="connect-to-marketo"></a>Prisijunkite prie „Marketo“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Skyriuje **„Marketo“** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

1. Įveskite savo **[„Marketo“ kliento ID, Kliento saugų ir REST galutinio taško šeimininko pavadinimą](https://developers.marketo.com/rest-api/authentication/)**.

1. Įveskite savo **[„Marketo“ sąrašo ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Pasirinkite **Sutikti** siekiant patvirtinti **Duomenų privatumą ir atitiktį** ir pasirinkite **Sujungti** siekiant pradėti jungį su „Marketo“.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportuoti momentinę nuotrauką „Marketo“ jungčiai":::

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. 

1. Pasirinktinai, galite eksportuoti **Vardą**, **Pavardę**, **Miestą**, **Valstiją** ir **Šalį/Regioną**  kaip papildomus laukelius siekiant sukurti labiau suasmenintus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Marketo“.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Pasirinkite laukelius ir segmentus eksportavimui į „Marketo“":::

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab). „Marketo“ galite dabar surasti savo segmentus skyriuje [„Marketo“ sąrašus](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „Marketo“.
- Eksportavimas į „Marketo“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų. 
- Profilių skaičius, kurį galite eksportuoti į „Marketo“ priklauso ir yra apribojtas jūsų sutartimi su „Marketo“.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Marketo“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Marketo“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
