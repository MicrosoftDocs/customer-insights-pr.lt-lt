---
title: Segmentų kūrimas ir valdymas
description: Kurkite klientų segmentus, kad jie būtų sugrupuoti pagal įvairius atributus.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597063"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="b54d0-103">Segmentų kūrimas ir valdymas</span><span class="sxs-lookup"><span data-stu-id="b54d0-103">Create and manage segments</span></span>

<span data-ttu-id="b54d0-104">Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes.</span><span class="sxs-lookup"><span data-stu-id="b54d0-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="b54d0-105">Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.</span><span class="sxs-lookup"><span data-stu-id="b54d0-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="b54d0-106">Galite apibrėžti sudėtinius filtrus kliento profilio objektui ir su juo susijusiems objektams.</span><span class="sxs-lookup"><span data-stu-id="b54d0-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="b54d0-107">Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus.</span><span class="sxs-lookup"><span data-stu-id="b54d0-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="b54d0-108">Kai kurie [paslaugų apribojimai](service-limits.md) yra taikomi.</span><span class="sxs-lookup"><span data-stu-id="b54d0-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="b54d0-109">Nebent nurodyta kitaip, visi segmentai yra **„Dynamic“ segmentai**, kurie yra paleidžiami iš naujo pasikartojančiame grafike.</span><span class="sxs-lookup"><span data-stu-id="b54d0-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="b54d0-110">Tolesnis pavyzdys rodo segmento pajėgumą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="b54d0-111">Nustatėme klientų, kurie per paskutines 90 dienų užsisakė prekių bent už 500 $ *ir* kurie atliko klientų aptarnavimo skambutį, kuris buvo perskirtas, segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b54d0-112">![Sudėtinės grupės](media/segmentation-group1-2.png "Sudėtinės grupės")</span><span class="sxs-lookup"><span data-stu-id="b54d0-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="b54d0-113">Sukurkite naują segmentą</span><span class="sxs-lookup"><span data-stu-id="b54d0-113">Create a new segment</span></span>

<span data-ttu-id="b54d0-114">Segmentai yra valdomi **Segmentų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="b54d0-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="b54d0-115">Publikos įžvalgose, eikite į **Segmentai** puslapį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="b54d0-116">Pasirinkite **Naujas** > **Tuščias segmentas**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="b54d0-117">Srityje **Naujas segmentas** pasirinkite segmento tipą ir nurodykite **pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="b54d0-118">Galite pasirinktinai nurodyti rodomą pavadinimą ir aprašą, padedantį identifikuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="b54d0-119">Norėdami atidaryti **segmentų kūrimo priemonės** puslapį, kuriame apibrėžėte grupė, pasirinkite **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="b54d0-120">Grupė yra klientų rinkinys.</span><span class="sxs-lookup"><span data-stu-id="b54d0-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="b54d0-121">Pasirinkite objektą, kuriame yra atributas, pagal kurį norite segmentuoti.</span><span class="sxs-lookup"><span data-stu-id="b54d0-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="b54d0-122">Pasirinkite atributą, pagal kurį norite segmentuoti.</span><span class="sxs-lookup"><span data-stu-id="b54d0-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="b54d0-123">Šis atributas gali turėti vieną iš keturių reikšmių tipų: skaičiaus, eilutės, datos arba Bulio.</span><span class="sxs-lookup"><span data-stu-id="b54d0-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="b54d0-124">Pasirinkite operatorių ir pasirinkto atributo reikšmę.</span><span class="sxs-lookup"><span data-stu-id="b54d0-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54d0-125">![Pasirinktinis grupės filtras](media/customer-group-numbers.png "Klientų grupės filtras")</span><span class="sxs-lookup"><span data-stu-id="b54d0-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="b54d0-126">Numeris</span><span class="sxs-lookup"><span data-stu-id="b54d0-126">Number</span></span> |<span data-ttu-id="b54d0-127">Apibrėžtis</span><span class="sxs-lookup"><span data-stu-id="b54d0-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="b54d0-128">1</span><span class="sxs-lookup"><span data-stu-id="b54d0-128">1</span></span>     |<span data-ttu-id="b54d0-129">Entity</span><span class="sxs-lookup"><span data-stu-id="b54d0-129">Entity</span></span>          |
   |<span data-ttu-id="b54d0-130">2</span><span class="sxs-lookup"><span data-stu-id="b54d0-130">2</span></span>     |<span data-ttu-id="b54d0-131">Atributas</span><span class="sxs-lookup"><span data-stu-id="b54d0-131">Attribute</span></span>          |
   |<span data-ttu-id="b54d0-132">3</span><span class="sxs-lookup"><span data-stu-id="b54d0-132">3</span></span>    |<span data-ttu-id="b54d0-133">Operatorius</span><span class="sxs-lookup"><span data-stu-id="b54d0-133">Operator</span></span>         |
   |<span data-ttu-id="b54d0-134">4</span><span class="sxs-lookup"><span data-stu-id="b54d0-134">4</span></span>    |<span data-ttu-id="b54d0-135">Vertė</span><span class="sxs-lookup"><span data-stu-id="b54d0-135">Value</span></span>         |

8. <span data-ttu-id="b54d0-136">Jei objektas yra sujungtas su sujungtu kliento objektu naudojant [ryšius](relationships.md), turite apibrėžti ryšio kelią, kad sukurtumėte tinkamą segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="b54d0-137">Įtraukite objektus iš ryšio kelio, kol išplečiamajame sąraše galėsite pasirinkti objektą **Customer : CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="b54d0-138">Tada prie kiekvienos sąlygos pasirinkite **Visi įrašai**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54d0-139">![Ryšių kelias kuriant segmentą](media/segments-multiple-relationships.png "Ryšių kelias kuriant segmentą")</span><span class="sxs-lookup"><span data-stu-id="b54d0-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="b54d0-140">Pagal numatytuosius nustatymus, segmentai generuoja išvesties objektą, kuriame yra visi klientų profilių atributai, atitinkantys nustatytus filtrus.</span><span class="sxs-lookup"><span data-stu-id="b54d0-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="b54d0-141">Jei segmentas pagrįstas kitais objektais nei *Kliento* objektas, į išvesties objektą galite įtraukti daugiau atributų iš šių objektų.</span><span class="sxs-lookup"><span data-stu-id="b54d0-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="b54d0-142">Pažymėkite **Projekto atributai**, kad pasirinktumėte atributus, kurie bus pridėti prie išvesties objekto.</span><span class="sxs-lookup"><span data-stu-id="b54d0-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="b54d0-143">Pavyzdys: segmentas A yra pagrįstas objektu, kuriame yra kliento veiklos duomenų, susijusių su *Kliento* objektu.</span><span class="sxs-lookup"><span data-stu-id="b54d0-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="b54d0-144">Segmentas ieško visų klientų, skambinusių pagalbos tarnybai per pastarąsias 60 dienų.</span><span class="sxs-lookup"><span data-stu-id="b54d0-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="b54d0-145">Galite pasirinkti pridėti skambučio trukmę ir skambučių skaičių prie visų sutampančių išvesties objekto kliento įrašų.</span><span class="sxs-lookup"><span data-stu-id="b54d0-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="b54d0-146">Ši informacija gali būti naudinga siunčiant el. laišką su naudingomis nuorodomis į internetinius žinyno straipsnius ir DUK dažnai skambinusiems klientams.</span><span class="sxs-lookup"><span data-stu-id="b54d0-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="b54d0-147">Pasirinkite **Įrašyti**, kad įrašytumėte segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="b54d0-148">Jūsų segmentas bus įrašytas ir apdorojamas, jei visi reikalavimai bus patvirtinti.</span><span class="sxs-lookup"><span data-stu-id="b54d0-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="b54d0-149">Kitu atveju jis bus Išsaugota kaip juodraštis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="b54d0-150">Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="b54d0-151">Esamų segmentų tvarkymas</span><span class="sxs-lookup"><span data-stu-id="b54d0-151">Manage existing segments</span></span>

<span data-ttu-id="b54d0-152">Puslapyje **„Segmentai“**, galite peržiūrėti visus įrašytus segmentus ir juos valdyti.</span><span class="sxs-lookup"><span data-stu-id="b54d0-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="b54d0-153">Kiekvieną segmentą atitinka eilutė, kurioje pateikta papildoma informacija apie segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="b54d0-154">Galite rikiuoti segmentus stulpelyje spustelėdami stulpelio antraštę.</span><span class="sxs-lookup"><span data-stu-id="b54d0-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="b54d0-155">Norėdami filtruoti segmentus, naudokite viršutiniame dešiniajame kampe esantį lauką **Ieška**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b54d0-156">![Esamo segmento valdymo parinktys](media/segments-selected-segment.png "Esamo segmento valdymo parinktys")</span><span class="sxs-lookup"><span data-stu-id="b54d0-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="b54d0-157">Pasirinkus segmentą pasiekiami toliau nurodyti veiksmai.</span><span class="sxs-lookup"><span data-stu-id="b54d0-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="b54d0-158">**Peržiūrėti** segmento išsamią informaciją, įskaitant narių skaičių, tendencijas ir segmento narių peržiūrą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="b54d0-159">**Redaguoti** segmentą ir pakeisti jo ypatybes.</span><span class="sxs-lookup"><span data-stu-id="b54d0-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="b54d0-160">**Kurti dublikatą** segmentui.</span><span class="sxs-lookup"><span data-stu-id="b54d0-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="b54d0-161">Galite iš karto pasirinkti redaguoti jo ypatybes arba tiesiog įrašyti dublikatą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="b54d0-162">**Atnaujinti** segmentą, kad būtų įtraukti naujausi duomenys.</span><span class="sxs-lookup"><span data-stu-id="b54d0-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="b54d0-163">**Aktyvinti** arba **Išjungti** segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="b54d0-164">Segmentai turi dvi galimas būsenas – aktyvią arba neaktyvią.</span><span class="sxs-lookup"><span data-stu-id="b54d0-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="b54d0-165">Šios būsenos yra naudingos redaguojant segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="b54d0-166">Neaktyvių segmentų aprašas yra, bet į jį dar neįtraukta klientų.</span><span class="sxs-lookup"><span data-stu-id="b54d0-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="b54d0-167">Suaktyvinus segmentą, jo būsena keičiasi iš neaktyvios į aktyvią, ir jis pradeda ieškoti klientų, atitinkančių segmento aprašą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="b54d0-168">Jei [suplanuotas atnaujinimas](system.md#schedule-tab) yra sukonfigūruotas, neaktyvių segmentų **Būsena** nurodoma kaip **Praleista** – tai reiškia, kad net nebuvo bandyta atnaujinti.</span><span class="sxs-lookup"><span data-stu-id="b54d0-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="b54d0-169">Suaktyvinus neaktyvų segmentą, jis bus atnaujintas ir įtrauktas į suplanuotus atnaujinimus.</span><span class="sxs-lookup"><span data-stu-id="b54d0-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="b54d0-170">Taip pat galite naudoti funkciją **Planuoti vėliau**, esančią iškleidžiamajame meniu **Aktyvinti / išjungti**, kad nurodytumėte būsimą datą ir laiką, kada reikia aktyvinti ir išjungti tam tikrą segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="b54d0-171">**Pervardyti** segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-171">**Rename** the segment.</span></span>
- <span data-ttu-id="b54d0-172">**Atsisiųsti** narių sąrašą kaip .CSV failą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="b54d0-173">Parinktis **Įtraukti į** siunčia klientų ID sąrašą į segmentą apdoroti kitoje programoje.</span><span class="sxs-lookup"><span data-stu-id="b54d0-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="b54d0-174">**Naikinti** segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="b54d0-175">Segmentų atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="b54d0-175">Refresh segments</span></span>

<span data-ttu-id="b54d0-176">Visus segmentus galite atnaujinti vienu metu pažymėdami **Atnaujinti viską** puslapyje **Segmentai** arba galite atnaujinti vieną ar kelis segmentus, kai juos pažymite ir parinktyse pasirenkate **Atnaujinti**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="b54d0-177">Taip pat galite sukonfigūruoti pasikartojantį atnaujinimą dalyje **Administravimas** > **Sistemas** > **Planuoti**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="b54d0-178">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="b54d0-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b54d0-179">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b54d0-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b54d0-180">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b54d0-181">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="b54d0-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="b54d0-182">Segmentų atsisiuntimas ir eksportavimas</span><span class="sxs-lookup"><span data-stu-id="b54d0-182">Download and export segments</span></span>

<span data-ttu-id="b54d0-183">Galite atsisiųsti segmentus į CSV failą arba juos eksportuoti į „Dynamics 365 Sales“.</span><span class="sxs-lookup"><span data-stu-id="b54d0-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="b54d0-184">Segmentų atsisiuntimas į CSV failą</span><span class="sxs-lookup"><span data-stu-id="b54d0-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="b54d0-185">Publikos įžvalgose, eikite į **Segmentai** puslapį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b54d0-186">Konkretaus segmento plytelėje spustelėkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b54d0-187">Veiksmų išplečiamajame sąraše pasirinkite **Atsisiųsti kaip CSV**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="b54d0-188">Segmentų eksportavimas į „Dynamics 365 Sales“</span><span class="sxs-lookup"><span data-stu-id="b54d0-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="b54d0-189">Prieš eksportuojant segmentus į „Dynamics 365 Sales“ administratorius turi [sukurti „Dynamics 365 Sales“ eksportavimo paskirties vietą](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b54d0-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="b54d0-190">Publikos įžvalgose, eikite į **Segmentai** puslapį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="b54d0-191">Konkretaus segmento plytelėje spustelėkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="b54d0-192">Spustelėkite **Įtraukti į** veiksmų išplečiamajame sąraše ir pasirinkite eksportavimo paskirties vietą, į kurią norite siųsti duomenis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="b54d0-193">Segmentų juodraščio režimas</span><span class="sxs-lookup"><span data-stu-id="b54d0-193">Draft mode for segments</span></span>

<span data-ttu-id="b54d0-194">Jei ne visi segmento apdorojimo reikalavimai įvykdyti, galite įrašyti segmentą kaip juodraštį ir pasiekti jį puslapyje **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="b54d0-195">Jis bus įrašytas kaip neaktyvus segmentas ir jo negalima aktyvinti tol, kol jis nebus tinkamas.</span><span class="sxs-lookup"><span data-stu-id="b54d0-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="b54d0-196">Įtraukti daugiau sąlygų į grupę</span><span class="sxs-lookup"><span data-stu-id="b54d0-196">Add more conditions to a group</span></span>

<span data-ttu-id="b54d0-197">Norėdami įtraukti daugiau sąlygų į grupę, galite naudoti du loginius operatorius:</span><span class="sxs-lookup"><span data-stu-id="b54d0-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="b54d0-198">Operatorius **IR**: abi sąlygos turi būti įvykdytos kaip segmentavimo proceso dalis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="b54d0-199">Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.</span><span class="sxs-lookup"><span data-stu-id="b54d0-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="b54d0-200">Operatorius **ARBA**: viena iš sąlygų turi būti įvykdyta kaip segmentavimo proceso dalis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="b54d0-201">Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.</span><span class="sxs-lookup"><span data-stu-id="b54d0-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54d0-202">![Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta](media/segmentation-either-condition.png "Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta")</span><span class="sxs-lookup"><span data-stu-id="b54d0-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="b54d0-203">Šiuo metu galima įtraukti operatorių **Arba** į operatorių **Ir**, o ne atvirkščiai.</span><span class="sxs-lookup"><span data-stu-id="b54d0-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="b54d0-204">Kelių grupių derinimas</span><span class="sxs-lookup"><span data-stu-id="b54d0-204">Combine multiple groups</span></span>

<span data-ttu-id="b54d0-205">Kiekviena grupė sukuria konkretų klientų rinkinį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="b54d0-206">Galite jungti šias grupes, kad įtrauktumėte klientus, reikalingus jūsų verslo atvejui.</span><span class="sxs-lookup"><span data-stu-id="b54d0-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="b54d0-207">Publikos įžvalgose eikite į **Segmentų** puslapį ir pasirinkite segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="b54d0-208">Pažymėkite **Įtraukti grupę**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54d0-209">![Klientų grupės grupės įtraukimas](media/customer-group-add-group.png "Klientų grupės grupės įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="b54d0-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="b54d0-210">Pasirinkite vieną iš šių rinkinio operatorių: **Sujungimas**, **Susikirtimas** arba **Išskyrus**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b54d0-211">![Klientų grupės sujungimo įtraukimas](media/customer-group-union.png "Klientų grupės sujungimo įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="b54d0-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="b54d0-212">Pasirinkite rinkinio operatorių, kad apibrėžtumėte naują grupę.</span><span class="sxs-lookup"><span data-stu-id="b54d0-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="b54d0-213">Įrašykite skirtingas grupes tam, kad nustatytumėte, kokie duomenys bus laikomi:</span><span class="sxs-lookup"><span data-stu-id="b54d0-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="b54d0-214">**Sujungimas** sujungia dvi grupes.</span><span class="sxs-lookup"><span data-stu-id="b54d0-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="b54d0-215">**Susikirtimas** persidengia su dviem grupėmis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="b54d0-216">Tik duomenys, kurie *yra bendri* abiem grupėms yra laikomi vieningoje grupėje.</span><span class="sxs-lookup"><span data-stu-id="b54d0-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="b54d0-217">**Išskyrus** sujungia dvi grupes.</span><span class="sxs-lookup"><span data-stu-id="b54d0-217">**Except** combines the two groups.</span></span> <span data-ttu-id="b54d0-218">Laikomi tik duomenys, kurie yra A grupėje ir *nėra bendri* duomenims grupėje B.</span><span class="sxs-lookup"><span data-stu-id="b54d0-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="b54d0-219">Apdorojimo retrospektyvos ir segmento narių peržiūra</span><span class="sxs-lookup"><span data-stu-id="b54d0-219">View processing history and segment members</span></span>

<span data-ttu-id="b54d0-220">Konsoliduotus duomenis apie segmentą galite peržiūrėti peržiūrėdami išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="b54d0-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="b54d0-221">Puslapyje **Segmentai** pažymėkite segmentą, kurį norite peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="b54d0-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="b54d0-222">Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius.</span><span class="sxs-lookup"><span data-stu-id="b54d0-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="b54d0-223">Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data.</span><span class="sxs-lookup"><span data-stu-id="b54d0-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="b54d0-224">Galite atnaujinti vizualizacijos laiko tarpą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b54d0-225">![Segmento laiko diapazonas](media/segment-time-range.png "Segmento laiko diapazonas")</span><span class="sxs-lookup"><span data-stu-id="b54d0-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="b54d0-226">Apatinėje dalyje yra segmento narių sąrašas.</span><span class="sxs-lookup"><span data-stu-id="b54d0-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="b54d0-227">Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.</span><span class="sxs-lookup"><span data-stu-id="b54d0-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="b54d0-228">Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia.</span><span class="sxs-lookup"><span data-stu-id="b54d0-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="b54d0-229">Norėdami peržiūrėti visu sutampančius įrašus, turite [eksportuoti segmentą](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b54d0-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="b54d0-230">Spartieji segmentai</span><span class="sxs-lookup"><span data-stu-id="b54d0-230">Quick segments</span></span>

<span data-ttu-id="b54d0-231">Kartu su segmentų kūrimo įrankiu, yra kitas kelias sukurti segmentus.</span><span class="sxs-lookup"><span data-stu-id="b54d0-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="b54d0-232">Naudodami sparčiuosius segmentus galite greitai kurti paprastus segmentus su vienu operatoriumi su tiesioginėmis įžvalgomis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="b54d0-233">Puslapyje **Segmentai** pasirinkite **Naujas** > **Greitai kurti naudojant**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="b54d0-234">Pažymėkite parinktį **Profiliai** ir sukurkite segmentą, pagrįstą vieningu kliento objektu.</span><span class="sxs-lookup"><span data-stu-id="b54d0-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="b54d0-235">Pažymėkite parinktį **Priemonės**, kad sukurtumėte segmentą kiekvienam kliento atributo priemonių tipams, kuriuos anksčiau sukūrėte puslapyje **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="b54d0-236">Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="b54d0-237">Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="b54d0-238">Sistema pateiks keletą papildomų įžvalgų, kurios padės kurti geresnius klientų segmentus.</span><span class="sxs-lookup"><span data-stu-id="b54d0-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="b54d0-239">Pagal kategorinius laukus parodysime 10 geriausių klientų skaičių.</span><span class="sxs-lookup"><span data-stu-id="b54d0-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="b54d0-240">Pasirinkite **Reikšmė** ir pažymėkite **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="b54d0-241">Jei yra skaičiaus atributas, sistema parodys, kokią atributo reikšmę turi kiekvienas kliento procentilis.</span><span class="sxs-lookup"><span data-stu-id="b54d0-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="b54d0-242">Pasirinkite **operatorių** ir **reikšmę**, tada pažymėktie **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="b54d0-243">Sistema parodys **numatomą segmento dydį**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="b54d0-244">Galite pasirinkti, ar generuoti apibrėžtą segmentą arba iš naujo jį peržiūrėti ir gauti kitą segmento dydį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b54d0-245">![Sparčiojo segmento pavadinimas ir įvertinimas](media/quick-segment-name.png "Sparčiojo segmento pavadinimas ir įvertinimas")</span><span class="sxs-lookup"><span data-stu-id="b54d0-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="b54d0-246">Įveskite segmento **Pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="b54d0-247">Pasirinktinai įveskite **rodomą pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="b54d0-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="b54d0-248">Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="b54d0-249">Kai segmento apdorojimas baigtas, jį galite peržiūrėti kaip bet kurį kitą sukurtą segmentą.</span><span class="sxs-lookup"><span data-stu-id="b54d0-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="b54d0-250">Toliau nurodytais atvejais patariama naudoti segmentų kūrimo priemonę, o ne rekomenduojamas segmentų galimybes:</span><span class="sxs-lookup"><span data-stu-id="b54d0-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="b54d0-251">Segmentų kūrimas naudojant filtrus laukams, skirstomiems į kategorijas, kai operatorius skiriasi nuo operatoriaus **Yra**</span><span class="sxs-lookup"><span data-stu-id="b54d0-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="b54d0-252">Segmentų kūrimas naudojant filtrus skaičiaus laukams, kai operatorius skiriasi nuo operatorių **Tarp**, **Didesnis nei** ir **Mažesnis nei**</span><span class="sxs-lookup"><span data-stu-id="b54d0-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="b54d0-253">Segmentų su datos tipo laukų filtrais kūrimas</span><span class="sxs-lookup"><span data-stu-id="b54d0-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="b54d0-254">Kiti veiksmai</span><span class="sxs-lookup"><span data-stu-id="b54d0-254">Next steps</span></span>

<span data-ttu-id="b54d0-255">[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [kliento kortele](customer-card-add-in.md) bei [jungtimis](export-power-bi.md), kad gautumėte įžvalgų apie kliento lygį.</span><span class="sxs-lookup"><span data-stu-id="b54d0-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]