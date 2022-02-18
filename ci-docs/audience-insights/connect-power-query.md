---
title: Duomenų prarijimas per jungtį Power Query (yra vaizdo įrašas)
description: Duomenų šaltinių jungtys, pagrįstos Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 727cb9a4d754b6dbd74d6ecab1b183d41f713d8f
ms.sourcegitcommit: aadee829eff111c95eb30c0a97a68dcc87994acf
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092082"
---
# <a name="connect-to-a-power-query-data-source"></a>Prisijungimas prie Power Query duomenų šaltinis

Power Query siūlo platų jungčių rinkinį, kad būtų galima nuryti duomenis. Daugelį šių jungčių palaiko „Dynamics 365 Customer Insights“. 

Duomenų šaltinių, pagrįstų Power Query jungtimis, pridėjimas paprastai atitinka šiame skyriuje nurodytus veiksmus. Tačiau, atsižvelgiant į naudojamą jungtį, reikalinga kita informacija. Norėdami sužinoti daugiau, peržiūrėkite dokumentaciją apie atskiras jungtis jungties nuorodoje [Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Sukurkite naują duomenų šaltinį

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **„Microsoft Power Query“**.

1. Nurodykite duomenų šaltinio **Pavadinimas** ir pasirinkite **Toliau**, kad sukurtumėte duomenų šaltinį.

1. Pasirinkite vieną iš [galimų jungčių](#available-power-query-data-sources). Šiame pavyzdyje pasirenkame **teksto / CSV** jungtį.

1. Įveskite reikiamą pasirinktos jungties informaciją dalyje **Ryšio parametrai** ir pasirinkite **Toliau**, kad peržiūrėtumėte duomenis.

1. Pasirinkite **Transformuoti duomenis**. Atlikę šį veiksmą, įtrauksite objektų į savo duomenų šaltinį. Objektai yra duomenų rinkiniai. Jei turite duomenų bazę, kurioje yra keletas duomenų rinkinių, kiekvienas duomenų rinkinys yra savo paties objektas.

1. Dialogo **Power Query langas – Redaguoti užklausas** leidžia peržiūrėti ir patikslinti duomenis. Objektai, kuriuos sistema nustatė jūsų pasirinktame duomenų šaltinyje, rodomi kairiosios srities dalyje.

   > [!div class="mx-imgBorder"]
   > ![Užklausų dialogo lango redagavimas.](media/data-manager-configure-edit-queries.png "Užklausų redagavimo dialogo langas")

1. Taip pat galite pertvarkyti savo duomenis. Pažymėkite objektą, kurį norite redaguoti arba pertvarkyti. Norėdami taikyti transformacijas, Power Query naudokite lango parinktis. Vis transformavimai išvardijami dalyje **Pritaikyti veiksmai**. Power Query suteikia daug iš anksto sukonstikuojamų transformacijos parinkčių. Daugiau informacijos rasite [Power Query Transformacijos](/power-query/power-query-what-is-power-query#transformations).

   Rekomenduojame atlikti šias transformacijas:

   - Jei duomenis įtraukiate iš CSV failo, pirmojoje eilutėje dažnai pateikiamos antraštės. Eikite į **Transformuoti** ir pasirinkite **Naudoti pirmąją eilutę kaip antraštes**.
   - Užtikrinkite, kad tinkamai nustatytas duomenų tipas. Pavyzdžiui, datos laukams pasirinkite datos tipą.

1. Norėdami įtraukti papildomų objektų į duomenų šaltinis dialogo lange Užklausų redagavimas, eikite **į** Pagrindinis **ir pasirinkite** Gauti duomenis **.**

1. Norėdami įrašyti transformacijas, **lango apačioje pasirinkite** Įrašyti Power Query. Įrašę, duomenų šaltinį rasite pasirinkę **Duomenys** > **Duomenų šaltiniai**.

1. Puslapyje **Duomenų šaltiniai** pastebėsite, kad naujo duomenų šaltinio būsena yra **Atnaujinama**.

## <a name="available-power-query-data-sources"></a>Galimi Power Query duomenų šaltiniai

Peržiūrėkite [Power Query jungčių, kurias galite naudoti duomenims importuoti į "Customer Insights", jungties nuorodą](/power-query/connectors/). 

Jungtys su varnele stulpelyje **Customer Insights (Dataflows)** yra prieinamos naujiems duomenų šaltiniams kurti pagal Power Query. Peržiūrėkite konkrečios jungties dokumentaciją ir sužinokite daugiau apie būtinąsias sąlygas, apribojimus ir kitą išsamią informaciją.

## <a name="edit-power-query-data-sources"></a>Redaguoti Power Query duomenų šaltinius

> [!NOTE]
> Gali būti neįmanoma keisti duomenų šaltinius, kurie dabar yra naudojami viename iš programos procesų (pvz., *segmentavimo*, *sutapdinimo* arba *suliejimo*). 
>
> **Puslapyje Parametrai** galite stebėti kiekvieno aktyvaus proceso eigą. Kai procesas bus užbaigtas, galite grįžti į puslapį **Duomenų šaltiniai** ir atlikti pakeitimus.

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elešką šalia norimos duomenų šaltinis dalies ir **išplečiamajame** meniu pasirinkite Redaguoti.

   > [!div class="mx-imgBorder"]
   > ![Parinkties redagavimas.](media/edit-option-data-sources.png "Redagavimo parinktis")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Taikykite keitimus ir transformacijas **Power Query dialogo lange – Redaguoti užklausas**, kaip aprašyta skyriuje [Kurti naują duomenų šaltinis](#create-a-new-data-source).

4. Baigę redagavimus, norėdami įrašyti keitimus, pasirinkite **Įrašyti** Power Query.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
