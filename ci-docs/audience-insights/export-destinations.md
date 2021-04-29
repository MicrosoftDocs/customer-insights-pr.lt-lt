---
title: Duomenų eksportavimas iš „Customer Insights“
description: 'Tvarkykite duomenų bendrinimo eksportavimus. '
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896153"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="5e390-103">Eksportavimų (peržiūra) apžvalga</span><span class="sxs-lookup"><span data-stu-id="5e390-103">Exports (preview) overview</span></span>

<span data-ttu-id="5e390-104">Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai.</span><span class="sxs-lookup"><span data-stu-id="5e390-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="5e390-105">Eksportavimuose su įvairiomis programomis bendrinami konkretūs duomenys.</span><span class="sxs-lookup"><span data-stu-id="5e390-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="5e390-106">Jie gali apimti klientų profilius arba objektus, schemas ir žymėjimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="5e390-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="5e390-107">Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md).</span><span class="sxs-lookup"><span data-stu-id="5e390-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5e390-108">Iki 2021 m. kovo mėn. eksportavimai automatiškai sukūrė ryšį su atitinkama paslauga.</span><span class="sxs-lookup"><span data-stu-id="5e390-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="5e390-109">Dabar eksportavimams reikia [administratoriaus sukurto ir bendrinamo ryšio](connections.md), kad juos galėtumėte sukurti.</span><span class="sxs-lookup"><span data-stu-id="5e390-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="5e390-110">Eikite į **Duomenys** > **Eksportavimai**, kad peržiūrėtumėte eksportavimų puslapį.</span><span class="sxs-lookup"><span data-stu-id="5e390-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="5e390-111">Visi naudotojo vaidmenys turi prieigą sukonfigūruotiems eksportavimams peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="5e390-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="5e390-112">Naudokite komandų juostoje esantį paieškos laukelį eksportavimams rasti pagal pavadinimą, ryšio pavadinimą arba ryšio tipą.</span><span class="sxs-lookup"><span data-stu-id="5e390-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="5e390-113">Naujo eksportavimo sąranka</span><span class="sxs-lookup"><span data-stu-id="5e390-113">Set up a new export</span></span>

<span data-ttu-id="5e390-114">Jei norite nustatyti ar redaguoti eksportavimą, turite turėti prieinamų ryšių.</span><span class="sxs-lookup"><span data-stu-id="5e390-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="5e390-115">Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="5e390-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="5e390-116">Administratoriai turi prieigą prie visų ryšių.</span><span class="sxs-lookup"><span data-stu-id="5e390-116">Administrators have access to all connections.</span></span> <span data-ttu-id="5e390-117">Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="5e390-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="5e390-118">Bendradarbiai gali turėti prieigą prie konkrečių ryšių.</span><span class="sxs-lookup"><span data-stu-id="5e390-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="5e390-119">Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius.</span><span class="sxs-lookup"><span data-stu-id="5e390-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="5e390-120">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5e390-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="5e390-121">Žiūrovai gali tik peržiūrėti esamus eksportavimus, tačiau ne juos kurti.</span><span class="sxs-lookup"><span data-stu-id="5e390-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="5e390-122">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="5e390-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5e390-123">Pasirinkite **Pridėti eksportavimą**, jei norite sukurti naują eksportavimo paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="5e390-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="5e390-124">Srityje **Sąrankos eksportavimas** pasirinkite, kurį ryšį naudoti.</span><span class="sxs-lookup"><span data-stu-id="5e390-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="5e390-125">[Ryšius](connections.md) tvarko administratoriai.</span><span class="sxs-lookup"><span data-stu-id="5e390-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="5e390-126">Jei norite sukurti eksportavimą, pateikite reikiamus duomenis ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5e390-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="5e390-127">Eksportavimo redagavimas</span><span class="sxs-lookup"><span data-stu-id="5e390-127">Edit an export</span></span>

1. <span data-ttu-id="5e390-128">Pažymėkite eksportavimo paskirties vietos, kurią norite redaguoti, vertikalią elipsę.</span><span class="sxs-lookup"><span data-stu-id="5e390-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="5e390-129">Išskleidžiamajame meniu pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="5e390-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="5e390-130">Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5e390-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="5e390-131">Eksportavimo ir eksportavimo duomenų peržiūra</span><span class="sxs-lookup"><span data-stu-id="5e390-131">View Exports and export details</span></span>

<span data-ttu-id="5e390-132">Sukūrus eksportavimo paskirties vietas jų sąrašas pateikiamas pasirinkus **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="5e390-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="5e390-133">Visi naudotojai mato, kurie duomenys bendrinami ir kokia jų naujausia būsena.</span><span class="sxs-lookup"><span data-stu-id="5e390-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="5e390-134">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="5e390-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5e390-135">Naudotojai, neturintys redagavimo teisių, pasirenka **Peržiūrėti**, o ne **Redaguoti**. Peržiūrėkite eksportavimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="5e390-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="5e390-136">Šioje šoninėje srityje rodoma šio eksportavimo sąranka.</span><span class="sxs-lookup"><span data-stu-id="5e390-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="5e390-137">Jei neturite redagavimo teisių, reikšmių keisti negalite.</span><span class="sxs-lookup"><span data-stu-id="5e390-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="5e390-138">Jei norite grįžti prie eksportavimų puslapio, pasirinkite **Uždaryti**.</span><span class="sxs-lookup"><span data-stu-id="5e390-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="5e390-139">Pageidaujamų eksportavimų paleidimas</span><span class="sxs-lookup"><span data-stu-id="5e390-139">Run exports on demand</span></span>

<span data-ttu-id="5e390-140">Sukonfigūravus eksportavimą jis bus vykdomas kiekvieno [planinio atnaujinimo metu](system.md#schedule-tab), kol yra veikiantis ryšys.</span><span class="sxs-lookup"><span data-stu-id="5e390-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="5e390-141">Jei duomenis norite eksportuoti nelaukdami planuojamo atnaujinimo, eikite į **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="5e390-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="5e390-142">Turite du pasirinkimus:</span><span class="sxs-lookup"><span data-stu-id="5e390-142">You have two options:</span></span>

- <span data-ttu-id="5e390-143">Jei norite peržiūrėti visus eksportavimus, komandų juostoje pasirinkite **Vykdyti viską**.</span><span class="sxs-lookup"><span data-stu-id="5e390-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="5e390-144">Jei norite vykdyti vieną eksportavimą, sąrašo elemente pasirinkite elipsę (...) ir pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="5e390-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="5e390-145">Eksportavimo pašalinimas</span><span class="sxs-lookup"><span data-stu-id="5e390-145">Remove an Export</span></span>

1. <span data-ttu-id="5e390-146">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="5e390-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5e390-147">Pažymėkite norimos pašalinti eksportavimo vertikalią elipsę.</span><span class="sxs-lookup"><span data-stu-id="5e390-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="5e390-148">Išskleidžiamajame meniu pasirinkite **Pašalinti**.</span><span class="sxs-lookup"><span data-stu-id="5e390-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="5e390-149">Patvirtinkite pašalinimą pasirinkdami **Pašalinti** patvirtinimo ekrane.</span><span class="sxs-lookup"><span data-stu-id="5e390-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
