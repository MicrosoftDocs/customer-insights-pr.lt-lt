---
title: „Customer Insights“ duomenų eksportavimas į „Campaign Monitor“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Campaign Monitor“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124191"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="b3adb-103">Segmentų eksportavimas į „Campaign Monitor“ (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="b3adb-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="b3adb-104">Eksportuokite vieningų klientų profilių segmentus į „Campaign Monitor“ ir naudokite juos rinkodaros veiklai.</span><span class="sxs-lookup"><span data-stu-id="b3adb-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3adb-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="b3adb-105">Prerequisites</span></span>

-   <span data-ttu-id="b3adb-106">Turite [„Campaign Monitor“ paskyros](https://www.campaignmonitor.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="b3adb-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b3adb-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="b3adb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b3adb-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="b3adb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b3adb-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="b3adb-109">Known limitations</span></span>

- <span data-ttu-id="b3adb-110">Vienu metu į „Campaign Monitor“ galima eksportuoti iki 1 milijono profilių.</span><span class="sxs-lookup"><span data-stu-id="b3adb-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="b3adb-111">Eksportavimas į „Campaign Monitor“ leidžiamas tik segmentuose.</span><span class="sxs-lookup"><span data-stu-id="b3adb-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="b3adb-112">Iki 1 milijono profilių eksportavimas į „Campaign Monitor“ gali užtrukti iki 20 min.</span><span class="sxs-lookup"><span data-stu-id="b3adb-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="b3adb-113">Profilių, kuriuos galite eksportuoti į „Campaign Monitor“ yra ribojamas ir priklauso nuo jūsų sutarties su „Campaign Monitor“.</span><span class="sxs-lookup"><span data-stu-id="b3adb-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="b3adb-114">Ryšio su „Campaign Monitor“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="b3adb-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="b3adb-115">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="b3adb-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b3adb-116">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Campaign Monitor“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="b3adb-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="b3adb-117">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="b3adb-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b3adb-118">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="b3adb-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b3adb-119">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="b3adb-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b3adb-120">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="b3adb-120">Choose who can use this connection.</span></span> <span data-ttu-id="b3adb-121">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="b3adb-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b3adb-122">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b3adb-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b3adb-123">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="b3adb-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b3adb-124">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Campaign Monitor“.</span><span class="sxs-lookup"><span data-stu-id="b3adb-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="b3adb-125">Pažymėkite **Autentifikuoti naudojant „Campaign Monitor“** ir pateikite savo „Campaign Monitor“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="b3adb-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="b3adb-126">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="b3adb-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b3adb-127">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="b3adb-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b3adb-128">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b3adb-128">Configure an export</span></span>

<span data-ttu-id="b3adb-129">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="b3adb-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b3adb-130">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b3adb-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b3adb-131">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="b3adb-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b3adb-132">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="b3adb-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b3adb-133">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Campaign Monitor“.</span><span class="sxs-lookup"><span data-stu-id="b3adb-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="b3adb-134">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="b3adb-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b3adb-135">Įveskite savo [**„Campaign Monitor“ sąrašo ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="b3adb-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="b3adb-136">[Norėdami peržiūrėti PI sąrašo ID pirmiausia sugeneruokite API raktą](https://www.campaignmonitor.com/api/getting-started/) „Campaign Monitor“ **paskyros nustatymų** srityje.</span><span class="sxs-lookup"><span data-stu-id="b3adb-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="b3adb-137">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="b3adb-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b3adb-138">To reikia norint segmentus eksportuoti į „Campaign Monitor“.</span><span class="sxs-lookup"><span data-stu-id="b3adb-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="b3adb-139">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="b3adb-139">Select **Save**.</span></span>

<span data-ttu-id="b3adb-140">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="b3adb-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b3adb-141">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b3adb-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b3adb-142">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b3adb-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b3adb-143">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="b3adb-143">Data privacy and compliance</span></span>

<span data-ttu-id="b3adb-144">Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „Campaign Monitor“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis.</span><span class="sxs-lookup"><span data-stu-id="b3adb-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b3adb-145">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „Campaign Monitor“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="b3adb-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b3adb-146">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b3adb-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b3adb-147">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="b3adb-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
