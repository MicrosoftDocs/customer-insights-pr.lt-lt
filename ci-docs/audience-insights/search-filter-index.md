---
title: Ieškokite ir filtruokite kliento profilius
description: Greitai raskite vieningų klientų profilių informaciją ir filtruokite nurodytus atributus.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597153"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="5e257-103">Klientų profiliai: ieškos ir filtro rodyklė</span><span class="sxs-lookup"><span data-stu-id="5e257-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="5e257-104">Kliento duomenų suvienodinimo rezultatas yra kliento profilio objektas, kuris jūsų bendroje klientų bazėje teikia vieningą rodinį.</span><span class="sxs-lookup"><span data-stu-id="5e257-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="5e257-105">Norėdami greitai [rasti informaciją apie tam tikrą klientą arba klientų grupę](customer-profiles.md), galite sukonfigūruoti **ieškos** ir **filtro** galimybes **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="5e257-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="5e257-106">Skaitydami toliau sužinosite, kaip administratoriai gali redaguoti **ieškos ir filtrų rodyklės** puslapyje esančius atributus, pasiekiamus norint ieškoti ir filtruoti.</span><span class="sxs-lookup"><span data-stu-id="5e257-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5e257-107">![Ieškos filtras](media/search-filter.png "Ieškos filtras")</span><span class="sxs-lookup"><span data-stu-id="5e257-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="5e257-108">Įtraukti laukus ir nurodyti atributus</span><span class="sxs-lookup"><span data-stu-id="5e257-108">Add fields and specify attributes</span></span>

<span data-ttu-id="5e257-109">Jei pirmą kartą nustatote ieškomus atributus kaip administratorius, pirmiausia turite apibrėžti indeksuotus laukus.</span><span class="sxs-lookup"><span data-stu-id="5e257-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="5e257-110">Patariame pasirinkti visus atributus, pagal kuriuos naudotojai gali ieškoti ir filtruoti klientus **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="5e257-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="5e257-111">Galite nurodyti tik per duomenų suvienijimo procesą sukurtus, klientų profilio objekte esančius atributus.</span><span class="sxs-lookup"><span data-stu-id="5e257-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="5e257-112">Atidarykite puslapį **Klientai** ir pasirinkite **Ieškos ir filtro rodyklė**.</span><span class="sxs-lookup"><span data-stu-id="5e257-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="5e257-113">Pasirinkite **+ Įtraukti**, kad nurodytumėte indeksuotus laukus.</span><span class="sxs-lookup"><span data-stu-id="5e257-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="5e257-114">Pasirinkite sąraše esančius atributus, kuriuos norite įtraukti kaip indeksuotus laukus.</span><span class="sxs-lookup"><span data-stu-id="5e257-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="5e257-115">Bet kada galite įtraukti daugiau atributų, pasirinkę **Įtraukti**.</span><span class="sxs-lookup"><span data-stu-id="5e257-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="5e257-116">Taip pat galite pašalinti bet kokius pasirinktus atributus pažymėdami simbolį **Šalinti**.</span><span class="sxs-lookup"><span data-stu-id="5e257-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="5e257-117">Susipažinkite su indeksuotų klientų laukų lentele</span><span class="sxs-lookup"><span data-stu-id="5e257-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="5e257-118">Ši informacija yra pateikta lentelėje.</span><span class="sxs-lookup"><span data-stu-id="5e257-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="5e257-119">**Pavadinimas**: nurodo atributo pavadinimą, kai jis atsiranda kliento profilio objekte.</span><span class="sxs-lookup"><span data-stu-id="5e257-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="5e257-120">**Duomenų tipas**: nurodo, ar duomenų tipas yra eilutė, skaičius ar data.</span><span class="sxs-lookup"><span data-stu-id="5e257-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="5e257-121">**Įtrauktas į iešką**: nurodo, ar šis atributas gali būti naudojamas ieškant klientų **klientų** puslapyje per **ieškos** lauką.</span><span class="sxs-lookup"><span data-stu-id="5e257-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="5e257-122">**Pridėti filtrą**: nuspręsti, kaip šis atributas gali būti naudojamas filtruojant **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="5e257-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="5e257-123">Duoto atributo filtravimo parametrų redagavimas</span><span class="sxs-lookup"><span data-stu-id="5e257-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="5e257-124">**Filtro** meniu, esantis **klientų** puslapyje, gali turėti įvairius atributų lygius (pavyzdžiui, filtruoti klientus galima pagal skirtingas amžiaus grupes).</span><span class="sxs-lookup"><span data-stu-id="5e257-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="5e257-125">Pasirinkite **pridėti filtrą** duotam atributui **ieškos ir filtro rodyklės** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="5e257-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="5e257-126">Galite apibrėžti rezultatų skaičių ir eiliškumą, pagal kurį jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="5e257-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="5e257-127">Atsižvelgiant į atributo duomenų tipą, pasirodo viena iš toliau nurodytų sričių.</span><span class="sxs-lookup"><span data-stu-id="5e257-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="5e257-128">Eilutės tipo atributai: nurodykite norimų rezultatų skaičių srityje **Eilutės filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="5e257-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5e257-129">Skaičiaus tipo atributai: nurodykite intervalus, įtrauktus srityje **Numerių filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="5e257-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="5e257-130">Datos tipo atributai: nurodykite intervalus, įtrauktus srityje **Datos filtro parinktys**, ir eiliškumo tvarką, pagal kurią jie bus tvarkomi.</span><span class="sxs-lookup"><span data-stu-id="5e257-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="5e257-131">Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.</span><span class="sxs-lookup"><span data-stu-id="5e257-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="5e257-132">Kai būsite pasirengę taikyti savo parametrus, pasirinkite **vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="5e257-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e257-133">Paskesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="5e257-133">Next steps</span></span>

<span data-ttu-id="5e257-134">Eikite į **klientų** puslapį norėdami peržiūrėti visų klientų profilių antrinį ir ieškokite klientų profilių arba naudodami indeksuoti laukus rinkinį.</span><span class="sxs-lookup"><span data-stu-id="5e257-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]