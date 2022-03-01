---
title: Peržiūrėti ir kurti metrikas
description: Kaip kurti, redaguoti ir naikinti metrikas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 97189168e0f5586aad8be8089a1f9e27893c2115c7e805ddaab1efc00e11b860
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034279"
---
# <a name="view-and-create-metrics"></a>Peržiūrėti ir kurti metrikas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrikos padeda suprasti jūsų lankytojų elgesį. Jos padaro įvykių ypatybių suvestines ir apskaičiuoja jūsų žiniatinklio ypatybių statistinius duomenis bei efektyvumą.  

Tarkime, vykdote rinkodaros reklaminę kampaniją savo žiniatinklio svetainėje. Naudodami metrikas galite sekti unikalių lankytojų arba vartotojų, kurie apsilankė jūsų svetainėje reklaminės kampanijos metu, skaičių. Metrikų analizavimas padeda jums geriau suprasti žiniatinklio svetainės auditoriją. Metrikų derinimas su [dimensijomis](dimensions.md) [pasirinktinėje ataskaitoje](custom-reports.md) leidžia jums įvertinti ir suprasti vartotojų elgesį. Pavyzdžiui, galite suskirstyti lankytojus į naujų ir sugrįžtančių kategorijas, kad nustatytumėte grupių susidomėjimo ir tikslų skirtumus.

## <a name="view-metrics"></a>Peržiūrėti metrikas

Įtraukimo įžvalgos apima dažnai naudojamas įvykio ypatybių suvestines kaip sistemos metrikas: 

- Lankytojai
- Apsilankymai
- Puslapio peržiūros
- Spustelėjimai

Šios sistemos metrikos pagrįstos esamomis pagrindinių įvykių ypatybėmis.

1. Eikite į **Duomenys** kairiojoje naršymo srityje. 
1. Pasirinkite **Metrikų** skirtuką, kad pamatytumėte visų metrikų sąrašą darbo srityje. 
   > [!NOTE]
   > Sistemos sugeneruotos metrikos yra tik skaitomos. Negalite jų pakeisti ar panaikinti. Kurti ir redaguoti galite tik pasirinktines metrikas.

## <a name="create-a-metric"></a>Metrikos kūrimas

Aplinkų ir darbo srities administratoriai gali kurti metrikas. Prieš kurdami metriką turite nusiųsti įvykio ypatybes į darbo sritį. Galite kurti metrikas pagal įvykių ypatybes, siunčiamas pagrindiniais įvykiais, arba naudoti žiniatinklio SDK [pasirinktinėms įvykių ypatybėms siųsti](advanced-SDK-implementation.md).

1. Eiti į **Duomenys** > **Metrikos**.
1. Pasirinkite **Nauja metrika**.

   :::image type="content" source="media/new-metric.png" alt-text="Įtraukti metriką į įvykį.":::

1. Formatui pasirinkite **Sveikąjį** arba **Dvigubą** duomenų tipą. Sveikasis reiškia sveikąjį skaičių. Jei naudojate Dvigubą, galite pasirinkti nuo vieno iki trijų dešimtainių skilčių.
1. Srityje **Išteklių biblioteka** suraskite įvykio ypatybę, pagal kurią norite pagrįsti metriką.
1. Pasirinkite **pliuso ženklą (+)** prie ypatybės, kad jį būtų galima naudoti formulėje. Formulę galite kurti tik pagal vieną ypatybę. 
1. Pasirinkite vieną iš šių suvestinės funkcijų. 

   - Suma: visų reikšmių bendra aritmetinė suma 
   - Vidurkis: visų reikšmių vidutinis vidurkis
   - Skaičiavimas: bendras reikšmių skaičius
   - Atskiras skaičiavimas: bendras atskirų reikšmių skaičius

   Kai apibrėšite metriką, matysite paskutinės valandos metrikos veiklos peržiūrą.

1. Pasirinkite **Įrašyti**. 
1. Įveskite metrikos pavadinimą ir pasirinkite **Įrašyti**.

Gali trukti iki minutės, kol galėsite naudoti metriką [pasirinktinių ataskaitų kūrimui](custom-reports.md).

## <a name="edit-a-metric"></a>Metrikos redagavimas

1. Eiti į **Duomenys** > **Metrikos**.
1. Sąraše pasirinkite metriką.
1. Metrikos aprašo keitimas
1. Pasirinkite **Įrašyti**.

## <a name="change-the-name-of-a-metric"></a>Metrikos pavadinimo keitimas

1. Eiti į **Duomenys** > **Metrikos**.
1. Metrikai pasirinkite **Daugiau [...]** ir **Redaguoti pavadinimą**.
1. Pakeiskite pavadinimą. 
1. Pažymėkite **Pervardyti**.

## <a name="delete-a-metric"></a>Metrikos naikinimas

1. Eiti į **Duomenys** > **Metrikos**.
1. Metrikai pasirinkite **Daugiau [...]** ir **Naikinti**.

   :::image type="content" source="media/delete-metric.png" alt-text="Naikinti metriką iš įvykio.":::

1. Pasirinkite **Naikinti** naikinimo patvirtinimui.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
