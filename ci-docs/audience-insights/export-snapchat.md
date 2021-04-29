---
title: „Customer Insights“ duomenų eksportavimas į „Snapchat“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Snapchat“.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760585"
---
# <a name="export-segment-lists-to-snapchat-preview"></a>Segmentų sąrašų eksportavimas į „Snapchat“ (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į „Snapchat“ ir naudokite juos reklamai. 

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Snapchat“ įmonės paskyrą](https://business.snapchat.com/), [„Snapchat Ads“ paskyrą](https://ads.snapchat.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Segmentų eksportavimas į „Snapchat“ ribojamas.
- Iki 1 milijono profilių eksportavimas į „Snapchat“ gali užtrukti iki 15 min. 

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

1. Įveskite [**„Snapchat“ auditorijos ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. To reikia norint segmentus eksportuoti į „Snapchat“.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „Snapchat“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „Snapchat“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.