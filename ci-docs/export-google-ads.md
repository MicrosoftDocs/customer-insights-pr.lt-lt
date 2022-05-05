---
title: Eksportuoti „Customer Insights“ duomenis į „Google Ads“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Google Ads“.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3e0eb91be97d69a999e90708d29c572f0055527e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643399"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentų eksportavimas į „Google Ads“ (peržiūra)

Eksportuokite unifikuotų klientų profilių segmentus į „Google Ads" auditorijų sąrašą ir naudokite juos norėdami juos naudoti reklamuojant „Google" paiešką, „Gmail" „YouTube“ ir „Google Display Network". 


## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Google Ads“ paskyrą](https://ads.google.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Atitinkate [„Customer Match Policy“ reikalavimus](https://support.google.com/adspolicy/answer/6299717).
-   Atitinkate [pakartotinės rinkodaros sąrašo dydžių reikalavimus](https://support.google.com/google-ads/answer/7558048).
-   Turite [konfigūruoti segmentus](segments.md).
-   Vieninguose klientų profiliuose eksportuotuose segmentuose yra laukų, nurodančių el. pašto adresą, telefoną, mobiliojo reklamuotojo ID, trečiosios šalies vartotojo ID arba adresą.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportavimas į „Google Ads“ yra apribotas segmentais.
- Dėl paslaugų teikėjų apribojimų segmentai, kuriuose iš viso yra 1 milijono klientų profilių, gali trukti iki 30 minučių. 
- Suderinamumas „Google Ads“ gali trukti iki 48 valandų.

## <a name="set-up-connection-to-google-ads"></a>Ryšio su „Google Ads“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Google Ads“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **[„Google Ads“ kliento ID](https://support.google.com/google-ads/answer/1704344)**.

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Google Ads“. Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.

1. Jei norite sukurti naują auditoriją, palikite "Google Audience ID" lauką tuščią. Mes automatiškai sukursime naują auditoriją "Google Ads" paskyroje ir naudosime eksportuoto segmento pavadinimą. Jei norite atnaujinti esamą "Google Ads" auditoriją, įveskite ["Google Ads" auditorijos ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Sekcijoje **Duomenų atitikimas** pasirinkite vieną ar daugiau eksportuotinų duomenų laukų ir pasirinkite lauką, kuris nurodo atitinkamus "Customer Insights" duomenų laukus.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. 

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). 

Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Google Ads“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Google Ads“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.


[!INCLUDE [footer-include](includes/footer-banner.md)]
