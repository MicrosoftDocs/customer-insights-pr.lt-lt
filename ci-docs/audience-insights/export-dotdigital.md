---
title: Eksportuoti „Customer Insights“ duomenis į „DotDigital“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „DotDigital“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124421"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentų eksportavimas į „DotDigital“ (peržiūros versija)

Eksportuokite suvienodintų klientų profilio segmentus į „DotDigital“ adresų knygas ir naudokite juos kampanijos, el. pašto reklamavimui ir siekiant kurti tinkintus segmentus su „DotDigital“. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„DotDigital“ paskyrą](https://dotdigital.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių adreso knygų „DotDigital“ ir atitinkamų ID. ID gali būti prieinamas URL, kurį pasirinkote ir atvėrėte adresų knygoje. Dėl daugiau informacijos, žr. [„DotDigital“ adresų knygos](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „DotDigital“.
- Eksportavimas į „DotDigital“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų dėl apribojimų tiekėjo pusėje. 
- Profilių skaičius, kurį galite eksportuoti į „DotDigital“ priklauso ir yra apribotas jūsų sutartimi su „DotDigital“.

## <a name="set-up-connection-to-dotdigital"></a>„DotDigital“ ryšio sąranka

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„DotDigital“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **„DotDigital“ vartotojo vardą ir slaptažodį**.

1. Įveskite savo **[„DotDigital“ adreso knygos ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Sujungti** siekiant pradėti sujungimą su „DotDigital“.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „DotDigital“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.


1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius kitiems pasirenkamiems laukeliams, tokius kaip **Vardas**, **Pavardė**, **Vardas ir pavardė**, **Lytis** ir **Pašto kodas**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „DotDigital“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 
 
„DotDigital“ galite dabar surasti savo segmentus skyriuje [„DotDigital“ adresų knygose](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „DotDigital“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „DotDigital“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
