---
title: Papildykite suvienodintus kliento profilius
description: Naudokite savybes siekiant papildyti jūsų kliento duomenis.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954497"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="688d0-103">Klientų profilių papildymas (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="688d0-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="688d0-104">Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.</span><span class="sxs-lookup"><span data-stu-id="688d0-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis":::

<span data-ttu-id="688d0-106">Publikos įžvalgose eikite į **Duomenys** > **Papildymas** tam, kad dirbtumėte su papildymo parinktimis.</span><span class="sxs-lookup"><span data-stu-id="688d0-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="688d0-107">Norėdami kurti arba redaguoti papildymus, turite turėti dalyvio arba administratoriaus teises.</span><span class="sxs-lookup"><span data-stu-id="688d0-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="688d0-108">Daugiau informacijos žr. [Teisės](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="688d0-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="688d0-109">Skirtuke **Atrasti** rasite šiuos papildymus:</span><span class="sxs-lookup"><span data-stu-id="688d0-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="688d0-110">[Rūšys](enrichment-microsoft.md), kurias teikia „Microsoft“</span><span class="sxs-lookup"><span data-stu-id="688d0-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="688d0-111">[Pomėgiai](enrichment-microsoft.md), kuriuos teikia „Microsoft“</span><span class="sxs-lookup"><span data-stu-id="688d0-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="688d0-112">[Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft”</span><span class="sxs-lookup"><span data-stu-id="688d0-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="688d0-113">[Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“</span><span class="sxs-lookup"><span data-stu-id="688d0-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="688d0-114">[Demografiniai duomenys](enrichment-experian.md), pateikti „Experian“</span><span class="sxs-lookup"><span data-stu-id="688d0-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="688d0-115">[Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“</span><span class="sxs-lookup"><span data-stu-id="688d0-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="688d0-116">[Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP)</span><span class="sxs-lookup"><span data-stu-id="688d0-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="688d0-117">Skirtuke **Mano papildymai** galite matyti sukonfigūruotus papildymus ir redaguoti jų ypatybes.</span><span class="sxs-lookup"><span data-stu-id="688d0-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="688d0-118">Esamų papildymų tvarkymas</span><span class="sxs-lookup"><span data-stu-id="688d0-118">Manage existing enrichments</span></span>

<span data-ttu-id="688d0-119">Eikite į **Mano papildymai**, kad peržiūrėtumėte visus sukonfigūruotus papildymus.</span><span class="sxs-lookup"><span data-stu-id="688d0-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="688d0-120">Kiekvienas papildymas atvaizduotas kaip eilutė su papildoma informacija apie papildymą.</span><span class="sxs-lookup"><span data-stu-id="688d0-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="688d0-121">Pasirinkite papildymą, kad pamatytumėte galimas parinktis.</span><span class="sxs-lookup"><span data-stu-id="688d0-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="688d0-122">Taip pat galite pažymėti elipsę (...) sąrašo elemente ir peržiūrėti parinktis.</span><span class="sxs-lookup"><span data-stu-id="688d0-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Papildymų tvarkymo parinktys papildymų sąraše":::

- <span data-ttu-id="688d0-124">**Peržiūrėkite** papildymo informaciją su papildytų klientų profilių skaičiumi.</span><span class="sxs-lookup"><span data-stu-id="688d0-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="688d0-125">**Redaguokite** papildymo konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="688d0-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="688d0-126">**Vykdykite** papildymą ir atnaujinkite klientų profilius naujausiais duomenimis.</span><span class="sxs-lookup"><span data-stu-id="688d0-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="688d0-127">**Išjunkite** esamą papildymą, kad jis nebebūtų automatiškai atnaujinamas per kiekvieną suplanuotą atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="688d0-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="688d0-128">Paskutinio sėkmingo atnaujinimo duomenys išliks prieinami.</span><span class="sxs-lookup"><span data-stu-id="688d0-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="688d0-129">**Aktyvinkite** neaktyvų papildymą, jei norite iš naujo paleisti automatinį atnaujinimą su kiekvienu suplanuotu atnaujinimu.</span><span class="sxs-lookup"><span data-stu-id="688d0-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="688d0-130">**Panaikinti** papildymą.</span><span class="sxs-lookup"><span data-stu-id="688d0-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="688d0-131">Vienu metu galite vykdyti arba išjungti kelis papildymus pažymėdami juos sąraše.</span><span class="sxs-lookup"><span data-stu-id="688d0-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="688d0-132">Peržiūros ir redagavimo parinktys nepasiekiamos kaip masiniai veiksmai ir vienu metu veikia tik viename papildyme.</span><span class="sxs-lookup"><span data-stu-id="688d0-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="688d0-133">Papildymai ir ryšiai</span><span class="sxs-lookup"><span data-stu-id="688d0-133">Enrichments and connections</span></span>

<span data-ttu-id="688d0-134">Trečiosios šalies papildymai konfigūruojami naudojant [ryšius](connections.md), kuriuos administratorius nustato su kredencialais ir pateikia sutikimą duomenims perduoti.</span><span class="sxs-lookup"><span data-stu-id="688d0-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="688d0-135">Tada administratoriai ir bendradarbiai ryšį gali naudoti papildymams konfigūruoti.</span><span class="sxs-lookup"><span data-stu-id="688d0-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="688d0-136">Keli to paties tipo papildymai</span><span class="sxs-lookup"><span data-stu-id="688d0-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="688d0-137">Objektas, kurį reikia papildyti, nurodomas papildymo konfigūracijoje, o tai jums leidžia papildyti tik antrinį jūsų profilių rinkinį.</span><span class="sxs-lookup"><span data-stu-id="688d0-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="688d0-138">Pavyzdžiui, duomenų papildymas tik konkrečiam segmentui.</span><span class="sxs-lookup"><span data-stu-id="688d0-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="688d0-139">Galite konfigūruoti kelis to paties tipo papildymus ir pakartotinai naudoti tą patį ryšį.</span><span class="sxs-lookup"><span data-stu-id="688d0-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="688d0-140">Kai kuriems papildymams bus ribojamas to paties tipo sukuriamų papildymų skaičius.</span><span class="sxs-lookup"><span data-stu-id="688d0-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="688d0-141">Apribojimus ir dabartinį naudojima galima peržiūrėti puslapyje **Papildymas**.</span><span class="sxs-lookup"><span data-stu-id="688d0-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
