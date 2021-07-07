---
title: Matų kūrimas ir valdymas
description: Apibrėžkite verslo efektyvumo analizės ir peržiūros priemones.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304810"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="60891-103">Matų apibrėžimas ir valdymas</span><span class="sxs-lookup"><span data-stu-id="60891-103">Define and manage measures</span></span>

<span data-ttu-id="60891-104">Šios priemonės padeda jums geriau suprasti klientų elgesį ir įmonės efektyvumą.</span><span class="sxs-lookup"><span data-stu-id="60891-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="60891-105">Jos peržvelgia atitinkamas vertes iš [vieningųjų profilių](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="60891-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="60891-106">Pavyzdžiui, įmonė nori, kad *bendras vienam klientui* skirtas išlaidas būtų galima pamatyti norint suprasti kliento pirkimo retrospektyvą arba įvertinti *bendrą įmonės pardavimą* tam, kad būtų galima suprasti agregavimo lygio pajamas visoje įmonėje.</span><span class="sxs-lookup"><span data-stu-id="60891-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="60891-107">Priemonės kuriamos naudojant priemonę eilės duomenų užklausos platformą su įvairiais operatoriais ir paprastomis susiejimo parinktimis.</span><span class="sxs-lookup"><span data-stu-id="60891-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="60891-108">Ji leidžia filtruoti duomenis, grupuoti rezultatus, aptikti [objekto ryšio maršrutus](relationships.md), ir peržiūrėti išvestį.</span><span class="sxs-lookup"><span data-stu-id="60891-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="60891-109">Naudodami matą, galite planuoti verslo veiklas užklausdami klientų duomenis ir išskleisti įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="60891-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="60891-110">Pavyzdžiui, sukūrus *bendrą vienam klientui išleidus sumą* ir *bendrą grąžą klientui* galima nustatyti klientų grupę, kurios išlaidos yra didelės, bet didelė ir grąža.</span><span class="sxs-lookup"><span data-stu-id="60891-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="60891-111">Galite  [sukurti segmentą](segments.md)ir imtis kitų geriausių veiksmų.</span><span class="sxs-lookup"><span data-stu-id="60891-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="60891-112">Savo priemonės kūrimas nuo pradžių</span><span class="sxs-lookup"><span data-stu-id="60891-112">Build your own measure from scratch</span></span>

<span data-ttu-id="60891-113">Šiame skyriuje pateikiama informacija apie naujos priemonės sukūrimą nuo pradžių.</span><span class="sxs-lookup"><span data-stu-id="60891-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="60891-114">Galite sukurti priemonę su duomenų atributais iš duomenų objektų, kurių ryšys nustatytas taip, kad būtų galima prisijungti prie kliento objekto.</span><span class="sxs-lookup"><span data-stu-id="60891-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="60891-115">Publikos įžvalgose, eikite į **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="60891-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="60891-116">Pasirinkite **Naujas** ir pasirinkite **Kurti savo**.</span><span class="sxs-lookup"><span data-stu-id="60891-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="60891-117">Pasirinkite **Redaguoti pavadinimą** ir įveskite priemonės **pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="60891-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="60891-118">Jei jūsų naujo matavimo konfigūracijoje yra tik du laukai, pavyzdžiui, Kliento ID ir vienas skaičiavimas, išeiga bus įtraukta kaip naujas stulpelis į sistemos sugeneruotą objektą, pavadintą Kliento matavimas.</span><span class="sxs-lookup"><span data-stu-id="60891-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="60891-119">O priemonės vertę galėsite matyti unifikuotame kliento profilyje.</span><span class="sxs-lookup"><span data-stu-id="60891-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="60891-120">Kitos priemonės sugeneruos nuosavus objektus.</span><span class="sxs-lookup"><span data-stu-id="60891-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="60891-121">Konfigūracijos srityje pasirinkite agregavimo funkciją išplečiamajame meniu **Pažymėti funkciją**.</span><span class="sxs-lookup"><span data-stu-id="60891-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="60891-122">Agregavimo funkcijos yra šios:</span><span class="sxs-lookup"><span data-stu-id="60891-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="60891-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="60891-123">**Sum**</span></span>
   - <span data-ttu-id="60891-124">**Vidurkis**</span><span class="sxs-lookup"><span data-stu-id="60891-124">**Average**</span></span>
   - <span data-ttu-id="60891-125">**Skaičius**</span><span class="sxs-lookup"><span data-stu-id="60891-125">**Count**</span></span>
   - <span data-ttu-id="60891-126">**Unikalusis skaičius**</span><span class="sxs-lookup"><span data-stu-id="60891-126">**Count Unique**</span></span>
   - <span data-ttu-id="60891-127">**Didžiausia**</span><span class="sxs-lookup"><span data-stu-id="60891-127">**Max**</span></span>
   - <span data-ttu-id="60891-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="60891-128">**Min**</span></span>
   - <span data-ttu-id="60891-129">**Pirma:** perima pirmą duomenų įrašo reikšmę</span><span class="sxs-lookup"><span data-stu-id="60891-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="60891-130">**Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę</span><span class="sxs-lookup"><span data-stu-id="60891-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Apibrėžkite mato skaičiavimus.":::

1. <span data-ttu-id="60891-132">Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.</span><span class="sxs-lookup"><span data-stu-id="60891-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="60891-133">Pasirinkti **Atributus**.</span><span class="sxs-lookup"><span data-stu-id="60891-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="60891-134">Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.</span><span class="sxs-lookup"><span data-stu-id="60891-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="60891-135">Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti.</span><span class="sxs-lookup"><span data-stu-id="60891-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="60891-136">Vienu metu galite pasirinkti tik vieną atributą.</span><span class="sxs-lookup"><span data-stu-id="60891-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="60891-137">Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės**. Arba galite ieškoti objekto arba priemonės pavadinimo.</span><span class="sxs-lookup"><span data-stu-id="60891-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="60891-138">Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.</span><span class="sxs-lookup"><span data-stu-id="60891-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pažymėkite atributą, kuris bus naudojamas skaičiavimams.":::

1. <span data-ttu-id="60891-140">Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.</span><span class="sxs-lookup"><span data-stu-id="60891-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Sukurkite sudėtingą matą su operatoriais, kuriuose yra operatoriai.":::

1. <span data-ttu-id="60891-142">Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**.</span><span class="sxs-lookup"><span data-stu-id="60891-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="60891-143">Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.</span><span class="sxs-lookup"><span data-stu-id="60891-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="60891-144">Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.</span><span class="sxs-lookup"><span data-stu-id="60891-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="60891-145">Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.</span><span class="sxs-lookup"><span data-stu-id="60891-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="60891-146">Norėdami įtraukti dimensijas, konfigūracijos srityje pažymėkite **Dimensijos**.</span><span class="sxs-lookup"><span data-stu-id="60891-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="60891-147">Dimensijų rezultatai bus rodomi kaip stulpeliai.</span><span class="sxs-lookup"><span data-stu-id="60891-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="60891-148">Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes.</span><span class="sxs-lookup"><span data-stu-id="60891-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="60891-149">Pvz.: miestą arba lytį.</span><span class="sxs-lookup"><span data-stu-id="60891-149">For example, city or gender.</span></span> <span data-ttu-id="60891-150">Pagal numatytuosius nustatymus, siekiant kurti *kliento lygio matus*, pasirenkama *Kliento ID*.</span><span class="sxs-lookup"><span data-stu-id="60891-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="60891-151">Jei norite kurti verslo lygio priemones, galite pašalinti *numatytąją dimensiją*.</span><span class="sxs-lookup"><span data-stu-id="60891-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="60891-152">Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.</span><span class="sxs-lookup"><span data-stu-id="60891-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="60891-153">Jei jūsų duomenyse yra verčių, kurias reikia pakeisti, pavyzdžiui, sveikuoju skaičiumi, reikšmę *null* pakeiskite į *0* ir pasirinkite **Taisyklės**.</span><span class="sxs-lookup"><span data-stu-id="60891-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="60891-154">Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius.</span><span class="sxs-lookup"><span data-stu-id="60891-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="60891-155">Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="60891-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="60891-156">Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.</span><span class="sxs-lookup"><span data-stu-id="60891-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="60891-157">Pažymėkite **Duomenų nuostatas** ir pasirinkite kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti.</span><span class="sxs-lookup"><span data-stu-id="60891-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="60891-158">Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.</span><span class="sxs-lookup"><span data-stu-id="60891-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="60891-159">Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.</span><span class="sxs-lookup"><span data-stu-id="60891-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pasirinkite diagramos objektą.":::

1. <span data-ttu-id="60891-161">Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**.</span><span class="sxs-lookup"><span data-stu-id="60891-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="60891-162">Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje.</span><span class="sxs-lookup"><span data-stu-id="60891-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="60891-163">naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.</span><span class="sxs-lookup"><span data-stu-id="60891-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="60891-164">Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.</span><span class="sxs-lookup"><span data-stu-id="60891-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="60891-165">**Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas.</span><span class="sxs-lookup"><span data-stu-id="60891-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="60891-166">Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.</span><span class="sxs-lookup"><span data-stu-id="60891-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="60891-167">Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus.</span><span class="sxs-lookup"><span data-stu-id="60891-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="60891-168">Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.</span><span class="sxs-lookup"><span data-stu-id="60891-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="60891-169">Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.</span><span class="sxs-lookup"><span data-stu-id="60891-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="60891-170">Šablono naudojimas priemonei kurti</span><span class="sxs-lookup"><span data-stu-id="60891-170">Use a template to build a measure</span></span>

<span data-ttu-id="60891-171">Jiems kurti galite naudoti iš anksto apibrėžtus dažniausiai naudojamų priemonių šablonus.</span><span class="sxs-lookup"><span data-stu-id="60891-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="60891-172">Išsamūs šablonų aprašymai ir interaktyvioji patirtis padeda efektyviai matuoti kūrimą.</span><span class="sxs-lookup"><span data-stu-id="60891-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="60891-173">Šablonai kuriami pagal žymimys duomenis iš objekto *„Unified Activity“*.</span><span class="sxs-lookup"><span data-stu-id="60891-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="60891-174">Prieš kurdami priemonę pagal šabloną įsitikinkite, kad sukonfigūravote [kleinto veiklą](activities.md).</span><span class="sxs-lookup"><span data-stu-id="60891-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="60891-175">Galimi priemonių šablonai:</span><span class="sxs-lookup"><span data-stu-id="60891-175">Available measure templates:</span></span> 
- <span data-ttu-id="60891-176">Vidutinė operacijų vertė (ATV)</span><span class="sxs-lookup"><span data-stu-id="60891-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="60891-177">Bendra operacijos vertė</span><span class="sxs-lookup"><span data-stu-id="60891-177">Total transaction value</span></span>
- <span data-ttu-id="60891-178">Vidutinės dienos pajamos</span><span class="sxs-lookup"><span data-stu-id="60891-178">Average daily revenue</span></span>
- <span data-ttu-id="60891-179">Vidutinės metų pajamos</span><span class="sxs-lookup"><span data-stu-id="60891-179">Average yearly revenue</span></span>
- <span data-ttu-id="60891-180">Operacijų skaičius</span><span class="sxs-lookup"><span data-stu-id="60891-180">Transaction count</span></span>
- <span data-ttu-id="60891-181">Gauti lojalumo taškai</span><span class="sxs-lookup"><span data-stu-id="60891-181">Loyalty points earned</span></span>
- <span data-ttu-id="60891-182">Panaudoti lojalumo taškai</span><span class="sxs-lookup"><span data-stu-id="60891-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="60891-183">Lojalumo taškų balansas</span><span class="sxs-lookup"><span data-stu-id="60891-183">Loyalty points balance</span></span>
- <span data-ttu-id="60891-184">Aktyvaus kliento veiklos trukmė</span><span class="sxs-lookup"><span data-stu-id="60891-184">Active customer lifespan</span></span>
- <span data-ttu-id="60891-185">Lojalumo narystės trukmė</span><span class="sxs-lookup"><span data-stu-id="60891-185">Loyalty membership duration</span></span>
- <span data-ttu-id="60891-186">Laikas nuo paskutinio pirkimo</span><span class="sxs-lookup"><span data-stu-id="60891-186">Time since last purchase</span></span>

<span data-ttu-id="60891-187">Tolesnė procedūra apžvelgia veiksmus, reikalingus naujai priemonei kurti naudojant šabloną.</span><span class="sxs-lookup"><span data-stu-id="60891-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="60891-188">Publikos įžvalgose, eikite į **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="60891-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="60891-189">Pasirinkite **Naujas** ir pasirinkite **Rinktis šabloną**.</span><span class="sxs-lookup"><span data-stu-id="60891-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Kai kuriate naują priemonę su šablono paryškinimo parinktimi, išskleidžiamajame meniu yra šiek tiek pasislėpęs.":::

1. <span data-ttu-id="60891-191">Raskite jūsų poreikius atitinkantį šabloną ir pasirinkite **Rinktis šabloną**.</span><span class="sxs-lookup"><span data-stu-id="60891-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="60891-192">Peržiūrėkite reikiamus duomenis ir pasirinkite **Darbo pradžia**, jei turite visus duomenis.</span><span class="sxs-lookup"><span data-stu-id="60891-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="60891-193">Srityje **Pavadinimo redagavimas** nustatykite savo priemonės pavadinimą ir išvesties objektą.</span><span class="sxs-lookup"><span data-stu-id="60891-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="60891-194">Pasirinkite **Atlikta**.</span><span class="sxs-lookup"><span data-stu-id="60891-194">Select **Done**.</span></span>

1. <span data-ttu-id="60891-195">Skiltyje **Laikotarpio nustatymas** apibrėžkite naudojamų duomenų laiko tarpą.</span><span class="sxs-lookup"><span data-stu-id="60891-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="60891-196">Pasirinkite, ar norite, kad nauja priemonė apimtų visą duomenų rinkinį pažymėdami "Visas laikas" arba, jei norite, kad **priemonė sufokusuos** konkretų laiko **periodą**.</span><span class="sxs-lookup"><span data-stu-id="60891-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrano nuotrauka, kurioje rodoma laikotarpio skiltis konfigūruojant priemonę iš šablono.":::

1. <span data-ttu-id="60891-198">Kitoje skiltyje pasirinkite **Pridėti duomenis** ir pasirinkite veiklas bei pažymėkite attitinkamus duomenis iš savo objekto *Unified Activity*.</span><span class="sxs-lookup"><span data-stu-id="60891-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="60891-199">1 veiksmas iš 2: skiltyje **Veiklos tipas** pasirinkite norimo naudoti objekto tipą.</span><span class="sxs-lookup"><span data-stu-id="60891-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="60891-200">Skiltyje **Veiklos** pasirinkite objektus, kuriuos norite žymėti.</span><span class="sxs-lookup"><span data-stu-id="60891-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="60891-201">2 veiksmas iš 2: pasirinkite formulės reikalaujamo komponento atributą iš objekto *Unified Activity*.</span><span class="sxs-lookup"><span data-stu-id="60891-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="60891-202">Pvz., jei operacijos vertė vidutinė, tai operacijos vertę vaiduojantis atributas.</span><span class="sxs-lookup"><span data-stu-id="60891-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="60891-203">**Veiklos laiko žymai** pasirinkite atributą iš objekto „Unified Activity“, kuriame vaizduojama veiklos data ir laikas.</span><span class="sxs-lookup"><span data-stu-id="60891-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="60891-204">Sėkmingai pažymėjė duomenis būseną galite matyti kaip **Baigta** kartu su pažymėtų veiklų ir atributų pavadinimu.</span><span class="sxs-lookup"><span data-stu-id="60891-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Baigtų priemonių šablono konfigūravimo ekrano nuotrauka.":::

1. <span data-ttu-id="60891-206">Dabar galite pasirinkti **Vykdyti** ir apskaičiuoti priemonės rezultatus.</span><span class="sxs-lookup"><span data-stu-id="60891-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="60891-207">Jei paiešką vėliau norėsite susiaurinti, pasirinkite **Išsaugoti juodarštį**.</span><span class="sxs-lookup"><span data-stu-id="60891-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="60891-208">Matų valdymas</span><span class="sxs-lookup"><span data-stu-id="60891-208">Manage your measures</span></span>

<span data-ttu-id="60891-209">Priemonių sąrašą galima rasti puslapyje **Priemonės**.</span><span class="sxs-lookup"><span data-stu-id="60891-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="60891-210">Rasite informacijos apie matavimo tipą, kūrėją, kūrimo datą, būseną ir būseną.</span><span class="sxs-lookup"><span data-stu-id="60891-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="60891-211">Kai sąraše pažymite priemonę, galite peržiūrėti išvestį ir atsisiųsti CSV failą.</span><span class="sxs-lookup"><span data-stu-id="60891-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="60891-212">Norėdami tuo pačiu metu atnaujinti visus savo matus, spustelėkite **Atnaujinti visus** nepažymėdami konkretaus mato.</span><span class="sxs-lookup"><span data-stu-id="60891-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="60891-213">![Atskirų matų valdymo veiksmai.](media/measure-actions.png "Atskirų matų valdymo veiksmai.")</span><span class="sxs-lookup"><span data-stu-id="60891-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="60891-214">Sąraše pažymėkite toliau nurodytų parinkčių matą.</span><span class="sxs-lookup"><span data-stu-id="60891-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="60891-215">Pažymėkite mato pavadinimą, kad peržiūrėtumėte jo išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="60891-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="60891-216">**Redaguokite** mato konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="60891-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="60891-217">**Atnaujinkite** priemonę pagal naujausius duomenis.</span><span class="sxs-lookup"><span data-stu-id="60891-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="60891-218">**Pervardykite** matą.</span><span class="sxs-lookup"><span data-stu-id="60891-218">**Rename** the measure.</span></span>
- <span data-ttu-id="60891-219">**Panaikinkite** matą.</span><span class="sxs-lookup"><span data-stu-id="60891-219">**Delete** the measure.</span></span>
- <span data-ttu-id="60891-220">**Aktyvuokite** arba **Deaktyvuokite**.</span><span class="sxs-lookup"><span data-stu-id="60891-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="60891-221">Suplanuoto atnaujinimo metu neaktyvūs duomenys nebus [atnaujinti](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="60891-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="60891-222">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="60891-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="60891-223">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="60891-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="60891-224">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="60891-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="60891-225">Pažymėję Peržiūrėti vienos iš užduoties užduočių išsamią informaciją rasite papildomos informacijos: apdorojimo laiko, paskutinio apdorojimo datos ir visų su užduotimi susijusių klaidų **ir įspėjimų**.</span><span class="sxs-lookup"><span data-stu-id="60891-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="60891-226">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="60891-226">Next step</span></span>

<span data-ttu-id="60891-227">Galite naudoti esamus priemones klientų [segmentui kurti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="60891-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
