---
title: „Customer Insights“ duomenų eksportavimas į „Campaign Monitor“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Campaign Monitor“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124191"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentų eksportavimas į „Campaign Monitor“ (peržiūros versija)

Eksportuokite vieningų klientų profilių segmentus į „Campaign Monitor“ ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„Campaign Monitor“ paskyros](https://www.campaignmonitor.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Vienu metu į „Campaign Monitor“ galima eksportuoti iki 1 milijono profilių.
- Eksportavimas į „Campaign Monitor“ leidžiamas tik segmentuose.
- Iki 1 milijono profilių eksportavimas į „Campaign Monitor“ gali užtrukti iki 20 min. 
- Profilių, kuriuos galite eksportuoti į „Campaign Monitor“ yra ribojamas ir priklauso nuo jūsų sutarties su „Campaign Monitor“.

## <a name="set-up-connection-to-campaign-monitor"></a>Ryšio su „Campaign Monitor“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Campaign Monitor“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Campaign Monitor“.

1. Pažymėkite **Autentifikuoti naudojant „Campaign Monitor“** ir pateikite savo „Campaign Monitor“ administratoriaus kredencialus.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Campaign Monitor“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo [**„Campaign Monitor“ sąrašo ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Norėdami peržiūrėti PI sąrašo ID pirmiausia sugeneruokite API raktą](https://www.campaignmonitor.com/api/getting-started/) „Campaign Monitor“ **paskyros nustatymų** srityje.  

3. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. To reikia norint segmentus eksportuoti į „Campaign Monitor“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „Campaign Monitor“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „Campaign Monitor“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
