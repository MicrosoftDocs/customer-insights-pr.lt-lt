---
title: Segmentų eksportavimas į Criteo (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082789"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentų eksportavimas į Criteo (peržiūra)

Eksportuokite vieningų klientų profilių segmentus, kad sukurtumėte kampanijas, teiktumėte rinkodarą el. paštu ir naudotumėte konkrečias klientų grupes naudodami "Criteo".

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

-   Turite [Criteo Dynamics Retargeting paskyrą](https://www.criteo.com/login/) ir atitinkamus administratoriaus kredencialus.
-   Turite [konfigūruoti segmentus](segments.md).
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono klientų profilių vienam eksportui į Criteo.
- Eksportavimas į Criteo apsiriboja segmentais.
- Iš viso 1 milijono klientų profilių segmentų eksportavimas gali trukti iki 30 minučių. 
- Klientų profilių, kuriuos galite eksportuoti į Criteo, skaičius priklauso nuo jūsų sutarties su Criteo ir yra ribotas.

## <a name="set-up-connection-to-criteo"></a>Ryšio su Criteo nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Criteo**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkite **Sutinku**, kad patvirtintumėte duomenų privatumą **ir atitiktį**, ir pasirinkite **Prisijungti**, kad pradėtumėte ryšį su Criteo.

1. Pasirinkite **Autentifikuoti naudojant Criteo** ir pateikite savo administratoriaus vartotojo vardą bei "Criteo" kredencialus. 

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. **Lauke Ryšys eksportavimui** pasirinkite ryšį iš skyriaus Criteo. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių. 

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. 

1. Pasirinktinai galite eksportuoti **reklamuotojo ID** ir **vardą**

1. Pasirinkite segmentus, kuriuos norite eksportuoti. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis "Criteo", leidžiate perduoti duomenis už atitikties ribos Dynamics 365 Customer Insights ribų, įskaitant potencialiai neskelbtinus duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, bet jūs esate atsakingi už tai, kad "Criteo" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](includes/footer-banner.md)]
