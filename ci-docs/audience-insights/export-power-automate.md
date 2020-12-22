---
title: Power Automate jungtis | „Microsoft Docs“
description: Kurkite srautus „Microsoft“ programoje „Power Automate“ iš „Dynamics 365 Customer Insights“.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406377"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="8f9de-103">„Power Automate“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="8f9de-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="8f9de-104">Nustatykite, kad konkretūs įvykiai būtų automatiškai vykdomi pasikeitus duomenims ir tvarkykite sudėtingesnius srautus tiesiai programoje [„Power Automate“](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="8f9de-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="8f9de-105">„Power Automate“ paleidikliai</span><span class="sxs-lookup"><span data-stu-id="8f9de-105">Power Automate triggers</span></span>

<span data-ttu-id="8f9de-106">Galite naudoti įvairius paleidiklius, leidžiančius kurti srautus, automatizuojančius pasikartojančias užduotis, pvz., pranešimus ar sudėtingesnius veiksmus.</span><span class="sxs-lookup"><span data-stu-id="8f9de-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="8f9de-107">Paleidiklis, kai nepavyksta atnaujinti duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="8f9de-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="8f9de-108">Paleidiklis, kai pavyksta atnaujinti duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="8f9de-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="8f9de-109">Paleidiklis, pasiekus segmento ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="8f9de-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="8f9de-110">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="8f9de-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="8f9de-111">Paleidiklis, pasiekus verslo mato ribinę reikšmę.</span><span class="sxs-lookup"><span data-stu-id="8f9de-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="8f9de-112">Paleidiklis taikomas tik ribinės vertės viršijimui.</span><span class="sxs-lookup"><span data-stu-id="8f9de-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="8f9de-113">Paleidimas, kai visas paleidimas iš naujo (duomenų šaltinių, segmentų, priemonių,...) yra pabaigtas.</span><span class="sxs-lookup"><span data-stu-id="8f9de-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="8f9de-114">Suaktyvinamas baigus sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="8f9de-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="8f9de-115">[Paleidiklių konfigūravimas „Power Automate“](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="8f9de-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="8f9de-116">„Power Automate“ veiksmai</span><span class="sxs-lookup"><span data-stu-id="8f9de-116">Power Automate actions</span></span>
<span data-ttu-id="8f9de-117">„Power Automate“ jungtis leidžia atlikti veiksmus, papildančius pasiekiamus paleidiklius.</span><span class="sxs-lookup"><span data-stu-id="8f9de-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="8f9de-118">Norėdami gauti daugiau informacijos, žr. [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="8f9de-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="8f9de-119">Sukurkite „Power Automate“ eigą publikso įžvalgose</span><span class="sxs-lookup"><span data-stu-id="8f9de-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="8f9de-120">Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="8f9de-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="8f9de-121">Puslapyje **Sistema** pasirinkite skirtuką **Būsena**.</span><span class="sxs-lookup"><span data-stu-id="8f9de-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="8f9de-122">Skyriuje **Duomenų šaltiniai** pasirinkite **Srautai**, o išplečiamajame sąraše pasirinkite **Kurti srautą**.</span><span class="sxs-lookup"><span data-stu-id="8f9de-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8f9de-123">![„Power Automate“ jungtis, rodanti srauto kūrimo veiksmą](media/power-automate-connector-create-flow.png "„Power Automate“ jungtis, rodanti srauto kūrimo veiksmą")</span><span class="sxs-lookup"><span data-stu-id="8f9de-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="8f9de-124">Programoje „Power Automate“ pasirinkite vieną iš galimų paleidiklių, kad sukurtumėte pageidaujamą srautą.</span><span class="sxs-lookup"><span data-stu-id="8f9de-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="8f9de-125">Jei kuriate pirmąjį srautą, pirmiausia turite patvirtinti savo tapatybę su „Power Automate“ jungtimi.</span><span class="sxs-lookup"><span data-stu-id="8f9de-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
