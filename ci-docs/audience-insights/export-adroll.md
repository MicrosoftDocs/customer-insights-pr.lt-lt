---
title: „Customer Insights” duomenų eksportavimas į „AdRoll”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „AdRoll“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124375"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentų eksportavimas į „AdRoll“ (peržiūros versija)

Eksportuokite vieningųjų klientų profilių segmentus į „AdRoll” ir naudokite juos reklamai. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„AdRoll” abonementą](https://www.adroll.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Į „AdRoll” galite eksportuoti iki 250'000 profilių per vieną eksportavimą.
- Į „AdRoll” negalite eksportuoti segmentų, kuriuose yra mažiau nei 100 profilių. 
- Eksportavimas į „AdRoll” ribojamas segmentais.
- Iki 250'000 profilių eksportavimas į „AdRoll” gali užtrukti iki 10 minučių. 
- Profilių skaičius, kurį galite eksportuoti į „AdRoll“ priklauso ir yra apribotas jūsų sutartimi su „AdRoll“.

## <a name="set-up-connection-to-adroll"></a>Ryšio su „AdRoll“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„AdRoll“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ryšio su „AdRoll” inicijavimui.

1. Pasirinkite **Autentifikuoti su „AdRoll”** ir pateikite savo administratoriaus kredencialus, skirtus „AdRoll”. 

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „AdRoll“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo **„AdRoll“ reklamuotojo ID** Daugiau informacijos žr. [„AdRoll“ reklamuotojo profiliai](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Būtina eksportuoti segmentus į „AdRoll”.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Pasirinkite segmentą, turintį mažiausiai 100 narių. Negalite eksportuoti mažesnių segmentų. Be to, didžiausias eksportuojamo segmento dydis yra 250'000 narių vienam eksportavimui. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „AdRoll”, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai konfidencialius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „AdRoll“ atitiktų visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
