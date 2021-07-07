---
title: Žiniatinklio duomenų integravimas su įtraukimo įžvalgomis auditorijų apžvalgoje
description: Galite pateikti klientų žiniatinklio informaciją nuo įtraukimo įžvalgų iki auditorijos įžvalgų.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305028"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="1fb48-103">Žiniatinklio duomenų integravimas su įtraukimo įžvalgomis auditorijų apžvalgoje</span><span class="sxs-lookup"><span data-stu-id="1fb48-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="1fb48-104">Klientai dažnai kasdien pavedimus atlieka internetu, naudodami interneto svetaines.</span><span class="sxs-lookup"><span data-stu-id="1fb48-104">Customers often do their day-to-day transactions online using web sites.</span></span> <span data-ttu-id="1fb48-105">Įtraukimo įžvalgų (peržiūros) galimybė yra „Dynamics 365 Customer Insights“ patogus sprendimas integruoti žiniatinklio duomenis kaip šaltinį.</span><span class="sxs-lookup"><span data-stu-id="1fb48-105">The engagement insights (preview) capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="1fb48-106">Be operacijų, demografinių ar elgsenos duomenų veiklą žiniatinklyje galime matyti vieninguose klientų profiliuose.</span><span class="sxs-lookup"><span data-stu-id="1fb48-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="1fb48-107">Naudodami šiuos profilius galime gauti papildomų įžvalgų, pvz., segmentų, priemonių ar auditorijos suaktyvinimo prognozių.</span><span class="sxs-lookup"><span data-stu-id="1fb48-107">We can use these profiles to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="1fb48-108">Šiame straipsnyje aprašomi veiksmai, kurių reikia norint klientų žiniatinklio veiklos duomenis pateikti iš įtraukimo įžvalgų į esamą auditorijos įžvalgų aplinką.</span><span class="sxs-lookup"><span data-stu-id="1fb48-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="1fb48-109">Šiame pavyzdyje tarkime, kad aplinkoje yra vieningų klientų profilių.</span><span class="sxs-lookup"><span data-stu-id="1fb48-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="1fb48-110">Profiliai buvo suvienodinti su apklausų, mažmeninės prekybos ir bilietų pardavimo sistemos šaltiniais.</span><span class="sxs-lookup"><span data-stu-id="1fb48-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="1fb48-111">Čia taip pat rodoma susijusi klientų veikla.</span><span class="sxs-lookup"><span data-stu-id="1fb48-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="1fb48-112">Dabar norėtume žinoti, ar klientas lankosi mūsų žiniatinklio ypatybėse ir supranta jų veiklą.</span><span class="sxs-lookup"><span data-stu-id="1fb48-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="1fb48-113">Veiklos apima, pvz.: peržiūrėtus produktų puslapius iš el. paštu gautų saitų arba peržiūrėtus produktų puslapius.</span><span class="sxs-lookup"><span data-stu-id="1fb48-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fb48-114">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="1fb48-114">Prerequisites</span></span>

<span data-ttu-id="1fb48-115">Norint integruoti duomenis iš įtraukimo įžvalgų, reikia įvykdyti kelias būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="1fb48-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="1fb48-116">Integruokite įtraukimo įžvalgų SDK į svetainę.</span><span class="sxs-lookup"><span data-stu-id="1fb48-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="1fb48-117">Daugiau informacijos žr. [Kūrėjų resursų apžvalga](../engagement-insights/developer-resources.md).</span><span class="sxs-lookup"><span data-stu-id="1fb48-117">For more information, see [Developer resources overview](../engagement-insights/developer-resources.md).</span></span>
- <span data-ttu-id="1fb48-118">Norint eksportuoti žiniatinklio įvykius iš įtraukimo įžvalgų, reikalinga prieiga prie kliento, kuris bus naudojamas žiniatinklio „Azure Data Lake Storage“ įvykių duomenims pereiti prie auditorijos įžvalgų.</span><span class="sxs-lookup"><span data-stu-id="1fb48-118">Exporting web events from engagement insights requires access to an Azure Data Lake Storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="1fb48-119">Daugiau informacijos ieškokite [Terminų atnaujinimas](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="1fb48-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="1fb48-120">Patobulintos įvykių konfigūravimas įtraukimo įžvalgose</span><span class="sxs-lookup"><span data-stu-id="1fb48-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="1fb48-121">Kai administratorius sustoją svetainę su įtraukimo įžvalgų SDK, *pagrindiniai įvykiai* surenkami vartotojui rodius tinklalapį arba spusteli išsamūs.</span><span class="sxs-lookup"><span data-stu-id="1fb48-121">After an administrator instruments a website with the engagement insights SDK, *base events* are gathered when a user views a webpage or clicks somewhere.</span></span> <span data-ttu-id="1fb48-122">Pagrindiniai įvykiai pateikia išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="1fb48-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="1fb48-123">Atsižvelgiant į naudojimo atvejį, jums reikalingas tik pagrindinio įvykio duomenų antrinis rinkinys.</span><span class="sxs-lookup"><span data-stu-id="1fb48-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="1fb48-124">Naudodami įtraukimo įžvalgas galite kurti *tobulintinus įvykius*, kuriuose yra tik jūsų pasirinkto pagrindinio įvykio ypatybės.</span><span class="sxs-lookup"><span data-stu-id="1fb48-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="1fb48-125">Daugiau informacijos ieškokite [Patobulintos įvykių kūrimas ir modifikavimas](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="1fb48-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="1fb48-126">Aspektai kuriant tobulintinus įvykius:</span><span class="sxs-lookup"><span data-stu-id="1fb48-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="1fb48-127">Teikia prasmingą patikslintame įvykyje pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="1fb48-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="1fb48-128">Jis bus naudojamas kaip veiklos pavadinimas auditorijos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="1fb48-128">It will be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="1fb48-129">Jei norite kurti veiklą auditorijos įžvalgose, pasirinkite bent šias ypatybes:</span><span class="sxs-lookup"><span data-stu-id="1fb48-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="1fb48-130">Signal.Action.Name – nurodoma išsami veiklos informacija.</span><span class="sxs-lookup"><span data-stu-id="1fb48-130">Signal.Action.Name – indicates the activity details.</span></span>
    - <span data-ttu-id="1fb48-131">Signal.User.Id – naudojama susieti su kliento ID.</span><span class="sxs-lookup"><span data-stu-id="1fb48-131">Signal.User.Id – used to map with the customer ID.</span></span>
    - <span data-ttu-id="1fb48-132">Signal.View.Uri – naudojamas kaip žiniatinklio adresas kaip segmentų arba priemonių pagrindas.</span><span class="sxs-lookup"><span data-stu-id="1fb48-132">Signal.View.Uri – used as a web address as a basis for segments or measures.</span></span>
    - <span data-ttu-id="1fb48-133">Signal.Export.Id – naudojamas kaip pirminis įvykių raktas.</span><span class="sxs-lookup"><span data-stu-id="1fb48-133">Signal.Export.Id – used as a primary key for events.</span></span>
    - <span data-ttu-id="1fb48-134">Signal.Timestamp – nustato apklausos veiklos kanalo data ir laikas.</span><span class="sxs-lookup"><span data-stu-id="1fb48-134">Signal.Timestamp – determines the date and time for the activity.</span></span>

<span data-ttu-id="1fb48-135">Pažymėkite filtrus, sufokusuojamus į įvykius ir puslapius, kurie susiję su jūsų naudojimo atveju.</span><span class="sxs-lookup"><span data-stu-id="1fb48-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="1fb48-136">Šiame pavyzdyje naudosime veiksmo pavadinimą „El. pašto reklama”.</span><span class="sxs-lookup"><span data-stu-id="1fb48-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="1fb48-137">Eksportuoti tobulintus žiniatinklio įvykius</span><span class="sxs-lookup"><span data-stu-id="1fb48-137">Export the refined web events</span></span> 

<span data-ttu-id="1fb48-138">Apibrėžę patobulintą įvykį turite sukonfigūruoti įvykių duomenų eksportavimą į, kurį galima nustatyti duomenų šaltinis auditorijos įžvalgų „Azure Data Lake Storage“ prarijus.</span><span class="sxs-lookup"><span data-stu-id="1fb48-138">After defining the refined event, you have to configure the export of the event data to Azure Data Lake Storage, which can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="1fb48-139">Iš žiniatinklio ypatybės nuolat eksportuojama kaip įvykiai.</span><span class="sxs-lookup"><span data-stu-id="1fb48-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="1fb48-140">Daugiau informacijos ieškokite [Terminų atnaujinimas](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="1fb48-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="1fb48-141">Pereidami įvykių duomenis prie auditorijos įžvalgų</span><span class="sxs-lookup"><span data-stu-id="1fb48-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="1fb48-142">Dabar, kai apibrėšite patobulintą įvykį ir sukonfigūravote jo eksportavimą, pereisime prie duomenų įkėlimo į auditorijos įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="1fb48-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="1fb48-143">Turite sukurti naują duomenų šaltinį pagal aplanką „Įprastas duomenų modelis”.</span><span class="sxs-lookup"><span data-stu-id="1fb48-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="1fb48-144">Įveskite saugyklos, į kurią eksportuojate įvykius, išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="1fb48-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="1fb48-145">*default.cdm.json* faile pažymėkite patobulintą įvykį ir sukurkite objektą auditorijos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="1fb48-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="1fb48-146">Daugiau informacijos žr. [Prisijungimas prie „Common Data Model“ naudojant „Azure Data Lake” paskyrą](connect-common-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="1fb48-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md).</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="1fb48-147">Patobulinti įvykių duomenys susieti su kliento profilio veikla</span><span class="sxs-lookup"><span data-stu-id="1fb48-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="1fb48-148">Papildę objektą galite sukonfigūruoti kliento profilio veiklą.</span><span class="sxs-lookup"><span data-stu-id="1fb48-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="1fb48-149">Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).</span><span class="sxs-lookup"><span data-stu-id="1fb48-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Veiklos puslapis su išplėsta veiklos redagavimo sritimi ir laukais.":::

<span data-ttu-id="1fb48-151">Sukonfigūruokite naują veiklą naudodami šį susiejimą:</span><span class="sxs-lookup"><span data-stu-id="1fb48-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="1fb48-152">**Pirminis raktas**: Signal.Export.Id– unikalus ID, pasiekiamas kiekvienam įvykio įrašui įtraukimo įžvalgų metu.</span><span class="sxs-lookup"><span data-stu-id="1fb48-152">**Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="1fb48-153">Ši ypatybė generuojama automatiškai.</span><span class="sxs-lookup"><span data-stu-id="1fb48-153">This property is automatically generated.</span></span>

- <span data-ttu-id="1fb48-154">**Laiko žyma**: įvykio ypatybės signalo laiko žyma.</span><span class="sxs-lookup"><span data-stu-id="1fb48-154">**Timestamp**: Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="1fb48-155">**Įvykis**: Signal.Name, norimo naudoti įvykio pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="1fb48-155">**Event**: Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="1fb48-156">**Žiniatinklio adresas**: signal.View.Uri nurodantis įvykį sukūrusio puslapio URI.</span><span class="sxs-lookup"><span data-stu-id="1fb48-156">**Web address**: Signal.View.Uri referring to the URI of the page that created the event.</span></span>

- <span data-ttu-id="1fb48-157">**Išsami informacija**: Signal.Action.Name pateikti informaciją, susijusią su įvykiu.</span><span class="sxs-lookup"><span data-stu-id="1fb48-157">**Details**: Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="1fb48-158">Pažymėta ypatybė tokiu atveju nurodo, kad įvykis skirtas el. pašto reklamai.</span><span class="sxs-lookup"><span data-stu-id="1fb48-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="1fb48-159">**Veiklos tipas**: šiame pavyzdyje pasirinkite esamą veiklos tipą "WebLog".</span><span class="sxs-lookup"><span data-stu-id="1fb48-159">**Activity type**: In this example, we choose the existing activity type WebLog.</span></span> <span data-ttu-id="1fb48-160">Šis pasirinkimas yra naudinga filtro parinktis, norint prognozė modelius ar kurti segmentus pagal šį veiklos tipą.</span><span class="sxs-lookup"><span data-stu-id="1fb48-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="1fb48-161">**Ryšio nustatymas** : šiuo svarbiu parametru veikla susijusi su esamais klientų profiliais.</span><span class="sxs-lookup"><span data-stu-id="1fb48-161">**Set up relationship**: This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="1fb48-162">**Signal.User.Id** yra identifikatorius, sukonfigūruotas SDK, kurį reikia rinkti ir kuris susijęs su vartotojo ID kituose duomenų šaltiniuose, sukonfigūruotuose auditorijos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="1fb48-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="1fb48-163">Šiame pavyzdyje konfigūruojame ryšį tarp "Signal.User.Id" ir "RetailCustomers:Customer VideoilId", kuris yra pirminis raktas, kuris buvo nustatytas duomenų suvienodinimo proceso struktūros žingsnyje.</span><span class="sxs-lookup"><span data-stu-id="1fb48-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.</span></span>

<span data-ttu-id="1fb48-164">Apdorojus veiklas galite peržiūrėti klientų įrašus ir atidaryti kliento korteles, kad veiklas peržiūrėtumėte iš įtraukimo įžvalgų laiko planavimo juostoje.</span><span class="sxs-lookup"><span data-stu-id="1fb48-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="1fb48-165">Norėdami rasti kliento ID, kuriame yra įtraukimo įžvalgų veikla, eikite į **Objektai** ir peržiūrėkite objekto UnifiedActivity duomenis.</span><span class="sxs-lookup"><span data-stu-id="1fb48-165">To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="1fb48-166">ActivityTypeDisplay = "WebLog" yra įtraukimo įžvalgų veikla, sukonfigūruota aukščiau pateiktame pavyzdyje.</span><span class="sxs-lookup"><span data-stu-id="1fb48-166">ActivityTypeDisplay = WebLog contains the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="1fb48-167">Nukopijuokite vieno iš šių įrašų kliento ID ir to ID **klientų** puslapyje.</span><span class="sxs-lookup"><span data-stu-id="1fb48-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1fb48-168">Paskesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="1fb48-168">Next steps</span></span>

<span data-ttu-id="1fb48-169">Dabar galite kurti [segmentus](segments.md), [priemones](measures.md) ir [prognozes](predictions.md) prasmingo ryšio su klientais kūrimui.</span><span class="sxs-lookup"><span data-stu-id="1fb48-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
