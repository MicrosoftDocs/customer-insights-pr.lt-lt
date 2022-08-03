---
title: „Power BI“ jungtis (peržiūra)
description: Sužinokite, kaip naudoti „Dynamics 365 Customer Insights connector“ programoje „Power BI“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196680"
---
# <a name="power-bi-connector-preview"></a>„Power BI“ jungtis (peržiūra)

Kurkite duomenų vizualizacijas naudodami darbalaukį Microsoft Power BI. Generuokite papildomas įžvalgas ir kurkite ataskaitas naudodami sujungtus klientų duomenis.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Vieningi klientų profiliai.
- Naujausia [„Microsoft Power BI Desktop”](https://powerbi.microsoft.com/desktop/) versija yra įdiegta jūsų kompiuteryje. [Sužinokite daugiau apie „Power BI Desktop”](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>„Power BI“ jungties konfigūravimas

1. „Power BI Desktop“ pasirinkite **Failas** > **Gauti duomenis**.

1. Pasirinkite **Rodyti daugiau** ir ieškokite **„Dynamics 365 Customer Insights“**

1. Pasirinkite **Prisijungti**.

1. **Prisijunkite** naudodami tą patį organizacijos klientą, kurį naudojate „Customer Insights“, ir pasirinkite **Prisijungti**.
   > [!NOTE]
   > Klientas, kurį nurodėte atlikdami šį veiksmą, naudojamas duomenims iš „Customer Insights“ gauti ir jis neturi sutapti su klientu, kurį pasirinkę prisijungėte prie „Power BI“. Norėdami paleisti iš naujo paskyrą naudojamą duomenų naudojimui, atverkite „Power BI“ ir eikite į **Failai** > **Parinktys** > **Nustatymai** > **Duomenų šaltinio nustatymai**. Duomenų šaltinių sąraše pasirinkite **Dynamics 365 Customer Insights prisijungimas** ir pasirinkite **Aiškios teisės**.  

1. Dialogo lange **Naršyklė** peržiūrėkite visų aplinkų, prie kurių turite prieigą, sąrašą. Išplėskite aplinką ir atverkite bet kurį katalogą (objektų, priemonių, segmentų, praturtinimų). Pavyzdžiui, atidarykite aplanką **Objektai**, kad pamatytumėte visus objektus, kuriuos galite importuoti.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI jungčių naršyklė.":::

1. Pažymėkite žymės langelius šalia objektų, kuriuos reikia įtraukti, ir **įkelkite**. Galite pažymėti kelis objektus iš kelių aplinkų.

   Įkėlimo dialogo langas rodomas, kol objektai įkeliami. Kai visi jūsų pasirinkti objektai bus įkelti, naudokite galimybes Power BI vizualizuoti duomenis.

## <a name="large-data-sets"></a>Dideli duomenų rinkiniai

„Customer Insights“ jungtis, skirta „Power BI“, sukurta veikti su duomenų rinkiniais, kuriuose yra iki 1 milijono klientų profilių. Didesnių duomenų rinkinių importavimas gali veikti, tačiau užtrunka ilgai ir dėl apribojimų Power BI gali praeiti tam skirtas laikas. Norėdami gauti daugiau informacijos, žr. [„Power BI“: rekomendacijos dėl didelių duomenų rinkinių](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Darbas su antriniu duomenų rinkiniu

Apgalvokite darbą su jūsų duomenų papildomu rinkiniu. Pavyzdžiui, kurkite [segmentus](segments.md), o ne eksportuokite visus kliento įrašus į Power BI.

## <a name="troubleshooting"></a>Trikčių šalinimas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>„Customer Insights” aplinka, kuri nerodoma „Power BI”

Aplinkos, kuriose yra daugiau nei vienas [ryšys](relationships.md), apibrėžtas tarp dviejų identiškų objektų programoje "Customer Insights", nebus pasiekiamos jungtyje Power BI.

Identifikuokite ir pašalinkite pasikartojančius ryšius.

1. Eikite į **Duomenų** > **ryšiai** aplinkoje, kurios jums trūksta Power BI.
1. Identifikuoti dubliuotus ryšius:
   - Patikrinkite, ar tarp tų pačių dviejų objektų yra daugiau nei vienas ryšys.
   - Patikrinkite, ar yra ryšys, sukurtas tarp dviejų objektų, kurie abu įtraukti į suvienodinimo procesą. Tarp visų į suvienodinimo procesą įtrauktų objektų nustatomas numanomas ryšys.
1. Pašalinti visus nustatytus dublikatų ryšius.

Pašalę dubliuotų ryšių bandykite dar kartą Power BI programoje sukonfigūruoti jungtį.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Klaidos datos laukuose, kai įkeliami objektai „Power BI Desktop”

Įkeldami objektus, kuriuose yra laukų su datos formatu, pvz., MM / DD / MMMM, galite susidurti su klaidomis dėl nesuderintų lokalių formatų. Šis neatitikimas įvyksta, kai failas Power BI Desktop nustatomas į kitą lokalę nei anglų (JAV), nes datos laukai "Customer Insights" įrašomi JAV formatu.

„Power BI Desktop” faile yra vienas lokalės parametras, taikomas duomenims gauti. Norėdami ištaisyti datos klaidas, [nustatykite . BPI failas](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) į anglų kalbą (Jungtinės Amerikos Valstijos).

[!INCLUDE [footer-include](includes/footer-banner.md)]
