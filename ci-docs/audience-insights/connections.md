---
title: Ryšiai su kitomis paslaugomis iš „Customer Insights“.
description: Bendrinkite duomenis su kitomis paslaugomis.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304982"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="cb5e9-103">Ryšių (peržiūros) apžvalga</span><span class="sxs-lookup"><span data-stu-id="cb5e9-103">Connections (preview) overview</span></span>

<span data-ttu-id="cb5e9-104">Ryšiai yra pagrindinis duomenų bendrinimo į „Customer Insights“ ir iš jo raktas.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="cb5e9-105">Kiekvienas ryšys sukuria duomenų bendrinimą su konkrečia paslauga.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="cb5e9-106">Ryšiai yra [trečiųjų šalių papildymų konfigūravimo](enrichment-hub.md) ir [eksportavimo konfigūravimo](export-destinations.md) pagrindas.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="cb5e9-107">Tą patį ryšį galima naudoti kelis kartus.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="cb5e9-108">Pavyzdžiui, vienas ryšys su „Dynamics 365 Marketing“ veikia keliems eksportams, o vienas „Leadspace“ ryšys gali būti naudojamas keliems papildymams.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="cb5e9-109">Eikite į **Administravimas** > **Ryšiai** ir kurkite bei peržiūrėkite ryšius.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="cb5e9-110">Skirtuke **Ryšiai** rodomi visi aktyvūs ryšiai.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="cb5e9-111">Sąraše rodoma kiekvieno ryšio eilutė.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="cb5e9-112">Greitai peržiūrėkite, gaukite aprašą ir sužinokite, ką galite daryti su kiekviena išplėtimo parinktimi skirtuke **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="cb5e9-113">Eksportavimai</span><span class="sxs-lookup"><span data-stu-id="cb5e9-113">Exports</span></span>

<span data-ttu-id="cb5e9-114">Naujus ryšius gali konfigūruoti tik administratoriai, tačiau jie gali suteikti prieigą prie bendraautorių, kad galėtų naudoti esamus ryšius.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="cb5e9-115">Administratoriai valdo, kur gali būti perkeliami duomenys, bendradarbiai apibrėžia jų poreikius pagal apkrovą ir dažnumą.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="cb5e9-116">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cb5e9-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="cb5e9-117">Papildymai</span><span class="sxs-lookup"><span data-stu-id="cb5e9-117">Enrichments</span></span>

<span data-ttu-id="cb5e9-118">Naujus ryšius gali konfigūruoti tik administratoriai, bet sukurti ryšiai visada pasiekiami ir administratoriams, ir bendradarbiams.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="cb5e9-119">Administratoriai valdo kredencialus ir sutinka, kad duomenys būtų perduoti.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="cb5e9-120">Tada administratoriai ir bendradarbiai ryšius gali naudoti papildymams.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="cb5e9-121">Pridėti naują ryšį</span><span class="sxs-lookup"><span data-stu-id="cb5e9-121">Add a new connection</span></span>

<span data-ttu-id="cb5e9-122">Norėdami įtraukti ryšius, turite turėti [administratoriaus teises](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="cb5e9-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="cb5e9-123">Jei prisijungsite prie kitų „Microsoft“ paslaugų, manysime, kad abi paslaugos teikiamos toje pačioje organizacijoje.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="cb5e9-124">Eikite į **Administravimas** > **Ryšiai (peržiūra)**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="cb5e9-125">Eikite į skirtuką **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="cb5e9-126">Norėdami sukurti naują ryšį, pasirinkite **Pridėti ryšį**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="cb5e9-127">Išplečiamajame meniu pasirinkite, kokio tipo ryšį norite sukurti.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="cb5e9-128">Srityje **Nustatyti ryšį** pateikite reikiamą informaciją.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="cb5e9-129">**Rodomas pavadinimas** ir ryšio tipas apibūdina ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="cb5e9-130">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas šio ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="cb5e9-131">Tikslūs laukeliai priklauso nuo to, prie kokios paslaugos jungiatės.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="cb5e9-132">Apie konkretaus ryšio tipo duomenis galite sužinoti straipsnyje apie tikslinę paslaugą.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="cb5e9-133">Jei norite sukurti ryšį, pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="cb5e9-134">Taip pat galite pasirinkti **Nustatyti** plytelėje, esančioje skirtuke **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="cb5e9-135">Leidimas bendradarbiams naudoti ryšį eksportuojant</span><span class="sxs-lookup"><span data-stu-id="cb5e9-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="cb5e9-136">Nustatę arba redaguodami eksportavimo ryšį pasirenkate, kuriems naudotojams bus leidžiama naudoti šį konkretų ryšį [eksportavimui](export-destinations.md) apibrėžti.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="cb5e9-137">Pagal numatytuosius nustatymus ryšys prieinamas naudotojams, kuriems priskirtas administratoriaus vaidmuo.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="cb5e9-138">Šį parametrą galite keisti dalyje **Pasirinkite, kas gali naudoti šį ryšį** ir leisti šiuo ryšiu naudotis naudotojams, kuriems priskirtas bendradarbio vaidmuo.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="cb5e9-139">Bendradarbiai negalės peržiūrėti ar redaguoti ryšio.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="cb5e9-140">Rodomas pavadinimas ir jo tipas bus rodomi tik kuriant eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="cb5e9-141">Bendrindami ryšį leidžiate bendradarbiams naudoti ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="cb5e9-142">Nustatydami eksportavimą, bendradarbiai matys bendrai naudojamus ryšius.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="cb5e9-143">Jie gali valdyti kiekvieną eksportavimą, kuris naudoja šį konkretų ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="cb5e9-144">Šį parametrą galima keisti išlaikant eksportavimą, kurį jau yra nustatę bendradarbiai.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="cb5e9-145">Ryšio redagavimas</span><span class="sxs-lookup"><span data-stu-id="cb5e9-145">Edit a connection</span></span>

1. <span data-ttu-id="cb5e9-146">Eikite į **Administravimas** > **Ryšiai (peržiūra)**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="cb5e9-147">Eikite į skirtuką **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="cb5e9-148">Pažymėkite norimo redaguoti ryšio vertikalią elipsę.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="cb5e9-149">Pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-149">Select **Edit**.</span></span>

1. <span data-ttu-id="cb5e9-150">Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="cb5e9-151">Ryšio pašalinimas</span><span class="sxs-lookup"><span data-stu-id="cb5e9-151">Remove a connection</span></span>

<span data-ttu-id="cb5e9-152">Jei ryšys, kurį šalinate, naudojamas praturtinant ar eksportuojant, pirmiausia turite juos atsieti arba pašalinti.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="cb5e9-153">Šalinimo dialogas padės atlikti svarbius papildymus arba eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="cb5e9-154">Atsieti papildymai ir eksportavimai tampa neaktyvūs.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="cb5e9-155">Iš naujo suaktyvinate juos prie jų pridėdami kitą ryšį puslapyje [Papildymai](enrichment-hub.md) arba [Eksporavimai](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cb5e9-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="cb5e9-156">Eikite į **Administravimas** > **Ryšiai (peržiūra)**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="cb5e9-157">Eikite į skirtuką **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="cb5e9-158">Pažymėkite norimo pašalinti ryšio vertikalią elipsę.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="cb5e9-159">Išskleidžiamajame meniu pasirinkite **Pašalinti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="cb5e9-160">Rodomos patvirtinimo dialogas.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="cb5e9-161">Jei naudojant šį ryšį atliekami papildymai ar eksportavimai, pažymėkite mygtuką, kad pamatytumėte, kas naudoja ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="cb5e9-162">**Eksportavimai:** galite pasirinkti pašalinti arba atjungti eksportavimą, kad galėtumėte pašalinti ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="cb5e9-163">Norėdami atjungti eksportavimą, administratoriai gali naudoti veiksmą **Atjungti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="cb5e9-164">Šį veiksmą galima naudoti pavieniam arba keliems pasirinktiems eksportavimams.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="cb5e9-165">Atjungdami išlaikote eksportavimo konfigūraciją, tačiau ji nebus vykdoma, kol prie jos nebus pridėtas kitas ryšys.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="cb5e9-166">**Papildymai:** galite pasirinkti pašalinti arba atjungti papildymus, kad galėtumėte pašalinti ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="cb5e9-167">Kai ryšys nebeturi priklausomybių, grįžkite į **Administravimas** > **Ryšiai** ir dar kartą pabandykite pašalinti ryšį.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="cb5e9-168">Jei norite patvirtinti trynimą, pasirinkite **Šalinti**.</span><span class="sxs-lookup"><span data-stu-id="cb5e9-168">To confirm the deletion, select **Remove**.</span></span>

