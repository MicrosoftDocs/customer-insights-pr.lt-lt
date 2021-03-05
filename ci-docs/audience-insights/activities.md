---
title: Kliento veiklos
description: Nustatykite kliento vieklas ir peržiūrėkite jas kliento laiko juostoje.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267442"
---
# <a name="customer-activities"></a><span data-ttu-id="278ce-103">Kliento veiklos</span><span class="sxs-lookup"><span data-stu-id="278ce-103">Customer activities</span></span>

<span data-ttu-id="278ce-104">Derinkite kliento veiklas per [įvairius duomenų šaltinius](data-sources.md) „Dynamics 365 Customer Insights“ norėdami sukurti kliento laiko juostą, kurioje pateiktos veiklos chronologine tvarka.</span><span class="sxs-lookup"><span data-stu-id="278ce-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="278ce-105">Galite įtraukti laiko planavimo juostą į klientų įtraukimo programas, esančias „Dynamics 365”, per [Kliento kortelės papildinį](customer-card-add-in.md) arba „Power BI” ataskaitų sritį.</span><span class="sxs-lookup"><span data-stu-id="278ce-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="278ce-106">Veiklos apibrėžimas</span><span class="sxs-lookup"><span data-stu-id="278ce-106">Define an activity</span></span>

<span data-ttu-id="278ce-107">Jūsų duomenų šaltiniuose yra objektų su operacijų ir veiklos duomenimis iš kelių duomenų šaltinių.</span><span class="sxs-lookup"><span data-stu-id="278ce-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="278ce-108">Identifikuokite šiuos objektus ir pasirinkite veiklas, kurias norite peržiūrėti kliento laiko planavimo juostoje.</span><span class="sxs-lookup"><span data-stu-id="278ce-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="278ce-109">Pasirinkite objektą, kuriame yra jūsų tikslinė veikla arba veiklos.</span><span class="sxs-lookup"><span data-stu-id="278ce-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="278ce-110">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="278ce-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="278ce-111">Pasirinkti **Įtraukti veiklą**.</span><span class="sxs-lookup"><span data-stu-id="278ce-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="278ce-112">Objekte turi būti bent vienas **Data** tipo atributas, kurį reikia įtraukti į kliento planavimo juostą; negalite įtraukti objektų be **Data** laukų.</span><span class="sxs-lookup"><span data-stu-id="278ce-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="278ce-113">Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.</span><span class="sxs-lookup"><span data-stu-id="278ce-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="278ce-114">Srityje **įtraukti veiklą** nustatykite šių laukų reikšmes:</span><span class="sxs-lookup"><span data-stu-id="278ce-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="278ce-115">**Objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="278ce-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="278ce-116">**Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą.</span><span class="sxs-lookup"><span data-stu-id="278ce-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="278ce-117">Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.</span><span class="sxs-lookup"><span data-stu-id="278ce-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="278ce-118">**Laiko žyma**: pasirinkite lauką, kuris nurodo veiklos pradžios laiką.</span><span class="sxs-lookup"><span data-stu-id="278ce-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="278ce-119">**Įvykis**: pasirinkite lauką, kuris yra veiklos įvykis.</span><span class="sxs-lookup"><span data-stu-id="278ce-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="278ce-120">**Žiniatinklio adresas**: pažymėkite lauką, kuris nurodo URL, skirtą papildomai informacijai apie šią veiklą.</span><span class="sxs-lookup"><span data-stu-id="278ce-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="278ce-121">Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai.</span><span class="sxs-lookup"><span data-stu-id="278ce-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="278ce-122">Šis URL gali būti bet kuris laukas iš duomenų šaltinio arba jį galima sukurti kaip naują lauką naudojant „Power Query“ transformaciją.</span><span class="sxs-lookup"><span data-stu-id="278ce-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="278ce-123">Šie URL duomenys bus saugomi vieningosios veiklos objekte, kurį galima pasiekti naudojant API.</span><span class="sxs-lookup"><span data-stu-id="278ce-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="278ce-124">**Išsami informacija**: (pasirinktinai) pasirinkite lauką, įtrauktą į papildomą išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="278ce-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="278ce-125">**Piktograma**: (pasirinktinai) pasirinkite piktogramą, vaizduojančią šią veiklą.</span><span class="sxs-lookup"><span data-stu-id="278ce-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="278ce-126">**Veiklos tipas**: nustatykite veiklos tipo nuorodą į „Common Data Model“, kuris geriausiai atitinka veiklos semantinį apibrėžimą.</span><span class="sxs-lookup"><span data-stu-id="278ce-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="278ce-127">Skyriuje **Nustatyti ryšį** konfigūruokite išsamią informaciją, kad savo veiklos duomenis prijungtumėte prie atitinkamo kliento.</span><span class="sxs-lookup"><span data-stu-id="278ce-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="278ce-128">**Veiklos objekto laukas**: pasirinkite veiklos objekto lauką, kuris bus naudojamas ryšiui su kitu objektu nustatyti.</span><span class="sxs-lookup"><span data-stu-id="278ce-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="278ce-129">**Kliento objektas**: pasirinkite atitinkamą šaltinio kliento objektą, su kuriuo bus nustatytas jūsų veiklos objekto ryšys.</span><span class="sxs-lookup"><span data-stu-id="278ce-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="278ce-130">Galite susieti tik su tais šaltinio kliento objektais, kurie naudojami duomenų sujungimo procese.</span><span class="sxs-lookup"><span data-stu-id="278ce-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="278ce-131">**Kliento objekto laukas**: šiame lauke rodomas šaltinio kliento objekto, pasirinkto susiejimo procese, pagrindinis raktas.</span><span class="sxs-lookup"><span data-stu-id="278ce-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="278ce-132">Šis šaltinio kliento objekto pagrindinio rakto laukas naudojamas ryšiui su veiklos objektu nustatyti.</span><span class="sxs-lookup"><span data-stu-id="278ce-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="278ce-133">**Pavadinimas**: jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas bus rodomas skaitymo režimu.</span><span class="sxs-lookup"><span data-stu-id="278ce-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="278ce-134">Jei tokio ryšio nėra, bus sukurtas naujas ryšys su pateiktu pavadinimu.</span><span class="sxs-lookup"><span data-stu-id="278ce-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="278ce-135">![Objekto ryšio apibrėžimas](media/activities-entities-define.png "Objekto ryšio apibrėžimas")</span><span class="sxs-lookup"><span data-stu-id="278ce-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="278ce-136">Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.</span><span class="sxs-lookup"><span data-stu-id="278ce-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="278ce-137">Puslapyje **Veiklos** pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="278ce-138">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="278ce-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="278ce-139">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="278ce-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="278ce-140">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="278ce-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="278ce-141">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="278ce-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="278ce-142">Veiklos redagavimas</span><span class="sxs-lookup"><span data-stu-id="278ce-142">Edit an activity</span></span>

1. <span data-ttu-id="278ce-143">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="278ce-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="278ce-144">Pasirinkite veiklos objektą, kurį norite redaguoti, ir spustelėkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="278ce-145">Arba galite užvesti žymiklį virš objekto eilutės ir spustelėti piktogramą **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="278ce-146">Spustelėkite piktogramą **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="278ce-147">Srityje **Redaguoti veiklą** atnaujinkite reikšmes ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="278ce-148">Puslapyje **Veiklos** pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="278ce-149">Veiklos panaikinimas</span><span class="sxs-lookup"><span data-stu-id="278ce-149">Delete an activity</span></span>

1. <span data-ttu-id="278ce-150">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="278ce-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="278ce-151">Pasirinkite veiklos objektą, kurį norite pašalinti, ir spustelėkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="278ce-152">Arba galite užvesti žymiklį virš objekto eilutės ir spustelėti piktogramą **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="278ce-153">Be to, galite pažymėti kelis veiklos objektus, kuriuos norite panaikinti vienu metu.</span><span class="sxs-lookup"><span data-stu-id="278ce-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="278ce-154">![Objekto ryšio redagavimas arba naikinimas](media/activities-entities-edit-delete.png "Objekto ryšio redagavimas arba naikinimas")</span><span class="sxs-lookup"><span data-stu-id="278ce-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="278ce-155">Spustelėkite piktogramą **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="278ce-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="278ce-156">Patvirtinkite šį naikinimą.</span><span class="sxs-lookup"><span data-stu-id="278ce-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]