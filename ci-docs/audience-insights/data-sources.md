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
# <a name="overview-about-data-sources"></a><span data-ttu-id="f34ea-103">Duomenų šaltinių apžvalga</span><span class="sxs-lookup"><span data-stu-id="f34ea-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f34ea-104">Publikos įžvalgų galimybės „Dynamics 365 Customer Insights“ sujungia su duomenimis iš platesnio šaltinių rinkinio.</span><span class="sxs-lookup"><span data-stu-id="f34ea-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="f34ea-105">Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*.</span><span class="sxs-lookup"><span data-stu-id="f34ea-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="f34ea-106">Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.</span><span class="sxs-lookup"><span data-stu-id="f34ea-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="f34ea-107">Įtraukti duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="f34ea-107">Add a data source</span></span>

<span data-ttu-id="f34ea-108">Informacijos apie tai, kaip įtraukti duomenų šaltinį, atsižvelgiant į pasirinktą parinktį, žr. išsamiuose straipsniuose.</span><span class="sxs-lookup"><span data-stu-id="f34ea-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="f34ea-109">Duomenų šaltinį galite įtraukti trimis pagrindiniais būdais.</span><span class="sxs-lookup"><span data-stu-id="f34ea-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="f34ea-110">Per dešimtis „Power Query“ jungčių</span><span class="sxs-lookup"><span data-stu-id="f34ea-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="f34ea-111">Iš „Common Data Model“ aplanko</span><span class="sxs-lookup"><span data-stu-id="f34ea-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="f34ea-112">Iš savo „Common Data Service“ telkinio</span><span class="sxs-lookup"><span data-stu-id="f34ea-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="f34ea-113">Kol kas duomenų iš vietinių duomenų šaltinių įtraukti negalite.</span><span class="sxs-lookup"><span data-stu-id="f34ea-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="f34ea-114">Įtrauktų duomenų peržiūra</span><span class="sxs-lookup"><span data-stu-id="f34ea-114">Review ingested data</span></span>

<span data-ttu-id="f34ea-115">Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką.</span><span class="sxs-lookup"><span data-stu-id="f34ea-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="f34ea-116">Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.</span><span class="sxs-lookup"><span data-stu-id="f34ea-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f34ea-117">![Įtrauktas duomenų šaltinis](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")</span><span class="sxs-lookup"><span data-stu-id="f34ea-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="f34ea-118">Būsena</span><span class="sxs-lookup"><span data-stu-id="f34ea-118">Status</span></span>  |<span data-ttu-id="f34ea-119">Aprašo</span><span class="sxs-lookup"><span data-stu-id="f34ea-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f34ea-120">Sėkminga</span><span class="sxs-lookup"><span data-stu-id="f34ea-120">Successful</span></span>   |<span data-ttu-id="f34ea-121">Duomenų šaltinis buvo sėkmingai suvartotas, jei laikas yra paminėtas **Paleistas iš naujo** stulpelyje.</span><span class="sxs-lookup"><span data-stu-id="f34ea-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="f34ea-122">Nepradėta</span><span class="sxs-lookup"><span data-stu-id="f34ea-122">Not started</span></span>   |<span data-ttu-id="f34ea-123">Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.</span><span class="sxs-lookup"><span data-stu-id="f34ea-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="f34ea-124">Atnaujinama</span><span class="sxs-lookup"><span data-stu-id="f34ea-124">Refreshing</span></span>    |<span data-ttu-id="f34ea-125">Vyksta duomenų apdorojimas.</span><span class="sxs-lookup"><span data-stu-id="f34ea-125">Data ingestion is in progress.</span></span> <span data-ttu-id="f34ea-126">Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**.</span><span class="sxs-lookup"><span data-stu-id="f34ea-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="f34ea-127">Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.</span><span class="sxs-lookup"><span data-stu-id="f34ea-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="f34ea-128">Atlikta nesėkmingai</span><span class="sxs-lookup"><span data-stu-id="f34ea-128">Failed</span></span>     |<span data-ttu-id="f34ea-129">Apdorojant duomenis įvyko klaidų.</span><span class="sxs-lookup"><span data-stu-id="f34ea-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="f34ea-130">Pasirinkite **Naujinimo būsena** tam, kad peržiūrėtumėte daugiau išsamios informacijos apie atnaujinimo būseną, įskaitant išsamią informaciją apie klaidas ir proceso pasroviui naujinimus.</span><span class="sxs-lookup"><span data-stu-id="f34ea-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="f34ea-131">Duomenų įkėlimas gali šiek tiek užtrukti.</span><span class="sxs-lookup"><span data-stu-id="f34ea-131">Loading data can take some time.</span></span> <span data-ttu-id="f34ea-132">Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="f34ea-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="f34ea-133">Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).</span><span class="sxs-lookup"><span data-stu-id="f34ea-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="f34ea-134">Paleisti iš naujo duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="f34ea-134">Refresh a data source</span></span>

<span data-ttu-id="f34ea-135">Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį.</span><span class="sxs-lookup"><span data-stu-id="f34ea-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="f34ea-136">Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.</span><span class="sxs-lookup"><span data-stu-id="f34ea-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="f34ea-137">Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:</span><span class="sxs-lookup"><span data-stu-id="f34ea-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="f34ea-138">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**</span><span class="sxs-lookup"><span data-stu-id="f34ea-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="f34ea-139">Pasirinkite vertikalią elipsę šalia duomenų šaltinio, kurį norite paleisti iš naujo ir pasirinkite **Paleisti iš naujo** iš iškrentančio meniu.</span><span class="sxs-lookup"><span data-stu-id="f34ea-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="f34ea-140">Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo.</span><span class="sxs-lookup"><span data-stu-id="f34ea-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="f34ea-141">Duomenų šaltinio paleidimas iš naujo atnaujins tiek objekto schemą, tiek ir duomenis iš visų objektų nurodytų duomenų šaltinyje.</span><span class="sxs-lookup"><span data-stu-id="f34ea-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="f34ea-142">Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.</span><span class="sxs-lookup"><span data-stu-id="f34ea-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="f34ea-143">Naikinti duomenų šaltinį</span><span class="sxs-lookup"><span data-stu-id="f34ea-143">Delete a data source</span></span>

1. <span data-ttu-id="f34ea-144">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="f34ea-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f34ea-145">Pažymėkite vertikalią elipsę, esančią šalia duomenų šaltinio, kurį norite pašalinti, ir išplečiamajame meniu pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="f34ea-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="f34ea-146">Patvirtinkite šį naikinimą.</span><span class="sxs-lookup"><span data-stu-id="f34ea-146">Confirm your deletion.</span></span>
