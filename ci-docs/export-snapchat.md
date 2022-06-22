---
title: „Customer Insights“ duomenų eksportavimas į „Snapchat“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Snapchat“.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947286"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentų eksportavimas į „Snapchat“ (peržiūros versija)

Eksportuokite vieningų klientų profilių segmentus į „Snapchat“ ir naudokite juos reklamai. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Snapchat“ įmonės paskyrą](https://business.snapchat.com/), [„Snapchat Ads“ paskyrą](https://ads.snapchat.com/) ir atitinkamus administratoriaus kredencialus. YOu turi būti bent jau organizacijos paskyros narys ir konkrečios skelbimo paskyros duomenų valdytojas. 
-   Turite bent vieną auditoriją SAM tipo "Snapchat Audience Manager" ("Snap Audience Match"). 
-   Sukonfigūravote [segmentus](segments.md) programoje "Customer Insights".
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Segmentų eksportavimas į „Snapchat“ ribojamas.
- Iki 1 milijono klientų profilių eksportavimas į „Snapchat“ gali užtrukti iki 15 minučių. 

## <a name="set-up-connection-to-snapchat"></a>Ryšio su „Snapchat“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Snapchat“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Snapchat“.

1. Pažymėkite **Autentifikuoti naudojant „Snapchat“** ir pateikite savo „Snapchat“ administratoriaus kredencialus. 

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Snapchat“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. [**Įveskite "Snapchat" segmento / auditorijos ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). Auditorijos ID galima rasti URL pasirinkus auditoriją "Snapchat Audience Manager". 

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. To reikia norint segmentus eksportuoti į „Snapchat“.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „Snapchat“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „Snapchat“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
