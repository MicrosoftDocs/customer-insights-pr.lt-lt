---
title: Eksportuoti „Customer Insights“ duomenis į „Marketo“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Marketo“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759831"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentų eksportavimas į „Marketo“ (peržiūra)

Eksportuokite suvienodintų klientų profilio segmentus siekiant sugeneruoti kampanijas, pateikti el. pašto reklamavimą ir naudoti konkrečias klientų grupes su „Marketo“.

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Marketo“ paskyrą](https://login.marketo.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių sąrašų „Marketo“ ir atitinkamų ID. Dėl daugiau informacijos, žr. [„Marketo“ sąrašus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Turite [konfigūruoti segmentus](segments.md).
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „Marketo“.
- Eksportavimas į „Marketo“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų. 
- Profilių skaičius, kurį galite eksportuoti į „Marketo“ priklauso ir yra apribotas jūsų sutartimi su „Marketo“.

## <a name="set-up-connection-to-marketo"></a>Ryšio su „Marketo“ sąranka

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Marketo“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **[„Marketo“ kliento ID, kliento slapyvardį ir REST galutinio taško pagrindinio kompiuterio pavadinimą](https://developers.marketo.com/rest-api/authentication/)**.

1. Pasirinkite **Sutikti** siekiant patvirtinti **Duomenų privatumą ir atitiktį** ir pasirinkite **Sujungti** siekiant pradėti ryšį su „Marketo“.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Marketo“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo **[„Marketo“ sąrašo ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. 

1. Taip pat galite eksportuoti **vardą**, **pavardę**, **miestą**, **valstiją** ir **šalį / regioną**, jei norite sukurti labiau personalizuotus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Marketo“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). „Marketo“ galite dabar surasti savo segmentus skyriuje [„Marketo“ sąrašus](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Marketo“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Marketo“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]