---
title: „Customer Insights” duomenų eksportavimas į „Autopilot”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Autopilot“.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7a7a67a52fcf39da8d50bd95817d25470fc90b6f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227676"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentų eksportavimas į „Autopilot“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „Autopilot” kontaktų sąrašus ir naudokite juos el. pašto rinkodarai naudojant „Autopilot”. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Autopilot” abonementą](https://www.autopilothq.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Į „Autopilot‟ iš viso galima eksportuoti iki 100 000 klientų profilių.
- Eksportavimas į „Autopilot” ribojamas segmentais.
- Iki 100 000 klientų profilių eksportavimas į „Autopilot" gali užtrukti iki kelių valandų. 
- Klientų profilių, kuriuos galite eksportuoti į „Autopilot“, skaičius priklauso ir yra apribotas pagal sutartį su „Autopilot“.

## <a name="set-up-connection-to-autopilot"></a>Ryšio su „Autopilot“ sąranka

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Autopilot“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite [„Autopilot“ API raktą](https://autopilot.docs.apiary.io/#).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „Autopilot”.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Autopilot“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.: **Vardas** ar **Pavardė**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „Autopilot”. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis iš „Dynamics 365 Customer Insights” į „Autopilot”, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis. „Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „Autopilot” atitiktų privatumo arba saugos reikalavimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
