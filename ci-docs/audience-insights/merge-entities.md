---
title: Suliekite objektus duomenų suvienyjime
description: Suliekite objektus tam, kad sukurtumėte suvienytus kliento profilius.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305658"
---
# <a name="merge-entities"></a><span data-ttu-id="2ab0b-103">Suliekite objektus</span><span class="sxs-lookup"><span data-stu-id="2ab0b-103">Merge entities</span></span>

<span data-ttu-id="2ab0b-104">Suliejimo etapas yra paskutinis duomenų sujungimo proceso etapas.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="2ab0b-105">Jo tikslas – suderinti prieštaringus duomenis.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="2ab0b-106">Prieštaringų duomenų pavyzdžiai: kliento vardas, randamas dviejuose jūsų duomenų rinkiniuose, bet kiekviename iš jų rašomas šiek tiek skirtingai (pvz., „Grant Marshall“ ir „Grant Marshal“), arba telefono numeris, kurio formatas skiriasi (617-803-091X ir 617803091X).</span><span class="sxs-lookup"><span data-stu-id="2ab0b-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="2ab0b-107">Šių prieštaringų duomenų taškų sujungimas atliekamas „atributas pagal atributą“ pagrindu.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Suliejimo puslapis duomenų unifikavimo procese, rodantis lentelę su sulietais laukais, kurie apibrėžia vieningąjį kliento profilį.":::

<span data-ttu-id="2ab0b-109">Užbaigus [sutapdinimo etapą](match-entities.md) pradedamas suliejimo etapas, pasirinkus plytelę **Sulieti**, pateikiamą puslapyje **Sujungti**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="2ab0b-110">Sistemos rekomendacijų peržiūra</span><span class="sxs-lookup"><span data-stu-id="2ab0b-110">Review system recommendations</span></span>

<span data-ttu-id="2ab0b-111">**Duomenys** > **Suvienodinti** > **Sulieti** galite pasirinkti ir išskirti atributus iš suliejimo jūsų vieningojo kliento profilio objekte.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="2ab0b-112">Vieningasis kliento profilis yra duomenų unifikavimo proceso rezultatas.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="2ab0b-113">Kai kuriuos atributus sistema sulieja automatiškai.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="2ab0b-114">Norėdami peržiūrėti atributus, įtrauktus į vieną iš jūsų automatiškai sulietų atributų, pasirinkite sulietą atributą lentelės skirtuke **Kliento laukai**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="2ab0b-115">Atributai, kurie sudaro sulietą atributą, yra rodomi dviejose naujose eilutėse po sulietu atributu.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="2ab0b-116">Sulietų laukų atskyrimas, pervardijimas, išbraukimas ir redagavimas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="2ab0b-117">Galite pakeisti, kaip sistema apdoroja sulietus atributus, kad sugeneruotų vieningąjį kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="2ab0b-118">Pažymėkite **Rodyti daugiau** ir pasirinkite norimą keisti parinktį.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Parinktys išplečiamajame meniu Rodyti daugiau, kad valdytume sulietus atributus.":::

<span data-ttu-id="2ab0b-120">Daugiau informacijos rasite tolesniuose skyriuose.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="2ab0b-121">Sulietų laukų atskyrimas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-121">Separate merged fields</span></span>

<span data-ttu-id="2ab0b-122">Norėdami atskirti sulietus laukus, lentelėje suraskite atributą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="2ab0b-123">Vieningajame kliento profilyje atskiri laukai yra rodomi kaip atskiri duomenų elementai.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="2ab0b-124">Pasirinkite sulietą lauką.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="2ab0b-125">Pažymėkite **Rodyti daugiau** ir pasirinkite **Atskirti laukus**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="2ab0b-126">Patvirtinkite atskyrimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-126">Confirm the separation.</span></span>

1. <span data-ttu-id="2ab0b-127">Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="2ab0b-128">Sulietų laukų pervardijimas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-128">Rename merged fields</span></span>

<span data-ttu-id="2ab0b-129">Pakeiskite sulietų atributų rodomą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="2ab0b-130">Negalite pakeisti įvesties objekto pavadinimo.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="2ab0b-131">Pasirinkite sulietą lauką.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="2ab0b-132">Pažymėkite **Rodyti daugiau** ir pasirinkite **Pervadinti**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="2ab0b-133">Patvirtinkite pakeistą rodomą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="2ab0b-134">Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="2ab0b-135">Sulietų laukų išbraukimas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-135">Exclude merged fields</span></span>

<span data-ttu-id="2ab0b-136">Išbraukite atributą iš vieningojo kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="2ab0b-137">Jei laukas yra naudojamas kituose procesuose, pavyzdžiui, segmente, pašalinkite jį iš šių procesų prieš išbraukdami jį iš kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="2ab0b-138">Pasirinkite sulietą lauką.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="2ab0b-139">Pažymėkite **Rodyti daugiau** ir pasirinkite **Išbraukti**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="2ab0b-140">Patvirtinkite neišbraukimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="2ab0b-141">Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="2ab0b-142">Puslapyje **Sulieti** pasirinkite **Išbraukti laukai**, kad peržiūrėtumėte visų išbrauktų laukų sąrašą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="2ab0b-143">Ši sritis jums leidžia vėl įtraukti išbrauktus laukus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="2ab0b-144">Laukų sujungimas neautomatiniu būdu</span><span class="sxs-lookup"><span data-stu-id="2ab0b-144">Manually combine fields</span></span>

<span data-ttu-id="2ab0b-145">Sulietą atributą nurodykite rankiniu būdu.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="2ab0b-146">Puslapyje **Sulieti** pasirinkite **Sujungti laukus**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="2ab0b-147">Įveskite **Pavadinimą** ir **Išvesties lauko pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="2ab0b-148">Pasirinkite lauką, kurį norite įtraukti.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-148">Choose a field to add.</span></span> <span data-ttu-id="2ab0b-149">Pasirinkite **Įtraukti laukus**, kad sujungtumėte daugiau laukų.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="2ab0b-150">Patvirtinkite neišbraukimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="2ab0b-151">Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="2ab0b-152">Laukų tvarkos keitimas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-152">Change the order of fields</span></span>

<span data-ttu-id="2ab0b-153">Kai kuriuose objektuose yra daugiau išsamios informacijos nei kituose.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-153">Some entities contain more details than others.</span></span> <span data-ttu-id="2ab0b-154">Jei objekte yra naujausių duomenų apie lauką, galite jam teikti pirmenybę prieš kitus objektus, kai suliejate reikšmes.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="2ab0b-155">Pasirinkite sulietą lauką.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="2ab0b-156">Pažymėkite **Rodyti daugiau** ir pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="2ab0b-157">Srityje **Sujungti laukus** pasirinkite **Perkelti aukštyn/žemyn**, kad nustatytumėte jų tvarką arba juos nuvilktumėte į norimą padėtį.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="2ab0b-158">Patvirtinkite pakeitimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-158">Confirm the change.</span></span>

1. <span data-ttu-id="2ab0b-159">Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="2ab0b-160">Suliejimo vykdymas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-160">Run your merge</span></span>

<span data-ttu-id="2ab0b-161">Nesvarbu, ar atributus suliejate rankiniu būdu, ar leidžiate juos sulieti sistemai, visada galite vykdyti savo suliejimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="2ab0b-162">Norėdami pradėti procesą, puslapyje **Sulieti** pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2ab0b-163">![Duomenų suliejimo įrašymas ir vykdymas](media/configure-data-merge-save-run.png "Duomenų suliejimo įrašymas ir vykdymas")</span><span class="sxs-lookup"><span data-stu-id="2ab0b-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="2ab0b-164">Pasirinkite **Vykdyti tik suliejimą**, jei norite tik peržiūrėti išvestį, kuri atsispindi vieningajame kliento objekte.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="2ab0b-165">Tolesni procesai bus atnaujinti taip, kaip [apibrėžta atnaujinimo grafike](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2ab0b-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="2ab0b-166">Pasirinkite **Vykdyti suliejimą ir tolesnius procesus**, kad atnaujintumėte sistemą savo pakeitimais.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="2ab0b-167">Visi procesai, įskaitant papildymą, segmentus ir priemones, bus vykdomi iš naujo automatiškai.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="2ab0b-168">Užbaigus visus tolesnius procesus, klientų profiliai atspindės visus jūsų atliktus pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="2ab0b-169">Jei norite atlikti daugiau pakeitimų ir iš naujo vykdyti veiksmą, galite atšaukti vykdomą suliejimą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="2ab0b-170">Spustelėkite **Atnaujinama...** ir pasirodžiusiame šoniniame skydo pasirinkite **Atšaukti užduotį**.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="2ab0b-171">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2ab0b-172">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2ab0b-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2ab0b-173">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2ab0b-174">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="2ab0b-175">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="2ab0b-175">Next Step</span></span>

<span data-ttu-id="2ab0b-176">Norėdami gauti daugiau įžvalgų apie savo klientus, sukonfigūruokite [veiklas](activities.md), [papildymą](enrichment-hub.md) arba [ryšius](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="2ab0b-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="2ab0b-177">Jei jau sukonfigūravote veiklas, papildymą ar segmentus, jie bus automatiškai apdorojami, kad naudotų naujausius kliento duomenys.</span><span class="sxs-lookup"><span data-stu-id="2ab0b-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
