---
title: „Power BI“ jungtis
description: Sužinokite, kaip naudoti „Dynamics 365 Customer Insights connector“ programoje „Power BI“.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: dccc069a355725bae09c1fece9292b9aee374e6d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225526"
---
# <a name="connector-for-power-bi-preview"></a>„Power BI“ jungtis (peržiūra)

Sukurkite vizualizacija jūsų duomenims su „Power BI Desktop“. Generuokite papildomas įžvalgas ir kurkite ataskaitas naudodami sujungtus klientų duomenis.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Turite suvienodintus kliento profilius.
- Naujausia [„Microsoft Power BI Desktop”](https://powerbi.microsoft.com/desktop/) versija yra įdiegta jūsų kompiuteryje. [Sužinokite daugiau apie „Power BI Desktop”](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>„Power BI“ jungties konfigūravimas

1. „Power BI Desktop“ pasirinkite **Failas** > **Gauti duomenis**.

1. Pasirinkite **Rodyti daugiau** ir ieškokite **„Dynamics 365 Customer Insights“**

1. Pasirinkite **Prisijungti**.

1. **Prisijunkite** naudodami tą patį organizacijos klientą, kurį naudojate „Customer Insights“, ir pasirinkite **Prisijungti**.
   > [!NOTE]
   > Klientas, kurį nurodėte atlikdami šį veiksmą, naudojamas duomenims iš „Customer Insights“ gauti ir jis neturi sutapti su klientu, kurį pasirinkę prisijungėte prie „Power BI“. Norėdami paleisti iš naujo paskyrą naudojamą duomenų naudojimui, atverkite „Power BI“ ir eikite į **Failai** > **Parinktys** > **Nustatymai** > **Duomenų šaltinio nustatymai**. Duomenų šaltinių sąraše pasirinkite **Dynamics 365 Customer Insights prisijungimas** ir pasirinkite **Aiškios teisės**.  

1. Dialogo lange **„Navigator“**. matysite aplinkų sąrašą, prie kurio turite prieigą. Išplėskite aplinką ir atverkite bet kurį katalogą (objektų, priemonių, segmentų, praturtinimų). Pavyzdžiui, atidarykite aplanką **Objektai**, kad pamatytumėte visus objektus, kuriuos galite importuoti.

   ![Power BI jungčių naršyklė.](media/power-bi-navigator.png "„Power BI“ jungčių naršyklė")

1. Pažymėkite žymės langelius šalia objektų, kuriuos reikia įtraukti, ir **įkelkite**. Galite pažymėti kelis objektus iš kelių aplinkų.

1. Kol objektai įkeliami, matysite įkėlimo dialogo langą. Jums pasirinkus įkeltus objektus, galite naudoti „Power BI“ pajėgumus tam, kad rodytumėte duomenis.

## <a name="large-data-sets"></a>Dideli duomenų rinkiniai

„Customer Insights“ jungtis, skirta „Power BI“, sukurta veikti su duomenų rinkiniais, kuriuose yra iki 1 milijono klientų profilių. Didesnių duomenų rinkinių importavimas gali pavykti, tačiau reikia daug laiko. Be to, dėl „Power BI“ apribojimų gali baigti procesui skirtas laikas. Norėdami gauti daugiau informacijos, žr. [„Power BI“: rekomendacijos dėl didelių duomenų rinkinių](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Darbas su antriniu duomenų rinkiniu

Apgalvokite darbą su jūsų duomenų papildomu rinkiniu. Pavyzdžiui, galite sukurti [segmentus](segments.md) vietoje visų kliento įrašų eksportavimo į „Power BI“.

## <a name="troubleshooting"></a>Trikčių šalinimas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>„Customer Insights” aplinka, kuri nerodoma „Power BI”

Aplinkos, kurios turi daugiau nei vieną ryšį, nustatytą tarp dviejų identiškų objektų auditorijos [įžvalgose](relationships.md), pasiekti Power BI nepavyks.

Galite identifikuoti ir pašalinti dubliuotas ryšius.

1. Auditorijos įžvalgose eikite **Duomenys** > **Ryšiai** aplinkoje, kurios trūksta Power BI.
2. Identifikuoti dubliuotus ryšius:
   - Patikrinkite, ar tarp tų pačių dviejų objektų yra daugiau nei vienas ryšys.
   - Patikrinkite, ar yra ryšys, sukurtas tarp dviejų objektų, kurie abu įtraukti į suvienodinimo procesą. Tarp visų į suvienodinimo procesą įtrauktų objektų nustatomas numanomas ryšys.
3. Pašalinti visus nustatytus dublikatų ryšius.

Pašalę dubliuotų ryšių bandykite dar kartą Power BI programoje sukonfigūruoti jungtį. Aplinka turėtų būti prieinama dabar.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Klaidos datos laukuose, kai įkeliami objektai „Power BI Desktop”

Įkeliant objektus, kuriuose yra laukų su datos formatu kaip MM/DD/YYYY, galite susidurti su klaidomis dėl nesutampančių lokalės formatų. Šis neatitikimas atsitinka, kai jūsų „Power BI Desktop” failas nustatomas į kitą lokalę nei anglų (Jungtinių Valstijų), nes datos laukai auditorijos įžvalgose įrašomi JAV formatu.

„Power BI Desktop” faile yra vienas lokalės parametras, taikomas duomenims gauti. Tam, kad šie datos laukai būtų interpretuojami teisingai, nustatykite .BPI failo lokalę į anglų kalbą (Jungtinių Valstijų). [Sužinokite, kaip pakeisti „Power BI desktop” failo lokalę](/power-bi/fundamentals/supported-languages-countries-regions.md#choose-the-locale-for-importing-data-into-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
