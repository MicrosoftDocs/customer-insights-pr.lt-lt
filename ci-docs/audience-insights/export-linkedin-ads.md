---
title: „Customer Insights“ duomenų eksportavimas į „LinkedIn Ads”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „LinkedIn Ads”.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866898"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentų eksportavimas į „LinkedIn Ads” (peržiūra)

Eksportuokite vieningųjų klientų profilius į „LinkedIn Ads”, kad sukurtumėte „matched audiences”. Naudokite „matched audiences”, kad būtų galima taikyti pagal įmonę ir pagal kontaktus.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [LinkedIn Campaign Manager abonementą](https://business.linkedin.com/marketing-solutions/ads) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Klientų profiliuose, esančiuose eksportuotuose segmentuose, yra laukas su el. pašto adresu.

## <a name="known-limitations"></a>Žinomi apribojimai

- Jūsų segmente programoje "Customer Insights" turi būti bent 300 unikalių profilių. 
- Į „LinkedIn Ads‟ iš viso galima eksportuoti iki 100 tūkstančių eksportuojamų klientų profilių.
- Eksportavimas į „LinkedIn Ads“ apsiriboja segmentais.
- Iki 100 tūkstančių klientų profilių eksportavimas į „LinkedIn Ads“ gali užtrukti iki 10 minučių. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Ryšio su „LinkedIn Ads” nustatymas

1. Auditorijos įžvalgose eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtrauktti ryšį** ir pasirinkite **„LinkedIn Ads“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei neatliksite jokio veiksmo, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite [savo LinkedIn Campaign Manager paskyros ID](https://www.linkedin.com/help/lms/answer/a424270).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Campaign Monitor“.

1. Pasirinkite **Autentifikuoti naudojant "LinkedIn"** ir pateikite savo administratoriaus kredencialus LinkedIn Campaign Manager.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Galite sukonfigūruoti eksportavimą, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „LinkedIn Ads“ skyriaus. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pasirinkite, ar norite eksportuoti duomenis [taikymui pagal kontaktą](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ar [taikymui pagal įmonę](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) „LinkedIn” platformoje. 

1. Jei tai kontaktas, skyriuje **Duomenų gretinimas** pažymėkite bent vieną lauką, kuriame pateikiamas kliento el. pašto adresas „Apple Ad ID", „Google Ad ID", „Google" vartotojo ID arba pirmasis pavardė. Jei pasirinksite taiką pagal įmonę, pažymėkite bent vieną lauką, kuriame pateikiamas įmonės pavadinimas, el. pašto domenas, „LinkedIn" puslapio URL, akcijų simbolis arba svetainė. Papildomus laukus galima pasirinkti norint labiau apibrėžti eksportavimą. 

1. Pasirinkite segmentus, kuriuos norite eksportuoti. LinkedIn Campaign Manager suderintos auditorijos bus automatiškai sukurtos su segmentų, kuriuos pasirinkote eksportuoti, pavadinimu. Kiekviename segmente bus sukurta atskira „matched audience”. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis į "LinkedIn Ads", leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant potencialiai neskelbtinus duomenis, pvz., Asmens duomenis. „Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, jog „LinkedIn Ads“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų Dynamics 365 Customer Insights administratorius gali bet kuriuo metu pašalinti šią eksportavimo paskirties vietą, kad sustabdytų šios funkcijos naudojimą.
