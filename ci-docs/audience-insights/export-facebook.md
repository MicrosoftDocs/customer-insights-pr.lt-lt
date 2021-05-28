---
title: Eksportuoti „Customer Insights“ duomenis į „Facebook“ reklamos tvarkytuvą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Facebook „Ads Manager“.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976052"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmentų sąrašo eksportavimas į Facebook „Ads Manager“ (peržiūra)

Eksportuokite sujungtų klientų profilių segmentus į „Facebook“ reklamos tvarkytuvą, kad sukurtumėte kampanijas „Facebook“ ir „Instagram“.

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

- Turite turėti [**Facebook reklamos paskyrą**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kuroje yra [**Facebook įmonės paskyra**](https://business.facebook.com/).
- Jums reikia būti administratoriumi [**„Facebook“ reklamos paskyroje**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 10 mln. klientų profilių vienam eksportavimui į Facebook „Ads Manager“.
- Eksportavimas į Facebook „Ads Manager“ ribojamas segmentais.
- Sukurkite arba įkelkite pasirenkamas auditorijas tik Facebook tipo *klientų sąraše*.
- Segmentų, kurių bendra suma yra 10 mln. profilių, eksportavimas gali trukti iki 90 minučių.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Ryšio su Facebook „Ads Manager“ nustatymas

Kad naudotojai galėtų sukurti eksportavimą, administratorius turi sukonfigūruoti ryšį su paslauga ir bendradarbiams leisti naudoti ryšį.

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Facebook „Ads Manager“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus **Administratoriai**. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentifikuoti naudojant Facebook reklamą: 

   1. Pasirinkite **Tęsti naudojant „Facebook“**, kad prisijungtumėte prie „Facebook“ reklamos kliento.

   1. Leiskite **reklamos_valdymu** leidimą po autentifikavimo su „Facebook“.

   1. Pasirinkite **„Facebook“ reklamos klientą**, kurį norite naudoti.

   1. Išplečiamajame sąraše pasirinkite **Esama pasirinktinė auditorija** arba sukurkite **Nauja pasirinktinė auditorija**. Norėdami gauti daugiau informacijos, žr. [**„Facebook“ reklamos tvarkytuvo auditorijos**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Su šiuo eksportavimu galima sukurti arba atnaujinti pasirenkamas auditorijas Facebook tipo *klientų sąraše*. Kai kuriais atvejais išskleidžiamajame sąraše matote skirtingų tipų pasirinktines auditorijas. Pasirinkus kitą tipą, o ne *klientų sąrašą*, eksportavimas bus nevykdomas. 

1. Peržiūrėkite **Duomenų privatumas ir suderinamumas** ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**. 

1. Srityje **Eksportavimo ryšys** pasirinkite ryšį iš skilties **Facebook „Ads Manager“**. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Lauke **Pasirinkite rakto identifikatorių**, pasirinkite **El. paštas**, **Vardas ir adresas** arba **Telefonas**, siųstiną į „Facebook“ reklamos tvarkytuvą. 

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.

1. Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.
   > [PATARIMAS] Labiausiai tikėtina, kad bus atitikimų, jei pažymėsite rakto identifikatorių **El. paštas**. Įtraukus papildomų identifikatorių, gali pagerėti atitikimų nustatymas.

1. Pasirinkite **Pridėti atributą**, kad žymėtumėte daugiau atributų siuntimui į Facebook „Ads Manager“. Atributai iš Facebook „Ads Manager“ žymimi šiais naudotojams draugiškais pavadinimais: **FN** = **vardas**, **LN** = **pavardė**, **FI** = **vardo inicialas**, **PHONE** = **telefonas**, **GEN** = **lytis**, **DOB** = **gimimo data**, **ST** = **vastija**, **CT** = **miestas**, **ZIP** = **pašto kodas / indeksas**, **COUNTRY** = **šalis / regionas**

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Facebook“ reklamos tvarkytuvą, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights“, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Facebook“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
