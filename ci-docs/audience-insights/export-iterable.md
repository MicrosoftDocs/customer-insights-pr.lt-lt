---
title: Eksportuoti "Customer Insights" duomenis į pasikartojančius duomenis
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į "Iterable".
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4de499fcc4a5a0dcc2dfd3bae02913c81a59647b
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524592"
---
# <a name="export-segment-lists-to-iterable-preview"></a>Segmentų sąrašų eksportavimas į "Iterable" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "Iterable" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite pasikartojantį abonementą [ir](https://iterable.com/) atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportas į "Iterable" apsiriboja segmentais.
- Iki 1 milijono klientų profilių eksportas į "Iterable" gali užtrukti iki 30 minučių. 
- Klientų profilių, kuriuos galite eksportuoti į "Iterable", skaičius priklauso ir yra ribotas nuo jūsų sutarties su "Iterable".

## <a name="set-up-connection-to-iterable"></a>Nustatyti ryšį su pasikartojančiu

1. Eikite į **Administravimas** > **Ryšiai**.

1. Norėdami konfigūruoti ryšį, pasirinkite **Įtraukti ryšį** ir pasirinkite **Iterable**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite pasikartojantį [API raktą](https://support.iterable.com/hc/en-us/articles/360043464871), kad galėtumėte toliau prisijungti. 

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su iterable.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke Ryšys **eksportui** pasirinkite ryšį iš sekcijos Pasikartojantis. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

3. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Būtina eksportuoti segmentus į Iterable.Iterable sukurtas sąrašas gaus tą patį pavadinimą kaip ir segmento Dynamics 365 Customer Insights pavadinimas.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate Dynamics 365 Customer Insights perduoti duomenis "Iterable", leidžiate perduoti duomenis už atitikties ribos, įskaitant potencialiai neskelbtinus Dynamics 365 Customer Insights duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "Iterable" atitiktų visus privatumo ar saugos įsipareigojimus, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
