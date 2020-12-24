---
title: Naudokite duomenų šaltinius duomenų suvartojimui
description: Sužinokite, kaip importuoti duomenis iš įvairių šaltinių.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643963"
---
# <a name="overview-about-data-sources"></a>Duomenų šaltinių apžvalga

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Publikos įžvalgų galimybės „Dynamics 365 Customer Insights“ sujungia su duomenimis iš platesnio šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.

## <a name="add-a-data-source"></a>Įtraukti duomenų šaltinį

Informacijos apie tai, kaip įtraukti duomenų šaltinį, atsižvelgiant į pasirinktą parinktį, žr. išsamiuose straipsniuose.

Duomenų šaltinį galite įtraukti trimis pagrindiniais būdais.

- [Per dešimtis „Power Query“ jungčių](connect-power-query.md)
- [Iš „Common Data Model“ aplanko](connect-common-data-model.md)
- [Iš savo „Common Data Service“ telkinio](connect-common-data-service-lake.md)

> [!NOTE]
> Kol kas duomenų iš vietinių duomenų šaltinių įtraukti negalite.

## <a name="review-ingested-data"></a>Įtrauktų duomenų peržiūra

Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką. Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.

> [!div class="mx-imgBorder"]
> ![Įtrauktas duomenų šaltinis](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")

|Būsena  |Aprašo  |
|---------|---------|
|Sėkminga   |Duomenų šaltinis buvo sėkmingai suvartotas, jei laikas yra paminėtas **Paleistas iš naujo** stulpelyje.
|Nepradėta   |Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.         |
|Atnaujinama    |Vyksta duomenų apdorojimas. Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**. Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.       |
|Atlikta nesėkmingai     |Apdorojant duomenis įvyko klaidų.         |

Pasirinkite **Naujinimo būsena** tam, kad peržiūrėtumėte daugiau išsamios informacijos apie atnaujinimo būseną, įskaitant išsamią informaciją apie klaidas ir proceso pasroviui naujinimus.

Duomenų įkėlimas gali šiek tiek užtrukti. Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**. Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).

## <a name="refresh-a-data-source"></a>Paleisti iš naujo duomenų šaltinį

Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį. 

Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.

Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**

2. Pasirinkite vertikalią elipsę šalia duomenų šaltinio, kurį norite paleisti iš naujo ir pasirinkite **Paleisti iš naujo** iš iškrentančio meniu.

3. Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo. Duomenų šaltinio paleidimas iš naujo atnaujins tiek objekto schemą, tiek ir duomenis iš visų objektų nurodytų duomenų šaltinyje.

4. Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.

## <a name="delete-a-data-source"></a>Naikinti duomenų šaltinį

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elipsę, esančią šalia duomenų šaltinio, kurį norite pašalinti, ir išplečiamajame meniu pasirinkite **Naikinti**.

3. Patvirtinkite šį naikinimą.