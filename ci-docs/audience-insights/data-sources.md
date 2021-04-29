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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887904"
---
# <a name="data-sources-overview"></a><span data-ttu-id="9566c-103">Duomenų šaltinių apžvalga</span><span class="sxs-lookup"><span data-stu-id="9566c-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9566c-104">Publikos įžvalgų galimybės „Dynamics 365 Customer Insights“ sujungia su duomenimis iš platesnio šaltinių rinkinio.</span><span class="sxs-lookup"><span data-stu-id="9566c-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="9566c-105">Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*.</span><span class="sxs-lookup"><span data-stu-id="9566c-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="9566c-106">Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.</span><span class="sxs-lookup"><span data-stu-id="9566c-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="9566c-107">Įtraukti duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="9566c-107">Add a data source</span></span>

<span data-ttu-id="9566c-108">Informacijos apie tai, kaip įtraukti duomenų šaltinį, atsižvelgiant į pasirinktą parinktį, žr. išsamiuose straipsniuose.</span><span class="sxs-lookup"><span data-stu-id="9566c-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="9566c-109">Duomenų šaltinį galite įtraukti trimis pagrindiniais būdais.</span><span class="sxs-lookup"><span data-stu-id="9566c-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="9566c-110">Per dešimtis „Power Query“ jungčių</span><span class="sxs-lookup"><span data-stu-id="9566c-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="9566c-111">Iš „Common Data Model“ aplanko</span><span class="sxs-lookup"><span data-stu-id="9566c-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="9566c-112">Iš savo „Common Data Service“ telkinio</span><span class="sxs-lookup"><span data-stu-id="9566c-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="9566c-113">Duomenų įtraukimas iš vietinių duomenų šaltinių</span><span class="sxs-lookup"><span data-stu-id="9566c-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="9566c-114">Duomenų tyrimas iš vietinių duomenų šaltinių „Audience Insights“ palaikomas atsižvelgiant į Power Platform duomenų srautus.</span><span class="sxs-lookup"><span data-stu-id="9566c-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="9566c-115">Nustatant aplinką duomenų eigas galima įgalinti „Customer Insights“ [pateikiant Microsoft Dataverse aplinkos URL](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="9566c-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="9566c-116">Numatyta, kad duomenų šaltiniai, sukurti Dataverse aplinką susiejus su „Customer Insights“, naudos [Power Platform duomenų eigas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="9566c-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="9566c-117">Duomenų eigos palaiko vietos ryšį, naudojant duomenų tinklų sietuvus.</span><span class="sxs-lookup"><span data-stu-id="9566c-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="9566c-118">Pašalinkite ir iš naujo sukurkite duomenų šaltinius, kurie buvo prieš Dataverse aplinką susiejant su vietinių tinklų sietuvų naudojimu.</span><span class="sxs-lookup"><span data-stu-id="9566c-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="9566c-119">Esamos Power BI arba Power Apps aplinkos duomenų tinklų sietuvai bus matomi ir galėsite pakartotinai naudoti „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="9566c-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="9566c-120">Duomenų šaltinių puslapyje rodomos nuorodos perėjimui į Power Platform aplinką, kurioje galima peržiūrėti ir konfigūruoti vietinius duomenų tinklų sietuvus.</span><span class="sxs-lookup"><span data-stu-id="9566c-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Duomenų šaltinių puslapio, kuriame rodomos nuorodos į Power Platform aplinką, ekrano vaizdas.":::

## <a name="review-ingested-data"></a><span data-ttu-id="9566c-122">Įtrauktų duomenų peržiūra</span><span class="sxs-lookup"><span data-stu-id="9566c-122">Review ingested data</span></span>

<span data-ttu-id="9566c-123">Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką.</span><span class="sxs-lookup"><span data-stu-id="9566c-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="9566c-124">Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.</span><span class="sxs-lookup"><span data-stu-id="9566c-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9566c-125">![Įtrauktas duomenų šaltinis](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")</span><span class="sxs-lookup"><span data-stu-id="9566c-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="9566c-126">Būsena</span><span class="sxs-lookup"><span data-stu-id="9566c-126">Status</span></span>  |<span data-ttu-id="9566c-127">Aprašo</span><span class="sxs-lookup"><span data-stu-id="9566c-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9566c-128">Sėkminga</span><span class="sxs-lookup"><span data-stu-id="9566c-128">Successful</span></span>   |<span data-ttu-id="9566c-129">Duomenų šaltinis buvo sėkmingai suvartotas, jei laikas yra paminėtas **Paleistas iš naujo** stulpelyje.</span><span class="sxs-lookup"><span data-stu-id="9566c-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="9566c-130">Nepradėta</span><span class="sxs-lookup"><span data-stu-id="9566c-130">Not started</span></span>   |<span data-ttu-id="9566c-131">Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.</span><span class="sxs-lookup"><span data-stu-id="9566c-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="9566c-132">Atnaujinama</span><span class="sxs-lookup"><span data-stu-id="9566c-132">Refreshing</span></span>    |<span data-ttu-id="9566c-133">Vyksta duomenų apdorojimas.</span><span class="sxs-lookup"><span data-stu-id="9566c-133">Data ingestion is in progress.</span></span> <span data-ttu-id="9566c-134">Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**.</span><span class="sxs-lookup"><span data-stu-id="9566c-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="9566c-135">Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.</span><span class="sxs-lookup"><span data-stu-id="9566c-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="9566c-136">Atlikta nesėkmingai</span><span class="sxs-lookup"><span data-stu-id="9566c-136">Failed</span></span>     |<span data-ttu-id="9566c-137">Apdorojant duomenis įvyko klaidų.</span><span class="sxs-lookup"><span data-stu-id="9566c-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="9566c-138">Pasirinkite **Statusas**, kad sužinotumėte bet kurios būsenos duomenų šaltinio reikšmę.</span><span class="sxs-lookup"><span data-stu-id="9566c-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="9566c-139">Išsamios informacijos **apie eigą** srityje išplėskite  **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="9566c-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="9566c-140">Pasirinkite **Gauti daugiau informacijos** apie naujinimo būseną, įskaitant klaidų informaciją ir tolesnius procesų naujinimus.</span><span class="sxs-lookup"><span data-stu-id="9566c-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="9566c-141">Duomenų įkėlimas gali šiek tiek užtrukti.</span><span class="sxs-lookup"><span data-stu-id="9566c-141">Loading data can take some time.</span></span> <span data-ttu-id="9566c-142">Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="9566c-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="9566c-143">Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).</span><span class="sxs-lookup"><span data-stu-id="9566c-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="9566c-144">Paleisti iš naujo duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="9566c-144">Refresh a data source</span></span>

<span data-ttu-id="9566c-145">Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį.</span><span class="sxs-lookup"><span data-stu-id="9566c-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="9566c-146">Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.</span><span class="sxs-lookup"><span data-stu-id="9566c-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="9566c-147">Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:</span><span class="sxs-lookup"><span data-stu-id="9566c-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="9566c-148">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**</span><span class="sxs-lookup"><span data-stu-id="9566c-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="9566c-149">Pasirinkite vertikalią elipsę šalia duomenų šaltinio, kurį norite paleisti iš naujo ir pasirinkite **Paleisti iš naujo** iš iškrentančio meniu.</span><span class="sxs-lookup"><span data-stu-id="9566c-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="9566c-150">Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo.</span><span class="sxs-lookup"><span data-stu-id="9566c-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="9566c-151">Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.</span><span class="sxs-lookup"><span data-stu-id="9566c-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="9566c-152">Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.</span><span class="sxs-lookup"><span data-stu-id="9566c-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="9566c-153">Naikinti duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="9566c-153">Delete a data source</span></span>

1. <span data-ttu-id="9566c-154">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="9566c-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9566c-155">Pažymėkite vertikalią elipsę, esančią šalia duomenų šaltinio, kurį norite pašalinti, ir išplečiamajame meniu pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="9566c-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="9566c-156">Patvirtinkite šį naikinimą.</span><span class="sxs-lookup"><span data-stu-id="9566c-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
