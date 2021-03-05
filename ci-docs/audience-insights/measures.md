---
title: Matų kūrimas ir valdymas
description: Apibrėžkite verslo efektyvumo analizės ir peržiūros priemones.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269938"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="51aa4-103">Matų apibrėžimas ir valdymas</span><span class="sxs-lookup"><span data-stu-id="51aa4-103">Define and manage measures</span></span>

<span data-ttu-id="51aa4-104">Priemonės padeda jums geriau suprasti klientų elgesį ir verslo našumą nuskaitant atitinkamas reikšmes iš [vieningųjų profilių](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="51aa4-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="51aa4-105">Pavyzdžiui, įmonė nori, kad *bendras vienam klientui skirtas išlaidas* būtų galima pamatyti norint suprasti atskirų klientų pirkimo retrospektyvą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="51aa4-106">Arba *matuokite visą įmonės* pardavimą, kad suprastumėte agregavimo lygio pajamas visoje įmonėje.</span><span class="sxs-lookup"><span data-stu-id="51aa4-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="51aa4-107">Priemonės kuriamos naudojant priemonę eilės duomenų užklausos platformą su įvairiais operatoriais ir paprastomis susiejimo parinktimis.</span><span class="sxs-lookup"><span data-stu-id="51aa4-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="51aa4-108">Ji leidžia filtruoti duomenis, grupuoti rezultatus, aptikti [objekto ryšio maršrutus](relationships.md), ir peržiūrėti išvestį.</span><span class="sxs-lookup"><span data-stu-id="51aa4-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="51aa4-109">Naudodami matą, galite planuoti verslo veiklas užklausdami klientų duomenis ir išskleisti įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="51aa4-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="51aa4-110">Pavyzdžiui, sukūrus *bendrą vienam klientui išleidus sumą* ir *bendrą grąžą klientui* galima nustatyti klientų grupę, kurios išlaidos yra didelės, bet didelė ir grąža.</span><span class="sxs-lookup"><span data-stu-id="51aa4-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="51aa4-111">Galite  [sukurti segmentą](segments.md)ir imtis kitų geriausių veiksmų.</span><span class="sxs-lookup"><span data-stu-id="51aa4-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="51aa4-112">Sukurti matą</span><span class="sxs-lookup"><span data-stu-id="51aa4-112">Create a measure</span></span>

<span data-ttu-id="51aa4-113">Šiame skyriuje pateikiama informacija apie naujos priemonės sukūrimą nuo pradžių.</span><span class="sxs-lookup"><span data-stu-id="51aa4-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="51aa4-114">Galite sukurti priemonę su duomenų atributais iš duomenų objektų, kurių ryšys nustatytas taip, kad būtų galima prisijungti prie kliento objekto.</span><span class="sxs-lookup"><span data-stu-id="51aa4-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="51aa4-115">Publikos įžvalgose, eikite į **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="51aa4-116">Pasirinkite **Naujas**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-116">Select **New**.</span></span>

1. <span data-ttu-id="51aa4-117">Pasirinkite **Redaguoti pavadinimą** ir įveskite priemonės **pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="51aa4-118">Jei jūsų naujo matavimo konfigūracijoje yra tik du laukai: iškvietai, "CustomerID" ir vienam skaičiavimui rezultatai bus įtraukti kaip naujas stulpelis į sistemos sugeneruotą objektą, kurio pavadinimas Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="51aa4-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="51aa4-119">O priemonės vertę galėsite matyti unifikuotame kliento profilyje.</span><span class="sxs-lookup"><span data-stu-id="51aa4-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="51aa4-120">Kitos priemonės sugeneruos nuosavus objektus.</span><span class="sxs-lookup"><span data-stu-id="51aa4-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="51aa4-121">Konfigūracijos srityje pasirinkite agregavimo funkciją **Pažymėti funkciją** išplečiamajame meniu.</span><span class="sxs-lookup"><span data-stu-id="51aa4-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="51aa4-122">Agregavimo funkcijos yra šios:</span><span class="sxs-lookup"><span data-stu-id="51aa4-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="51aa4-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="51aa4-123">**Sum**</span></span>
   - <span data-ttu-id="51aa4-124">**Vidurkis**</span><span class="sxs-lookup"><span data-stu-id="51aa4-124">**Average**</span></span>
   - <span data-ttu-id="51aa4-125">**Skaičius**</span><span class="sxs-lookup"><span data-stu-id="51aa4-125">**Count**</span></span>
   - <span data-ttu-id="51aa4-126">**Unikalusis skaičius**</span><span class="sxs-lookup"><span data-stu-id="51aa4-126">**Count Unique**</span></span>
   - <span data-ttu-id="51aa4-127">**Didžiausia**</span><span class="sxs-lookup"><span data-stu-id="51aa4-127">**Max**</span></span>
   - <span data-ttu-id="51aa4-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="51aa4-128">**Min**</span></span>
   - <span data-ttu-id="51aa4-129">**Pirma:** perima pirmą duomenų įrašo reikšmę</span><span class="sxs-lookup"><span data-stu-id="51aa4-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="51aa4-130">**Paskutin:** perima paskutinę į duomenų įrašą pridėtą reikšmę</span><span class="sxs-lookup"><span data-stu-id="51aa4-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Apibrėžkite mato skaičiavimus.":::

1. <span data-ttu-id="51aa4-132">Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.</span><span class="sxs-lookup"><span data-stu-id="51aa4-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="51aa4-133">Pasirinkti **Atributus**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="51aa4-134">Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.</span><span class="sxs-lookup"><span data-stu-id="51aa4-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="51aa4-135">Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti.</span><span class="sxs-lookup"><span data-stu-id="51aa4-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="51aa4-136">Vienu metu galite pasirinkti tik vieną atributą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="51aa4-137">Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės**. Arba galite ieškoti objekto arba priemonės pavadinimo.</span><span class="sxs-lookup"><span data-stu-id="51aa4-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="51aa4-138">Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.</span><span class="sxs-lookup"><span data-stu-id="51aa4-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pažymėkite atributą, kuris bus naudojamas skaičiavimams.":::

1. <span data-ttu-id="51aa4-140">Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.</span><span class="sxs-lookup"><span data-stu-id="51aa4-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Sukurkite sudėtingą matą su operatoriais, kuriuose yra operatoriai.":::

1. <span data-ttu-id="51aa4-142">Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="51aa4-143">Filtrų srities atributų skyriuje **Įtraukti atributą** ir **Filtrai** pažymėkite atributą, kurį norite naudoti kurdami filtrus.</span><span class="sxs-lookup"><span data-stu-id="51aa4-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="51aa4-144">Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="51aa4-145">Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.</span><span class="sxs-lookup"><span data-stu-id="51aa4-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="51aa4-146">Norėdami įtraukti dimensijas, konfigūracijos srityje pažymėkite **Dimensijos**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="51aa4-147">Dimensijų rezultatai bus rodomi kaip stulpeliai.</span><span class="sxs-lookup"><span data-stu-id="51aa4-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="51aa4-148">Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes.</span><span class="sxs-lookup"><span data-stu-id="51aa4-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="51aa4-149">Pvz.: miestą arba lytį.</span><span class="sxs-lookup"><span data-stu-id="51aa4-149">For example, city or gender.</span></span> <span data-ttu-id="51aa4-150">Pagal numatytuosius nustatymus, siekiant kurti *kliento lygio matus*, pasirenkama *"CustomerID"*.</span><span class="sxs-lookup"><span data-stu-id="51aa4-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="51aa4-151">Jei norite kurti verslo lygio priemones, galite pašalinti *numatytąją dimensiją*.</span><span class="sxs-lookup"><span data-stu-id="51aa4-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="51aa4-152">Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.</span><span class="sxs-lookup"><span data-stu-id="51aa4-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="51aa4-153">Jei tarp jūsų susietų duomenų objektų ir kliento objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="51aa4-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="51aa4-154">Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.</span><span class="sxs-lookup"><span data-stu-id="51aa4-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="51aa4-155">Pažymėkite **Duomenų nuostatas** ir pasirinkite kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti.</span><span class="sxs-lookup"><span data-stu-id="51aa4-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="51aa4-156">Pasirinkite **Atlikta**, kad pritaikyumėte savo pasirinkimą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pasirinkite diagramos objektą.":::

1. <span data-ttu-id="51aa4-158">Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="51aa4-159">Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje.</span><span class="sxs-lookup"><span data-stu-id="51aa4-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="51aa4-160">naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.</span><span class="sxs-lookup"><span data-stu-id="51aa4-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="51aa4-161">Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.</span><span class="sxs-lookup"><span data-stu-id="51aa4-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="51aa4-162">**Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas.</span><span class="sxs-lookup"><span data-stu-id="51aa4-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="51aa4-163">Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.</span><span class="sxs-lookup"><span data-stu-id="51aa4-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="51aa4-164">Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus.</span><span class="sxs-lookup"><span data-stu-id="51aa4-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="51aa4-165">Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.</span><span class="sxs-lookup"><span data-stu-id="51aa4-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="51aa4-166">Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.</span><span class="sxs-lookup"><span data-stu-id="51aa4-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="51aa4-167">Matų valdymas</span><span class="sxs-lookup"><span data-stu-id="51aa4-167">Manage your measures</span></span>

<span data-ttu-id="51aa4-168">Sukūrę [priemonę](#create-a-measure), matų sąrašą matysite puslapyje **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="51aa4-169">Rasite informacijos apie matavimo tipą, kūrėją, kūrimo datą, būseną ir būseną.</span><span class="sxs-lookup"><span data-stu-id="51aa4-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="51aa4-170">Kai sąraše pažymite priemonę, galite peržiūrėti išvestį ir atsisiųsti .CSV failą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="51aa4-171">Norėdami tuo pačiu metu atnaujinti visus savo matus, spustelėkite **Atnaujinti visus** nepažymėdami konkretaus mato.</span><span class="sxs-lookup"><span data-stu-id="51aa4-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="51aa4-172">![Atskirų matų valdymo veiksmai](media/measure-actions.png "Atskirų matų valdymo veiksmai")</span><span class="sxs-lookup"><span data-stu-id="51aa4-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="51aa4-173">Sąraše pažymėkite toliau nurodytų parinkčių matą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="51aa4-174">Pažymėkite mato pavadinimą, kad peržiūrėtumėte jo išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="51aa4-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="51aa4-175">**Redaguokite** mato konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="51aa4-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="51aa4-176">**Atnaujinkite** priemonę pagal naujausius duomenis.</span><span class="sxs-lookup"><span data-stu-id="51aa4-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="51aa4-177">**Pervardykite** matą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-177">**Rename** the measure.</span></span>
- <span data-ttu-id="51aa4-178">**Panaikinkite** matą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-178">**Delete** the measure.</span></span>
- <span data-ttu-id="51aa4-179">**Aktyvuokite** arba **Deaktyvuokite**.</span><span class="sxs-lookup"><span data-stu-id="51aa4-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="51aa4-180">Suplanuoto atnaujinimo metu neaktyvūs duomenys nebus [atnaujinti](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="51aa4-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="51aa4-181">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="51aa4-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="51aa4-182">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="51aa4-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="51aa4-183">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="51aa4-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="51aa4-184">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="51aa4-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="51aa4-185">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="51aa4-185">Next step</span></span>

<span data-ttu-id="51aa4-186">Naudodami esamas priemones, vaizdo kamera kuriate [klientų segmentą](segments.md).</span><span class="sxs-lookup"><span data-stu-id="51aa4-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]