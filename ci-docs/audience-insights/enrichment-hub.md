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
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896015"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="a6bb4-103">Klientų profilių papildymas (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="a6bb4-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="a6bb4-104">Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis":::

<span data-ttu-id="a6bb4-106">Publikos įžvalgose eikite į **Duomenys** > **Papildymas** tam, kad dirbtumėte su papildymo parinktimis.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="a6bb4-107">Norėdami kurti arba redaguoti papildymus, turite turėti dalyvio arba administratoriaus teises.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="a6bb4-108">Daugiau informacijos žr. [Teisės](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a6bb4-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="a6bb4-109">Skirtuke **Atrasti** rasite šiuos papildymus:</span><span class="sxs-lookup"><span data-stu-id="a6bb4-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="a6bb4-110">[Rūšys](enrichment-microsoft.md), kurias teikia „Microsoft“</span><span class="sxs-lookup"><span data-stu-id="a6bb4-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="a6bb4-111">[Pomėgiai](enrichment-microsoft.md), kuriuos teikia „Microsoft“</span><span class="sxs-lookup"><span data-stu-id="a6bb4-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="a6bb4-112">[Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“</span><span class="sxs-lookup"><span data-stu-id="a6bb4-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="a6bb4-113">[Demografiniai duomenys](enrichment-experian.md), pateikti „Experian“</span><span class="sxs-lookup"><span data-stu-id="a6bb4-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="a6bb4-114">[Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“</span><span class="sxs-lookup"><span data-stu-id="a6bb4-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="a6bb4-115">[Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP)</span><span class="sxs-lookup"><span data-stu-id="a6bb4-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="a6bb4-116">Skirtuke **Mano papildymai** galite matyti sukonfigūruotus papildymus ir redaguoti jų ypatybes.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="a6bb4-117">Esamų papildymų tvarkymas</span><span class="sxs-lookup"><span data-stu-id="a6bb4-117">Manage existing enrichments</span></span>

<span data-ttu-id="a6bb4-118">Eikite į **Mano papildymai**, kad peržiūrėtumėte visus sukonfigūruotus papildymus.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="a6bb4-119">Kiekvienas papildymas atvaizduotas kaip eilutė su papildoma informacija apie papildymą.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="a6bb4-120">Pasirinkite papildymą, kad pamatytumėte galimas parinktis.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="a6bb4-121">Taip pat galite pažymėti elipsę (...) sąrašo elemente ir peržiūrėti parinktis.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Papildymų tvarkymo parinktys papildymų sąraše":::

- <span data-ttu-id="a6bb4-123">**Peržiūrėkite** papildymo informaciją su papildytų klientų profilių skaičiumi.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="a6bb4-124">**Redaguokite** papildymo konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="a6bb4-125">**Vykdykite** papildymą ir atnaujinkite klientų profilius naujausiais duomenimis.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="a6bb4-126">**Išjunkite** esamą papildymą, kad jis nebebūtų automatiškai atnaujinamas per kiekvieną suplanuotą atnaujinimą.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="a6bb4-127">Paskutinio sėkmingo atnaujinimo duomenys išliks prieinami.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="a6bb4-128">**Aktyvinkite** neaktyvų papildymą, jei norite iš naujo paleisti automatinį atnaujinimą su kiekvienu suplanuotu atnaujinimu.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="a6bb4-129">**Panaikinti** papildymą.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="a6bb4-130">Vienu metu galite vykdyti arba išjungti kelis papildymus pažymėdami juos sąraše.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="a6bb4-131">Peržiūros ir redagavimo parinktys nepasiekiamos kaip masiniai veiksmai ir vienu metu veikia tik viename papildyme.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="a6bb4-132">Papildymai ir ryšiai</span><span class="sxs-lookup"><span data-stu-id="a6bb4-132">Enrichments and connections</span></span>

<span data-ttu-id="a6bb4-133">Trečiosios šalies papildymai konfigūruojami naudojant [ryšius](connections.md), kuriuos administratorius nustato su kredencialais ir pateikia sutikimą duomenims perduoti.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="a6bb4-134">Tada administratoriai ir bendradarbiai ryšį gali naudoti papildymams konfigūruoti.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="a6bb4-135">Keli to paties tipo papildymai</span><span class="sxs-lookup"><span data-stu-id="a6bb4-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="a6bb4-136">Objektas, kurį reikia papildyti, nurodomas papildymo konfigūracijoje, o tai jums leidžia papildyti tik antrinį jūsų profilių rinkinį.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="a6bb4-137">Pavyzdžiui, duomenų papildymas tik konkrečiam segmentui.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="a6bb4-138">Galite konfigūruoti kelis to paties tipo papildymus ir pakartotinai naudoti tą patį ryšį.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="a6bb4-139">Kai kuriems papildymams bus ribojamas to paties tipo sukuriamų papildymų skaičius.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="a6bb4-140">Apribojimus ir dabartinį naudojima galima peržiūrėti puslapyje **Papildymas**.</span><span class="sxs-lookup"><span data-stu-id="a6bb4-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
