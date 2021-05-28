---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft Power Automate” platformoje iš „Dynamics 365 Customer Insights”.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976098"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="14aea-103">„Power Automate“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="14aea-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="14aea-104">Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="14aea-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="14aea-105">„Power Automate“ paleidikliai</span><span class="sxs-lookup"><span data-stu-id="14aea-105">Power Automate triggers</span></span>

<span data-ttu-id="14aea-106">Naudokite paleidinius debesies srautams kurti ir pasikartojančioms užduotims, pvz.: pranešimams ar išplėstiniams veiksmams, automatizuoti.</span><span class="sxs-lookup"><span data-stu-id="14aea-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="14aea-107">Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="14aea-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="14aea-108">Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="14aea-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="14aea-109">Paleidiklis, pasiekus segmento ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="14aea-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="14aea-110">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="14aea-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="14aea-111">Paleidiklis, pasiekus verslo mato ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="14aea-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="14aea-112">Palaikomi tik verslo matai be dimensijos.</span><span class="sxs-lookup"><span data-stu-id="14aea-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="14aea-113">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="14aea-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="14aea-114">Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių,...) yra pabaigtas.</span><span class="sxs-lookup"><span data-stu-id="14aea-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="14aea-115">Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="14aea-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="14aea-116">[Paleidiklių konfigūravimas „Power Automate“](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="14aea-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="14aea-117">„Power Automate“ veiksmai</span><span class="sxs-lookup"><span data-stu-id="14aea-117">Power Automate actions</span></span>
<span data-ttu-id="14aea-118">„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius.</span><span class="sxs-lookup"><span data-stu-id="14aea-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="14aea-119">Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="14aea-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="14aea-120">Kurti Power Automate srautą</span><span class="sxs-lookup"><span data-stu-id="14aea-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="14aea-121">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="14aea-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="14aea-122">Plytelėje **„Power Automate”** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="14aea-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="14aea-123">Atsidaro „Power Automate“ jungtis programoje „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="14aea-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="14aea-124">**Prisijunkite** prie „Power Automate“.</span><span class="sxs-lookup"><span data-stu-id="14aea-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="14aea-125">Pasirinkite vieną iš galimų paleidiklių ir įtraukite daugiau veiksmų į naują srautą.</span><span class="sxs-lookup"><span data-stu-id="14aea-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="14aea-126">Daugiau informacijos [žr. Debesies srauto kūrimas Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="14aea-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="14aea-127">Pavyzdžiai, kaip naudoti srautus:</span><span class="sxs-lookup"><span data-stu-id="14aea-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="14aea-128">Jei nepavyksta atnaujinti duomenų šaltinio kanale, praneškite Microsoft Teams kanale.</span><span class="sxs-lookup"><span data-stu-id="14aea-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="14aea-129">Duomenų savininkams nusiuntus ribinę segmento ribinę vertę, el. laišką siųskite duomenų savininkams.</span><span class="sxs-lookup"><span data-stu-id="14aea-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
