---
title: Darbo su įtraukimo įžvalgų funkcijomis pradžia
description: Žinyno išteklių apžvalga, norint greitai pradėti darbą.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225608"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Darbo su įtraukimo „Dynamics 365 Customer Insights“ įžvalgų funkcijomis pradžia (vieša peržiūra)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Naudodami įtraukimo įžvalgų galimybes galite rinkti ir matuoti klientų elgesį svetainėje. Jis integruotas su auditorijos įžvalgų funkcija, kad būtų galima matyti gausias elgsenos realiuoju laiku analizės ataskaitas, panašias į klientų profilių ataskaitas. Šio straipsnio saitai padeda greitai sukonfigūruoti ir nustatyti aplinką.

## <a name="step-1-review-prerequisites"></a>1 veiksmas: būtinųjų sąlygų peržiūra

Visų pirma, turite turėti aktyvų „Microsoft Azure Active Directory“ vartotojo abonementą. Tada, prieš nustatydami įtraukimo įžvalgų darbo sritį, perskaitykite šiuos straipsnius.

- Peržiūrėkite ir sutikite su [„Microsoft" paslaugų teikimo](terms-of-service.md) sąlygomis.  
- Perskaitykite straipsnį [Tvarkyti slapukus ir vartotojo](user-consent-storage.md) sutikimą. Tada įvertinkite, ar turite atnaujinti savo vartotojo sutikimo pranešimą. Jei anksčiau nebuvote „neesmių“ slapukų, tikriausiai reikės atnaujinti savo svetainės strategiją.
- Peržiūrėkite [sąvokų žodyną](glossary.md), kad galėtumėte greitai įvesti pagrindines sąvokas ir sąvokas.

## <a name="step-2-explore-engagement-insights"></a>2 žingsnis: susipažinkite su įtraukimo įžvalgomis

Pirmą kartą lankydami įtraukimo įžvalgas galite konfigūruoti parametrus, peržiūrėti strategijas ir naršyti galimybes.

1. Prisijunkite prie [įtraukimo įžvalgų galimybių portalo](https://home.ci.ai.dynamics.com/app/engagement-insights) naudodami savo „Microsoft” AAD vartotojo (mokymo įstaigos arba darbo) abonementą.

1. Pažymėkite savo regioną ir žymės langelį, jei norite pasirinkti gauti elektroninių laiškų naujinimus ir pasiūlymus.

1. Peržiūrėkite įtraukimo įžvalgų (peržiūros versijos) **Naudojimo sąlygos** ir **Privatumo nuostatas**, o tada rinkitės **Naršykite demonstracinę versiją** tam, kad priimtumėte šiuos parametrus.

1. Susipažinkite su produktu naudodami duomenų pavyzdžių rinkinį.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>3 žingsnis: darbo srities kūrimas ir ataskaitų kūrimas

Darbo srityje galite peržiūrėti vartotojo veiklą tikruoju laiku ir saugoti bei valdyti ataskaitas. Įtraukite kodą į savo svetainę norėdami pradėti *rinkti* įvykius, veiklos duomenis, kuriuos vartotojai gali gauti.

1. [Kurti darbo sritį](create-workspace.md) ir įtraukti narius.

1. Įtraukite kodą į [svetainę](instrument-website.md) arba [mobiliąją programą](developer-resources.md#capture-events-from-mobile-apps) ir peržiūrėkite vartotojo veiklos susekimo į darbo sritį sąrašą.

1. Peržiūrėkite [realiojo laiko ataskaitą](view-reports.md), kurioje rodomi aktyvūs vartotojai pagal naršyklę, įrenginį, operacinę sistemą, vietą ir kalbą. Taip pat galite kurti [pasirinktines ataskaitas](custom-reports.md) ir kurti savo vizualizacijas.

1. Kurti [dimensijas](dimensions.md) norint rūšiuoti lankytojus pagal naujus ir grįžtančius vartotojus, [metrikos](metrics.md) gali padėti geriau suprasti vartotojų elgesį bei [segmentus](segments.md), kurie nustato lankytojų papildomas parinktis pagal savybes ar svetainės sąveikas.
    
## <a name="step-4-export-data-to-other-channels"></a>4 žingsnis: duomenų eksportavimas į kitus kanalus

Galite kurti *patobulintą įvykius* (virtualų rodinį) savo žiniatinklio analizės duomenims. Tada filtruokite ir eksportuokite duomenis į „Azure Data Lake Storage“. Eksportuotus duomenis galite naudoti kaip duomenų šaltinį.

1. [Kurti tobulintimus eksportavimo](refined-events.md) įvykius.

1. [Duomenų eksportavimas](export-events.md) į „Azure Data Lake Storage“.

1. [Sukurkite saitą tarp auditorijos ir įtraukimo įžvalgų](integrate-audience-insights-engagement-insights.md), kad bendrintumėte duomenis tarp dviejų galimybių.

1. [Atpažinti žiniatinklio įvykius iš anksčiau autentifikuotos vartotojų](unknown-to-known.md) su **nežinoma ar žinoma** funkcija.

1. Sužinokite, kaip [naikinti ir eksportuoti įvykių duomenis, kuriuose yra asmeninė informacija](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>5 žingsnis: piltuvėlio ataskaitų kūrimas ir valdymas

Piltuvėlio ataskaita renka informaciją apie veiksmus, kuriuos reikia atlikti klientų veiklos ciklas per žiniatinklio svetainę arba mobiliąją programą. Galite kurti ne tik iš anksto sukurtas profilio ataskaitas ir pasirinktines ataskaitas, bet ir piltuvėlio ataskaitą, padėsia nustatyti, ko klientai gali imtis prieš jiems perkant. 

1. [Sukurkite piltuvėlio ataskaitą,](funnel-reports.md) kurioje kurkite sprendimus ir nurodykite optimizavimo bei procesų patobulinimų sritis.

1. Sukurkite kelių kanalų piltuvėlio ataskaitas, kai savo mobiliąją programą pereisite naudodami įtraukimo įžvalgų [Android SDK](get-started-android.md) arba [iOS SDK](get-started-ios.md).

1. Naudokite [piltuvėlio įžvalgas](funnel-reports.md#funnel-insights) tam, kad gautumėte gilesnių įžvalgų apie klientų elgesį apie veiksmus savo piltuvėlio ataskaitoje.
 
## <a name="step-6-stay-connected"></a>6 žingsnis: palaikykite ryšį

Mes vertiname jūsų aktyvų dalyvavimą ir atsižvelgiama į visus svarbius atsiliepimus kurdami būsimus naujinimus. Bendrinkite savo atsiliepimus ir praneškite apie problemas vienu iš šių kanalų:
- [Bendruomenė](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Pateikite atsiliepimą](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Palaikymo užklausa](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
