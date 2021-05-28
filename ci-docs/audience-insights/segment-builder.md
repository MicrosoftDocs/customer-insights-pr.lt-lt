---
title: Segmentų kūrimas ir valdymas
description: Kurkite klientų segmentus, kad jie būtų sugrupuoti pagal įvairius atributus.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064947"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="37919-103">Segmentų kūrimas ir valdymas</span><span class="sxs-lookup"><span data-stu-id="37919-103">Create and manage segments</span></span>

<span data-ttu-id="37919-104">Apibrėžkite vieningojo kliento objekto ir su juo susijusių objektų sudėtinius filtrus.</span><span class="sxs-lookup"><span data-stu-id="37919-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="37919-105">Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus.</span><span class="sxs-lookup"><span data-stu-id="37919-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="37919-106">Segmentai yra valdomi **Segmentų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="37919-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="37919-107">Tolesnis pavyzdys rodo segmento pajėgumą.</span><span class="sxs-lookup"><span data-stu-id="37919-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="37919-108">Nustatėme klientų, kurie per paskutines 90 dienų užsisakė prekių bent už 500 $ *ir* kurie atliko klientų aptarnavimo skambutį, kuris buvo perskirtas, segmentą.</span><span class="sxs-lookup"><span data-stu-id="37919-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Segmento kūrimo priemonės vieningosios sąsajos su dvejomis grupėmis, nurodančiomis kliento segmentą, ekrano kopija.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="37919-110">Sukurkite naują segmentą</span><span class="sxs-lookup"><span data-stu-id="37919-110">Create a new segment</span></span>

<span data-ttu-id="37919-111">Naują segmentą galima sukurti keliais būdais.</span><span class="sxs-lookup"><span data-stu-id="37919-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="37919-112">Šiame skyriuje aprašoma, kaip sukurti *tuščią segmentą* nuo nulio.</span><span class="sxs-lookup"><span data-stu-id="37919-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="37919-113">Taip pat galite sukurti *spartųjį segmentą*, pagrįstą esamais objektais, arba naudoti mašininio mokymo modelį, kad gautumėte *siūlomus segmentus*.</span><span class="sxs-lookup"><span data-stu-id="37919-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="37919-114">Daugiau informacijos: [Segmentų apžvalga](segments.md).</span><span class="sxs-lookup"><span data-stu-id="37919-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="37919-115">Kurdami segmentą, jūs galite įrašyti juodraštį.</span><span class="sxs-lookup"><span data-stu-id="37919-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="37919-116">Jis bus įrašytas kaip neaktyvusis segmentas ir jo nebus galima suaktyvinti užbaigus jį naudojant tinkamą konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="37919-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="37919-117">Eikite į puslapį **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="37919-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="37919-118">Pasirinkite **Naujas** > **Tuščias segmentas**.</span><span class="sxs-lookup"><span data-stu-id="37919-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="37919-119">Srityje **Naujas segmentas** pasirinkite segmento tipą:</span><span class="sxs-lookup"><span data-stu-id="37919-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="37919-120">**Dinaminiai segmentai** [atnaujinami](segments.md#refresh-segments) pagal pasikartojantį grafiką.</span><span class="sxs-lookup"><span data-stu-id="37919-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="37919-121">**Statiniai segmentai** paleidžiami vieną kartą, kai juos kuriate.</span><span class="sxs-lookup"><span data-stu-id="37919-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="37919-122">Įveskite segmento **Išvesties objekto pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="37919-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="37919-123">Galite pasirinktinai nurodyti rodomą pavadinimą ir aprašą, padedantį identifikuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="37919-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="37919-124">Norėdami atidaryti **segmentų kūrimo priemonės** puslapį, kuriame apibrėžėte grupė, pasirinkite **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="37919-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="37919-125">Grupė yra klientų rinkinys.</span><span class="sxs-lookup"><span data-stu-id="37919-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="37919-126">Pasirinkite objektą, kuriame yra atributas, pagal kurį norite segmentuoti.</span><span class="sxs-lookup"><span data-stu-id="37919-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="37919-127">Pasirinkite atributą, pagal kurį norite segmentuoti.</span><span class="sxs-lookup"><span data-stu-id="37919-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="37919-128">Šis atributas gali turėti vieną iš keturių reikšmių tipų: skaičiaus, eilutės, datos arba Bulio.</span><span class="sxs-lookup"><span data-stu-id="37919-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="37919-129">Pasirinkite operatorių ir pasirinkto atributo reikšmę.</span><span class="sxs-lookup"><span data-stu-id="37919-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37919-130">![Pasirinktinis grupės filtras](media/customer-group-numbers.png "Klientų grupės filtras")</span><span class="sxs-lookup"><span data-stu-id="37919-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="37919-131">Skaičius</span><span class="sxs-lookup"><span data-stu-id="37919-131">Number</span></span> |<span data-ttu-id="37919-132">Apibrėžtis</span><span class="sxs-lookup"><span data-stu-id="37919-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="37919-133">1</span><span class="sxs-lookup"><span data-stu-id="37919-133">1</span></span>     |<span data-ttu-id="37919-134">Objektas</span><span class="sxs-lookup"><span data-stu-id="37919-134">Entity</span></span>          |
   |<span data-ttu-id="37919-135">2</span><span class="sxs-lookup"><span data-stu-id="37919-135">2</span></span>     |<span data-ttu-id="37919-136">Atributas</span><span class="sxs-lookup"><span data-stu-id="37919-136">Attribute</span></span>          |
   |<span data-ttu-id="37919-137">3</span><span class="sxs-lookup"><span data-stu-id="37919-137">3</span></span>    |<span data-ttu-id="37919-138">Operatorius</span><span class="sxs-lookup"><span data-stu-id="37919-138">Operator</span></span>         |
   |<span data-ttu-id="37919-139">4</span><span class="sxs-lookup"><span data-stu-id="37919-139">4</span></span>    |<span data-ttu-id="37919-140">Reikšmė</span><span class="sxs-lookup"><span data-stu-id="37919-140">Value</span></span>         |

   1. <span data-ttu-id="37919-141">Norėdami įtraukti daugiau sąlygų į grupę, galite naudoti du loginius operatorius:</span><span class="sxs-lookup"><span data-stu-id="37919-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="37919-142">Operatorius **IR**: abi sąlygos turi būti įvykdytos kaip segmentavimo proceso dalis.</span><span class="sxs-lookup"><span data-stu-id="37919-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="37919-143">Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.</span><span class="sxs-lookup"><span data-stu-id="37919-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="37919-144">Operatorius **ARBA**: viena iš sąlygų turi būti įvykdyta kaip segmentavimo proceso dalis.</span><span class="sxs-lookup"><span data-stu-id="37919-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="37919-145">Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.</span><span class="sxs-lookup"><span data-stu-id="37919-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="37919-146">![Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta](media/segmentation-either-condition.png "Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta")</span><span class="sxs-lookup"><span data-stu-id="37919-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="37919-147">Šiuo metu galima įtraukti operatorių **Arba** į operatorių **Ir**, o ne atvirkščiai.</span><span class="sxs-lookup"><span data-stu-id="37919-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="37919-148">Kiekviena grupė atitinka klientų rinkinį.</span><span class="sxs-lookup"><span data-stu-id="37919-148">Each group matches set of customers.</span></span> <span data-ttu-id="37919-149">Galite sujungti grupes, kad įtrauktumėte klientus, reikalingus jūsų veiklos atvejui.</span><span class="sxs-lookup"><span data-stu-id="37919-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="37919-150">Pažymėkite **Įtraukti grupę**.</span><span class="sxs-lookup"><span data-stu-id="37919-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="37919-151">![Klientų grupės grupės įtraukimas](media/customer-group-add-group.png "Klientų grupės grupės įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="37919-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="37919-152">Pažymėkite vieną iš rinkinio operatorių: **Sąjunga**, **Susikirtimas** arba **Išskyrus**.</span><span class="sxs-lookup"><span data-stu-id="37919-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37919-153">![Klientų grupės sujungimo įtraukimas](media/customer-group-union.png "Klientų grupės sujungimo įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="37919-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="37919-154">**Sujungimas** sujungia dvi grupes.</span><span class="sxs-lookup"><span data-stu-id="37919-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="37919-155">**Susikirtimas** persidengia su dviem grupėmis.</span><span class="sxs-lookup"><span data-stu-id="37919-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="37919-156">Tik duomenys, kurie *yra bendri* abiem grupėms yra laikomi vieningoje grupėje.</span><span class="sxs-lookup"><span data-stu-id="37919-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="37919-157">**Išskyrus** sujungia dvi grupes.</span><span class="sxs-lookup"><span data-stu-id="37919-157">**Except** combines the two groups.</span></span> <span data-ttu-id="37919-158">Laikomi tik duomenys, kurie yra A grupėje ir *nėra bendri* duomenims grupėje B.</span><span class="sxs-lookup"><span data-stu-id="37919-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="37919-159">Jei objektas yra sujungtas su sujungtu kliento objektu naudojant [ryšius](relationships.md), turite apibrėžti ryšio kelią, kad sukurtumėte tinkamą segmentą.</span><span class="sxs-lookup"><span data-stu-id="37919-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="37919-160">Įtraukite objektus iš ryšio kelio, kol išplečiamajame sąraše galėsite pasirinkti objektą **Customer : CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="37919-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="37919-161">Tada pasirinkite **Visi įrašai** kiekvienam veiksmui.</span><span class="sxs-lookup"><span data-stu-id="37919-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37919-162">![Ryšių kelias kuriant segmentą](media/segments-multiple-relationships.png "Ryšių kelias kuriant segmentą")</span><span class="sxs-lookup"><span data-stu-id="37919-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="37919-163">Pagal numatytuosius nustatymus, segmentai generuoja išvesties objektą, kuriame yra visi klientų profilių atributai, atitinkantys nustatytus filtrus.</span><span class="sxs-lookup"><span data-stu-id="37919-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="37919-164">Jei segmentas pagrįstas kitais objektais nei *Kliento* objektas, į išvesties objektą galite įtraukti daugiau atributų iš šių objektų.</span><span class="sxs-lookup"><span data-stu-id="37919-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="37919-165">Pažymėkite **Projekto atributai**, kad pasirinktumėte atributus, kurie bus pridėti prie išvesties objekto.</span><span class="sxs-lookup"><span data-stu-id="37919-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="37919-166">Pavyzdys: segmentas A yra pagrįstas objektu, kuriame yra kliento veiklos duomenų, susijusių su *Kliento* objektu.</span><span class="sxs-lookup"><span data-stu-id="37919-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="37919-167">Segmentas ieško visų klientų, skambinusių pagalbos tarnybai per pastarąsias 60 dienų.</span><span class="sxs-lookup"><span data-stu-id="37919-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="37919-168">Galite pasirinkti pridėti skambučio trukmę ir skambučių skaičių prie visų sutampančių išvesties objekto kliento įrašų.</span><span class="sxs-lookup"><span data-stu-id="37919-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="37919-169">Ši informacija gali būti naudinga siunčiant el. laišką su naudingomis nuorodomis į internetinius žinyno straipsnius ir DUK dažnai skambinusiems klientams.</span><span class="sxs-lookup"><span data-stu-id="37919-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="37919-170">Suplanuoti atributai veikia tik tiems objektams, kurie turi „vienas su daugeliu” ryšį su kliento objektu.</span><span class="sxs-lookup"><span data-stu-id="37919-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="37919-171">Pavyzdžiui, vienas klientas gali turėti kelias prenumeratas.</span><span class="sxs-lookup"><span data-stu-id="37919-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="37919-172">Suplanuoti atributus galite tik iš to objekto, kuris yra naudojamas kiekvienoje jūsų kuriamų segmentų užklausų grupėje.</span><span class="sxs-lookup"><span data-stu-id="37919-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="37919-173">Suplanuoti atributai yra įtraukiami naudojant rinkinio operatorius.</span><span class="sxs-lookup"><span data-stu-id="37919-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="37919-174">Pasirinkite **Įrašyti**, kad įrašytumėte segmentą.</span><span class="sxs-lookup"><span data-stu-id="37919-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="37919-175">Jūsų segmentas bus įrašytas ir apdorojamas, jei visi reikalavimai bus patvirtinti.</span><span class="sxs-lookup"><span data-stu-id="37919-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="37919-176">Kitu atveju jis bus Išsaugota kaip juodraštis.</span><span class="sxs-lookup"><span data-stu-id="37919-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="37919-177">Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="37919-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="37919-178">Spartieji segmentai</span><span class="sxs-lookup"><span data-stu-id="37919-178">Quick segments</span></span>

<span data-ttu-id="37919-179">Spartieji segmentai leidžia jums greitai sukurti paprastus segmentus naudojant vieną operatorių, kad įžvalgos būtų greitesnės.</span><span class="sxs-lookup"><span data-stu-id="37919-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="37919-180">Puslapyje **Segmentai** pasirinkite **Naujas** > **Kurti iš**.</span><span class="sxs-lookup"><span data-stu-id="37919-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="37919-181">Pažymėkite parinktį **Profiliai**, kad sukurtumėte segmentą, pagrįstą *vieningojo klientu* objektu.</span><span class="sxs-lookup"><span data-stu-id="37919-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="37919-182">Pažymėkite parinktį **Matavimai**, kad sukurtumėte segmentą pagal anksčiau jūsų sukurtus matavimus.</span><span class="sxs-lookup"><span data-stu-id="37919-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="37919-183">Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.</span><span class="sxs-lookup"><span data-stu-id="37919-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="37919-184">Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**.</span><span class="sxs-lookup"><span data-stu-id="37919-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="37919-185">Sistema pateiks keletą papildomų įžvalgų, kurios padės kurti geresnius klientų segmentus.</span><span class="sxs-lookup"><span data-stu-id="37919-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="37919-186">Pagal kategorinius laukus parodysime 10 geriausių klientų skaičių.</span><span class="sxs-lookup"><span data-stu-id="37919-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="37919-187">Pasirinkite **Reikšmė** ir pažymėkite **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="37919-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="37919-188">Jei yra skaičiaus atributas, sistema parodys, kokią atributo reikšmę turi kiekvienas kliento procentilis.</span><span class="sxs-lookup"><span data-stu-id="37919-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="37919-189">Pasirinkite **operatorių** ir **reikšmę**, tada pažymėktie **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="37919-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="37919-190">Sistema parodys **numatomą segmento dydį**.</span><span class="sxs-lookup"><span data-stu-id="37919-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="37919-191">Galite pasirinkti, ar generuoti apibrėžtą segmentą arba iš naujo jį peržiūrėti ir gauti kitą segmento dydį.</span><span class="sxs-lookup"><span data-stu-id="37919-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="37919-192">![Sparčiojo segmento pavadinimas ir įvertinimas](media/quick-segment-name.png "Sparčiojo segmento pavadinimas ir įvertinimas")</span><span class="sxs-lookup"><span data-stu-id="37919-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="37919-193">Įveskite segmento **Pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="37919-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="37919-194">Pasirinktinai įveskite **rodomą pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="37919-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="37919-195">Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą.</span><span class="sxs-lookup"><span data-stu-id="37919-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="37919-196">Kai segmento apdorojimas baigtas, jį galite peržiūrėti kaip bet kurį kitą sukurtą segmentą.</span><span class="sxs-lookup"><span data-stu-id="37919-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="37919-197">Paskesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="37919-197">Next steps</span></span>

<span data-ttu-id="37919-198">[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [kliento kortele](customer-card-add-in.md) bei [jungtimis](export-power-bi.md), kad gautumėte įžvalgų apie kliento lygį.</span><span class="sxs-lookup"><span data-stu-id="37919-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
