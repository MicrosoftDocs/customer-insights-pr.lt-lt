---
title: Suliekite objektus duomenų suvienyjime
description: Suliekite objektus tam, kad sukurtumėte suvienytus kliento profilius.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597843"
---
# <a name="merge-entities"></a><span data-ttu-id="e8b80-103">Suliekite objektus</span><span class="sxs-lookup"><span data-stu-id="e8b80-103">Merge entities</span></span>

<span data-ttu-id="e8b80-104">Suliejimo etapas yra paskutinis duomenų sujungimo proceso etapas.</span><span class="sxs-lookup"><span data-stu-id="e8b80-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e8b80-105">Jo tikslas – suderinti prieštaringus duomenis.</span><span class="sxs-lookup"><span data-stu-id="e8b80-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e8b80-106">Prieštaringų duomenų pavyzdžiai: kliento vardas, randamas dviejuose jūsų duomenų rinkiniuose, bet kiekviename iš jų rašomas šiek tiek skirtingai (pvz., „Grant Marshall“ ir „Grant Marshal“), arba telefono numeris, kurio formatas skiriasi (617-803-091X ir 617803091X).</span><span class="sxs-lookup"><span data-stu-id="e8b80-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e8b80-107">Šių prieštaringų duomenų taškų sujungimas atliekamas „atributas pagal atributą“ pagrindu.</span><span class="sxs-lookup"><span data-stu-id="e8b80-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="e8b80-108">Užbaigus [sutapdinimo etapą](match-entities.md) pradedamas suliejimo etapas, pasirinkus plytelę **Sulieti**, pateikiamą puslapyje **Sujungti**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e8b80-109">Sistemos rekomendacijų peržiūra</span><span class="sxs-lookup"><span data-stu-id="e8b80-109">Review system recommendations</span></span>

<span data-ttu-id="e8b80-110">Puslapyje **Sulieti** galite pasirinkti ir pašalinti atributus, kurie bus sulieti jūsų sujungtame kliento profilio objekte (konfigūravimo proceso rezultatas).</span><span class="sxs-lookup"><span data-stu-id="e8b80-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="e8b80-111">Kai kuriuos atributus sistema sulieja automatiškai.</span><span class="sxs-lookup"><span data-stu-id="e8b80-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="e8b80-112">Sulietų atributų peržiūra</span><span class="sxs-lookup"><span data-stu-id="e8b80-112">View merged attributes</span></span>

<span data-ttu-id="e8b80-113">Norėdami peržiūrėti atributus, įtrauktus į vieną iš automatiškai sulietų atributų, pažymėkite tą sulietą atributą.</span><span class="sxs-lookup"><span data-stu-id="e8b80-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="e8b80-114">Du atributai, kurie sudaro sulietą atributą, rodomi dviejose naujose eilėse po sulietu atributu.</span><span class="sxs-lookup"><span data-stu-id="e8b80-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8b80-115">![Sulieto atributo pasirinkimas](media/configure-data-merge-profile-attributes.png "Sulieto atributo pasirinkimas")</span><span class="sxs-lookup"><span data-stu-id="e8b80-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="e8b80-116">Sulietų atributų atskyrimas</span><span class="sxs-lookup"><span data-stu-id="e8b80-116">Separate merged attributes</span></span>

<span data-ttu-id="e8b80-117">Norėdami atskirti bet kurį automatiškai sulietą atributą arba atšaukti jo suliejimą, tą atributą susiraskite lentelėje **Profilio atributai**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="e8b80-118">Pasirinkite mygtuką su daugtaškiu (...).</span><span class="sxs-lookup"><span data-stu-id="e8b80-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="e8b80-119">Išplečiamajame sąraše pasirinkite **Atskiri laukai**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="e8b80-120">Sulietų atributų pašalinimas</span><span class="sxs-lookup"><span data-stu-id="e8b80-120">Remove merged attributes</span></span>

<span data-ttu-id="e8b80-121">Norėdami pašalinti atributą iš galutinio kliento profilio objekto, tą atributą susiraskite lentelėje **Profilio atributai**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="e8b80-122">Pasirinkite mygtuką su daugtaškiu (...).</span><span class="sxs-lookup"><span data-stu-id="e8b80-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="e8b80-123">Išplečiamajame sąraše pasirinkite **Nesulieti**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="e8b80-124">Atributas perkeliamas į sekciją **Pašalinta iš kliento įrašo**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="e8b80-125">Sulieto atributo įtraukimas rankiniu būdu</span><span class="sxs-lookup"><span data-stu-id="e8b80-125">Manually add a merged attribute</span></span>

<span data-ttu-id="e8b80-126">Norėdami įtraukti sulietą atributą, nueikite į puslapį **Suliejimas**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="e8b80-127">Pasirinkite **Įtraukti sulietą atributą**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="e8b80-128">Nurodykite **Pavadinimą**, kad jį vėliau galėtumėte identifikuoti puslapyje **Suliejimas**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="e8b80-129">Papildomai galite nurodyti **Rodomą pavadinimą**, kuris rodomas sujungtame kliento profilio objekte.</span><span class="sxs-lookup"><span data-stu-id="e8b80-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="e8b80-130">Sukonfigūruokite **Pasirinkti dubliuotus atributus**, kad pasirinktumėte atributus, kuriuos norite sulieti iš sutapdintų objektų.</span><span class="sxs-lookup"><span data-stu-id="e8b80-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="e8b80-131">Taip pat galite ieškoti atributų.</span><span class="sxs-lookup"><span data-stu-id="e8b80-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="e8b80-132">Nustatykite **Rikiuoti pagal svarbą**, kad suteiktumėte prioritetą vienam atributui.</span><span class="sxs-lookup"><span data-stu-id="e8b80-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="e8b80-133">Pavyzdžiui, jei objekte *WebAccountCSV* pateikiami tiksliausi duomenys apie atributą *Vardai ir pavardės*, pasirinkdami *WebAccountCSV*, galite nustatyti, kad šiam objektui būtų teikiama daugiau svarbos nei *ContactCSV*.</span><span class="sxs-lookup"><span data-stu-id="e8b80-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="e8b80-134">Todėl kai reikia išgauti atributo *Vardas ir pavardė* detales, *WebAccountCSV* suteikiamas pirmasis prioritetas, o *ContactCSV* perkeliamas į antrąjį prioritetą.</span><span class="sxs-lookup"><span data-stu-id="e8b80-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e8b80-135">Suliejimo vykdymas</span><span class="sxs-lookup"><span data-stu-id="e8b80-135">Run your merge</span></span>

<span data-ttu-id="e8b80-136">Nesvarbu, ar atributus suliejate rankiniu būdu, ar leidžiate juos sulieti sistemai, visada galite vykdyti savo suliejimą.</span><span class="sxs-lookup"><span data-stu-id="e8b80-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e8b80-137">Norėdami pradėti procesą, puslapyje **Sulieti** pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8b80-138">![Duomenų suliejimo įrašymas ir vykdymas](media/configure-data-merge-save-run.png "Duomenų suliejimo įrašymas ir vykdymas")</span><span class="sxs-lookup"><span data-stu-id="e8b80-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e8b80-139">Norėdami atlikti papildomų pakeitimų ir iš naujo paleisti veiksmą, vykdomą suliejimą galite atšaukti.</span><span class="sxs-lookup"><span data-stu-id="e8b80-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e8b80-140">Spustelėkite **Atnaujinama...** ir pasirodžiusiame šoniniame skydo pasirinkite **Atšaukti užduotį**.</span><span class="sxs-lookup"><span data-stu-id="e8b80-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="e8b80-141">Kai tekstas **Atnaujinama...** pasikeičia į **Sėkmingai atlikta**, suliejimas yra baigtas, o duomenų prieštaravimai buvo išspręsti pagal jūsų apibrėžtą strategiją.</span><span class="sxs-lookup"><span data-stu-id="e8b80-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="e8b80-142">Sulieti ir nesulieti atributai įtraukiami į vieningojo profilio objektą.</span><span class="sxs-lookup"><span data-stu-id="e8b80-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="e8b80-143">Neįtraukti atributai į vieningojo profilio objektą neįtraukiami.</span><span class="sxs-lookup"><span data-stu-id="e8b80-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="e8b80-144">Jei tai nėra pirmas kartas, kai sėkmingai įvykdėte suliejimą, visi proceso pabaigos procesai, įskaitant papildymą, segmentaciją ir matavimą, bus automatiškai paleisti iš naujo.</span><span class="sxs-lookup"><span data-stu-id="e8b80-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="e8b80-145">Kai visi proceso pabaigos procesai bus įvykdyti pakartotinai, klientų profiliuose bus matomi bet kokie atlikti pakeitimai.</span><span class="sxs-lookup"><span data-stu-id="e8b80-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="e8b80-146">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="e8b80-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e8b80-147">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e8b80-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e8b80-148">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="e8b80-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e8b80-149">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="e8b80-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8b80-150">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="e8b80-150">Next Step</span></span>

<span data-ttu-id="e8b80-151">Norėdami gauti daugiau įžvalgų apie savo klientus, sukonfigūruokite [veiklas](activities.md), [papildymą](enrichment-microsoft-graph.md) arba [ryšius](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e8b80-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e8b80-152">Jei jau sukonfigūravote veiklas, papildymą arba ryšius arba jei sukonfigūravote segmentus, jie bus apdorojami automatiškai, kad būtų naudojami naujausi kliento duomenys.</span><span class="sxs-lookup"><span data-stu-id="e8b80-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]