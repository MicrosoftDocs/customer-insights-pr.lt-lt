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
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667239"
---
# <a name="customer-activities"></a><span data-ttu-id="14b48-103">Kliento veiklos</span><span class="sxs-lookup"><span data-stu-id="14b48-103">Customer activities</span></span>

<span data-ttu-id="14b48-104">Derinkite kliento veiklas per [įvairius duomenų šaltinius](data-sources.md) „Dynamics 365 Customer Insights“ norėdami sukurti kliento laiko juostą, kurioje pateiktos veiklos chronologine tvarka.</span><span class="sxs-lookup"><span data-stu-id="14b48-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="14b48-105">Galite įtraukti laiko planavimo juostą į klientų įtraukimo programas, esančias „Dynamics 365”, per [Kliento kortelės papildinį](customer-card-add-in.md) arba „Power BI” ataskaitų sritį.</span><span class="sxs-lookup"><span data-stu-id="14b48-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="14b48-106">Veiklos apibrėžimas</span><span class="sxs-lookup"><span data-stu-id="14b48-106">Define an activity</span></span>

<span data-ttu-id="14b48-107">Jūsų duomenų šaltiniuose yra objektų su operacijų ir veiklos duomenimis iš kelių duomenų šaltinių.</span><span class="sxs-lookup"><span data-stu-id="14b48-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="14b48-108">Identifikuokite šiuos objektus ir pasirinkite veiklas, kurias norite peržiūrėti kliento laiko planavimo juostoje.</span><span class="sxs-lookup"><span data-stu-id="14b48-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="14b48-109">Pasirinkite objektą, kuriame yra jūsų tikslinė veikla arba veiklos.</span><span class="sxs-lookup"><span data-stu-id="14b48-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="14b48-110">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="14b48-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="14b48-111">Pasirinkti **Įtraukti veiklą**.</span><span class="sxs-lookup"><span data-stu-id="14b48-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="14b48-112">Objekte turi būti bent vienas **Data** tipo atributas, kurį reikia įtraukti į kliento planavimo juostą; negalite įtraukti objektų be **Data** laukų.</span><span class="sxs-lookup"><span data-stu-id="14b48-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="14b48-113">Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.</span><span class="sxs-lookup"><span data-stu-id="14b48-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="14b48-114">Srityje **įtraukti veiklą** nustatykite šių laukų reikšmes:</span><span class="sxs-lookup"><span data-stu-id="14b48-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="14b48-115">**Objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="14b48-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="14b48-116">**Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą.</span><span class="sxs-lookup"><span data-stu-id="14b48-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="14b48-117">Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.</span><span class="sxs-lookup"><span data-stu-id="14b48-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="14b48-118">**Laiko žyma**: pasirinkite lauką, kuris nurodo veiklos pradžios laiką.</span><span class="sxs-lookup"><span data-stu-id="14b48-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="14b48-119">**Įvykis**: pasirinkite lauką, kuris yra veiklos įvykis.</span><span class="sxs-lookup"><span data-stu-id="14b48-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="14b48-120">**Žiniatinklio adresas**: pažymėkite lauką, kuris nurodo URL, skirtą papildomai informacijai apie šią veiklą.</span><span class="sxs-lookup"><span data-stu-id="14b48-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="14b48-121">Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai.</span><span class="sxs-lookup"><span data-stu-id="14b48-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="14b48-122">Šis URL gali būti bet kuris laukas iš duomenų šaltinio arba jį galima sukurti kaip naują lauką naudojant „Power Query“ transformaciją.</span><span class="sxs-lookup"><span data-stu-id="14b48-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="14b48-123">Šie URL duomenys bus saugomi vieningosios veiklos objekte, kurį galima pasiekti naudojant API.</span><span class="sxs-lookup"><span data-stu-id="14b48-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="14b48-124">**Išsami informacija**: (pasirinktinai) pasirinkite lauką, įtrauktą į papildomą išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="14b48-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="14b48-125">**Piktograma**: (pasirinktinai) pasirinkite piktogramą, vaizduojančią šią veiklą.</span><span class="sxs-lookup"><span data-stu-id="14b48-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="14b48-126">**Veiklos tipas**: nustatykite veiklos tipo nuorodą į „Common Data Model“, kuris geriausiai atitinka veiklos semantinį apibrėžimą.</span><span class="sxs-lookup"><span data-stu-id="14b48-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="14b48-127">Skyriuje **Nustatyti ryšį** konfigūruokite išsamią informaciją, kad savo veiklos duomenis prijungtumėte prie atitinkamo kliento.</span><span class="sxs-lookup"><span data-stu-id="14b48-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14b48-128">![Objekto ryšio apibrėžimas](media/activities-entities-define.png "Objekto ryšio apibrėžimas")</span><span class="sxs-lookup"><span data-stu-id="14b48-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="14b48-129">**Veiklos objekto laukas**: pasirinkite veiklos objekto lauką, kuris bus naudojamas ryšiui su kitu objektu nustatyti.</span><span class="sxs-lookup"><span data-stu-id="14b48-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="14b48-130">**Kliento objektas**: pasirinkite atitinkamą šaltinio kliento objektą, su kuriuo bus nustatytas jūsų veiklos objekto ryšys.</span><span class="sxs-lookup"><span data-stu-id="14b48-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="14b48-131">Galite susieti tik su tais šaltinio kliento objektais, kurie naudojami duomenų sujungimo procese.</span><span class="sxs-lookup"><span data-stu-id="14b48-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="14b48-132">**Kliento objekto laukas**: šiame lauke rodomas šaltinio kliento objekto, pasirinkto susiejimo procese, pagrindinis raktas.</span><span class="sxs-lookup"><span data-stu-id="14b48-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="14b48-133">Šis šaltinio kliento objekto pagrindinio rakto laukas naudojamas ryšiui su veiklos objektu nustatyti.</span><span class="sxs-lookup"><span data-stu-id="14b48-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="14b48-134">**Pavadinimas**: jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas bus rodomas skaitymo režimu.</span><span class="sxs-lookup"><span data-stu-id="14b48-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="14b48-135">Jei tokio ryšio nėra, bus sukurtas naujas ryšys su pateiktu pavadinimu.</span><span class="sxs-lookup"><span data-stu-id="14b48-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="14b48-136">Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.</span><span class="sxs-lookup"><span data-stu-id="14b48-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="14b48-137">Puslapyje **Veiklos** pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="14b48-138">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="14b48-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="14b48-139">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="14b48-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="14b48-140">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="14b48-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="14b48-141">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="14b48-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="14b48-142">Veiklos redagavimas</span><span class="sxs-lookup"><span data-stu-id="14b48-142">Edit an activity</span></span>

1. <span data-ttu-id="14b48-143">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="14b48-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="14b48-144">Pasirinkite veiklos objektą, kurį norite redaguoti, ir spustelėkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="14b48-145">Arba galite užvesti žymiklį virš objekto eilutės ir spustelėti piktogramą **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="14b48-146">Spustelėkite piktogramą **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="14b48-147">Srityje **Redaguoti veiklą** atnaujinkite reikšmes ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="14b48-148">Puslapyje **Veiklos** pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="14b48-149">Veiklos panaikinimas</span><span class="sxs-lookup"><span data-stu-id="14b48-149">Delete an activity</span></span>

1. <span data-ttu-id="14b48-150">Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.</span><span class="sxs-lookup"><span data-stu-id="14b48-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="14b48-151">Pasirinkite veiklos objektą, kurį norite pašalinti, ir spustelėkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="14b48-152">Arba galite užvesti žymiklį virš objekto eilutės ir spustelėti piktogramą **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="14b48-153">Be to, galite pažymėti kelis veiklos objektus, kuriuos norite panaikinti vienu metu.</span><span class="sxs-lookup"><span data-stu-id="14b48-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14b48-154">![Objekto ryšio redagavimas arba naikinimas](media/activities-entities-edit-delete.png "Objekto ryšio redagavimas arba naikinimas")</span><span class="sxs-lookup"><span data-stu-id="14b48-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="14b48-155">Spustelėkite piktogramą **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="14b48-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="14b48-156">Patvirtinkite šį naikinimą.</span><span class="sxs-lookup"><span data-stu-id="14b48-156">Confirm your deletion.</span></span>
