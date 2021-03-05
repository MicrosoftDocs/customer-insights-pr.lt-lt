---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft“ programoje „Power Automate“ iš „Dynamics 365 Customer Insights“.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268834"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="b5540-103">„Power Automate“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b5540-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="b5540-104">Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b5540-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="b5540-105">„Power Automate“ paleidikliai</span><span class="sxs-lookup"><span data-stu-id="b5540-105">Power Automate triggers</span></span>

<span data-ttu-id="b5540-106">Naudokite paleidinius debesies srautams kurti ir pasikartojančioms užduotims, pvz.: pranešimams ar išplėstiniams veiksmams, automatizuoti.</span><span class="sxs-lookup"><span data-stu-id="b5540-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="b5540-107">Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="b5540-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="b5540-108">Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="b5540-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="b5540-109">Paleidiklis, pasiekus segmento ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="b5540-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="b5540-110">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="b5540-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="b5540-111">Paleidiklis, pasiekus verslo mato ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="b5540-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="b5540-112">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="b5540-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="b5540-113">Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių,...) yra pabaigtas.</span><span class="sxs-lookup"><span data-stu-id="b5540-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="b5540-114">Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="b5540-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="b5540-115">[Paleidiklių konfigūravimas „Power Automate“](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="b5540-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="b5540-116">„Power Automate“ veiksmai</span><span class="sxs-lookup"><span data-stu-id="b5540-116">Power Automate actions</span></span>
<span data-ttu-id="b5540-117">„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius.</span><span class="sxs-lookup"><span data-stu-id="b5540-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="b5540-118">Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="b5540-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="b5540-119">Kurti Power Automate srautą</span><span class="sxs-lookup"><span data-stu-id="b5540-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="b5540-120">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="b5540-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b5540-121">Plytelėje „**Power Automate**“ pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="b5540-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="b5540-122">Atsidaro „Power Automate“ jungtis programoje „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="b5540-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="b5540-123">**Prisijunkite** prie „Power Automate“.</span><span class="sxs-lookup"><span data-stu-id="b5540-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="b5540-124">Pasirinkite vieną iš galimų paleidklių ir įtraukite daugiau veiksmų į naują srautą.</span><span class="sxs-lookup"><span data-stu-id="b5540-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="b5540-125">Daugiau informacijos [žr. Debesies srauto kūrimas Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="b5540-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="b5540-126">Pavyzdžiai, kaip naudoti srautus:</span><span class="sxs-lookup"><span data-stu-id="b5540-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="b5540-127">Jei nepavyksta atnaujinti duomenų šaltinio kanale, praneškite Microsoft Teams kanale.</span><span class="sxs-lookup"><span data-stu-id="b5540-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="b5540-128">Duomenų savininkams nusiuntus ribinę segmento ribinę vertę, el. laišką siųskite duomenų savininkams.</span><span class="sxs-lookup"><span data-stu-id="b5540-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]