---
title: „Customer Insights” duomenų eksportavimas į „Autopilot”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Autopilot“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760153"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="92cfa-103">Segmentų eksportavimas į „Autopilot“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="92cfa-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="92cfa-104">Eksportuokite vieningųjų klientų profilių segmentus į „Autopilot” kontaktų sąrašus ir naudokite juos el. pašto rinkodarai naudojant „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="92cfa-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="92cfa-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="92cfa-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="92cfa-106">Turite [„Autopilot” abonementą](https://www.autopilothq.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="92cfa-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="92cfa-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="92cfa-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="92cfa-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="92cfa-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="92cfa-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="92cfa-109">Known limitations</span></span>

- <span data-ttu-id="92cfa-110">Į „Autopilot” iš viso galima eksportuoti iki 100 000 profilių.</span><span class="sxs-lookup"><span data-stu-id="92cfa-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="92cfa-111">Eksportavimas į „Autopilot” ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="92cfa-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="92cfa-112">Iki 100 000 profilių eksportavimas į „Autopilot” gali užtrukti iki kelių valandų.</span><span class="sxs-lookup"><span data-stu-id="92cfa-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="92cfa-113">Profilių, kuriuos galite eksportuoti į „Autopilot”, skaičius yra priklausomas ir apribotas pagal jūsų sutartį su „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="92cfa-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="92cfa-114">Ryšio su „Autopilot“ sąranka</span><span class="sxs-lookup"><span data-stu-id="92cfa-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="92cfa-115">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="92cfa-116">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Autopilot“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="92cfa-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="92cfa-117">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="92cfa-118">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="92cfa-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="92cfa-119">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="92cfa-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="92cfa-120">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="92cfa-120">Choose who can use this connection.</span></span> <span data-ttu-id="92cfa-121">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="92cfa-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="92cfa-122">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="92cfa-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="92cfa-123">Įveskite [„Autopilot“ API raktą](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="92cfa-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="92cfa-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="92cfa-125">Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="92cfa-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="92cfa-126">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="92cfa-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="92cfa-127">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="92cfa-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="92cfa-128">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="92cfa-128">Configure an export</span></span>

<span data-ttu-id="92cfa-129">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="92cfa-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="92cfa-130">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="92cfa-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="92cfa-131">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="92cfa-132">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="92cfa-133">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Autopilot“.</span><span class="sxs-lookup"><span data-stu-id="92cfa-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="92cfa-134">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="92cfa-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="92cfa-135">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="92cfa-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="92cfa-136">Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.: **Vardas** ar **Pavardė**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="92cfa-137">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="92cfa-137">Select the segments you want to export.</span></span> <span data-ttu-id="92cfa-138">Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="92cfa-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="92cfa-139">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="92cfa-139">Select **Save**.</span></span>

<span data-ttu-id="92cfa-140">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="92cfa-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="92cfa-141">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="92cfa-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="92cfa-142">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="92cfa-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92cfa-143">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="92cfa-143">Data privacy and compliance</span></span>

<span data-ttu-id="92cfa-144">Kai leidžiate perduoti duomenis iš „Dynamics 365 Customer Insights” į „Autopilot”, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="92cfa-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92cfa-145">„Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „Autopilot” atitiktų privatumo arba saugos reikalavimus.</span><span class="sxs-lookup"><span data-stu-id="92cfa-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="92cfa-146">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92cfa-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="92cfa-147">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="92cfa-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
