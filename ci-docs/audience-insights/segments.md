---
title: Segmentų kūrimas ir valdymas
description: Kurkite klientų segmentus, kad jie būtų sugrupuoti pagal įvairius atributus.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270366"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="64350-103">Segmentų kūrimas ir valdymas</span><span class="sxs-lookup"><span data-stu-id="64350-103">Create and manage segments</span></span>

<span data-ttu-id="64350-104">Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes.</span><span class="sxs-lookup"><span data-stu-id="64350-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="64350-105">Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.</span><span class="sxs-lookup"><span data-stu-id="64350-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="64350-106">Galite apibrėžti sudėtinius filtrus kliento profilio objektui ir su juo susijusiams objektams.</span><span class="sxs-lookup"><span data-stu-id="64350-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="64350-107">Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus.</span><span class="sxs-lookup"><span data-stu-id="64350-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="64350-108">Kai kurie [paslaugų apribojimai](service-limits.md) yra taikomi.</span><span class="sxs-lookup"><span data-stu-id="64350-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="64350-109">Nebent nurodyta kitaip, visi segmentai yra **„Dynamic“ segmentai**, kurie yra paleidžiami iš naujo pasikartojančiame grafike.</span><span class="sxs-lookup"><span data-stu-id="64350-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="64350-110">Tolesnis pavyzdys rodo segmento pajėgumą.</span><span class="sxs-lookup"><span data-stu-id="64350-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="64350-111">Nustatėme klientų, kurie per paskutines 90 dienų užsisakė prekių bent už 500 $ *ir* kurie atliko klientų aptarnavimo skambutį, kuris buvo perskirtas, segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64350-112">![Sudėtinės grupės](media/segmentation-group1-2.png "Sudėtinės grupės")</span><span class="sxs-lookup"><span data-stu-id="64350-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="64350-113">Sukurkite naują segmentą</span><span class="sxs-lookup"><span data-stu-id="64350-113">Create a new segment</span></span>

<span data-ttu-id="64350-114">Segmentai yra valdomi **Segmentų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="64350-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="64350-115">Publikos įžvalgose, eikite į **Segmentai** puslapį.</span><span class="sxs-lookup"><span data-stu-id="64350-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="64350-116">Pasirinkite **Naujas** > **Tuščias segmentas**.</span><span class="sxs-lookup"><span data-stu-id="64350-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="64350-117">Srityje **Naujas segmentas** pasirinkite segmento tipą ir nurodykite **pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="64350-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="64350-118">Galite pasirinktinai nurodyti rodomą pavadinimą ir aprašą, padedantį identifikuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="64350-119">Norėdami atidaryti **segmentų kūrimo priemonės** puslapį, kuriame apibrėžėte grupė, pasirinkite **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="64350-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="64350-120">Grupė yra klientų rinkinys.</span><span class="sxs-lookup"><span data-stu-id="64350-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="64350-121">Pasirinkite objektą, kuriame yra atributas, pagal kurį norite segmentuoti.</span><span class="sxs-lookup"><span data-stu-id="64350-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="64350-122">Pasirinkite atributą, pagal kurį norite segmentuoti.</span><span class="sxs-lookup"><span data-stu-id="64350-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="64350-123">Šis atributas gali turėti vieną iš keturių reikšmių tipų: skaičiaus, eilutės, datos arba Bulio.</span><span class="sxs-lookup"><span data-stu-id="64350-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="64350-124">Pasirinkite operatorių ir pasirinkto atributo reikšmę.</span><span class="sxs-lookup"><span data-stu-id="64350-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64350-125">![Pasirinktinis grupės filtras](media/customer-group-numbers.png "Klientų grupės filtras")</span><span class="sxs-lookup"><span data-stu-id="64350-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="64350-126">Numeris</span><span class="sxs-lookup"><span data-stu-id="64350-126">Number</span></span> |<span data-ttu-id="64350-127">Apibrėžtis</span><span class="sxs-lookup"><span data-stu-id="64350-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="64350-128">1</span><span class="sxs-lookup"><span data-stu-id="64350-128">1</span></span>     |<span data-ttu-id="64350-129">Entity</span><span class="sxs-lookup"><span data-stu-id="64350-129">Entity</span></span>          |
   |<span data-ttu-id="64350-130">2</span><span class="sxs-lookup"><span data-stu-id="64350-130">2</span></span>     |<span data-ttu-id="64350-131">Atributas</span><span class="sxs-lookup"><span data-stu-id="64350-131">Attribute</span></span>          |
   |<span data-ttu-id="64350-132">3</span><span class="sxs-lookup"><span data-stu-id="64350-132">3</span></span>    |<span data-ttu-id="64350-133">Operatorius</span><span class="sxs-lookup"><span data-stu-id="64350-133">Operator</span></span>         |
   |<span data-ttu-id="64350-134">4</span><span class="sxs-lookup"><span data-stu-id="64350-134">4</span></span>    |<span data-ttu-id="64350-135">Vertė</span><span class="sxs-lookup"><span data-stu-id="64350-135">Value</span></span>         |

8. <span data-ttu-id="64350-136">Jei objektas yra sujungtas su sujungtu kliento objektu naudojant [ryšius](relationships.md), turite apibrėžti ryšio kelią, kad sukurtumėte tinkamą segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="64350-137">Įtraukite objektus iš ryšio kelio, kol išplečiamajame sąraše galėsite pasirinkti objektą **Customer : CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="64350-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="64350-138">Tada prie kiekvienos sąlygos pasirinkite **Visi įrašai**.</span><span class="sxs-lookup"><span data-stu-id="64350-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64350-139">![Ryšių kelias kuriant segmentą](media/segments-multiple-relationships.png "Ryšių kelias kuriant segmentą")</span><span class="sxs-lookup"><span data-stu-id="64350-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="64350-140">Pasirinkite **Įrašyti**, kad įrašytumėte segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="64350-141">Jūsų segmentas bus įrašytas ir apdorojamas, jei visi reikalavimai bus patvirtinti.</span><span class="sxs-lookup"><span data-stu-id="64350-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="64350-142">Kitu atveju jis bus Išsaugota kaip juodraštis.</span><span class="sxs-lookup"><span data-stu-id="64350-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="64350-143">Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="64350-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="64350-144">Esamų segmentų tvarkymas</span><span class="sxs-lookup"><span data-stu-id="64350-144">Manage existing segments</span></span>

<span data-ttu-id="64350-145">Puslapyje **„Segmentai“**, galite peržiūrėti visus įrašytus segmentus ir juos valdyti.</span><span class="sxs-lookup"><span data-stu-id="64350-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="64350-146">Kiekvieną segmentą atitinka eilutė, kurioje pateikta papildoma informacija apie segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="64350-147">Galite rikiuoti segmentus stulpelyje spustelėdami stulpelio antraštę.</span><span class="sxs-lookup"><span data-stu-id="64350-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="64350-148">Norėdami filtruoti segmentus, naudokite viršutiniame dešiniajame kampe esantį lauką **Ieška**.</span><span class="sxs-lookup"><span data-stu-id="64350-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64350-149">![Esamo segmento valdymo parinktys](media/segments-selected-segment.png "Esamo segmento valdymo parinktys")</span><span class="sxs-lookup"><span data-stu-id="64350-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="64350-150">Pasirinkus segmentą pasiekiami toliau nurodyti veiksmai.</span><span class="sxs-lookup"><span data-stu-id="64350-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="64350-151">**Peržiūrėti** segmento išsamią informaciją, įskaitant narių skaičių, tendencijas ir segmento narių peržiūrą.</span><span class="sxs-lookup"><span data-stu-id="64350-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="64350-152">**Redaguoti** segmentą ir pakeisti jo ypatybes.</span><span class="sxs-lookup"><span data-stu-id="64350-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="64350-153">**Atnaujinti** segmentą, kad būtų įtraukti naujausi duomenys.</span><span class="sxs-lookup"><span data-stu-id="64350-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="64350-154">**Aktyvinti** arba **Išjungti** segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="64350-155">Segmentai turi dvi galimas būsenas – aktyvią arba neaktyvią.</span><span class="sxs-lookup"><span data-stu-id="64350-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="64350-156">Šios būsenos yra naudingos redaguojant segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="64350-157">Neaktyvių segmentų aprašas yra, bet į jį dar neįtraukta klientų.</span><span class="sxs-lookup"><span data-stu-id="64350-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="64350-158">Suaktyvinus segmentą, jo būsena keičiasi iš neaktyvios į aktyvią, ir jis pradeda ieškoti klientų, atitinkančių segmento aprašą.</span><span class="sxs-lookup"><span data-stu-id="64350-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="64350-159">Jei [suplanuotas atnaujinimas](system.md#schedule-tab) yra sukonfigūruotas, neaktyvių segmentų **Būsena** nurodoma kaip **Praleista** – tai reiškia, kad net nebuvo bandyta atnaujinti.</span><span class="sxs-lookup"><span data-stu-id="64350-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="64350-160">Suaktyvinus neaktyvų segmentą, jis bus atnaujintas ir įtrauktas į suplanuotus atnaujinimus.</span><span class="sxs-lookup"><span data-stu-id="64350-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="64350-161">Taip pat galite naudoti funkciją **Planuoti vėliau**, esančią iškleidžiamajame meniu **Aktyvinti / išjungti**, kad nurodytumėte būsimą datą ir laiką, kada reikia aktyvinti ir išjungti tam tikrą segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="64350-162">**Pervardyti** segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-162">**Rename** the segment.</span></span>
- <span data-ttu-id="64350-163">**Atsisiųsti** narių sąrašą kaip .CSV failą.</span><span class="sxs-lookup"><span data-stu-id="64350-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="64350-164">Parinktis **Įtraukti į** siunčia klientų ID sąrašą į segmentą apdoroti kitoje programoje.</span><span class="sxs-lookup"><span data-stu-id="64350-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="64350-165">**Naikinti** segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="64350-166">Segmentų atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="64350-166">Refresh segments</span></span>

<span data-ttu-id="64350-167">Visus segmentus galite atnaujinti vienu metu pažymėdami **Atnaujinti viską** puslapyje **Segmentai** arba galite atnaujinti vieną ar kelis segmentus, kai juos pažymite ir parinktyse pasirenkate **Atnaujinti**.</span><span class="sxs-lookup"><span data-stu-id="64350-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="64350-168">Taip pat galite sukonfigūruoti pasikartojantį atnaujinimą dalyje **Administravimas** > **Sistemas** > **Planuoti**.</span><span class="sxs-lookup"><span data-stu-id="64350-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="64350-169">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="64350-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="64350-170">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="64350-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="64350-171">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="64350-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="64350-172">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="64350-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="64350-173">Segmentų atsisiuntimas ir eksportavimas</span><span class="sxs-lookup"><span data-stu-id="64350-173">Download and export segments</span></span>

<span data-ttu-id="64350-174">Galite atsisiųsti segmentus į CSV failą arba juos eksportuoti į „Dynamics 365 Sales“.</span><span class="sxs-lookup"><span data-stu-id="64350-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="64350-175">Segmentų atsisiuntimas į CSV failą</span><span class="sxs-lookup"><span data-stu-id="64350-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="64350-176">Publikos įžvalgose, eikite į **Segmentai** puslapį.</span><span class="sxs-lookup"><span data-stu-id="64350-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="64350-177">Konkretaus segmento plytelėje spustelėkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="64350-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="64350-178">Veiksmų išplečiamajame sąraše pasirinkite **Atsisiųsti kaip CSV**.</span><span class="sxs-lookup"><span data-stu-id="64350-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="64350-179">Segmentų eksportavimas į „Dynamics 365 Sales“</span><span class="sxs-lookup"><span data-stu-id="64350-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="64350-180">Prieš eksportuojant segmentus į „Dynamics 365 Sales“ administratorius turi [sukurti „Dynamics 365 Sales“ eksportavimo paskirties vietą](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="64350-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="64350-181">Publikos įžvalgose, eikite į **Segmentai** puslapį.</span><span class="sxs-lookup"><span data-stu-id="64350-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="64350-182">Konkretaus segmento plytelėje spustelėkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="64350-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="64350-183">Spustelėkite **Įtraukti į** veiksmų išplečiamajame sąraše ir pasirinkite eksportavimo paskirties vietą, į kurią norite siųsti duomenis.</span><span class="sxs-lookup"><span data-stu-id="64350-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="64350-184">Segmentų juodraščio režimas</span><span class="sxs-lookup"><span data-stu-id="64350-184">Draft mode for segments</span></span>

<span data-ttu-id="64350-185">Jei ne visi segmento apdorojimo reikalavimai įvykdyti, galite įrašyti segmentą kaip juodraštį ir pasiekti jį puslapyje **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="64350-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="64350-186">Jis bus įrašytas kaip neaktyvus segmentas ir jo negalima aktyvinti tol, kol jis nebus tinkamas.</span><span class="sxs-lookup"><span data-stu-id="64350-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="64350-187">Įtraukti daugiau sąlygų į grupę</span><span class="sxs-lookup"><span data-stu-id="64350-187">Add more conditions to a group</span></span>

<span data-ttu-id="64350-188">Norėdami įtraukti daugiau sąlygų į grupę, galite naudoti du loginius operatorius:</span><span class="sxs-lookup"><span data-stu-id="64350-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="64350-189">Operatorius **IR**: abi sąlygos turi būti įvykdytos kaip segmentavimo proceso dalis.</span><span class="sxs-lookup"><span data-stu-id="64350-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="64350-190">Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.</span><span class="sxs-lookup"><span data-stu-id="64350-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="64350-191">Operatorius **ARBA**: viena iš sąlygų turi būti įvykdyta kaip segmentavimo proceso dalis.</span><span class="sxs-lookup"><span data-stu-id="64350-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="64350-192">Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.</span><span class="sxs-lookup"><span data-stu-id="64350-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64350-193">![Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta](media/segmentation-either-condition.png "Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta")</span><span class="sxs-lookup"><span data-stu-id="64350-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="64350-194">Šiuo metu galima įtraukti operatorių **Arba** į operatorių **Ir**, o ne atvirkščiai.</span><span class="sxs-lookup"><span data-stu-id="64350-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="64350-195">Kelių grupių derinimas</span><span class="sxs-lookup"><span data-stu-id="64350-195">Combine multiple groups</span></span>

<span data-ttu-id="64350-196">Kiekviena grupė sukuria konkretų klientų rinkinį.</span><span class="sxs-lookup"><span data-stu-id="64350-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="64350-197">Galite jungti šias grupes, kad įtrauktumėte klientus, reikalingus jūsų verslo atvejui.</span><span class="sxs-lookup"><span data-stu-id="64350-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="64350-198">Publikos įžvalgose eikite į **Segmentų** puslapį ir pasirinkite segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="64350-199">Pažymėkite **Įtraukti grupę**.</span><span class="sxs-lookup"><span data-stu-id="64350-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64350-200">![Klientų grupės grupės įtraukimas](media/customer-group-add-group.png "Klientų grupės grupės įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="64350-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="64350-201">Pasirinkite vieną iš šių rinkinio operatorių: **Sujungimas**, **Susikirtimas** arba **Išskyrus**.</span><span class="sxs-lookup"><span data-stu-id="64350-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64350-202">![Klientų grupės sujungimo įtraukimas](media/customer-group-union.png "Klientų grupės sujungimo įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="64350-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="64350-203">Pasirinkite rinkinio operatorių, kad apibrėžtumėte naują grupę.</span><span class="sxs-lookup"><span data-stu-id="64350-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="64350-204">Įrašykite skirtingas grupes tam, kad nustatytumėte, kokie duomenys bus laikomi:</span><span class="sxs-lookup"><span data-stu-id="64350-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="64350-205">**Sujungimas** sujungia dvi grupes.</span><span class="sxs-lookup"><span data-stu-id="64350-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="64350-206">**Susikirtimas** persidengia su dviem grupėmis.</span><span class="sxs-lookup"><span data-stu-id="64350-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="64350-207">Tik duomenys, kurie *yra bendri* abiem grupėms yra laikomi vieningoje grupėje.</span><span class="sxs-lookup"><span data-stu-id="64350-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="64350-208">**Išskyrus** sujungia dvi grupes.</span><span class="sxs-lookup"><span data-stu-id="64350-208">**Except** combines the two groups.</span></span> <span data-ttu-id="64350-209">Laikomi tik duomenys, kurie yra A grupėje ir *nėra bendri* duomenims grupėje B.</span><span class="sxs-lookup"><span data-stu-id="64350-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="64350-210">Apdorojimo retrospektyvos ir segmento narių peržiūra</span><span class="sxs-lookup"><span data-stu-id="64350-210">View processing history and segment members</span></span>

<span data-ttu-id="64350-211">Konsoliduotus duomenis apie segmentą galite peržiūrėti peržiūrėdami išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="64350-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="64350-212">Puslapyje **Segmentai** pažymėkite segmentą, kurį norite peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="64350-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="64350-213">Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius.</span><span class="sxs-lookup"><span data-stu-id="64350-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="64350-214">Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data.</span><span class="sxs-lookup"><span data-stu-id="64350-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="64350-215">Galite atnaujinti vizualizacijos laiko tarpą.</span><span class="sxs-lookup"><span data-stu-id="64350-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64350-216">![Segmento laiko diapazonas](media/segment-time-range.png "Segmento laiko diapazonas")</span><span class="sxs-lookup"><span data-stu-id="64350-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="64350-217">Apatinėje dalyje yra segmento narių sąrašas.</span><span class="sxs-lookup"><span data-stu-id="64350-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="64350-218">Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.</span><span class="sxs-lookup"><span data-stu-id="64350-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="64350-219">Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia.</span><span class="sxs-lookup"><span data-stu-id="64350-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="64350-220">Norėdami peržiūrėti visu sutampančius įrašus, turite [eksportuoti segmentą](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="64350-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="64350-221">Spartieji segmentai</span><span class="sxs-lookup"><span data-stu-id="64350-221">Quick segments</span></span>

<span data-ttu-id="64350-222">Kartu su segmentų kūrimo įrankiu, yra kitas kelias sukurti segmentus.</span><span class="sxs-lookup"><span data-stu-id="64350-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="64350-223">Naudodami sparčiuosius segmentus galite greitai kurti paprastus segmentus su vienu operatoriumi su tiesioginėmis įžvalgomis.</span><span class="sxs-lookup"><span data-stu-id="64350-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="64350-224">Puslapyje **Segmentai** pasirinkite **Naujas** > **Greitai kurti naudojant**.</span><span class="sxs-lookup"><span data-stu-id="64350-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="64350-225">Pažymėkite parinktį **Profiliai** ir sukurkite segmentą, pagrįstą vieningu kliento objektu.</span><span class="sxs-lookup"><span data-stu-id="64350-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="64350-226">Pažymėkite parinktį **Priemonės**, kad sukurtumėte segmentą kiekvienam kliento atributo priemonių tipam, kuriuos anksčiau sukūrėte puslapyje **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="64350-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="64350-227">Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.</span><span class="sxs-lookup"><span data-stu-id="64350-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="64350-228">Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**.</span><span class="sxs-lookup"><span data-stu-id="64350-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="64350-229">Sistema pateiks keletą papildomų įžvalgų, kurios padės kurti geresnius klientų segmentus.</span><span class="sxs-lookup"><span data-stu-id="64350-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="64350-230">Pagal kategorinius laukus parodysime 10 geriausių klientų skaičių.</span><span class="sxs-lookup"><span data-stu-id="64350-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="64350-231">Pasirinkite **Reikšmė** ir pažymėkie **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="64350-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="64350-232">Jei yra skaičiaus atributas, sistema parodys, kokią atributo reikšmę turi kiekvienas kliento procentilis.</span><span class="sxs-lookup"><span data-stu-id="64350-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="64350-233">Pasirinkite **operatorių** ir **reikšmę**, tada pažymėkte **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="64350-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="64350-234">Sistema parodys **numatomą segmento dydį**.</span><span class="sxs-lookup"><span data-stu-id="64350-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="64350-235">Galite pasirinkti, ar generuoti apibrėžtą segmentą arba iš naujo jį peržiūrėti ir gauti kitą segmento dydį.</span><span class="sxs-lookup"><span data-stu-id="64350-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64350-236">![Sparčiojo segmento pavadinimas ir įvertinimas](media/quick-segment-name.png "Sparčiojo segmento pavadinimas ir įvertinimas")</span><span class="sxs-lookup"><span data-stu-id="64350-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="64350-237">Įveskite segmento **Pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="64350-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="64350-238">Pasrinktinai įveskite **rodomą pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="64350-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="64350-239">Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="64350-240">Ka segmento apdorojimas baigtas, jį galite peržiūrėti kaip bet kurį kitą sukurtą segmentą.</span><span class="sxs-lookup"><span data-stu-id="64350-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="64350-241">Toliau nurodytais atvejais patariama naudoti segmentų kūrimo priemonę, o ne rekomenduojamas segmentų galimybes:</span><span class="sxs-lookup"><span data-stu-id="64350-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="64350-242">Segmentų kūrimas naudojant filtrus laukams, skirstomiems į kategorijas, kai operatorius skiriasi nuo operatoriaus **Yra**</span><span class="sxs-lookup"><span data-stu-id="64350-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="64350-243">Segmentų kūrimas naudojant filtrus skaičiaus laukams, kai operatorius skiriasi nuo operatorių **Tarp**, **Didesnis nei** ir **Mažesnis nei**</span><span class="sxs-lookup"><span data-stu-id="64350-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="64350-244">Segmentų su datos tipo laukų filtrais kūrimas</span><span class="sxs-lookup"><span data-stu-id="64350-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="64350-245">Kiti veiksmai</span><span class="sxs-lookup"><span data-stu-id="64350-245">Next steps</span></span>

<span data-ttu-id="64350-246">[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [kliento kortele](customer-card-add-in.md) bei [jungtimis](export-power-bi.md), kad gautumėte įžvalgų apie kliento lygį.</span><span class="sxs-lookup"><span data-stu-id="64350-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]