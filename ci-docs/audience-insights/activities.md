---
title: Kliento veiklos
description: Nustatykite kliento veiklas ir peržiūrėkite jas kliento laiko juostoje.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866417"
---
# <a name="customer-activities"></a><span data-ttu-id="63b5b-103">Kliento veiklos</span><span class="sxs-lookup"><span data-stu-id="63b5b-103">Customer activities</span></span>

<span data-ttu-id="63b5b-104">Suderinkite kliento veiklą iš [įvairių duomenų šaltinių](data-sources.md) sistemoje Dynamics 365 Customer Insights, kad sukurtumėte laiko juostą, kurioje veiklos sąrašas pateikiamas chronologine tvarka.</span><span class="sxs-lookup"><span data-stu-id="63b5b-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="63b5b-105">Laiko planavimo juostą įtraukite į „Dynamics 365“ programas naudodami sprendimą [Kliento kortelės priedas](customer-card-add-in.md) arba Power BI ataskaitų sritį.</span><span class="sxs-lookup"><span data-stu-id="63b5b-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="63b5b-106">Veiklos apibrėžimas</span><span class="sxs-lookup"><span data-stu-id="63b5b-106">Define an activity</span></span>

<span data-ttu-id="63b5b-107">Jūsų duomenų šaltiniuose gali būti objektų su operacijų ir veiklos duomenimis iš kelių duomenų šaltinių.</span><span class="sxs-lookup"><span data-stu-id="63b5b-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="63b5b-108">Identifikuokite šiuos objektus ir pasirinkite veiklas, kurias norite peržiūrėti kliento laiko planavimo juostoje.</span><span class="sxs-lookup"><span data-stu-id="63b5b-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="63b5b-109">Pasirinkite objektą, kuriame yra jūsų tikslinė veikla arba veiklos.</span><span class="sxs-lookup"><span data-stu-id="63b5b-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="63b5b-110">Objekte turi būti bent vienas **Data** tipo atributas, kurį reikia įtraukti į kliento planavimo juostą; negalite įtraukti objektų be **Data** laukų.</span><span class="sxs-lookup"><span data-stu-id="63b5b-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="63b5b-111">Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.</span><span class="sxs-lookup"><span data-stu-id="63b5b-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="63b5b-112">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="63b5b-113">Pasirinkite **Pridėti veiklą**, jei norite pradėti valdomą patirtį veiklos nustatymo procesui.</span><span class="sxs-lookup"><span data-stu-id="63b5b-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="63b5b-114">Žingsnyje **Veiklos duomenys** nustatykite šių laukelių reikšmes:</span><span class="sxs-lookup"><span data-stu-id="63b5b-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="63b5b-115">**Veiklos pavadinimas**: pasirinkite savo veiklos pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="63b5b-116">**Objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="63b5b-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="63b5b-117">**Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="63b5b-118">Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.</span><span class="sxs-lookup"><span data-stu-id="63b5b-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nustatykite veiklos duomenis su pavadinimu, objektu ir pagrindiniu raktu.":::

1. <span data-ttu-id="63b5b-120">Norėdami pereiti prie kito veiksmo, pasinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="63b5b-121">Atlikdami veiksmą **Santykis** konfigūruokite išsamią informaciją, kad veiklos duomenys būtų susieti su atitinkamu klientu.</span><span class="sxs-lookup"><span data-stu-id="63b5b-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="63b5b-122">Šiuo veiksmu vaizduojamas objektų ryšys.</span><span class="sxs-lookup"><span data-stu-id="63b5b-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="63b5b-123">**Pirma:** veiklos objekto, kuris bus naudojamas ryšiui su kitu objektu užmegzti, laukelis „Svetimas“.</span><span class="sxs-lookup"><span data-stu-id="63b5b-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="63b5b-124">**Antra:** atitinkamas šaltinio kliento objektas, su kuriuo sąveikaus jūsų veiklos objektas.</span><span class="sxs-lookup"><span data-stu-id="63b5b-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="63b5b-125">Ryšį galite nustatyti tik su tais šaltinio kliento objektais, kurie naudojami duomenų suvienodinimo procese.</span><span class="sxs-lookup"><span data-stu-id="63b5b-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="63b5b-126">**Trečia:** jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas veiks tik skaitymo režimu.</span><span class="sxs-lookup"><span data-stu-id="63b5b-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="63b5b-127">Jei tokio ryšio nėra, bus sukurtas naujas ryšys tokiu pavadinimu, kurį pateikiate šiame laukelyje.</span><span class="sxs-lookup"><span data-stu-id="63b5b-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Objekto ryšio apibrėžimas.":::

1. <span data-ttu-id="63b5b-129">Norėdami pereiti prie kito veiksmo, pasinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="63b5b-130">**Veiklos suvienodinimo** žingsnyje pasirinkite veiklos įvykį ir veiklos pradžios laiką.</span><span class="sxs-lookup"><span data-stu-id="63b5b-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="63b5b-131">**Būtini laukai**</span><span class="sxs-lookup"><span data-stu-id="63b5b-131">**Required fields**</span></span>
      1. <span data-ttu-id="63b5b-132">**Įvykio veikla**: laukelis, kuris yra šios veiklos įvykis</span><span class="sxs-lookup"><span data-stu-id="63b5b-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="63b5b-133">**Laiko žyma**: laukelis, nurodantis jūsų veiklos pradžios laiką.</span><span class="sxs-lookup"><span data-stu-id="63b5b-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="63b5b-134">**Pasirinktiniai laukai**</span><span class="sxs-lookup"><span data-stu-id="63b5b-134">**Optional fields**</span></span>
      1. <span data-ttu-id="63b5b-135">**Papildoma informacija**: laukelis su svarbia šios veiklos informacija.</span><span class="sxs-lookup"><span data-stu-id="63b5b-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="63b5b-136">**Piktograma:** piktograma, geriausiai atspindinti šį veiklos tipą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="63b5b-137">**Žiniatinklio adresas**: laukelis, kuriame yra URL su informacija apie šią veiklą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="63b5b-138">Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai.</span><span class="sxs-lookup"><span data-stu-id="63b5b-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="63b5b-139">Šis URL gali būti bet kuris laukas iš duomenų šaltinio arba jį galima sukurti kaip naują lauką naudojant „Power Query“ transformaciją.</span><span class="sxs-lookup"><span data-stu-id="63b5b-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="63b5b-140">URL duomenys bus išsaugoti *Unified Activity* objektui, kurį galima naudoti tolesniuose srautuose naudojant [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="63b5b-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Kliento veiklos duomenis nurodykite „Unified Activity“ objekte.":::

1. <span data-ttu-id="63b5b-142">Norėdami pereiti prie kito veiksmo, pasirinkite **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="63b5b-143">Galite pažymėti **Baigti ir peržiūrėti**, kad veiklą įrašytumėte dabar, kai veiklos tipas nustatytas kaip **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="63b5b-144">Žingsnyje **Veiklos tipas** pasirinkite veiklos tipą ir pasirinktinai pažymėkite, ar norite po kelis veiklos tipus susieti ir naudoti kitose „Customer Insights“ srityse.</span><span class="sxs-lookup"><span data-stu-id="63b5b-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="63b5b-145">Šiuo metu veiklos tipus *Prenumerata* & *SalesOrderLine* galima semantiškai susieti sutikus susieti laukelius.</span><span class="sxs-lookup"><span data-stu-id="63b5b-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="63b5b-146">Jei veiklos tipas nėra aktualus naujai veiklai, galite pasirinkti *Kita* arba *Kurti naują* pasirinktinio veiklos tipo atveju.</span><span class="sxs-lookup"><span data-stu-id="63b5b-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="63b5b-147">Norėdami pereiti prie kito veiksmo, pasirinkite **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="63b5b-148">Žingsnyje **Atsiliepimas** patikrinkite savo pasirinkimus.</span><span class="sxs-lookup"><span data-stu-id="63b5b-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="63b5b-149">Galite grįžti prie bet kurio iš ankstesnių veiksmų ir, jei reikia, atnaujinti informaciją.</span><span class="sxs-lookup"><span data-stu-id="63b5b-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Peržiūrėkite nurodytus veiklos laukelius.":::
   
1. <span data-ttu-id="63b5b-151">Pasirinkite **Įrašyti veiklą**, kad pritaikytumėte pakeitimus, ir pasirinkite **Atlikta**, kad grįžtumėte prie **Duomenys** > **Veikla**.</span><span class="sxs-lookup"><span data-stu-id="63b5b-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="63b5b-152">Čia matote, kurios veiklos nustatytos būti rodomos laiko planavimo juostoje.</span><span class="sxs-lookup"><span data-stu-id="63b5b-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="63b5b-153">Puslapyje **Veiklos** pasirinkite **Vykdyti**, kad apdorotumėte veiklą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="63b5b-154">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="63b5b-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="63b5b-155">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="63b5b-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="63b5b-156">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="63b5b-157">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="63b5b-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="63b5b-158">Esamos veiklos tvarkymas</span><span class="sxs-lookup"><span data-stu-id="63b5b-158">Manage existing activities</span></span>

<span data-ttu-id="63b5b-159">Srityje **Duomenys** > **Veikla** galite peržiūrėti visas įrašytas veiklas ir jas valdyti.</span><span class="sxs-lookup"><span data-stu-id="63b5b-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="63b5b-160">Kiekvienai veiklai skiriama eilutė, kurioje taip pat pateikiama išsami informacija apie šaltinį, objektą ir veiklos tipą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="63b5b-161">Pasirinkus veiklą galimi nurodyti veiksmai.</span><span class="sxs-lookup"><span data-stu-id="63b5b-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="63b5b-162">**Redaguoti**: peržiūros žingsnyje atidaro veiklos sąranką.</span><span class="sxs-lookup"><span data-stu-id="63b5b-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="63b5b-163">Atlikdami šį veiksmą galite keisti bet kurią arba visą dabartinę konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="63b5b-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="63b5b-164">Pakeitę konfigūraciją, pasirinkite **Įrašyti veiklą**, tada pasirinkite **Vykdyti**, kad būtų apdoroti pakeitimai.</span><span class="sxs-lookup"><span data-stu-id="63b5b-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="63b5b-165">**Pervadinti**: atidaromas dialogas, kuriame galima įvesti kitą pažymėtos veiklos pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="63b5b-166">Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.</span><span class="sxs-lookup"><span data-stu-id="63b5b-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="63b5b-167">**Trinti**: atidaro dialogą, kad patvirtintų pažymėtos veiklos trynimą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="63b5b-168">Taip pat iš karto galite ištrinti daugiau nei vieną veiklą, pažymėdami veiklas ir pažymėdami trynimo piktogramą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="63b5b-169">Pasirinkite **Trinti** ir patvirtinkite ištrynimą.</span><span class="sxs-lookup"><span data-stu-id="63b5b-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
