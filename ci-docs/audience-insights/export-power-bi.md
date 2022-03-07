---
title: „Power BI“ jungtis
description: Sužinokite, kaip naudoti „Dynamics 365 Customer Insights“ jungtį programoje „Power BI“.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406382"
---
# <a name="connector-for-power-bi-preview"></a>„Power BI“ jungtis (peržiūra)

Sukurkite vizualizacija jūsų duomenims su „Power BI Desktop“. Generuokite papildomas įžvalgas ir kurkite ataskaitas naudodami sujungtus klientų duomenis.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Turite suvienodintus kliento profilius.
- Jūsų kompiuteryje įdiegta naujausia [„Microsoft Power BI Desktop“](https://powerbi.microsoft.com/desktop/) versija. [Sužinokite daugiau apie „Power BI Desktop”](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>„Power BI“ jungties konfigūravimas

1. „Power BI Desktop“ pasirinkite **Failas** > **Gauti duomenis**.

1. Pasirinkite **Rodyti daugiau** ir ieškokite **„Dynamics 365 Customer Insights“**

1. Pasirinkite rezultatą ir spustelėkite **Prisijungti**.

1. **Prisijunkite** naudodami tą patį organizacijos klientą, kurį naudojate „Customer Insights“, ir pasirinkite **Prisijungti**.
   > [!NOTE]
   > Klientas, kurį nurodėte atlikdami šį veiksmą, naudojamas duomenims iš „Customer Insights“ gauti ir jis neturi sutapti su klientu, kurį pasirinkę prisijungėte prie „Power BI“. Norėdami paleisti iš naujo paskyrą naudojamą duomenų naudojimui, atverkite „Power BI“ ir eiktie į **Failai** > **Parinktys** > **Nustatymai** > **Duomenų šaltinio nustatymai**. Duomenų šaltinių sąraše pasirinkite **Dynamics 365 Customer Insights prisijungimas** ir pasirinkite **Aiškios teisės**.  

1. Dialogo lange **„Navigator“**. matysite aplinkų sąrašą, prie kurio turite prieigą. Išplėskite aplinką ir atverkite bet kurį katalogą (objektų, priemonių, segmentų, praturtinimų). Pavyzdžiui, atidarykite aplanką **Objektai**, kad pamatytumėte visus objektus, kuriuos galite importuoti.

   ![Power BI jungčių naršyklė](media/power-bi-navigator.png "„Power BI“ jungčių naršyklė")

1. Pažymėkite žymės langelius šalia objektų, kuriuos reikia įtraukti, ir **įkelkite**. Galite pažymėti kelis objektus iš kelių aplinkų.

1. Kol objektai įkeliami, matysite įkėlimo dialogo langą. Jums pasirinkus įkeltus objektus, galite naudoti „Power BI“ pajėgumus tam, kad rodytumėte duomenis.

## <a name="large-data-sets"></a>Dideli duomenų rinkiniai

„Customer Insights“ jungtis, skirta „Power BI“, sukurta veikti su duomenų rinkiniais, kuriuose yra iki 1 milijono klientų profilių. Didesnių duomenų rinkinių importavimas gali pavykti, tačiau reikia daug laiko. Be to, dėl „Power BI“ apribojimų gali baigti procesui skirtas laikas. Norėdami gauti daugiau informacijos, žr. [„Power BI“: rekomendacijos dėl didelių duomenų rinkinių](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Darbas su antriniu duomenų rinkiniu

Apgalvokite darbą su jūsų duomenų papildomu rinkiniu. Pavyzdžiui, galite sukurti [segmentus](segments.md) vietoje visų kliento įrašų eksportavimo į „Power BI“.
