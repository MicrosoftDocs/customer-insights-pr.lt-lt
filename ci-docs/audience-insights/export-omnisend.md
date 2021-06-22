---
title: „Customer Insights“ duomenų eksportavimas į „Omnisend“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Omnisend“.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124523"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="d3b4c-103">Segmentų eksportavimas į „Omnisend“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="d3b4c-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="d3b4c-104">Eksportuokite vieningųjų klientų profilių segmentus į „Omnisend“ ir naudokite juos rinkodaros veiklai.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3b4c-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="d3b4c-105">Prerequisites</span></span>

-   <span data-ttu-id="d3b4c-106">Turite [„Omnisend“ paskyrą](https://www.omnisend.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d3b4c-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d3b4c-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d3b4c-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="d3b4c-109">Known limitations</span></span>

- <span data-ttu-id="d3b4c-110">Vieno eksportavimo į „Omnisend” metu galite eksportuoti iki 1 milijono profilių ir tai gali užtrukti iki 4 valandų.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="d3b4c-111">Eksportavimas į „Omnisend“ apsiriboja segmentais.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="d3b4c-112">Profilių, kuriuos galite eksportuoti į „Omnisend”, skaičius priklauso nuo jūsų sutarties su „Omnisend”.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="d3b4c-113">Ryšio su „Omnisend“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="d3b4c-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="d3b4c-114">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d3b4c-115">Pasirinkite **Įtraukti ryšį** ir pasirinkite **„Omnisend“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="d3b4c-116">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d3b4c-117">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d3b4c-118">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d3b4c-119">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-119">Choose who can use this connection.</span></span> <span data-ttu-id="d3b4c-120">Pagal numatytuosius nustatymus, tik administratoriai.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-120">By default it's only administrators.</span></span> <span data-ttu-id="d3b4c-121">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d3b4c-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d3b4c-122">Įveskite savo [„Omnisend“ API raktą](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="d3b4c-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="d3b4c-123">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d3b4c-124">Pasirinkite **Prisijungti** ryšio su „Omnisend“ inicijavimui.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="d3b4c-125">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d3b4c-126">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d3b4c-127">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="d3b4c-127">Configure an export</span></span>

<span data-ttu-id="d3b4c-128">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d3b4c-129">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d3b4c-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d3b4c-130">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3b4c-131">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d3b4c-132">Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „Omnisend“ skyriaus.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="d3b4c-133">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d3b4c-134">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d3b4c-135">To reikia norint eksportuoti segmentus į „Omnisend“.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="d3b4c-136">Pasirinktinai galite eksportuoti Vardą, Pavardę, Adresą, Šalį/Regioną, Valstiją, Miestą ir Pašto kodą, jei norite sukurti labiau personalizuotus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="d3b4c-137">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="d3b4c-138">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-138">Select **Save**.</span></span>

<span data-ttu-id="d3b4c-139">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d3b4c-140">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d3b4c-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d3b4c-141">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d3b4c-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d3b4c-142">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="d3b4c-142">Data privacy and compliance</span></span>

<span data-ttu-id="d3b4c-143">Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „Omnisend“, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galima slaptus duomenis, pavyzdžiui, Asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d3b4c-144">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, kad „Omnisend“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d3b4c-145">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d3b4c-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d3b4c-146">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="d3b4c-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
