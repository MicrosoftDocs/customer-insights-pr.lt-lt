---
title: Duomenų eksportavimas iš „Customer Insights“
description: Tvarkykite duomenų bendrinimo eksportavimus.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253050"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="d3426-103">Eksportavimų (peržiūros versija) apžvalga</span><span class="sxs-lookup"><span data-stu-id="d3426-103">Exports (preview) overview</span></span>

<span data-ttu-id="d3426-104">Puslapyje **Eksportavimai** rodomi visi sukonfigūruoti eksportavimai.</span><span class="sxs-lookup"><span data-stu-id="d3426-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="d3426-105">Eksportavimuose su įvairiomis programomis bendrinami konkretūs duomenys.</span><span class="sxs-lookup"><span data-stu-id="d3426-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="d3426-106">Jie gali apimti klientų profilius arba objektus, schemas ir žymėjimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="d3426-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="d3426-107">Kiekvienam eksportavimui reikalingas [ryšys, kurį nustato administratorius, kad galėtų tvarkyti įgaliojimą ir prieigą](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d3426-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="d3426-108">Eikite į **Duomenys** > **Eksportavimai**, kad peržiūrėtumėte eksportavimų puslapį.</span><span class="sxs-lookup"><span data-stu-id="d3426-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="d3426-109">Visi naudotojo vaidmenys turi prieigą sukonfigūruotiems eksportavimams peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="d3426-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="d3426-110">Naudokite komandų juostoje esantį paieškos laukelį eksportavimams rasti pagal pavadinimą, ryšio pavadinimą arba ryšio tipą.</span><span class="sxs-lookup"><span data-stu-id="d3426-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="d3426-111">Naujo eksportavimo sąranka</span><span class="sxs-lookup"><span data-stu-id="d3426-111">Set up a new export</span></span>

<span data-ttu-id="d3426-112">Jei norite nustatyti ar redaguoti eksportavimą, turite turėti prieinamų ryšių.</span><span class="sxs-lookup"><span data-stu-id="d3426-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="d3426-113">Ryšiai priklauso nuo jūsų [naudotojo vaidmens](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="d3426-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="d3426-114">Administratoriai turi prieigą prie visų ryšių.</span><span class="sxs-lookup"><span data-stu-id="d3426-114">Administrators have access to all connections.</span></span> <span data-ttu-id="d3426-115">Jie taip pat gali kurti naujus ryšius nustatydami eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="d3426-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="d3426-116">Bendradarbiai gali turėti prieigą prie konkrečių ryšių.</span><span class="sxs-lookup"><span data-stu-id="d3426-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="d3426-117">Jie priklauso nuo administratorių, kad sukonfigūruotų ir bendrintų ryšius.</span><span class="sxs-lookup"><span data-stu-id="d3426-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="d3426-118">Eksportavimų sąraše pateikiama, ar bendraautoriai gali redaguoti, ar tik peržiūrėti eksportavimą **Jūsų teisių** stulpelyje.</span><span class="sxs-lookup"><span data-stu-id="d3426-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="d3426-119">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d3426-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="d3426-120">Žiūrovai gali tik peržiūrėti esamus eksportavimus, tačiau ne juos kurti.</span><span class="sxs-lookup"><span data-stu-id="d3426-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="d3426-121">Naujo eksportavimo apibrėžimas</span><span class="sxs-lookup"><span data-stu-id="d3426-121">Define a new export</span></span>

1. <span data-ttu-id="d3426-122">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3426-123">Pasirinkite **Įtraukti eksportavimą** naujo eksportavimo sukūrimui.</span><span class="sxs-lookup"><span data-stu-id="d3426-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="d3426-124">Srityje **Sąrankos eksportavimas** pasirinkite, kurį ryšį naudoti.</span><span class="sxs-lookup"><span data-stu-id="d3426-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="d3426-125">[Ryšius](connections.md) tvarko administratoriai.</span><span class="sxs-lookup"><span data-stu-id="d3426-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="d3426-126">Jei norite sukurti eksportavimą, pateikite reikiamus duomenis ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="d3426-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="d3426-127">Apibrėžti naują eksportavimą, pagrįstą esamu eksportavimu</span><span class="sxs-lookup"><span data-stu-id="d3426-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="d3426-128">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3426-129">Eksportavimų sąraše pasirinkite eksportavimą, kurio dublikatą norite sukurti.</span><span class="sxs-lookup"><span data-stu-id="d3426-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="d3426-130">Komandų juostoje pasirinkite **Kurti dublikatą**, kad atidarytumėte sritį **Nustatyti eksportavimą** su išsamia pasirinkto eksportavimo informacija.</span><span class="sxs-lookup"><span data-stu-id="d3426-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="d3426-131">Peržiūrėkite ir pritaikykite eksportavimą bei pasirinkite **Įrašyti**, kad sukurtumėte naują eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="d3426-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="d3426-132">Eksportavimo redagavimas</span><span class="sxs-lookup"><span data-stu-id="d3426-132">Edit an export</span></span>

1. <span data-ttu-id="d3426-133">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3426-134">Eksportavimų sąraše pasirinkite eksportavimą, kurį norite redaguoti.</span><span class="sxs-lookup"><span data-stu-id="d3426-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="d3426-135">Pasirinkite **Redaguoti** komandų juostoje.</span><span class="sxs-lookup"><span data-stu-id="d3426-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="d3426-136">Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="d3426-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="d3426-137">Eksportavimų ir išsamios eksportavimo informacijos peržiūra</span><span class="sxs-lookup"><span data-stu-id="d3426-137">View exports and export details</span></span>

<span data-ttu-id="d3426-138">Sukurtų eksportavimo paskirties vietų sąrašas yra pateikiamas **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="d3426-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="d3426-139">Visi naudotojai mato, kurie duomenys bendrinami ir kokia jų naujausia būsena.</span><span class="sxs-lookup"><span data-stu-id="d3426-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="d3426-140">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3426-141">Naudotojai, neturintys redagavimo teisių, pasirenka **Peržiūrėti**, o ne **Redaguoti**. Peržiūrėkite eksportavimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="d3426-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="d3426-142">Šoninėje srityje rodoma eksportavimo konfigūracija.</span><span class="sxs-lookup"><span data-stu-id="d3426-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="d3426-143">Jei neturite redagavimo teisių, reikšmių keisti negalite.</span><span class="sxs-lookup"><span data-stu-id="d3426-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="d3426-144">Jei norite grįžti prie eksportavimų puslapio, pasirinkite **Uždaryti**.</span><span class="sxs-lookup"><span data-stu-id="d3426-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="d3426-145">Eksportavimų planavimas ir vykdymas</span><span class="sxs-lookup"><span data-stu-id="d3426-145">Schedule and run exports</span></span>

<span data-ttu-id="d3426-146">Kiekvienas jūsų konfigūruojamas eksportavimas turi atnaujinimo grafiką.</span><span class="sxs-lookup"><span data-stu-id="d3426-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="d3426-147">Atnaujinimo metu sistema ieško naujų arba atnaujintų duomenų, kuriuos reikia įtraukti į eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="d3426-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="d3426-148">Pagal numatytuosius nustatymus, eksportavimai yra vykdomi kaip kiekvieno [suplanuoto sistemos atnaujinimo](system.md#schedule-tab) dalis.</span><span class="sxs-lookup"><span data-stu-id="d3426-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d3426-149">Galite tinkinti atnaujinimo grafiką arba išjungti jį, kad eksportavimus vykdytumėte rankiniu būdu.</span><span class="sxs-lookup"><span data-stu-id="d3426-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="d3426-150">Eksportavimo grafikai priklauso nuo jūsų aplinkos būsenos.</span><span class="sxs-lookup"><span data-stu-id="d3426-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="d3426-151">Jei progrese yra [priklausomybių](system.md#refresh-policies) atnaujinimų, kai turėtų prasidėti suplanuotas eksportavimas, sistema pirmiausia užbaigs priklausomybes ir tada vykdys eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="d3426-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="d3426-152">Galite matyti, kada eksportavimas paskutinį kartą buvo atnaujintas, stulpelyje **Atnaujinta**.</span><span class="sxs-lookup"><span data-stu-id="d3426-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="d3426-153">Eksportavimų grafikas</span><span class="sxs-lookup"><span data-stu-id="d3426-153">Schedule exports</span></span>

<span data-ttu-id="d3426-154">Vienu metu galite apibrėžti pasirinktinius atskirų arba kelių eksportavimų atnaujinimo grafikus.</span><span class="sxs-lookup"><span data-stu-id="d3426-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="d3426-155">Šiuo metu apibrėžtas grafikas pateikiamas eksportavimo sąrašo stulpelyje **Grafikas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="d3426-156">Teisė keisti grafiką yra tokia pat, kaip ir [redaguojant ir apibrėžiant eksportavimus](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d3426-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="d3426-157">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3426-158">Pasirinkite norimą suplanuoti eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="d3426-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="d3426-159">Pasirinkite **Grafikas** komandų juostoje.</span><span class="sxs-lookup"><span data-stu-id="d3426-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="d3426-160">Srityje **Eksportavimo grafikas** nustatykite **Vykdymo grafiką** į **Įjungta**, kad eksportavimas būtų vykdomas automatiškai.</span><span class="sxs-lookup"><span data-stu-id="d3426-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="d3426-161">Nustatykite į **Išjungta**, kad jį atnaujintumėte rankiniu būdu.</span><span class="sxs-lookup"><span data-stu-id="d3426-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="d3426-162">Automatiškai atnaujintiems eksportavimams pasirinkite **Pasikartojimo** reikšmę ir nurodykite jos išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="d3426-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="d3426-163">Nustatytas laikas taikomas visiems pasikartojimo atvejams.</span><span class="sxs-lookup"><span data-stu-id="d3426-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="d3426-164">Tai yra laikas, kai eksportavimas turėtų pradėti atsinaujinti.</span><span class="sxs-lookup"><span data-stu-id="d3426-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="d3426-165">Taikykite ir suaktyvinkite pakeitimus pažymėdami **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="d3426-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="d3426-166">Redaguodami kelių eksportavimų grafiką, turite pasirinkti skiltyje **Išsaugoti arba perrašyti grafikus**:</span><span class="sxs-lookup"><span data-stu-id="d3426-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="d3426-167">**Išlaikyti atskirus grafikus**: Išlaiko anksčiau apibrėžtą pasirinktų eksportavimų grafiką ir juos tik išjungia arba įjungia.</span><span class="sxs-lookup"><span data-stu-id="d3426-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="d3426-168">**Apibrėžti naują grafiką visiems pasirinktiems eksportavimams**: Perrašo esamus pasirinktų eksportavimų grafikus.</span><span class="sxs-lookup"><span data-stu-id="d3426-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="d3426-169">Pageidaujamų eksportavimų paleidimas</span><span class="sxs-lookup"><span data-stu-id="d3426-169">Run exports on demand</span></span>

<span data-ttu-id="d3426-170">Jei duomenis norite eksportuoti nelaukdami planuojamo atnaujinimo, eikite į **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="d3426-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="d3426-171">Jei norite peržiūrėti visus eksportavimus, komandų juostoje pasirinkite **Vykdyti viską**.</span><span class="sxs-lookup"><span data-stu-id="d3426-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="d3426-172">Šis veiksmas paleis tik eksportavimus, turinčius aktyvų grafiką.</span><span class="sxs-lookup"><span data-stu-id="d3426-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="d3426-173">Norėdami vykdyti vieną eksportavimą, pažymėkite jį sąraše ir pasirinkite **Vykdyti** komandų juostoje.</span><span class="sxs-lookup"><span data-stu-id="d3426-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="d3426-174">Taip vykdote eksportavimus, neturinčius aktyvaus grafiko.</span><span class="sxs-lookup"><span data-stu-id="d3426-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="d3426-175">Eksportavimo pašalinimas</span><span class="sxs-lookup"><span data-stu-id="d3426-175">Remove an Export</span></span>

1. <span data-ttu-id="d3426-176">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3426-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3426-177">Pažymėkite norimą pašalinti eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="d3426-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="d3426-178">Pasirinkite **Šalinti** komandų juostoje.</span><span class="sxs-lookup"><span data-stu-id="d3426-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="d3426-179">Patvirtinkite pašalinimą pasirinkdami **Pašalinti** patvirtinimo ekrane.</span><span class="sxs-lookup"><span data-stu-id="d3426-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
