---
title: Ieškokite ir filtruokite kliento profilius
description: Greitai raskite vieningų klientų profilių informaciją ir filtruokite nurodytus atributus.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406424"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="ead1a-103">Klientų profiliai: ieškos ir filtro rodyklė</span><span class="sxs-lookup"><span data-stu-id="ead1a-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="ead1a-104">Kliento duomenų suvienodinimo rezultatas yra kliento profilio objektas, kuris jūsų bendroje klientų bazėje teikia vieningą rodinį.</span><span class="sxs-lookup"><span data-stu-id="ead1a-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="ead1a-105">Norėdami greitai [rasti informaciją apie tam tikrą klientą arba klientų grupę](customer-profiles.md), galite sukonfigūruoti **ieškos** ir **filtro** galimybes **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="ead1a-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="ead1a-106">Skaitydami toliau sužinosite, kaip administratoriai gali redaguoti **ieškos ir filtrų rodyklės** puslapyje esančius atributus, pasiekiamus norint ieškoti ir filtruoti.</span><span class="sxs-lookup"><span data-stu-id="ead1a-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ead1a-107">![Ieškos filtras](media/search-filter.png "Ieškos filtras")</span><span class="sxs-lookup"><span data-stu-id="ead1a-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="ead1a-108">Įtraukti laukus ir nurodyti atributus</span><span class="sxs-lookup"><span data-stu-id="ead1a-108">Add fields and specify attributes</span></span>

<span data-ttu-id="ead1a-109">Jei pirmą kartą nustatote ieškomus atributus kaip administratorius, pirmiausia turite apibrėžti indeksuotus laukus.</span><span class="sxs-lookup"><span data-stu-id="ead1a-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="ead1a-110">Patariame pasirinkti visus atributus, pagal kuriuos naudotojai gali ieškoti ir filtruoti klientus **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="ead1a-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="ead1a-111">Galite nurodyti tik per duomenų suvienijimo procesą sukurtus, klientų profilio objekte esančius atributus.</span><span class="sxs-lookup"><span data-stu-id="ead1a-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="ead1a-112">Atidarykite puslapį **Klientai** ir pasirinkite **Ieškos ir filtro rodyklė**.</span><span class="sxs-lookup"><span data-stu-id="ead1a-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="ead1a-113">Iš šių semantikos tipų, kaip apibrėžta struktūros puslapyje, sukursime numatytąją ieškos rodyklės konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="ead1a-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="ead1a-114">Asmens vardas, pavardė, vidurinis vardas, pilnas vardas</span><span class="sxs-lookup"><span data-stu-id="ead1a-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="ead1a-115">Organizacijos pavadinimas</span><span class="sxs-lookup"><span data-stu-id="ead1a-115">Organization Name</span></span>
> - <span data-ttu-id="ead1a-116">El. pašto adresas</span><span class="sxs-lookup"><span data-stu-id="ead1a-116">Email address</span></span>
> - <span data-ttu-id="ead1a-117">Telefono numeris</span><span class="sxs-lookup"><span data-stu-id="ead1a-117">Phone number</span></span>
> - <span data-ttu-id="ead1a-118">Vietos informacija</span><span class="sxs-lookup"><span data-stu-id="ead1a-118">Location information</span></span>

2. <span data-ttu-id="ead1a-119">Pasirinkite **+ Įtraukti**, kad nurodytumėte indeksuotus laukus.</span><span class="sxs-lookup"><span data-stu-id="ead1a-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="ead1a-120">Pasirinkite sąraše esančius atributus, kuriuos norite įtraukti kaip indeksuotus laukus.</span><span class="sxs-lookup"><span data-stu-id="ead1a-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="ead1a-121">Bet kada galite įtraukti daugiau atributų, pasirinkę **Įtraukti**.</span><span class="sxs-lookup"><span data-stu-id="ead1a-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="ead1a-122">Taip pat galite pašalinti bet kokius pasirinktus atributus pažymėdami simbolį **Šalinti**.</span><span class="sxs-lookup"><span data-stu-id="ead1a-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="ead1a-123">Susipažinkite su indeksuotų klientų laukų lentele</span><span class="sxs-lookup"><span data-stu-id="ead1a-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="ead1a-124">Ši informacija yra pateikta lentelėje.</span><span class="sxs-lookup"><span data-stu-id="ead1a-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="ead1a-125">**Pavadinimas**: nurodo atributo pavadinimą, kai jis atsiranda kliento profilio objekte.</span><span class="sxs-lookup"><span data-stu-id="ead1a-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="ead1a-126">**Duomenų tipas**: nurodo, ar duomenų tipas yra eilutė, skaičius ar data.</span><span class="sxs-lookup"><span data-stu-id="ead1a-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="ead1a-127">**Įtrauktas į iešką**: nurodo, ar šis atributas gali būti naudojamas ieškant klientų **klientų** puslapyje per **ieškos** lauką.</span><span class="sxs-lookup"><span data-stu-id="ead1a-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="ead1a-128">**Pridėti filtrą**: nuspręsti, kaip šis atributas gali būti naudojamas filtruojant **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="ead1a-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="ead1a-129">Duoto atributo filtravimo parametrų redagavimas</span><span class="sxs-lookup"><span data-stu-id="ead1a-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="ead1a-130">**Filtro** meniu, esantis **klientų** puslapyje, gali turėti įvairius atributų lygius (pavyzdžiui, filtruoti klientus galima pagal skirtingas amžiaus grupes).</span><span class="sxs-lookup"><span data-stu-id="ead1a-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="ead1a-131">Pasirinkite **pridėti filtrą** duotam atributui **ieškos ir filtro rodyklės** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="ead1a-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="ead1a-132">Galite apibrėžti rezultatų skaičių ir eiliškumą, pagal kurį jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="ead1a-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="ead1a-133">Atsižvelgiant į atributo duomenų tipą, pasirodo viena iš toliau nurodytų sričių.</span><span class="sxs-lookup"><span data-stu-id="ead1a-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="ead1a-134">Eilutės tipo atributai: nurodykite norimų rezultatų skaičių srityje **Eilutės filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="ead1a-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ead1a-135">Skaičiaus tipo atributai: nurodykite intervalus, įtrauktus srityje **Numerių filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="ead1a-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ead1a-136">Datos tipo atributai: nurodykite intervalus, įtrauktus srityje **Datos filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="ead1a-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="ead1a-137">Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.</span><span class="sxs-lookup"><span data-stu-id="ead1a-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="ead1a-138">Kai būsite pasirengę taikyti savo parametrus, pasirinkite **vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="ead1a-138">Select **Run** once you're ready to apply your settings.</span></span>
