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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085540"
---
# <a name="data-sources-overview"></a><span data-ttu-id="d911e-103">Duomenų šaltinių apžvalga</span><span class="sxs-lookup"><span data-stu-id="d911e-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d911e-104">Publikos įžvalgų galimybės „Dynamics 365 Customer Insights“ sujungia su duomenimis iš platesnio šaltinių rinkinio.</span><span class="sxs-lookup"><span data-stu-id="d911e-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="d911e-105">Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*.</span><span class="sxs-lookup"><span data-stu-id="d911e-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="d911e-106">Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.</span><span class="sxs-lookup"><span data-stu-id="d911e-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="d911e-107">Įtraukti duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="d911e-107">Add a data source</span></span>

<span data-ttu-id="d911e-108">Informacijos apie tai, kaip įtraukti duomenų šaltinį, atsižvelgiant į pasirinktą parinktį, žr. išsamiuose straipsniuose.</span><span class="sxs-lookup"><span data-stu-id="d911e-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="d911e-109">Duomenų šaltinį galite įtraukti trimis pagrindiniais būdais.</span><span class="sxs-lookup"><span data-stu-id="d911e-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="d911e-110">Per dešimtis „Power Query“ jungčių</span><span class="sxs-lookup"><span data-stu-id="d911e-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="d911e-111">Iš „Common Data Model“ aplanko</span><span class="sxs-lookup"><span data-stu-id="d911e-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="d911e-112">Iš savo „Common Data Service“ telkinio</span><span class="sxs-lookup"><span data-stu-id="d911e-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="d911e-113">Duomenų įtraukimas iš vietinių duomenų šaltinių</span><span class="sxs-lookup"><span data-stu-id="d911e-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="d911e-114">Duomenų tyrimas iš vietinių duomenų šaltinių „Audience Insights“ palaikomas atsižvelgiant į Power Platform duomenų srautus.</span><span class="sxs-lookup"><span data-stu-id="d911e-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="d911e-115">Nustatant aplinką duomenų eigas galima įgalinti „Customer Insights“ [pateikiant Microsoft Dataverse aplinkos URL](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="d911e-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="d911e-116">Numatyta, kad duomenų šaltiniai, sukurti Dataverse aplinką susiejus su „Customer Insights“, naudos [Power Platform duomenų eigas](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).</span><span class="sxs-lookup"><span data-stu-id="d911e-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="d911e-117">Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus.</span><span class="sxs-lookup"><span data-stu-id="d911e-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="d911e-118">Pašalinkite ir iš naujo sukurkite duomenų šaltinius, kurie egzistavo prieš tai, kai „Dataverse” aplinka buvo susieta su [vietinių duomenų šliuzų naudojimu](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="d911e-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="d911e-119">Esamos Power BI arba Power Apps aplinkos duomenų tinklų sietuvai bus matomi ir galėsite pakartotinai naudoti „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="d911e-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="d911e-120">Duomenų šaltinių puslapyje rodomos nuorodos perėjimui į Power Platform aplinką, kurioje galima peržiūrėti ir konfigūruoti vietinius duomenų tinklų sietuvus.</span><span class="sxs-lookup"><span data-stu-id="d911e-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="d911e-121">Įtrauktų duomenų peržiūra</span><span class="sxs-lookup"><span data-stu-id="d911e-121">Review ingested data</span></span>

<span data-ttu-id="d911e-122">Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką.</span><span class="sxs-lookup"><span data-stu-id="d911e-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="d911e-123">Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.</span><span class="sxs-lookup"><span data-stu-id="d911e-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d911e-124">![Įtrauktas duomenų šaltinis](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")</span><span class="sxs-lookup"><span data-stu-id="d911e-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="d911e-125">Būsena</span><span class="sxs-lookup"><span data-stu-id="d911e-125">Status</span></span>  |<span data-ttu-id="d911e-126">Aprašo</span><span class="sxs-lookup"><span data-stu-id="d911e-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d911e-127">Sėkminga</span><span class="sxs-lookup"><span data-stu-id="d911e-127">Successful</span></span>   |<span data-ttu-id="d911e-128">Duomenų šaltinis buvo sėkmingai suvartotas, jei laikas yra paminėtas **Paleistas iš naujo** stulpelyje.</span><span class="sxs-lookup"><span data-stu-id="d911e-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="d911e-129">Nepradėta</span><span class="sxs-lookup"><span data-stu-id="d911e-129">Not started</span></span>   |<span data-ttu-id="d911e-130">Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.</span><span class="sxs-lookup"><span data-stu-id="d911e-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="d911e-131">Atnaujinama</span><span class="sxs-lookup"><span data-stu-id="d911e-131">Refreshing</span></span>    |<span data-ttu-id="d911e-132">Vyksta duomenų apdorojimas.</span><span class="sxs-lookup"><span data-stu-id="d911e-132">Data ingestion is in progress.</span></span> <span data-ttu-id="d911e-133">Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**.</span><span class="sxs-lookup"><span data-stu-id="d911e-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="d911e-134">Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.</span><span class="sxs-lookup"><span data-stu-id="d911e-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="d911e-135">Atlikta nesėkmingai</span><span class="sxs-lookup"><span data-stu-id="d911e-135">Failed</span></span>     |<span data-ttu-id="d911e-136">Apdorojant duomenis įvyko klaidų.</span><span class="sxs-lookup"><span data-stu-id="d911e-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="d911e-137">Pasirinkite **Statusas**, kad sužinotumėte bet kurios būsenos duomenų šaltinio reikšmę.</span><span class="sxs-lookup"><span data-stu-id="d911e-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="d911e-138">Išsamios informacijos **apie eigą** srityje išplėskite  **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="d911e-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="d911e-139">Pasirinkite **Gauti daugiau informacijos** apie naujinimo būseną, įskaitant klaidų informaciją ir tolesnius procesų naujinimus.</span><span class="sxs-lookup"><span data-stu-id="d911e-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="d911e-140">Duomenų įkėlimas gali šiek tiek užtrukti.</span><span class="sxs-lookup"><span data-stu-id="d911e-140">Loading data can take some time.</span></span> <span data-ttu-id="d911e-141">Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="d911e-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="d911e-142">Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).</span><span class="sxs-lookup"><span data-stu-id="d911e-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="d911e-143">Paleisti iš naujo duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="d911e-143">Refresh a data source</span></span>

<span data-ttu-id="d911e-144">Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį.</span><span class="sxs-lookup"><span data-stu-id="d911e-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="d911e-145">Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.</span><span class="sxs-lookup"><span data-stu-id="d911e-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="d911e-146">Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:</span><span class="sxs-lookup"><span data-stu-id="d911e-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="d911e-147">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**</span><span class="sxs-lookup"><span data-stu-id="d911e-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="d911e-148">Pasirinkite vertikalią elipsę šalia duomenų šaltinio, kurį norite paleisti iš naujo ir pasirinkite **Paleisti iš naujo** iš iškrentančio meniu.</span><span class="sxs-lookup"><span data-stu-id="d911e-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="d911e-149">Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo.</span><span class="sxs-lookup"><span data-stu-id="d911e-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="d911e-150">Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.</span><span class="sxs-lookup"><span data-stu-id="d911e-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="d911e-151">Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.</span><span class="sxs-lookup"><span data-stu-id="d911e-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="d911e-152">Naikinti duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="d911e-152">Delete a data source</span></span>

1. <span data-ttu-id="d911e-153">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="d911e-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d911e-154">Pažymėkite vertikalią elipsę, esančią šalia duomenų šaltinio, kurį norite pašalinti, ir išplečiamajame meniu pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="d911e-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="d911e-155">Patvirtinkite šį naikinimą.</span><span class="sxs-lookup"><span data-stu-id="d911e-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
