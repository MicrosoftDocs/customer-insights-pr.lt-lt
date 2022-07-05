---
title: Segmentų eksportavimas į „AdRoll“ (peržiūros versija)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „AdRoll“.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 13c7dd3b8556ad807fba6c537525b463480e860b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082831"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentų eksportavimas į „AdRoll“ (peržiūros versija)

Eksportuokite vieningųjų klientų profilių segmentus į „AdRoll” ir naudokite juos reklamai. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

- Turite [„AdRoll” abonementą](https://www.adroll.com/) ir atitinkamus administratoriaus kredencialus.
- Sukonfigūravote [segmentus](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Vienu metu į „AdRoll“ galite eksportuoti iki 250 000 klientų profilių.
- Į „AdRoll‟ negalite eksportuoti segmentų, kuriuose yra mažiau nei 100 klientų profilių. 
- Eksportavimas į „AdRoll” ribojamas segmentais.
- Iki 250 000 klientų profilių eksportavimas į „AdRoll" gali užtrukti iki 10 minučių. 
- Klientų profilių, kuriuos galite eksportuoti į „AdRoll", skaičius priklauso nuo sutarties su „AdRoll".

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

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „AdRoll“. Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.

1. Įveskite Ad **AdRoll reklamuotojo ID**. Daugiau informacijos rasite informacijos [„AdRoll Advertiser Profiles“](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Būtina eksportuoti segmentus į „AdRoll”.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Pasirinkite segmentą, turintį mažiausiai 100 narių. Negalite eksportuoti mažesnių segmentų. Be to, didžiausias eksportuojamo segmento dydis yra 250 000 narių vienam eksportavimui. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). 

Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „AdRoll”, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai konfidencialius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „AdRoll“ atitiktų visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.
