---
title: Papildykite suvienodintus kliento profilius
description: Naudokite savybes siekiant papildyti jūsų kliento duomenis.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269478"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="12864-103">Klientų profilių papildymas (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="12864-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="12864-104">Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.</span><span class="sxs-lookup"><span data-stu-id="12864-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis":::

<span data-ttu-id="12864-106">Publikos įžvalgose eikite į **Duomenys** > **Papildymas** tam, kad dirbtumėte su papildymo parinktimis.</span><span class="sxs-lookup"><span data-stu-id="12864-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="12864-107">Norėdami kurti arba redaguoti papildymus, turite turėti dalyvio arba administratoriaus teises.</span><span class="sxs-lookup"><span data-stu-id="12864-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="12864-108">Daugiau informacijos žr. [Teisės](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="12864-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="12864-109">Skirtuke **Atrasti** rasite šiuos papildymus:</span><span class="sxs-lookup"><span data-stu-id="12864-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="12864-110">[Prekių ženklai](enrichment-microsoft-graph.md), teikia „Microsoft Graph“</span><span class="sxs-lookup"><span data-stu-id="12864-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="12864-111">[Interesai](enrichment-microsoft-graph.md), teikia „Microsoft Graph“</span><span class="sxs-lookup"><span data-stu-id="12864-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="12864-112">[Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“</span><span class="sxs-lookup"><span data-stu-id="12864-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="12864-113">[Demografiniai duomenys](enrichment-experian.md), pateikti „Experian“</span><span class="sxs-lookup"><span data-stu-id="12864-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="12864-114">[Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“</span><span class="sxs-lookup"><span data-stu-id="12864-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="12864-115">[Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP)</span><span class="sxs-lookup"><span data-stu-id="12864-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="12864-116">Skirtuke **Mano papildymai** galite matyti sukonfigūruotus papildymus ir redaguoti jų ypatybes.</span><span class="sxs-lookup"><span data-stu-id="12864-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="12864-117">Esamų papildymų tvarkymas</span><span class="sxs-lookup"><span data-stu-id="12864-117">Manage existing enrichments</span></span>

<span data-ttu-id="12864-118">Eikite į **Mano papildymai**, kad peržiūrėtumėte visus sukonfigūruotus papildymus.</span><span class="sxs-lookup"><span data-stu-id="12864-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="12864-119">Kiekvienas papildymas atvaizduotas kaip eilutė su papildoma informacija apie papildymą.</span><span class="sxs-lookup"><span data-stu-id="12864-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="12864-120">Pasirinkite papildymą, kad pamatytumėte galimas parinktis.</span><span class="sxs-lookup"><span data-stu-id="12864-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="12864-121">Taip pat galite pažymėti elipsę (...) prie sąrašo elemento ir peržiūrėti parinktis.</span><span class="sxs-lookup"><span data-stu-id="12864-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Papildymų tvarkymo parinktys papildymų sąraše":::

- <span data-ttu-id="12864-123">**Peržiūrėkite** papildymo informaciją su papildytų klientų profilių skaičiumi.</span><span class="sxs-lookup"><span data-stu-id="12864-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="12864-124">**Redaguokite** papildymo konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="12864-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="12864-125">**Vykdykite** papildymą ir atnaujinkite klientų profilius naujausiais duomenimis.</span><span class="sxs-lookup"><span data-stu-id="12864-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="12864-126">**Išjunkite** esamą papildymą, kad jis nebebūtų automatiškai atnaujinamas per kiekvieną suplanuotą atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="12864-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="12864-127">Paskutinio sėkmingo atnaujinimo duomenys išliks prieinami.</span><span class="sxs-lookup"><span data-stu-id="12864-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="12864-128">**Aktyvinkite** neaktyvų papildymą, jei norite iš naujo paleisti automatinį atnaujinimą su kiekvienu suplanuotu atnaujinimu.</span><span class="sxs-lookup"><span data-stu-id="12864-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="12864-129">**Panaikinti** papildymą.</span><span class="sxs-lookup"><span data-stu-id="12864-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="12864-130">Vienu metu galite vykdyti arba išjungti kelis papildymus pažymėdami juos sąraše.</span><span class="sxs-lookup"><span data-stu-id="12864-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="12864-131">Peržiūros ir redagavimo parinktys nepasiekiamos kaip masiniai veiksmai ir vienu metu veikia tik viename papildyme.</span><span class="sxs-lookup"><span data-stu-id="12864-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]