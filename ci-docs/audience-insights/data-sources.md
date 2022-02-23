---
title: Naudokite duomenų šaltinius duomenų suvartojimui
description: Sužinokite, kaip importuoti duomenis iš įvairių šaltinių.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ca979527c9cb8418e12af4a74513033047e4901c
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046600"
---
# <a name="data-sources-overview"></a>Duomenų šaltinių apžvalga



Publikos įžvalgų galimybės „Dynamics 365 Customer Insights“ sujungia su duomenimis iš platesnio šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.

## <a name="add-a-data-source"></a>Įtraukti duomenų šaltinį

Peržiūrėkite išsamius straipsnius, kaip įtraukti duomenų šaltinis, priklausomai nuo pasirinktos parinkties.

Galite įtraukti šiuos duomenų šaltinius:

- [Power Query Jungtys](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse ežeras](connect-dataverse-managed-lake.md)

> [!NOTE]
> Jei naudojate bandomąją versiją, importavimo metodų skyriuje yra **"Customer Insights" duomenų bibliotekos** parinktis. Pasirinkite šią parinktį, jei norite pasirinkti duomenų rinkinio pavyzdį, prieinamą įvairioms pramonės šakoms. Daugiau informacijos rasite teisme [Dynamics 365 Customer Insights](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Duomenų įtraukimas iš vietinių duomenų šaltinių

Duomenų tyrimas iš vietinių duomenų šaltinių „Audience Insights“ palaikomas atsižvelgiant į „Microsoft Power Platform“ duomenų srautus. Duomenų srautus galite įgalinti "Customer Insights", nustatydami [aplinką pateikdami aplinkos URL Microsoft Dataverse.](create-environment.md)

Duomenų šaltiniai, sukurti susiedžius Dataverse aplinką su "Customer Insights", pagal numatytuosius nustatymus naudoja [Power Platform duomenų srautus](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus. Naudodami vietinis duomenų šliuzus, galite pašalinti ir iš naujo atkurti duomenų šaltinius, egzistavusius Dataverse prieš [susietą](/data-integration/gateway/service-gateway-app) aplinką.

Esamos Power BI arba Power Apps aplinkos duomenų tinklų sietuvai bus matomi ir galėsite pakartotinai naudoti „Customer Insights“. Duomenų šaltinių puslapyje rodomi saitai, kuriuos naudojant galima peržiūrėti ir konfigūruoti duomenų „Microsoft Power Platform“ vietinis aplinką.

## <a name="review-ingested-data"></a>Įtrauktų duomenų peržiūra

Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką. Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.

> [!div class="mx-imgBorder"]
> ![Įtrauktas duomenų šaltinis.](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

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
