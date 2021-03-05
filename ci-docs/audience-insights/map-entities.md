---
title: Sudarykite objektų žemėlapį duomenų suvienodinimui
description: Sudarykite duomenų žemėlapį tam, kad sukurtumėte suvienodintus klientų profilius.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267045"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="e5197-103">Susiekite objektus ir atributus</span><span class="sxs-lookup"><span data-stu-id="e5197-103">Map entities and attributes</span></span>

<span data-ttu-id="e5197-104">**Žemėlapis** yra pirmasis etapas duomenų suvienodinimo publikos įžvalgų procese.</span><span class="sxs-lookup"><span data-stu-id="e5197-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="e5197-105">Susiejimą sudaro trys etapai:</span><span class="sxs-lookup"><span data-stu-id="e5197-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="e5197-106">*Objekto pasirinkimas*: nustatykite suderinamus objektus, kurie nukreipia į duomenų rinkinį su išsamesne informacija apie jūsų klientus.</span><span class="sxs-lookup"><span data-stu-id="e5197-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="e5197-107">*Atributo pasirinkimas*: kiekvienam objektui nustatykite stulpelius, kuriuos norite sujungti ir suderinti *atitikimo* ir *sujungimo* etapuose.</span><span class="sxs-lookup"><span data-stu-id="e5197-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="e5197-108">Šie stulpeliai yra vadinami *Atributais*.</span><span class="sxs-lookup"><span data-stu-id="e5197-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="e5197-109">*Pirminio rakto ir semantinio tipo pasirinkimas*: kiekvienam objektui nustatykite atributą, kurį norite apibrėžti kaip to objekto pirminį raktą, ir kiekvienam atributui nustatykite semantinį tipą, geriausiai apibūdinantį tą atributą.</span><span class="sxs-lookup"><span data-stu-id="e5197-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="e5197-110">Daugiau informacijos apie bendrą duomenų suvienodinimo srautą galite rasti čia [Suvienodinti](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="e5197-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="e5197-111">Pasirinkti pirmus objektus</span><span class="sxs-lookup"><span data-stu-id="e5197-111">Select the first entities</span></span>

1. <span data-ttu-id="e5197-112">Publikos įžvalgose, eikite į **Duomenys** > **Sujungti** > **Žemėlapis**.</span><span class="sxs-lookup"><span data-stu-id="e5197-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="e5197-113">Pradėkite schemos etapą pasirinkdami **Pasirinkti objektus**.</span><span class="sxs-lookup"><span data-stu-id="e5197-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="e5197-114">Pasirinkite objektus ir atributus, kuriuos norite naudoti *gretinimo* ir *suliejimo* etapuose.</span><span class="sxs-lookup"><span data-stu-id="e5197-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="e5197-115">Reikiamus atributus galite pasirinkti atskirai iš objekto arba įtraukti visus objekto atributus pažymėdami žymės langelį **Įtraukti visus laukus** objekto lygyje.</span><span class="sxs-lookup"><span data-stu-id="e5197-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="e5197-116">Rekomenduojame pasirinkti bent du objektus, kad duomenų suvienijimo procesas būtų naudingas.</span><span class="sxs-lookup"><span data-stu-id="e5197-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e5197-117">![Įtraukti objektų pavyzdį](media/data-manager-configure-map-add-entities-example.png "Įtraukti objektų pavyzdį")</span><span class="sxs-lookup"><span data-stu-id="e5197-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="e5197-118">Šiame pavyzdyje įtraukiame objektus **eCommerceContacts** ir **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e5197-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="e5197-119">Pasirinkę šiuos objektus galite gauti įžvalgų apie tai, kurie internetinio verslo klientai yra lojalumo programos nariai.</span><span class="sxs-lookup"><span data-stu-id="e5197-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="e5197-120">Galite ieškoti raktažodžių visuose atributuose ir objektuose, kad pasirinktumėte reikiamus atributus, kuriuos norite susieti.</span><span class="sxs-lookup"><span data-stu-id="e5197-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e5197-121">![Laukų ieškos pavyzdys](media/data-manager-configure-map-search-fields-example.png "Laukų ieškos pavyzdys")</span><span class="sxs-lookup"><span data-stu-id="e5197-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="e5197-122">Pasirinkite **Taikyti**, kad patvirtintumėte pasirinkimus.</span><span class="sxs-lookup"><span data-stu-id="e5197-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="e5197-123">Pirminio rakto ir atributų semantinio tipo pasirinkimas</span><span class="sxs-lookup"><span data-stu-id="e5197-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="e5197-124">Pasirinkus objektus, puslapyje **Susieti** išvardijami pasirinkti objektai, kad galėtumėte juos peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="e5197-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="e5197-125">Apibrėžkite objekto pirminį raktą ir nurodykite objekto atributo semantinį tipą.</span><span class="sxs-lookup"><span data-stu-id="e5197-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="e5197-126">**Pirminis raktas**: kiekvienam savo objektui pasirinkite vieną atributą kaip pirminį raktą.</span><span class="sxs-lookup"><span data-stu-id="e5197-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="e5197-127">Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių.</span><span class="sxs-lookup"><span data-stu-id="e5197-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="e5197-128">Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai ir bus rodomi lauke, kad galėtumėte pasirinkti.</span><span class="sxs-lookup"><span data-stu-id="e5197-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="e5197-129">**Atributo semantinis tipas**: jūsų atributų kategorijos, pavyzdžiui, el. pašto adresas arba pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="e5197-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="e5197-130">Norėdami naudoti DI modelius išmaniojoje semantikos prognozėje, taupyti laiką ir pagerinti tikslumą, nustatykite parametro **Išmanusis susiejimas** parinktį **ĮJUNGTA**.</span><span class="sxs-lookup"><span data-stu-id="e5197-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="e5197-131">Išmanusis susiejimas paryškina DI pagrįstą semantikos rekomendaciją lauke **Tipas**.</span><span class="sxs-lookup"><span data-stu-id="e5197-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="e5197-132">Jei nustatysite parinktį **IŠJUNGTA**, matysite įprastas susiejimo rekomendacijas.</span><span class="sxs-lookup"><span data-stu-id="e5197-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="e5197-133">Galite pasirinkti bet kurį semantinį tipą iš galimų parinkčių sąrašo ir perrašyti siūlomą žymėjimą.</span><span class="sxs-lookup"><span data-stu-id="e5197-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e5197-134">![Atributo tipas ir semantinė prognozė](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Atributo tipas ir semantinė prognozė")</span><span class="sxs-lookup"><span data-stu-id="e5197-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="e5197-135">Taip pat galima pridėti pasirinktinį semantinį tipą.</span><span class="sxs-lookup"><span data-stu-id="e5197-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="e5197-136">Pasirinkite šiam atributui skirtą lauko tipą ir įrašykite savo pasirinktą semantinio tipo pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="e5197-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="e5197-137">Tokiu būdu taip pat galite pakeisti atributų tipus, kurie buvo identifikuoti sistemos.</span><span class="sxs-lookup"><span data-stu-id="e5197-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="e5197-138">Visi atributai, kuriems automatiškai nustatomas semantinis tipas, sugrupuojami skyriuje **Susietų laukų peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="e5197-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="e5197-139">Peržiūrėkite šiuos atributus ir jų semantinius tipus, nes jie bus naudojami jūsų objektams sulieti duomenų sujungimo proceso suliejimo etape.</span><span class="sxs-lookup"><span data-stu-id="e5197-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="e5197-140">Atributai, kurie automatiškai nesusiejami su semantiniu tipu, sugrupuojami skyriuje **Nesusietų laukų duomenų apibrėžimas**.</span><span class="sxs-lookup"><span data-stu-id="e5197-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="e5197-141">Pasirinkite nesusietų atributų semantinio tipo lauką arba įveskite pasirinktinį atributo tipo pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="e5197-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e5197-142">![Pirminio rakto ir atributo tipas](media/data-manager-configure-map-add-attributes.png "Pirminio rakto ir atributo tipas")</span><span class="sxs-lookup"><span data-stu-id="e5197-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="e5197-143">Vienas laukas turi būti susiejamas su semantiniu tipu Person.FullName, kad kliento pavardė būtų automatiškai įvesta kliento kortelėje.</span><span class="sxs-lookup"><span data-stu-id="e5197-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="e5197-144">Priešingu atveju kliento kortelės bus be vardo.</span><span class="sxs-lookup"><span data-stu-id="e5197-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="e5197-145">Atributų ir objektų įtraukimas bei šalinimas</span><span class="sxs-lookup"><span data-stu-id="e5197-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="e5197-146">Dalyje **Sujungti** > **Susieti** pasirinkite **Redaguoti laukus**.</span><span class="sxs-lookup"><span data-stu-id="e5197-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="e5197-147">Srityje **Redaguoti laukus** įtraukite arba pašalinkite atributus ir objektus.</span><span class="sxs-lookup"><span data-stu-id="e5197-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="e5197-148">Naudokite iešką arba slinkite, kad rastumėte ir pažymėtumėte dominančius atributus ir objektus.</span><span class="sxs-lookup"><span data-stu-id="e5197-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="e5197-149">Jei atributas ar objektas jau sugretintas, jų pašalinti negalima.</span><span class="sxs-lookup"><span data-stu-id="e5197-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e5197-150">![Įtraukti arba ištrinti atributus](media/configure-data-map-edit.png "Įtraukti arba ištrinti atributus")</span><span class="sxs-lookup"><span data-stu-id="e5197-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="e5197-151">Pasirinkite **Taikyti**.</span><span class="sxs-lookup"><span data-stu-id="e5197-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="e5197-152">Vaizdų įtraukimas į profilius</span><span class="sxs-lookup"><span data-stu-id="e5197-152">Add images to profiles</span></span>

<span data-ttu-id="e5197-153">Jei objekte yra viešai prieinamų profilio vaizdų ar logotipų URL, galite juos įtraukti į sujungtą kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="e5197-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="e5197-154">Pasirinkite objektą ir raskite lauką, kuriame yra profilio vaizdo URL.</span><span class="sxs-lookup"><span data-stu-id="e5197-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="e5197-155">Įvesties lauke **Tipas** rankiniu būdu įveskite toliau nurodytą reikšmę.</span><span class="sxs-lookup"><span data-stu-id="e5197-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="e5197-156">Asmuo: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="e5197-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="e5197-157">Organizacija: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="e5197-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="e5197-158">Atlikite kitus sujungimo veiksmus ir įsitikinkite, kad atributas, kuriame yra vaizdo URL, taip pat įtraukiamas į veiksmą [Sulieti](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="e5197-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="e5197-159">Nustatyti atributus organizacijoms</span><span class="sxs-lookup"><span data-stu-id="e5197-159">Set attributes for organizations</span></span>

<span data-ttu-id="e5197-160">Organizacijoms (peržiūra) atributo tipas turi būti susietas su „Organization.Name“</span><span class="sxs-lookup"><span data-stu-id="e5197-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="e5197-161">![Pirminio rakto ir atributo tipas B2B](media/configure-data-map-edit-b2b.png "Pirminio rakto ir atributo tipas B2B")</span><span class="sxs-lookup"><span data-stu-id="e5197-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="e5197-162">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="e5197-162">Next step</span></span>

<span data-ttu-id="e5197-163">Duomenų suvienijimo proceso metu nueikite į **suderinimo** puslapį.</span><span class="sxs-lookup"><span data-stu-id="e5197-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="e5197-164">Aplankykite [**suderinti**](match-entities.md) norėdami sužinoti apie šį etapą.</span><span class="sxs-lookup"><span data-stu-id="e5197-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="e5197-165">Peržiūrėkite šį vaizdo įrašą: [Pradžia: vieningo kliento profilio sukūrimas](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="e5197-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]