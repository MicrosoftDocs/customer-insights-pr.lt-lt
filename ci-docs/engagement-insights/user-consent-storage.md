---
title: Tvarkykite slapukus ir vartotojo sutikimą saugoti vartotojo duomenis „Dynamics 365 Customer Insights“
description: Suprasti, kaip slapukai ir vartotojo sutikimas naudojami žiniatinklio svetainės lankytojams identifikuoti.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558881"
---
# <a name="manage-cookies-and-user-consent"></a>Valdyti slapukus ir vartotojo leidimą

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

„Dynamics 365 Customer Insights“ įtraukimo įžvalgų funkcija naudoja slapukus ir ( `localStorage`) raktus svetainių lankytojams identifikuoti.

Slapukai yra maži failai, kuriuose saugoma informacijos apie vartotojo sąveiką su svetaine bitų. Jie saugomi žiniatinklio naršyklėse. Kai vartotojai lankosi svetainėje, kurioje jūsų vartotojai išsaugo slapukus, naršyklė šią informaciją siunčia į serverį, o tai vartotojui pateikia unikalią informaciją. Tai yra technologija, leidžianti, pvz., internetinio apsipirkimo vežimėlyje laikyti pasirinktas prekes net jei vartotojas nebenaršo svetainėje.

## <a name="user-consent"></a>Vartotojo sutikimas

[Bendrasis duomenų apsaugos reglamentas (BDAR) ](/dynamics365/get-started/gdpr/) yra Europos Sąjungos (ES) reglamentas, kuris nustato, kaip įstaigos privalo tvarkyti jų vartotojų privatumą ir saugą. Slapukai dažnai saugo arba renka „asmeninius duomenis", pvz., interneto identifikatorių, kuris yra saugomas BDAR. Jei jūsų įmonė talpina ir (ar) parduoda ES duomenų subjektas duomenis, BDAR jums taikomas. [Sužinokite daugiau apie tai, kaip „Microsoft" gali padėti jums vykdyti BDAR reikalavimus](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Norėdami leisti įtraukimo įžvalgų SDK saugoti slapukus arba kitą slaptą informaciją, turite nurodyti, ar vartotojai sutinka. Tai įvyksta inicijuojant SDK nustatant `userConsent` konfigūracijos lauką.

Jei nurodysite, kad vartotojo sutikimas nėra, SDK neišsiųs jokių duomenų ir nesiunčia įvykių, kuriuos galima naudoti vartotojo elgsenai sekti. Visi anksčiau išsaugoti duomenys bus panaikinti iš naršyklės.

Jei nenurodyta vartotojo sutikimo reikšmė, SDK manys, kad vartotojas sutinka. Tai reiškia, kad jei (kaip mūsų klientas) BDAR nenunurodysite vartotojo leidimo reikšmės, duomenys bus renkami. Tačiau, jei nurodysite, kad vartotojo sutikimas turi būti „teisinga", duomenys nebus renkami, jei vartotojas atsisakys arba negaus aiškaus sutikimo.

Toliau pateikiamas kodo fragmentas SDK inicijuojant vartotojui sutikus:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Lankytojų duomenų saugykla įtraukimo įžvalgų galimybėse

### <a name="cookies"></a>Slapukai

- _msei
    - Saugo anoniminį vartotojo ID. Šis slapukas nustatomas kliento domene ir baigia galioti po 365 dienų.

### <a name="local-storage"></a>Vietinė saugykla

Įsitraukimo įžvalgų funkcija taip pat naudoja ( `localStorage`) raktus ne slaptiems duomenims sekti. Šie duomenys visiškai saugomi pačioje naršyklėje ir nėra srauto, siunčiamo į jūsų serverius arba iš jų.

- *EISession.Id*
    - Saugo informaciją apie vykstantį vartotojo seansą, pvz., seanso ID, jį paleidus ir pasibaigus jo galiojimui.
- *EISession.Ankstesnis*
    - Saugo anksčiau atidaryto puslapio URL dabartiniame seanse.

Vietos saugykloje esantys klavišai automatiškai nebaigioja ir per kitą SDK seansą jie bus nustatyti iš naujo.

## <a name="deleting-cookies"></a>Slapukų naikinimas

Jūsų klientai, naudodami savo naršyklių parametrus, gali bet kada rankiniu būdu panaikinti slapukus ir vietinius saugojimo klavišus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
