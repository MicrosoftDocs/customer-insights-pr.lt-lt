---
title: Segmento įžvalgos esantiems segmentams
description: Gaukite įžvalgas apie esančius segmentus tam, kad matytumėte skirtumus ir panašumus.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 0803be651662480ddf1fd22952f6a69ee1603001
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554995"
---
# <a name="segment-insights-preview"></a>Segmentų įžvalgos (peržiūra)

Atraskite papildomos informacijos ir įžvalgų apie esamus segmentus. Sužinokite, kas išskiria du segmentus, ar ką jie turi bendro.

## <a name="segment-overlap"></a>Segmento persidengimas

Segmento persidengimo analizė rodo, kiek ir kokie klientai yra bendri dviems ar daugiau segmentų. Pavyzdžiui, kaip dažnų klientų segmentas persidengia su segmentu, kuriame yra klientų, kuriuos tenkina jūsų aptarnavimas arba produktas.
Taip pat galite analizuoti, kaip kinta persidengimas tam tikriems atributams.

### <a name="run-an-overlap-analysis"></a>Persidengimo analizės vykdymas

1. Eikite į **Segmentai** ir pasirinkite skirtuką **Įžvalgos (peržiūra)**.

1. Pažymėkite **Naujas** ir pasirinkite parinktį **Persidengimas**, esančią srityje **Pasirinkti įžvalgų tipą**.

1. Pasirinkite dominančius segmentus ir pasirinkite **Kitas**.

1. Pasirinktinai pasirinkite vieną ar kelis dominančius laukus ir analizuokite persidengimus pagal visas įmanomas lauko reikšmes ir pasirinkite **Pirmyn**.

1. Pateikite persidengimo analizės pavadinimą, pasirinktinį rodomą pavadinimą ir aprašą.

1. Norėdami pradėti analizę, pasirinkite **Įrašyti**. Persidengimo analizė yra paruošta, kai būsena pasikeičia iš „Atnaujinama“ į „Sėkmingai“.

### <a name="view-and-optimize-an-overlap-analysis"></a>Persidengimo analizės peržiūra ir optimizavimas

Užbaigę analizę, rasite išsamią informaciją apie šią įžvalgą skiltyje **Segmentai** > **Įžvalgos (peržiūra)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Segmentų persidengimo įžvalgų išsami informacija.":::

Pasirinkite įžvalgą, kad pamatytumėte analizės rezultatus:

- Narių skaičius, persidengiančių su analizei pažymėtais segmentais.
- Narių, įtrauktų į vieną iš segmentų, bet ne likusiais segmentais, skaičius.
- Jei pažymėjote laukus konfigūruodami persidengimo analizę, jas rasite atitinkamuose skirtukuose. Naudodami filtro išplečiamąjį sąrašą, galite pažymėti bet kokį dominantį atributo lygį, o apačioje esančioje lentelėje bus rodomi atitinkami duomenys.

## <a name="segment-differentiators"></a>Segmento diferenciatoriai

Segmentų diferenciatoriai padeda sužinoti, kas atskiria segmentą nuo likusių klientų arba kito segmento. Tereikia pažymėti segmentą, o sistema nustatys profilio atributus ir priemones, atskiriančias pasirinktą segmentą.

### <a name="run-a-differentiator-analysis"></a>Diferenciatoriaus analizės vykdymas

1. Eikite į **Segmentai** ir pasirinkite skirtuką **Įžvalgos (peržiūra)**.

1. Pažymėkite **Naujas** ir pasirinkite parinktį **Persidengimas**, esančią srityje **Pasirinkti įžvalgų tipą**.

1. Pasirinkite norimą analizuoti segmentą kaip **Pirminį segmentą** ir pasirinkite **Kitas**.

1. Pasirinkite **Visi klientai** arba **Antrinis segmentas**, kad palygintumėte pirminį segmentą ir pažymėkite **Kitas**.

1. Pasirinktinai pasirinkite vieną ar kelis dominančius laukus, kad sutelktumėte analizė ant tam tikrų atributų ir pasirinkite **Pirmyn**.

1. Pateikite persidengimo analizės pavadinimą, pasirinktinį rodomą pavadinimą ir aprašą.

1. Norėdami pradėti analizę, pasirinkite **Įrašyti**. Persidengimo analizė yra paruošta, kai būsena pasikeičia iš „Atnaujinama“ į „Sėkmingai“.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Diferenciatorių analizės peržiūra ir optimizavimas

Užbaigę analizę, rasite išsamią informaciją apie šią įžvalgą skiltyje **Segmentai** > **Įžvalgos (peržiūra)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmentų diferenciatoriaus įžvalgų išsami informacija.":::

Pasirinkite įžvalgą, kad pamatytumėte analizės rezultatus. Diferenciatoriaus analizė įtraukia du skirtukus. Skirtuke **Atributai** išvardijami profilio atributai, kurie laikomi diferenciatoriais. Skirtuke **Priemonės** išvardijami diferenciatoriai. Kiekviename skirtuke yra ši išsami informacija:

- Rangais suskirstytas diferenciatorių sąrašas, surūšiuotas pagal skirtumo balą.
- **Skirtumo balas** kiekvienam diferenciatoriui. Skirtumo balas nurodo dviejų segmentų atributo skirtumo laipsnį. Kuo didesnis skirtumo balas, tuo daugiau atributų skiriasi tarp dviejų segmentų. Pasirinkite rezultatą, kad atidarytumėte sritį **Skirtumo balas** su to atributo reikšmių paskirstymais.

## <a name="manage-segment-insights"></a>Segmentų įžvalgų valdymas

Komandų juostoje galite naudoti šias įžvalgų parinktis:

- **Atgal**, kad grįžtumėte į įžvalgų sąrašą
- **Atnaujinti**, kad vėl paleistumėte analizę
- **Panaikinti**, kad pašalintumėte šią įžvalgą


[!INCLUDE[footer-include](../includes/footer-banner.md)]