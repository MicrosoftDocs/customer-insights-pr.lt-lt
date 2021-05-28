---
title: Duomenų eksportavimas iš „Customer Insights“
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016624"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="170b6-103">Eksportavimų (peržiūros versija) apžvalga</span><span class="sxs-lookup"><span data-stu-id="170b6-103">Exports (preview) overview</span></span>

<span data-ttu-id="170b6-104">Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai.</span><span class="sxs-lookup"><span data-stu-id="170b6-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="170b6-105">Eksportavimuose su įvairiomis programomis bendrinami konkretūs duomenys.</span><span class="sxs-lookup"><span data-stu-id="170b6-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="170b6-106">Jie gali apimti klientų profilius arba objektus, schemas ir žymėjimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="170b6-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="170b6-107">Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md).</span><span class="sxs-lookup"><span data-stu-id="170b6-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="170b6-108">Eikite į **Duomenys** > **Eksportavimai**, kad peržiūrėtumėte eksportavimų puslapį.</span><span class="sxs-lookup"><span data-stu-id="170b6-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="170b6-109">Visi naudotojo vaidmenys turi prieigą sukonfigūruotiems eksportavimams peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="170b6-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="170b6-110">Naudokite komandų juostoje esantį paieškos laukelį eksportavimams rasti pagal pavadinimą, ryšio pavadinimą arba ryšio tipą.</span><span class="sxs-lookup"><span data-stu-id="170b6-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="170b6-111">Naujo eksportavimo sąranka</span><span class="sxs-lookup"><span data-stu-id="170b6-111">Set up a new export</span></span>

<span data-ttu-id="170b6-112">Jei norite nustatyti ar redaguoti eksportavimą, turite turėti prieinamų ryšių.</span><span class="sxs-lookup"><span data-stu-id="170b6-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="170b6-113">Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="170b6-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="170b6-114">Administratoriai turi prieigą prie visų ryšių.</span><span class="sxs-lookup"><span data-stu-id="170b6-114">Administrators have access to all connections.</span></span> <span data-ttu-id="170b6-115">Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="170b6-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="170b6-116">Bendradarbiai gali turėti prieigą prie konkrečių ryšių.</span><span class="sxs-lookup"><span data-stu-id="170b6-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="170b6-117">Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius.</span><span class="sxs-lookup"><span data-stu-id="170b6-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="170b6-118">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="170b6-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="170b6-119">Žiūrovai gali tik peržiūrėti esamus eksportavimus, tačiau ne juos kurti.</span><span class="sxs-lookup"><span data-stu-id="170b6-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="170b6-120">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="170b6-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="170b6-121">Pasirinkite **Pridėti eksportavimą**, jei norite sukurti naują eksportavimo paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="170b6-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="170b6-122">Srityje **Sąrankos eksportavimas** pasirinkite, kurį ryšį naudoti.</span><span class="sxs-lookup"><span data-stu-id="170b6-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="170b6-123">[Ryšius](connections.md) tvarko administratoriai.</span><span class="sxs-lookup"><span data-stu-id="170b6-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="170b6-124">Jei norite sukurti eksportavimą, pateikite reikiamus duomenis ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="170b6-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="170b6-125">Eksportavimo redagavimas</span><span class="sxs-lookup"><span data-stu-id="170b6-125">Edit an export</span></span>

1. <span data-ttu-id="170b6-126">Pažymėkite eksportavimo paskirties vietos, kurią norite redaguoti, vertikalią elipsę.</span><span class="sxs-lookup"><span data-stu-id="170b6-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="170b6-127">Išskleidžiamajame meniu pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="170b6-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="170b6-128">Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="170b6-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="170b6-129">Eksportavimo ir eksportavimo duomenų peržiūra</span><span class="sxs-lookup"><span data-stu-id="170b6-129">View Exports and export details</span></span>

<span data-ttu-id="170b6-130">Sukūrus eksportavimo paskirties vietas jų sąrašas pateikiamas pasirinkus **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="170b6-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="170b6-131">Visi naudotojai mato, kurie duomenys bendrinami ir kokia jų naujausia būsena.</span><span class="sxs-lookup"><span data-stu-id="170b6-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="170b6-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="170b6-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="170b6-133">Naudotojai, neturintys redagavimo teisių, pasirenka **Peržiūrėti**, o ne **Redaguoti**. Peržiūrėkite eksportavimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="170b6-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="170b6-134">Šioje šoninėje srityje rodoma šio eksportavimo sąranka.</span><span class="sxs-lookup"><span data-stu-id="170b6-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="170b6-135">Jei neturite redagavimo teisių, reikšmių keisti negalite.</span><span class="sxs-lookup"><span data-stu-id="170b6-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="170b6-136">Jei norite grįžti prie eksportavimų puslapio, pasirinkite **Uždaryti**.</span><span class="sxs-lookup"><span data-stu-id="170b6-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="170b6-137">Pageidaujamų eksportavimų paleidimas</span><span class="sxs-lookup"><span data-stu-id="170b6-137">Run exports on demand</span></span>

<span data-ttu-id="170b6-138">Sukonfigūravus eksportavimą jis bus vykdomas kiekvieno [planinio atnaujinimo metu](system.md#schedule-tab), kol yra veikiantis ryšys.</span><span class="sxs-lookup"><span data-stu-id="170b6-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="170b6-139">Jei duomenis norite eksportuoti nelaukdami planuojamo atnaujinimo, eikite į **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="170b6-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="170b6-140">Turite du pasirinkimus:</span><span class="sxs-lookup"><span data-stu-id="170b6-140">You have two options:</span></span>

- <span data-ttu-id="170b6-141">Jei norite peržiūrėti visus eksportavimus, komandų juostoje pasirinkite **Vykdyti viską**.</span><span class="sxs-lookup"><span data-stu-id="170b6-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="170b6-142">Jei norite vykdyti vieną eksportavimą, sąrašo elemente pasirinkite elipsę (...) ir pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="170b6-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="170b6-143">Eksportavimo pašalinimas</span><span class="sxs-lookup"><span data-stu-id="170b6-143">Remove an Export</span></span>

1. <span data-ttu-id="170b6-144">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="170b6-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="170b6-145">Pažymėkite norimos pašalinti eksportavimo vertikalią elipsę.</span><span class="sxs-lookup"><span data-stu-id="170b6-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="170b6-146">Išskleidžiamajame meniu pasirinkite **Pašalinti**.</span><span class="sxs-lookup"><span data-stu-id="170b6-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="170b6-147">Patvirtinkite pašalinimą pasirinkdami **Pašalinti** patvirtinimo ekrane.</span><span class="sxs-lookup"><span data-stu-id="170b6-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
