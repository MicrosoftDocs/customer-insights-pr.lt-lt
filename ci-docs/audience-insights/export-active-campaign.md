---
title: „Customer Insights“ duomenų eksportavimas į „ActiveCampaign“
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „ActiveCampaign“.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4fbdd5a51a3df35d31ad072eef64d20ee967d7ee
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618163"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentų eksportavimas į „ActiveCampaign“ (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į „ActiveCampaign" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [„ActiveCampaign“ abonementą](https://www.activecampaign.com/) ir atitinkamus administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Vieningieji klientų profiliai, esantys eksportuotuose segmentuose, ir turintys lauką su el. pašto adresu.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportuojant į „ActiveCampaign" galima eksportuoti iki 1 milijonai klientų profilių, o užbaigti gali trukti iki 90 minučių.
- Eksportavimas į „ActiveCampaign“ ribojamas segmentais.
- Klientų profilių, kuriuos galite eksportuoti į „ActiveCampaign", skaičius priklauso nuo sutarties su „ActiveCampaign".

## <a name="set-up-connection-to-activecampaign"></a>Nustatyti ryšį su „ActiveCampaign“

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **ActiveCampaign,** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo [„ActiveCampaign API" raktą ir REST galinių punktų pagrindinio kompiuterio pavadinimą](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). REST galinio punkto pagrindinio kompiuterio vardas yra tik pagrindinio kompiuterio vardas be https://. 

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** siekiant pradėti jungį su „ActiveCampaign“.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Galite sukonfigūruoti eksportavimą, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „ActiveCampaign“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo [**ActiveCampaign sąrašo ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. Būtina eksportuoti segmentus į „ActiveCampaign“. Arba galite eksportuoti vardas, pavardė ir telefonas sukurtumėte labiau personalizuotus el. laiškus. Pasirinkite Įtraukti atributą siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į „Dynamics 365 Customer Insights“ leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis „ActiveCampaign“, „Dynamics 365 Customer Insights“, įskaitant galimai jautrius, tokius kaip asmens. „Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „ActiveCampaign“ privatumo arba saugos apsauga. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.
