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
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="72459-103">Prisijungimas prie „Power Query“ duomenų šaltinio</span><span class="sxs-lookup"><span data-stu-id="72459-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="72459-104">„Power Query“ siūlo platų jungčių pasirinkimą duomenims įtraukti.</span><span class="sxs-lookup"><span data-stu-id="72459-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="72459-105">Daugelį šių jungčių palaiko „Dynamics 365 Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="72459-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="72459-106">Duomenų šaltiniai pagal „Power Query“ jungtis paprastai įtraukiami atliekant kitame skyriuje aprašytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="72459-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="72459-107">Tačiau, atsižvelgiant į naudojamą jungtį, reikalinga kita informacija.</span><span class="sxs-lookup"><span data-stu-id="72459-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="72459-108">Daugiau informacijos ieškokite dokumentacijoje apie konkrečias jungtis skyriuje [„Power Query“ jungčių aprašas](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="72459-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="72459-109">Sukurkite naują duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="72459-109">Create a new data source</span></span>

1. <span data-ttu-id="72459-110">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="72459-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="72459-111">Pasirinkite **Įtraukti duomenų šaltinį**.</span><span class="sxs-lookup"><span data-stu-id="72459-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="72459-112">Pasirinkite metodą **Importuoti duomenis** ir pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="72459-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="72459-113">Nurodykite duomenų šaltinio **Pavadinimas** ir pasirinkite **Toliau**, kad sukurtumėte duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="72459-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="72459-114">Pasirinkite vieną iš [galimų jungčių](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="72459-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="72459-115">Šiame pavyzdyje pasirinksime jungtį **Tekstas/CSV**.</span><span class="sxs-lookup"><span data-stu-id="72459-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="72459-116">Įveskite reikiamą pasirinktos jungties informaciją dalyje **Ryšio parametrai** ir pasirinkite **Toliau**, kad peržiūrėtumėte duomenis.</span><span class="sxs-lookup"><span data-stu-id="72459-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="72459-117">Pasirinkite **Transformuoti duomenis**.</span><span class="sxs-lookup"><span data-stu-id="72459-117">Select **Transform data**.</span></span> <span data-ttu-id="72459-118">Atlikę šį veiksmą, įtrauksite objektų į savo duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="72459-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="72459-119">Objektai yra duomenų rinkiniai.</span><span class="sxs-lookup"><span data-stu-id="72459-119">Entities are datasets.</span></span> <span data-ttu-id="72459-120">Jei turite duomenų bazę, kurioje yra keletas duomenų rinkinių, kiekvienas duomenų rinkinys yra savo paties objektas.</span><span class="sxs-lookup"><span data-stu-id="72459-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="72459-121">Dialogo lange **„Power Query“ – redaguoti užklausas** galima peržiūrėti ir tikslinti duomenis.</span><span class="sxs-lookup"><span data-stu-id="72459-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="72459-122">Objektai, kuriuos sistema nustatė jūsų pasirinktame duomenų šaltinyje, rodomi kairiosios srities dalyje.</span><span class="sxs-lookup"><span data-stu-id="72459-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="72459-123">![Užklausų redagavimo dialogo langas](media/data-manager-configure-edit-queries.png "Užklausų redagavimo dialogo langas")</span><span class="sxs-lookup"><span data-stu-id="72459-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="72459-124">Taip pat galite pertvarkyti savo duomenis.</span><span class="sxs-lookup"><span data-stu-id="72459-124">You can also transform your data.</span></span> <span data-ttu-id="72459-125">Pažymėkite objektą, kurį norite redaguoti arba pertvarkyti.</span><span class="sxs-lookup"><span data-stu-id="72459-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="72459-126">Norėdami pritaikyti transformavimą, naudokite lango „Power Query“ parinktis.</span><span class="sxs-lookup"><span data-stu-id="72459-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="72459-127">Vis transformavimai išvardijami dalyje **Pritaikyti veiksmai**.</span><span class="sxs-lookup"><span data-stu-id="72459-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="72459-128">„Power Query“ suteikia daug iš anksto sukurtų transformavimo galimybių.</span><span class="sxs-lookup"><span data-stu-id="72459-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="72459-129">Daugiau informacijos ieškokite [„Power Query“ transformavimai](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="72459-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="72459-130">Galite įtraukti papildomų objektų į savo duomenų šaltinį, dialogo lange **Redaguoti užklausas** pasirinkdami **Gauti duomenis**.</span><span class="sxs-lookup"><span data-stu-id="72459-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="72459-131">Primygtinai rekomenduojama atlikti šiuos pertvarkymus:</span><span class="sxs-lookup"><span data-stu-id="72459-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="72459-132">Jei duomenis įtraukiate iš CSV failo, pirmojoje eilutėje dažnai pateikiamos antraštės.</span><span class="sxs-lookup"><span data-stu-id="72459-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="72459-133">Pereikite prie **Transformavimo lentelė** ir pasirinkite **Naudoti antraštes kaip pirmąją eilutę**.</span><span class="sxs-lookup"><span data-stu-id="72459-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="72459-134">Užtikrinkite, kad tinkamai nustatytas duomenų tipas.</span><span class="sxs-lookup"><span data-stu-id="72459-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="72459-135">Lango „Power Query“ apačioje pasirinkite **Įrašyti**, kad įrašytumėte transformavimus.</span><span class="sxs-lookup"><span data-stu-id="72459-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="72459-136">Įrašę, duomenų šaltinį rasite pasirinkę **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="72459-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="72459-137">Puslapyje **Duomenų šaltiniai** pastebėsite, kad naujo duomenų šaltinio būsena yra **Atnaujinama**.</span><span class="sxs-lookup"><span data-stu-id="72459-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="72459-138">Pasiekiami „Power Query“ duomenų šaltiniai</span><span class="sxs-lookup"><span data-stu-id="72459-138">Available Power Query data sources</span></span>

<span data-ttu-id="72459-139">Žr. skyrių [„Power Query“ jungčių aprašas](https://docs.microsoft.com/power-query/connectors/), kuriame pateikiamas aktualus jungčių, kurias galite pasirinkti importuodami duomenis į „Customer Insights“, sąrašas.</span><span class="sxs-lookup"><span data-stu-id="72459-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="72459-140">Jungtys su varnele stulpelyje **„Customer Insights“ (duomenų srautai)** gali būti naudojamos kuriant naujus duomenų šaltinius pagal „Power Query“.</span><span class="sxs-lookup"><span data-stu-id="72459-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="72459-141">Peržiūrėkite konkrečios jungties dokumentaciją ir sužinokite daugiau apie būtinąsias sąlygas, apribojimus ir kitą išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="72459-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="72459-142">„Power Query“ duomenų šaltinių redagavimas</span><span class="sxs-lookup"><span data-stu-id="72459-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="72459-143">Gali būti neįmanoma keisti duomenų šaltinius, kurie dabar yra naudojami viename iš programos procesų (pvz., *segmentavimo*, *sutapdinimo* arba *suliejimo*).</span><span class="sxs-lookup"><span data-stu-id="72459-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="72459-144">Naudodamiesi puslapiu **Parametrai** galite sekti kiekvieno iš aktyvių procesų eigą.</span><span class="sxs-lookup"><span data-stu-id="72459-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="72459-145">Kai procesas bus užbaigtas, galite grįžti į puslapį **Duomenų šaltiniai** ir atlikti pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="72459-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="72459-146">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="72459-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="72459-147">Pažymėkite vertikalią elipsę, esančią šalia duomenų šaltinio, kurį norite pakeisti, ir išplečiamajame meniu pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="72459-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="72459-148">![Redagavimo parinktis](media/edit-option-data-sources.png "Redagavimo parinktis")</span><span class="sxs-lookup"><span data-stu-id="72459-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="72459-149">Pritaikykite savo pakeitimus ir transformavimus dialogo lange **„Power Query“ – redaguoti užklausas**, remdamiesi skyriumi [Naujo duomenų šaltinio kūrimas](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="72459-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="72459-150">Baigę redaguoti, pasirinkite **Įrašyti** dalyje „Power Query“, kad įrašytumėte pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="72459-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
