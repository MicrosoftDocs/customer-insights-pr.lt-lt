---
title: Suvartokite duomenis per „Power Query“ jungtį
description: Duomenų šaltinių jungtys pagal „Power Query“.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406401"
---
# <a name="connect-to-a-power-query-data-source"></a>Prisijungimas prie „Power Query“ duomenų šaltinio

„Power Query“ siūlo platų jungčių pasirinkimą duomenims įtraukti. Daugelį šių jungčių palaiko „Dynamics 365 Customer Insights“. Duomenų šaltiniai pagal „Power Query“ jungtis paprastai įtraukiami atliekant kitame skyriuje aprašytus veiksmus. Tačiau, atsižvelgiant į naudojamą jungtį, reikalinga kita informacija. Daugiau informacijos ieškokite dokumentacijoje apie konkrečias jungtis skyriuje [„Power Query“ jungčių aprašas](https://docs.microsoft.com/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Sukurkite naują duomenų šaltinį

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite metodą **Importuoti duomenis** ir pasirinkite **Toliau**.

1. Nurodykite duomenų šaltinio **Pavadinimas** ir pasirinkite **Toliau**, kad sukurtumėte duomenų šaltinį.

1. Pasirinkite vieną iš [galimų jungčių](#available-power-query-data-sources). Šiame pavyzdyje pasirinksime jungtį **Tekstas/CSV**.

1. Įveskite reikiamą pasirinktos jungties informaciją dalyje **Ryšio parametrai** ir pasirinkite **Toliau**, kad peržiūrėtumėte duomenis.

1. Pasirinkite **Transformuoti duomenis**. Atlikę šį veiksmą, įtrauksite objektų į savo duomenų šaltinį. Objektai yra duomenų rinkiniai. Jei turite duomenų bazę, kurioje yra keletas duomenų rinkinių, kiekvienas duomenų rinkinys yra savo paties objektas.

1. Dialogo lange **„Power Query“ – redaguoti užklausas** galima peržiūrėti ir tikslinti duomenis. Objektai, kuriuos sistema nustatė jūsų pasirinktame duomenų šaltinyje, rodomi kairiosios srities dalyje.

   > [!div class="mx-imgBorder"]
   > ![Užklausų redagavimo dialogo langas](media/data-manager-configure-edit-queries.png "Užklausų redagavimo dialogo langas")

1. Taip pat galite pertvarkyti savo duomenis. Pažymėkite objektą, kurį norite redaguoti arba pertvarkyti. Norėdami pritaikyti transformavimą, naudokite lango „Power Query“ parinktis. Vis transformavimai išvardijami dalyje **Pritaikyti veiksmai**. „Power Query“ suteikia daug iš anksto sukurtų transformavimo galimybių. Daugiau informacijos ieškokite [„Power Query“ transformavimai](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).

1. Galite įtraukti papildomų objektų į savo duomenų šaltinį, dialogo lange **Redaguoti užklausas** pasirinkdami **Gauti duomenis**.

   Primygtinai rekomenduojama atlikti šiuos pertvarkymus:

   - Jei duomenis įtraukiate iš CSV failo, pirmojoje eilutėje dažnai pateikiamos antraštės. Pereikite prie **Transformavimo lentelė** ir pasirinkite **Naudoti antraštes kaip pirmąją eilutę**.
   - Užtikrinkite, kad tinkamai nustatytas duomenų tipas.

1. Lango „Power Query“ apačioje pasirinkite **Įrašyti**, kad įrašytumėte transformavimus. Įrašę, duomenų šaltinį rasite pasirinkę **Duomenys** > **Duomenų šaltiniai**.

1. Puslapyje **Duomenų šaltiniai** pastebėsite, kad naujo duomenų šaltinio būsena yra **Atnaujinama**.

## <a name="available-power-query-data-sources"></a>Pasiekiami „Power Query“ duomenų šaltiniai

Žr. skyrių [„Power Query“ jungčių aprašas](https://docs.microsoft.com/power-query/connectors/), kuriame pateikiamas aktualus jungčių, kurias galite pasirinkti importuodami duomenis į „Customer Insights“, sąrašas. 

Jungtys su varnele stulpelyje **„Customer Insights“ (duomenų srautai)** gali būti naudojamos kuriant naujus duomenų šaltinius pagal „Power Query“. Peržiūrėkite konkrečios jungties dokumentaciją ir sužinokite daugiau apie būtinąsias sąlygas, apribojimus ir kitą išsamią informaciją.

## <a name="edit-power-query-data-sources"></a>„Power Query“ duomenų šaltinių redagavimas

> [!NOTE]
> Gali būti neįmanoma keisti duomenų šaltinius, kurie dabar yra naudojami viename iš programos procesų (pvz., *segmentavimo*, *sutapdinimo* arba *suliejimo*). 
>
> Naudodamiesi puslapiu **Parametrai** galite sekti kiekvieno iš aktyvių procesų eigą. Kai procesas bus užbaigtas, galite grįžti į puslapį **Duomenų šaltiniai** ir atlikti pakeitimus.

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elipsę, esančią šalia duomenų šaltinio, kurį norite pakeisti, ir išplečiamajame meniu pasirinkite **Redaguoti**.

   > [!div class="mx-imgBorder"]
   > ![Redagavimo parinktis](media/edit-option-data-sources.png "Redagavimo parinktis")

3. Pritaikykite savo pakeitimus ir transformavimus dialogo lange **„Power Query“ – redaguoti užklausas**, remdamiesi skyriumi [Naujo duomenų šaltinio kūrimas](#create-a-new-data-source).

4. Baigę redaguoti, pasirinkite **Įrašyti** dalyje „Power Query“, kad įrašytumėte pakeitimus.