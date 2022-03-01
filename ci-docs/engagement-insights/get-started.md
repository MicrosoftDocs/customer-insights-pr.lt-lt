---
title: Darbo su įtraukimo įžvalgų funkcijomis pradžia
description: Žinyno išteklių apžvalga, norint greitai pradėti darbą.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405368"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Darbo su įtraukimo „Dynamics 365 Customer Insights“ įžvalgų funkcijomis pradžia (vieša peržiūra)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Naudodami įtraukimo įžvalgų galimybes galite rinkti ir matuoti klientų elgesį svetainėje. Jis integruotas su auditorijos įžvalgų funkcija, kad būtų galima matyti gausias elgsenos realiuoju laiku analizės ataskaitas, panašias į klientų profilių ataskaitas. Šio straipsnio saitai padeda greitai sukonfigūruoti ir nustatyti aplinką.

## <a name="step-1-review-prerequisites"></a>1 veiksmas: būtinųjų sąlygų peržiūra

Pirma turite turėti aktyvų „Microsoft Azure Active Directory“ vartotojo abonementą. Tada, prieš nustatydami įtraukimo įžvalgų darbo sritį, perskaitykite šiuos straipsnius.

- Peržiūrėkite ir sutikite [su „Microsoft" paslaugų teikimo](terms-of-service.md) sąlygomis.  
- Perskaitykite straipsnį [Tvarkyti slapukus ir vartotojo](user-consent-storage.md) sutikimą. Peržiūrėsite šį straipsnį ir įvertinkite, ar turite atnaujinti savo vartotojo sutikimą. Jei anksčiau nebuvote „neesmių“ slapukų, tikriausiai reikės atnaujinti savo svetainės strategiją.
- Peržiūrėkite [sąvokų žodyną](glossary.md), kad galėtumėte greitai įvesti pagrindines sąvokas ir sąvokas.

## <a name="step-2-explore-engagement-insights"></a>2 žingsnis: susipažinkite su įtraukimo įžvalgomis

Pirmą kartą lankydami įtraukimo įžvalgas galite konfigūruoti parametrus, peržiūrėti strategijas ir naršyti produktą.

1. Prisijunkite prie [įtraukimo įžvalgų galimybių portalą](https://pi.dynamics.com) naudodami savo „Microsoft Azure Active Directory“ vartotojo paskyrą. (Tai gali būti jūsų mokymo įstaigos arba darbo paskyra.)

1. Pažymėkite savo regioną ir naudodami žymės langelį nurodykite, ar norite pasirinkti gauti naujinimus ir pasiūlymus el. paštu.

1. Peržiūrėkite **įtraukimo įžvalgų (peržiūros) naudojimo sąlygas** ir **privatumo patvirtinimą,** tada pasirinkite **Susipažinkite su demonstracinę** versiją ir priimkite jas.

1. Susipažinkite su produktu naudodami duomenų pavyzdžių rinkinį.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3 žingsnis: nustatykite darbo sritį ir įtraukite kodą į svetainę

Darbo srityje galite peržiūrėti vartotojo veiklą tikruuoju laiku ir saugoti bei valdyti ataskaitas. Įtraukite kodą į savo svetainę norėdami pradėti *rinkti* įvykius, veiklos duomenis, kuriuos vartotojai gali gauti.

1. [Kurti darbo sritį](create-workspace.md) ir įtraukti narius.

1. [Įtraukite kodą į svetainę](instrument-website.md) arba [mobiliąją programą](developer-resources.md#capture-events-from-mobile-apps)ir peržiūrėkite vartotojo veiklos susekimo į darbo sritį sąrašą.

1. Peržiūrėkite [realiojo laiko ataskaitą,](view-reports.md) kurioje rodomi aktyvūs vartotojai naudodami naršyklę, įrenginį, operacinę sistemą, vietą ir kalbą. Taip pat galite kurti [pasirinktines ataskaitas](custom-reports.md) ir kurti savo vizualizacijas.
    
## <a name="step-4-export-data-to-other-channels"></a>4 žingsnis: duomenų eksportavimas į kitus kanalus

Galite kurti *patobulintą įvykius* (virtualų rodinį) savo žiniatinklio analizės duomenims. Tada filtruokite ir eksportuokite duomenis į „Azure Data Lake Storage“. Eksportuotus duomenis galite naudoti kaip duomenų šaltinį. Daugiau informacijos, žr. [Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas](integrate-audience-insights-engagement-insights.md).

1. [Kurti tobulintimus eksportavimo](refined-events.md) įvykius.

1. [Eksportuokite duomenis į](export-events.md) „Data Lake Storage“.

1. Sužinokite, kaip [naikinti ir eksportuoti įvykių duomenis, kuriuose yra asmeninė informacija](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5 žingsnis: palaikykite ryšį

Aktyviame jūsų dalyvavimą ir ketiname įvertinti visus aktualius atsiliepimus kuriant būsimus pranešimus. Bendrinkite savo atsiliepimus ir praneškite apie problemas vienu iš šių kanalų:
- [Bendruomenė](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Pateikite atsiliepimą](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Palaikymo užklausa](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
