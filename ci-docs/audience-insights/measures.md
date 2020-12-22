---
title: Sukurti ir redaguoti priemones
description: Apibrėžkite su klientu susijusius matus, kad galėtumėte analizuoti ir pateikti tam tikrų verslo sričių rezultatus.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406420"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="d8bbb-103">Matų apibrėžimas ir valdymas</span><span class="sxs-lookup"><span data-stu-id="d8bbb-103">Define and manage measures</span></span>

<span data-ttu-id="d8bbb-104">**Matai** pateikia pagrindinius veiklos rodiklius (KPI), kurie atspindi tam tikrų verslo sričių našumą ir būseną.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="d8bbb-105">Publikos įžvalgos pateikia intuityvią patirtį skirtą sukurti skirtingus priemonių tipus naudojant laukimo kūrimo įrankį, kuriam neprivalote koduoti ar patvirtinti savo priemones rankiniu būdu.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="d8bbb-106">**Pagrindiniame** puslapyje galite sekti savo verslo matus, matyti konkrečių klientų matus **kliento kortelėje** ir naudoti matus klientų segmentams apibrėžti **segmentų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="d8bbb-107">Sukurti matą</span><span class="sxs-lookup"><span data-stu-id="d8bbb-107">Create a measure</span></span>

<span data-ttu-id="d8bbb-108">Šis skyrius padės jums sukurti matą nuo nulio.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="d8bbb-109">Galite kurti matus su duomenimis iš kelių duomenų šaltinių, sujungtų su kliento objektu.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="d8bbb-110">Kai kurie [paslaugų apribojimai](service-limits.md) yra taikomi.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="d8bbb-111">Publikos įžvalgose, eikite į **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="d8bbb-112">Pasirinkite **naujas matas**</span><span class="sxs-lookup"><span data-stu-id="d8bbb-112">Select **New measure**.</span></span>

3. <span data-ttu-id="d8bbb-113">Pasirinkite mato **tipą**:</span><span class="sxs-lookup"><span data-stu-id="d8bbb-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="d8bbb-114">**Kliento atributas**: vienas kliento laukas, kuris atspindi kliento rezultatą, vertę arba būseną.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="d8bbb-115">Kliento atributai kuriami kaip atributai naujame sistemos sugeneruotame objekte, vadinamame **kliento matu**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="d8bbb-116">**Kliento matas**: įžvalgos apie kliento elgseną pagal pažymėtų matmenų suskirstymą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="d8bbb-117">Naujas objektas yra sukuriamas kiekvienam matui, galimai su keliais įrašais klientui.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="d8bbb-118">**Verslo matas**: seka jūsų verslo veiklos rezultatus ir įmonės būseną.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="d8bbb-119">Verslo matai gali turėti dvi skirtingas išvestis: skaitmeninę išvestį, kuri rodoma **pagrindiniame** puslapyje arba naują objektą, kurį galite rasti **objektų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="d8bbb-120">Įveskite **pavadinimą** ir pasirinktinai **rodomą pavadinimą**, tada pasirinkite **toliau**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="d8bbb-121">**Objektų** skyriuje, pasirinkite pirmą objektą iš išskleidžiamojo sąrašo.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="d8bbb-122">Šiuo metu turite nuspręsti, ar jūsų mato apibrėžimui yra reikalingi papildomi objektai.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d8bbb-123">![Matavimo apibrėžimas](media/measure-definition.png "Matavimo apibrėžimas")</span><span class="sxs-lookup"><span data-stu-id="d8bbb-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="d8bbb-124">Norėdami įtraukti daugiau objektų, pasirinkite **pridėti objektą** ir pasirinkite objektus, kuriuos norite naudoti matui.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d8bbb-125">Galite pasirinkti tik tuos objektus, kurie turi ryšį su jūsų pradžios objektu.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="d8bbb-126">Daugiau informacijos apie ryšių apibrėžimą, žr. [ryšiai](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d8bbb-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="d8bbb-127">Pasirinktinai galite konfigūruoti kintamuosius.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="d8bbb-128">**Kintamųjų** skyriuje pasirinkite **naują kintamąjį**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="d8bbb-129">Kintamieji yra kiekvienam pasirinktam įrašui atliekami skaičiavimai.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="d8bbb-130">Pavyzdžiui, pardavimo vietos (POS) ir pardavimo internetu, kiekvienam jūsų kliento įrašui, apibendrinimas.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="d8bbb-131">Pateikite kintamojo **pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="d8bbb-132">**Išraiškos** srityje pasirinkite lauką, kad pradėtumėte skaičiavimą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="d8bbb-133">Įveskite išraišką **išraiškos** srityje kol renkatės daugiau į apskaičiavimą įtraukiamų laukų.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d8bbb-134">Šiuo metu tik aritmetinės išraiškos yra palaikomos.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="d8bbb-135">Be to, kintamųjų skaičiavimas nepalaikomas objektams iš skirtingų [objektų maršrutų](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d8bbb-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="d8bbb-136">Pasirinkite **Atlikta**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-136">Select **Done**.</span></span>

11. <span data-ttu-id="d8bbb-137">**Mato apibrėžimo** skyriuje apibrėšite, kaip jūsų pasirinkti objektai ir apskaičiuoti kintamieji yra sujungiami į naują objekto ar atributo matmenį.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="d8bbb-138">Pasirinkti **naują matmenį**.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-138">Select **New dimension**.</span></span> <span data-ttu-id="d8bbb-139">Galite galvoti apie matmenį kaip apie *grupuoti pagal* funkciją.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="d8bbb-140">Jūsų mato objekto ar atributo duomenų išvestis bus sugrupuota pagal visus apibrėžtus matmenis.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d8bbb-141">![Pasirinkti sujungimo ciklą](media/measures-businessreport-measure-definition2.png "Pasirinkti sujungimo ciklą")</span><span class="sxs-lookup"><span data-stu-id="d8bbb-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="d8bbb-142">Savo matmenų apibrėžimui pasirinkite arba įveskite šią informaciją:</span><span class="sxs-lookup"><span data-stu-id="d8bbb-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="d8bbb-143">**Objektas**: jei nustatote matavimo objektą, jis turi turėti bent vieną atributą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="d8bbb-144">Jei apibrėžiate matavimo atributą, pagal numatytąją reikšmę jis apims tik vieną atributą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="d8bbb-145">Šis pasirinkimas yra apie objekto, kuris turi atributą, pasirinkimą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="d8bbb-146">**Laukas**: pasirinkite konkretų atributą, kuris bus įtrauktas į matavimo objektą arba atributą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="d8bbb-147">**Talpykla**: pasirinkite, ar norite kaupti duomenis kasdien, kas mėnesį ar kas metus.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="d8bbb-148">Tai būtina pasirinkti tik tuo atveju, jei pasirinkote atributą Datos tipas.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="d8bbb-149">**Kaip**: apibrėžia naujo lauko pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="d8bbb-150">**Rodomas pavadinimas**: apibrėžia jūsų lauko rodomą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8bbb-151">Jūsų verslo matas bus išsaugotas kaip vieno skaičiaus objektas ir atsiras **pagrindiniame** puslapyje, nebent pridėsite daugiau matmenų.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="d8bbb-152">Pridėjus daugiau matmenų, matas *nebus* rodomas **pagrindiniame** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="d8bbb-153">Pasirinktinai įtraukite sujungimo funkcijas.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="d8bbb-154">Bet kokia jūsų sukurta agregacija pavirsta nauja jūsų mato objekto ar atributo reikšme.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="d8bbb-155">Palaikomos sujungimo funkcijos yra: **min**, **maks**, **vidurkis**, **mediana**, **suma**, **unikalus skaičius**, **pirmas** (užima pirmąjį matmens reikšmės įrašą) ir **paskutinis** (užima paskutinį įrašą, įtrauktą į matmens vertę).</span><span class="sxs-lookup"><span data-stu-id="d8bbb-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="d8bbb-156">Pasirinkite **išsaugoti** norėdami pritaikyti mato pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="d8bbb-157">Matų valdymas</span><span class="sxs-lookup"><span data-stu-id="d8bbb-157">Manage your measures</span></span>

<span data-ttu-id="d8bbb-158">Jums sukūrus mažiausiai vieną priemonę, matysite priemonių sąrašą **Priemonių** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="d8bbb-159">Rasite informaciją apie mato tipą, kūrėją, sukūrimo datą ir laiką, paskutinę redagavimo datą ir laiką, būseną (ar matas aktyvus, nesuaktyvintas arba nepavykęs) ir paskutinę naujinimo datą ir laiką.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="d8bbb-160">Iš sąrašo pasirinkę matą galite peržiūrėti jo išvesties peržiūrą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="d8bbb-161">Norėdami tuo pačiu metu atnaujinti visus savo matus, spustelėkite **Atnaujinti visus** nepažymėdami konkretaus mato.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8bbb-162">![Atskirų matų valdymo veiksmai](media/measure-actions.png "Atskirų matų valdymo veiksmai")</span><span class="sxs-lookup"><span data-stu-id="d8bbb-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="d8bbb-163">Arba pasirinkite priemonę iš sąrašo ir atlikite vieną iš toliau nurodytų veiksmų.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="d8bbb-164">Pažymėkite mato pavadinimą, kad peržiūrėtumėte jo išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="d8bbb-165">**Redaguokite** mato konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="d8bbb-166">**Pervardykite** matą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-166">**Rename** the measure.</span></span>
- <span data-ttu-id="d8bbb-167">**Panaikinkite** matą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-167">**Delete** the measure.</span></span>
- <span data-ttu-id="d8bbb-168">Pažymėkite elipsę (...), tada pasirinkite **Atnaujinti**, kad būtų pradėtas mato atnaujinimo procesas.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="d8bbb-169">Pažymėkite elipsę (...), tada pasirinkite **Atsisiųsti**, kad gautumėte mato .CSV failą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="d8bbb-170">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d8bbb-171">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d8bbb-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d8bbb-172">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d8bbb-173">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d8bbb-174">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="d8bbb-174">Next step</span></span>

<span data-ttu-id="d8bbb-175">Galite naudoti esančius matus, jei norite sukurti savo pirmą kliento segmentą **segmentų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="d8bbb-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="d8bbb-176">Daugiau informacijos galite rasti čia [segmentas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d8bbb-176">For more information, see [Segments](segments.md).</span></span>
