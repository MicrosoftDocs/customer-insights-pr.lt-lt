---
title: Segmentų eksportavimas į "Braze" (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į "Braze".
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082684"
---
# <a name="export-segments-to-braze-preview"></a>Segmentų eksportavimas į "Braze" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "Braze" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Braze" paskyra](https://www.braze.com/) ir atitinkami administratoriaus kredencialai.
- Esami [segmentai Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Sukonfigūruoti segmentai](segments.md) "Customer Insights".
- Eksportuotuose segmentuose esančiuose vieninguose klientų profiliuose yra laukas, nurodantis el. pašto adresą ir "Braze" kliento ID.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportavimas į "Braze" apsiriboja segmentais.
- Iki 1 milijono klientų profilių eksportavimas į "Braze" gali užtrukti iki 40 minučių.
- Klientų profilių, kuriuos galite eksportuoti į "Braze", skaičius priklauso nuo jūsų sutarties su "Braze" ir yra ribotas.

## <a name="set-up-connection-to-braze"></a>Ryšio su "Braze" nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Braze**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite " [Braze" API raktą](https://www.braze.com/docs/api/basics/), kad galėtumėte toliau prisijungti.

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad pradėtumėte ryšį su "Braze".

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. **Lauke Ryšys eksportui** pasirinkite ryšį iš braze skyriaus. Jei nematote šio skyriaus, tokio tipo ryšių jums nėra.  

1. Įtraukite **rodomą eksportavimo pavadinimą**.

1. Įtraukite "Braze" segmento API identifikatorių, į kurį norite eksportuoti lauke **"Braze" segmento API identifikatorius**. Identifikatorių galite rasti segmento detalėse "Braze" platformoje.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. **Lauke Kliento ID** pasirinkite lauką, kuris nurodo kliento Braze ID. Reikia eksportuoti segmentus į Braze. Pasirinktinai galite pasirinkti daugiau laukų.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate Dynamics 365 Customer Insights perduoti duomenis į "Braze", leidžiate perduoti duomenis už atitikties ribos Dynamics 365 Customer Insights ribų, įskaitant potencialiai neskelbtinus duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, bet jūs esate atsakingi už tai, kad "Braze" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
