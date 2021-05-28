---
title: Eksportuoti „Customer Insights“ duomenis į „Google Ads“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Google Ads“.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976328"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentų eksportavimas į „Google Ads“ (peržiūra)

Eksportuoti suvienodintų kliento profilių segmentus į „Google Ads“ publikos sąrašą ir naudoti juos reklamavimui „Google Search“, „Gmail“, „YouTube“ ir „Google Display Network“. 

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Google Ads“ paskyrą](https://ads.google.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Turite patvirtintą [„Google Ads“ kūrėjo atpažinimo ženklą](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Atitinkate [klientų atitikties politikos](https://support.google.com/adspolicy/answer/6299717) reikalavimus
-   Atitinkate [pakartotinės rinkodaros sąrašo dydžių reikalavimus](https://support.google.com/google-ads/answer/7558048) 

-   Yra esančių publikų „Google Ads“ ir atitinkamų ID. Dėl daugiau informacijos, žr. [„Google Ads“ publikos](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Turite [konfigūruoti segmentus](segments.md)
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelius rodančius el. pašto adresą, vardą ir pavardę

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono profilių vieno eksportavimo metu į „Google Ads“.
- Eksportavimas į „Google Ads“ yra apribotas segmentais.
- Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 5 minučių dėl apribojimų tiekėjo pusėje. 
- Suderinamumas „Google Ads“ gali trukti iki 48 valandų.

## <a name="set-up-connection-to-google-ads"></a>Ryšio su „Google Ads“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Google Ads“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **[„Google Ads“ kliento ID](https://support.google.com/google-ads/answer/1704344)**.

1. Įveskite savo **[„Google Ads“ patvirtinto kūrėjo žymą](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Google Ads“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo **[„Google Ads“ publikos ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ir pasirinkite **Sujungti** tam, kad pradėtumėte sujungimą su „Google Ads“.

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius **Vardo** ir **Pavardės** laukeliams.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Google Ads“.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Google Ads“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Google Ads“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
