---
title: „Power Apps“ jungtis
description: Susijunkite su „Power Apps“ ir „Power Automate“.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598165"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="f9ec5-103">„Microsoft Power Apps“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="f9ec5-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="f9ec5-104">Perkelkite sujungtus klientų profilius į individualizuotas programas naudodami „Power Apps“.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="f9ec5-105">Susijunkite su „Power Apps“ ir „Dynamics 365 Customer Insights“</span><span class="sxs-lookup"><span data-stu-id="f9ec5-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="f9ec5-106">„Customer Insights“ yra vienas iš daugelio [galimų duomenų šaltinių naudojant „Power Apps“](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="f9ec5-107">Žr. „Power Apps“ dokumentaciją, kad sužinotumėte, kaip [į programą įtraukti duomenų ryšį](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="f9ec5-108">Taip pat rekomenduojame peržiūrėti, [kaip „Power Apps“ naudojamas perdavimas siekiant apdoroti didelius drobės programų duomenų rinkinius](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="f9ec5-109">Galimi objektai</span><span class="sxs-lookup"><span data-stu-id="f9ec5-109">Available entities</span></span>

<span data-ttu-id="f9ec5-110">„Customer Insights“ įtraukę kaip duomenų ryšį, „Power Apps“ galite pasirinkti toliau nurodytus objektus.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="f9ec5-111">Klientas: norėdami naudoti duomenis iš [sujungto kliento profilio](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="f9ec5-112">Sujungta klientų veikla: norėdami, kad programėlėje būtų rodoma [sujungta laiko juosta](activities.md).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="f9ec5-113">Apribojimai</span><span class="sxs-lookup"><span data-stu-id="f9ec5-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="f9ec5-114">Gaunamieji objektai</span><span class="sxs-lookup"><span data-stu-id="f9ec5-114">Retrievable entities</span></span>

<span data-ttu-id="f9ec5-115">Naudodami „Power Apps“ jungtį, galite gauti tik objektus **Klientas**, **UnifiedActivity** ir **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="f9ec5-116">Kiti objektai rodomi, nes pagrindinė jungtis juos palaiko per „Power Automate“ paleidiklius.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="f9ec5-117">Perdavimas</span><span class="sxs-lookup"><span data-stu-id="f9ec5-117">Delegation</span></span>

<span data-ttu-id="f9ec5-118">Perdavimo funkcija veikia su objektais Customer ir UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="f9ec5-119">**Kliento** objekto perdavimas: Šio objekto perdavimo naudojimui, laukeliai turi būti sužymėti [Paieškos ir filtravimo turinyje](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="f9ec5-120">**UnifiedActivity** perdavimas: šiame objekte perdavimo funkcija veikia tik su laukais **ActivityId** ir **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="f9ec5-121">Norėdami gauti daugiau informacijos apie perdavimą, žr. [„Power Apps“ perduodamosios funkcijos ir operacijos](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="f9ec5-122">Galerijos valdiklio pavyzdys</span><span class="sxs-lookup"><span data-stu-id="f9ec5-122">Example gallery control</span></span>

<span data-ttu-id="f9ec5-123">Pavyzdžiui, įtraukiate kliento profilius į [galerijos valdymą](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="f9ec5-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="f9ec5-124">Įtraukite valdiklį **Galeriją** į kuriamą programą.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f9ec5-125">![Galerijos elemento įtraukimas](media/connector-powerapps9.png "Galerijos elemento įtraukimas")</span><span class="sxs-lookup"><span data-stu-id="f9ec5-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="f9ec5-126">Pasirinkite **Klientas** kaip elementų duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f9ec5-127">![Pasirinkti duomenų šaltinį](media/choose-datasource-powerapps.png "Duomenų šaltinio pasirinkimas")</span><span class="sxs-lookup"><span data-stu-id="f9ec5-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="f9ec5-128">Galite keisti duomenų skydą dešinėje ir pasirinkti, kurį kliento objekto lauką rodyti galerijoje.</span><span class="sxs-lookup"><span data-stu-id="f9ec5-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="f9ec5-129">Jei galerijoje norite parodyti bet kurį pasirinkto kliento lauką, užpildykite žymos teksto ypatybę:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="f9ec5-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="f9ec5-130">Pavyzdys: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="f9ec5-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="f9ec5-131">Norėdami, kad būtų rodoma vieninga kliento laiko planavimo juosta, įtraukite galerijos elementą ir įtraukite elementų ypatybę: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="f9ec5-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="f9ec5-132">Pavyzdys: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="f9ec5-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]