---
title: Duomenų praryjimas per Power Query jungtį (yra vaizdo įrašas)
description: Duomenų šaltinių jungtys, pagrįstos Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934988"
---
# <a name="connect-to-a-power-query-data-source"></a>Prisijungimas prie Power Query duomenų šaltinis

Power Query siūlo platų jungčių rinkinį duomenims nuryti. Daugelį šių jungčių palaiko „Dynamics 365 Customer Insights“. 

Duomenų šaltinių, pagrįstų jungtimis, pridėjimas Power Query paprastai vyksta pagal šiame skyriuje nurodytus veiksmus. Tačiau, atsižvelgiant į naudojamą jungtį, reikalinga kita informacija. Norėdami sužinoti daugiau, peržiūrėkite dokumentaciją apie atskiras jungtis [Power Query jungties jungties nuorodoje](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Sukurkite naują duomenų šaltinį

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Microsoft Power Query**, tada pasirinkite **Pirmyn**.

1. Nurodykite duomenų šaltinio **Pavadinimas** ir pasirinkite **Toliau**, kad sukurtumėte duomenų šaltinį.

1. Pasirinkite vieną iš [galimų jungčių](#available-power-query-data-sources). Šiame pavyzdyje pasirenkame **teksto / CSV** jungtį.

1. Įveskite reikiamą pasirinktos jungties informaciją dalyje **Ryšio parametrai** ir pasirinkite **Toliau**, kad peržiūrėtumėte duomenis.

1. Pasirinkite **Transformuoti duomenis**. Atlikę šį veiksmą, įtrauksite objektų į savo duomenų šaltinį. Objektai yra duomenų rinkiniai. Jei turite duomenų bazę, kurioje yra keletas duomenų rinkinių, kiekvienas duomenų rinkinys yra savo paties objektas.

1. **Power Query Dialogo langas Redaguoti užklausas leidžia peržiūrėti ir** patikslinti duomenis. Objektai, kuriuos sistema nustatė jūsų pasirinktame duomenų šaltinyje, rodomi kairiosios srities dalyje.

   > [!div class="mx-imgBorder"]
   > ![Užklausų dialogo lango redagavimas.](media/data-manager-configure-edit-queries.png "Užklausų redagavimo dialogo langas")

1. Taip pat galite pertvarkyti savo duomenis. Pažymėkite objektą, kurį norite redaguoti arba pertvarkyti. Norėdami taikyti Power Query transformacijas, naudokite lange pažymėtas parinktis. Vis transformavimai išvardijami dalyje **Pritaikyti veiksmai**. Power Query suteikia daug iš anksto sukonstruotos transformacijos galimybių. Daugiau informacijos ieškokite [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).

1. Galite įtraukti papildomų objektų į savo duomenų šaltinį, dialogo lange **Redaguoti užklausas** pasirinkdami **Gauti duomenis**.

   Rekomenduojame naudoti šias transformacijas:

   - Jei duomenis įtraukiate iš CSV failo, pirmojoje eilutėje dažnai pateikiamos antraštės. Pereikite prie **Transformavimo lentelė** ir pasirinkite **Naudoti antraštes kaip pirmąją eilutę**.
   - Užtikrinkite, kad tinkamai nustatytas duomenų tipas.

1. Norėdami **įrašyti** transformacijas, lango apačioje Power Query pasirinkite Įrašyti. Įrašę, duomenų šaltinį rasite pasirinkę **Duomenys** > **Duomenų šaltiniai**.

1. Puslapyje **Duomenų šaltiniai** pastebėsite, kad naujo duomenų šaltinio būsena yra **Atnaujinama**.

## <a name="available-power-query-data-sources"></a>Galimi Power Query duomenų šaltiniai

Peržiūrėkite [Power Query](/power-query/connectors/) jungčių, kurias galite naudoti duomenims importuoti į "Customer Insights", jungties nuorodą. 

Jungtys su varnele **stulpelyje Customer Insights (Dataflows)** galimos kurti naujus duomenų šaltinius pagal Power Query. Peržiūrėkite konkrečios jungties dokumentaciją ir sužinokite daugiau apie būtinąsias sąlygas, apribojimus ir kitą išsamią informaciją.

## <a name="edit-power-query-data-sources"></a>Redaguoti Power Query duomenų šaltinius

> [!NOTE]
> Gali būti neįmanoma keisti duomenų šaltinius, kurie dabar yra naudojami viename iš programos procesų (pvz., *segmentavimo*, *sutapdinimo* arba *suliejimo*). 
>
> Puslapyje **Parametrai** galite stebėti kiekvieno aktyvaus procesų eigą. Kai procesas bus užbaigtas, galite grįžti į puslapį **Duomenų šaltiniai** ir atlikti pakeitimus.

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elešką šalia norimos duomenų šaltinis dalies ir **išplečiamajame** meniu pasirinkite Redaguoti.

   > [!div class="mx-imgBorder"]
   > ![Parinkties redagavimas.](media/edit-option-data-sources.png "Redagavimo parinktis")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Taikykite keitimus ir transformacijas **Power Query dialogo lange – Redaguoti užklausas, kaip aprašyta**[skyriuje Kurti naują](#create-a-new-data-source) duomenų šaltinis.

4. **Baigę** redaguoti pasirinkite Power Query Įrašyti, kad įrašytumėte keitimus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
