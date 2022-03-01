---
title: Tvarkykite slapukus ir vartotojo sutikimą saugoti vartotojo duomenis
description: Suprasti, kaip slapukai ir vartotojo sutikimas naudojami žiniatinklio svetainės lankytojams identifikuoti.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036748"
---
# <a name="manage-cookies-and-user-consent"></a>Valdyti slapukus ir vartotojo leidimą

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

„Dynamics 365 Customer Insights“ įtraukimo įžvalgų funkcija naudoja slapukus ir vietinę saugyklą ( `localStorage`) žiniatinklio svetainės lankytojams identifikuoti.

Slapukai yra maži failai, kuriuose saugoma informacijos apie vartotojo sąveiką su svetaine bitų. Jie saugomi žiniatinklio naršyklėse. Kai vartotojai lankosi svetainėje, kurioje jūsų vartotojai išsaugo slapukus, naršyklė šią informaciją siunčia į serverį, o tai vartotojui pateikia unikalią informaciją. Tai yra technologija, leidžianti, pvz., internetinio apsipirkimo vežimėlyje laikyti pasirinktas prekes net jei vartotojas nebenaršo svetainėje.

## <a name="user-consent"></a>Vartotojo sutikimas

[Bendrasis duomenų apsaugos reglamentas (BDAR) ](/dynamics365/get-started/gdpr/) yra Europos Sąjungos (ES) reglamentas, kuris nustato, kaip įstaigos privalo tvarkyti jų vartotojų privatumą ir saugą. Slapukai dažnai saugo arba renka „asmeninius duomenis", pvz., interneto identifikatorių, kuris yra saugomas BDAR. Jei jūsų įmonė talpina ir (ar) parduoda ES duomenų subjektas duomenis, BDAR jums taikomas. [Sužinokite daugiau apie tai, kaip „Microsoft" gali padėti jums vykdyti BDAR reikalavimus](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Norėdami leisti įtraukimo įžvalgų SDK saugoti slapukus arba kitą slaptą informaciją, turite nurodyti, ar vartotojai sutinka. Taip nutinka inicijuojant SDK.

Jei nurodysite, kad vartotojo sutikimas nėra, SDK neišsiųs jokių duomenų ir nesiunčia įvykių, kuriuos galima naudoti vartotojo elgsenai sekti. Visi anksčiau išsaugoti duomenys bus panaikinti iš naršyklės.

Jei nenurodyta vartotojo sutikimo reikšmė, SDK manys, kad vartotojas sutinka. Tai reiškia, kad jei (kaip mūsų klientas) BDAR nenunurodysite vartotojo leidimo reikšmės, duomenys bus renkami. Tačiau, jei nurodysite, kad vartotojo sutikimas turi būti „teisinga", duomenys nebus renkami, jei vartotojas atsisakys arba negaus aiškaus sutikimo.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lankytojų duomenų saugykla įtraukimo įžvalgų galimybėse

### <a name="cookies"></a>Slapukai

- _msei
    - Saugo anoniminį vartotojo ID. Šis slapukas nustatomas kliento domene ir baigia galioti po 365 dienų.

### <a name="local-storage"></a>Vietinė saugykla

Įsitraukimo įžvalgų funkcija taip pat naudoja vietinę saugyklą (`localStorage`) neslaptiems duomenims sekti. Šie duomenys visiškai saugomi pačioje naršyklėje ir nėra srauto, siunčiamo į jūsų serverius arba iš jų.

- *EISession.Id* 
    - Saugo informaciją apie vykstantį vartotojo seansą, pvz., seanso ID, jį paleidus ir pasibaigus jo galiojimui.
- *EISession.Ankstesnis*
    - Saugo anksčiau atidaryto puslapio URL dabartiniame seanse.
    
Klavišai vietinėje saugykloje automatiškai nebaigioja. Kitą seansą SDK juos nustatys iš naujo.

## <a name="deleting-cookies"></a>Slapukų naikinimas

Jūsų klientai, naudodami savo naršyklių parametrus, gali bet kada rankiniu būdu panaikinti slapukus ir vietinius saugojimo klavišus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]