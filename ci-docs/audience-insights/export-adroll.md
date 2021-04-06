---
title: „Customer Insights” duomenų eksportavimas į „AdRoll”
description: Sužinokite, kaip konfigūruoti ryšį su „AdRoll”.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697084"
---
# <a name="connector-for-adroll-preview"></a>„AdRoll” jungtis (peržiūros versija)

Eksportuokite vieningųjų klientų profilių segmentus į „AdRoll” ir naudokite juos reklamai. 

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„AdRoll” abonementą](https://www.adroll.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="connect-to-adroll"></a>Prisijungti prie „AdRoll“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Dalyje **„AdRoll”** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll ryšio konfigūravimo sritis.":::

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ryšio su „AdRoll” inicijavimui.

1. Pasirinkite **Autentifikuoti su „AdRoll”** ir pateikite savo administratoriaus kredencialus, skirtus „AdRoll”. 

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Įveskite savo **„AdRoll” reklamuotojo ID**[„AdRoll” reklamuotojas](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Būtina eksportuoti segmentus į „AdRoll”.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Pasirinkite segmentą, turintį mažiausiai 100 narių. Negalite eksportuoti mažesnių segmentų. Be to, didžiausias eksportuojamo segmento dydis yra 250'000 narių vienam eksportavimui. 

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

## <a name="known-limitations"></a>Žinomi apribojimai

- Į „AdRoll” galite eksportuoti iki 250'000 profilių per vieną eksportavimą.
- Į „AdRoll” negalite eksportuoti segmentų, kuriuose yra mažiau nei 100 profilių. 
- Eksportavimas į „AdRoll” ribojamas segmentais.
- Iki 250'000 profilių eksportavimas į „AdRoll” gali užtrukti iki 10 minučių. 
- Profilių skaičius, kurį galite eksportuoti į „AdRoll“ priklauso ir yra apribotas jūsų sutartimi su „AdRoll“.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „AdRoll”, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai konfidencialius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „AdRoll“ atitiktų visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
