---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft Power Automate” platformoje iš „Dynamics 365 Customer Insights”.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597935"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="bf51a-103">„Power Automate“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="bf51a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="bf51a-104">Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="bf51a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="bf51a-105">„Power Automate“ paleidikliai</span><span class="sxs-lookup"><span data-stu-id="bf51a-105">Power Automate triggers</span></span>

<span data-ttu-id="bf51a-106">Naudokite paleidinius debesies srautams kurti ir pasikartojančioms užduotims, pvz.: pranešimams ar išplėstiniams veiksmams, automatizuoti.</span><span class="sxs-lookup"><span data-stu-id="bf51a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="bf51a-107">Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="bf51a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="bf51a-108">Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="bf51a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="bf51a-109">Paleidiklis, pasiekus segmento ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="bf51a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="bf51a-110">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="bf51a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="bf51a-111">Paleidiklis, pasiekus verslo mato ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="bf51a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="bf51a-112">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="bf51a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="bf51a-113">Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių,...) yra pabaigtas.</span><span class="sxs-lookup"><span data-stu-id="bf51a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="bf51a-114">Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="bf51a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="bf51a-115">[Paleidiklių konfigūravimas „Power Automate“](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="bf51a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="bf51a-116">„Power Automate“ veiksmai</span><span class="sxs-lookup"><span data-stu-id="bf51a-116">Power Automate actions</span></span>
<span data-ttu-id="bf51a-117">„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius.</span><span class="sxs-lookup"><span data-stu-id="bf51a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="bf51a-118">Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="bf51a-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="bf51a-119">Kurti Power Automate srautą</span><span class="sxs-lookup"><span data-stu-id="bf51a-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="bf51a-120">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="bf51a-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bf51a-121">Plytelėje **„Power Automate”** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="bf51a-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="bf51a-122">Atsidaro „Power Automate“ jungtis programoje „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="bf51a-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="bf51a-123">**Prisijunkite** prie „Power Automate“.</span><span class="sxs-lookup"><span data-stu-id="bf51a-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="bf51a-124">Pasirinkite vieną iš galimų paleidiklių ir įtraukite daugiau veiksmų į naują srautą.</span><span class="sxs-lookup"><span data-stu-id="bf51a-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="bf51a-125">Daugiau informacijos [žr. Debesies srauto kūrimas Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="bf51a-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="bf51a-126">Pavyzdžiai, kaip naudoti srautus:</span><span class="sxs-lookup"><span data-stu-id="bf51a-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="bf51a-127">Jei nepavyksta atnaujinti duomenų šaltinio kanale, praneškite Microsoft Teams kanale.</span><span class="sxs-lookup"><span data-stu-id="bf51a-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="bf51a-128">Duomenų savininkams nusiuntus ribinę segmento ribinę vertę, el. laišką siųskite duomenų savininkams.</span><span class="sxs-lookup"><span data-stu-id="bf51a-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]