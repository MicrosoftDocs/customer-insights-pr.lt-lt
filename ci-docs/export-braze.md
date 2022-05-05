---
title: Eksportuoti "Customer Insights" duomenis į "Braze"
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643152"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segmentų sąrašų eksportavimas į Braze (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "Braze" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite "Braze" [paskyrą](https://www.braze.com/) ir atitinkamus administratoriaus kredencialus.
-   Sukonfigūravote [segmentus](segments.md) programoje "Customer Insights".
-   Vieninguose eksportuotų segmentų klientų profiliuose yra laukas, nurodantis el. pašto adresą ir Braze kliento ID. 

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportas į Braze apsiriboja segmentais.
- Iki 1 milijono klientų profilių eksportavimas į "Braze" gali užtrukti iki 40 minučių. 
- Klientų profilių, kuriuos galite eksportuoti į "Braze", skaičius priklauso nuo jūsų sutarties su "Braze".

## <a name="set-up-connection-to-braze"></a>Nustatyti ryšį su Braze

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Braze**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite " [Braze" API raktą](https://www.braze.com/docs/api/basics/), kad galėtumėte toliau prisijungti. 

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį su Braze.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportui** pasirinkite ryšį iš skyriaus Braze. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.  

3. Sekcijos **Duomenų gretinimas** lauke El. paštas **pasirinkite** lauką, nurodantį pirkėjo el. pašto adresą, lauke "Kliento ID" pasirinkite lauką, nurodantį kliento Braze ID. Reikia eksportuoti segmentus į Braze. "Braze" segmentai bus sukurti tuo pačiu segmento pavadinimu, kaip ir Dynamics 365 Customer Insights. Galite pasirinkti papildomus pasirinktinius laukus duomenims gretinti. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis "Braze", leidžiate perduoti duomenis už atitikties ribos, įskaitant potencialiai neskelbtinus Dynamics 365 Customer Insights duomenis, pvz., asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "Braze" laikytųsi bet kokių privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
