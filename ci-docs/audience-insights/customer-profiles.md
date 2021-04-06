---
title: Peržiūrėti kliento profilius
description: Gaukite bendrą jūsų suvienodintų kliento duomenų rodinį.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596877"
---
# <a name="customer-profiles"></a><span data-ttu-id="5daa8-103">Klientų profiliai</span><span class="sxs-lookup"><span data-stu-id="5daa8-103">Customer profiles</span></span>

<span data-ttu-id="5daa8-104">**Klientų** puslapis rodo suderintą jūsų klientų rodinį pagrįstą profilio duomenimis gautais iš [visų duomenų šaltinių](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="5daa8-105">Klientų profiliai yra pasiekiami, tik [sukūrus sujungtą kliento objektą](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="5daa8-106">Įsitikinkite, kad užbaigėte duomenų sujungimo procesą, kad gautumėte geresnius klientų rodinius.</span><span class="sxs-lookup"><span data-stu-id="5daa8-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="5daa8-107">Puslapyje taip pat galite ieškoti klientų.</span><span class="sxs-lookup"><span data-stu-id="5daa8-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="5daa8-108">Klientai gali būti asmenys arba organizacijos (peržiūra).</span><span class="sxs-lookup"><span data-stu-id="5daa8-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="5daa8-109">Kiekvienas kliento arba organizacijos profilis atvaizduojamas plytele.</span><span class="sxs-lookup"><span data-stu-id="5daa8-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="5daa8-110">Pasirinkite plytelę, kad sužinotumėte papildomos informacijos apie konkretų klientą arba organizaciją.</span><span class="sxs-lookup"><span data-stu-id="5daa8-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="5daa8-111">Norėdami pamatyti papildomus įrašus, naudokite puslapio apačioje esančius skaidymo į puslapius valdiklius.</span><span class="sxs-lookup"><span data-stu-id="5daa8-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5daa8-112">![B2C klientų profiliai](media/profiles-customers.png "B2C klientų profiliai")</span><span class="sxs-lookup"><span data-stu-id="5daa8-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="5daa8-113">Organizacijos (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="5daa8-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="5daa8-114">![B2B klientų profiliai](media/profile-customers-b2b.png "B2B klientų profiliai")</span><span class="sxs-lookup"><span data-stu-id="5daa8-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="5daa8-115">Jei naršymo juostoje pasirinkus **Klientai** plytelės nerodomos, reikia, kad administratorius **ieškos ir filtro rodyklėje** [apibrėžtų bent vieną ieškomą atributą ](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="5daa8-116">Klientų paieška</span><span class="sxs-lookup"><span data-stu-id="5daa8-116">Search for customers</span></span>

<span data-ttu-id="5daa8-117">Klientų galite ieškoti, į paieškos laukelį įvesdami vardą ar kokį nors kitą atributą.</span><span class="sxs-lookup"><span data-stu-id="5daa8-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="5daa8-118">Paieška veikia tik kliento profilio objekte, sukurtame duomenų sujungimo proceso metu.</span><span class="sxs-lookup"><span data-stu-id="5daa8-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="5daa8-119">Turėdami administratoriaus teises, galite konfigūruoti paieškai pasiekiamus atributus, naudodami puslapį **Ieškos ir filtro rodyklė**.</span><span class="sxs-lookup"><span data-stu-id="5daa8-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="5daa8-120">Daugiau informacijos rasite [Ieškos ir filtro rodyklės valdymas](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="5daa8-121">Klientų filtravimas</span><span class="sxs-lookup"><span data-stu-id="5daa8-121">Filter customers</span></span>

<span data-ttu-id="5daa8-122">Klientus galite filtruoti pagal kliento profilio objekto laukus.</span><span class="sxs-lookup"><span data-stu-id="5daa8-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="5daa8-123">Panašiai kaip ir atliekant iešką, jūsų administratoriui pirmiausia reikės apibrėžti laukus kaip galimus filtruoti, naudojant puslapį **Ieškos ir filtro rodyklė**.</span><span class="sxs-lookup"><span data-stu-id="5daa8-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="5daa8-124">Pasirinkite **Filtruoti**  **Klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="5daa8-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="5daa8-125">Pažymėkite laukelius šalia atributų, pagal kuriuos norite filtruoti klientus.</span><span class="sxs-lookup"><span data-stu-id="5daa8-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="5daa8-126">![Klientų profiliai](media/profiles-customers3.png "Klientų profiliai")</span><span class="sxs-lookup"><span data-stu-id="5daa8-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="5daa8-127">Pašalinkite savo filtrus pasirinkę **Pašalinti filtrus** **Klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="5daa8-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="5daa8-128">Kliento informacijos puslapis</span><span class="sxs-lookup"><span data-stu-id="5daa8-128">Customer details page</span></span>

<span data-ttu-id="5daa8-129">Pasirinkite bet kurias kliento plytas tam, kad atvertumėte **Kliento informacijos puslapį**.</span><span class="sxs-lookup"><span data-stu-id="5daa8-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="5daa8-130">Šis rodinys apima suvienodintą informaciją pasirinktam klientui.</span><span class="sxs-lookup"><span data-stu-id="5daa8-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="5daa8-131">Kliento išsami informacija apima:</span><span class="sxs-lookup"><span data-stu-id="5daa8-131">Customer details include:</span></span>

-   <span data-ttu-id="5daa8-132">**Kliento profilio plyta:** Ši plyta rodo skirtingas vertes lyginant su suvienodintu kliento profilio objektu.</span><span class="sxs-lookup"><span data-stu-id="5daa8-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="5daa8-133">Ši išsami informacija gali apimti el. pašto adresą, vardą, miestą ir t.t.</span><span class="sxs-lookup"><span data-stu-id="5daa8-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="5daa8-134">**Galimi interesai, galimi prekės ženklai:** Rodo, ar jūs sukonfigūravote pirmosios šalies praturtinimą.</span><span class="sxs-lookup"><span data-stu-id="5daa8-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="5daa8-135">Jis rodo galimus interesus ir panašumus su kliento turimais prekių ženklais su profiliu.</span><span class="sxs-lookup"><span data-stu-id="5daa8-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="5daa8-136">Daugiau informacijos žr. [Klientų profilių papildymas prekių ženklų ir pomėgių panašumais](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="5daa8-137">**Priemonės:** Rodo, ar jūs sukonfigūravote vieną ar keletą priemonių konkrečiam tipui: kliento savybių priemonėms.</span><span class="sxs-lookup"><span data-stu-id="5daa8-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="5daa8-138">Jos apima apskaičiuotą KPI pagal jūsų klientus individualiu kliento lygmeniu.</span><span class="sxs-lookup"><span data-stu-id="5daa8-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="5daa8-139">Dėl daugiau informacijos, žr. [Nustatyti ir valdyti priemones](measures.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="5daa8-140">**Aktyvumo laiko juosta:** Rodo, ar konfigūravote veiklas.</span><span class="sxs-lookup"><span data-stu-id="5daa8-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="5daa8-141">Laiko juostos rodinys turi chronologiškai surikiuotas šio kliento veiklas, pradedant su naujausia veikla.</span><span class="sxs-lookup"><span data-stu-id="5daa8-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="5daa8-142">Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="5daa8-143">Pasirinkite **Atgal į klientus** norėdami grįžti į kliento paieškos puslapį.</span><span class="sxs-lookup"><span data-stu-id="5daa8-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5daa8-144">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="5daa8-144">Next steps</span></span>

<span data-ttu-id="5daa8-145">[Daugiau duomenų šaltinių įtraukimas](data-sources.md) arba [Klientų segmentų kūrimas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5daa8-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]