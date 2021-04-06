---
title: Eksportuoti „Customer Insights“ duomenis į „Mailchimp“
description: Sužinokite, kaip konfigūruoti jungtį su „Mailchimp“.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598211"
---
# <a name="connector-for-mailchimp-preview"></a>Jungtis „Mailchimp“ (peržiūra)

Eksportuoti suvienodintų kliento profilių segmentus į „Mailchimp“ siekiant sukurti naujienlaiškius ir el. pašto kampanijas.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Mailchimp“ paskyrą](https://mailchimp.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių publikų „Mailchimp“ ar atitinkamų ID. Dėl daugiau informacijos, žr. [„Mailchimp“ publikos](https://mailchimp.com/help/create-audience/).
-   Turite [konfigūruoti segmentus](segments.md)
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="connect-to-mailchimp"></a>Prisijungti prie „MailChimp“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Skyriuje **„Mailchimp“** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Įveskite savo **[„Mailchimp“ publikos ID](https://mailchimp.com/help/find-audience-id/)** ir pasirinkite **Sujungti** tam, kad pradėtumėte sujungimą su „Mailchimp“.

1. Pasirinkite **Autentifikuoti su „Mailchimp“** ir pateikti savo „Mailchimp“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportuoti momentinę nuotrauką „Mailchimp“ jungčiai":::

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. 

1. Pasirinktinai, galite eksportuoti **Vardą** ir **Pavardę** kaip papildomus laukelius norėdami sukurti labiau suasmenintus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Mailchimp“.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Pasirinkite laukelius ir segmentus eksportavimui į „Mailchimp“":::

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab). „Mailchimp“ galite dabar surasti savo segmentus skyriuje [„Mailchimp“ publikos](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „Mailchimp“.
- Eksportavimas į „Mailchimp“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki trijų valandų dėl apribojimų tiekėjo pusėje. 
- Profilių skaičius, kurį galite eksportuoti į „Mailchimp“ priklauso ir yra apribotas jūsų sutartimi su „Mailchimp“.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Mailchimp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Mailchimp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]