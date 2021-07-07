---
title: Naudokite duomenų šaltinius duomenų suvartojimui
description: Sužinokite, kaip importuoti duomenis iš įvairių šaltinių.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304706"
---
# <a name="data-sources-overview"></a>Duomenų šaltinių apžvalga

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Publikos įžvalgų galimybės „Dynamics 365 Customer Insights“ sujungia su duomenimis iš platesnio šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.

## <a name="add-a-data-source"></a>Įtraukti duomenų šaltinį

Informacijos apie tai, kaip įtraukti duomenų šaltinį, atsižvelgiant į pasirinktą parinktį, žr. išsamiuose straipsniuose.

Duomenų šaltinį galite įtraukti trimis pagrindiniais būdais.

- [Per dešimtis „Power Query“ jungčių](connect-power-query.md)
- [Iš „Common Data Model“ aplanko](connect-common-data-model.md)
- [Iš savo „Microsoft Dataverse“ telkinio](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Duomenų įtraukimas iš vietinių duomenų šaltinių

Duomenų tyrimas iš vietinių duomenų šaltinių „Audience Insights“ palaikomas atsižvelgiant į „Microsoft Power Platform“ duomenų srautus. Nustatant aplinką duomenų eigas galima įgalinti „Customer Insights“ [pateikiant Microsoft Dataverse aplinkos URL](manage-environments.md#create-an-environment-in-an-existing-organization).

Numatyta, kad duomenų šaltiniai, sukurti Dataverse aplinką susiejus su „Customer Insights“, naudos [Power Platform duomenų eigas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus. Pašalinkite ir iš naujo sukurkite duomenų šaltinius, kurie egzistavo prieš tai, kai „Dataverse” aplinka buvo susieta su [vietinių duomenų šliuzų naudojimu](/data-integration/gateway/service-gateway-app.md).

Esamos Power BI arba Power Apps aplinkos duomenų tinklų sietuvai bus matomi ir galėsite pakartotinai naudoti „Customer Insights“. Duomenų šaltinių puslapyje rodomi saitai, kuriuos naudojant galima peržiūrėti ir konfigūruoti duomenų „Microsoft Power Platform“ vietinis aplinką.

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

Pasirinkite **Statusas**, kad sužinotumėte bet kurios būsenos duomenų šaltinio reikšmę. Išsamios informacijos **apie eigą** srityje išplėskite  **Duomenų šaltiniai**. Pasirinkite **Gauti daugiau informacijos** apie naujinimo būseną, įskaitant klaidų informaciją ir tolesnius procesų naujinimus.

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**. Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).

## <a name="refresh-a-data-source"></a>Paleisti iš naujo duomenų šaltinį

Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį. 

Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.

Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elešką šalia norimos duomenų naujinti dalies ir **Naujinti** meniu pasirinkite Redaguoti.

3. Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo. Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.

4. Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.

## <a name="delete-a-data-source"></a>Naikinti duomenų šaltinį

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elešką šalia norimos duomenų naikinti dalies ir **Naikinti** meniu pasirinkite Redaguoti.

3. Patvirtinkite šį naikinimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
