---
title: „Customer Insights“ duomenų eksportavimas į „Microsoft Advertising“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Microsoft Advertising“.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124522"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="c9b35-103">Segmentų eksportavimas į „Microsoft Advertising“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="c9b35-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="c9b35-104">Eksportuokite „Customer Insights” segmentus į „Microsoft Advertising”, kad sukurtumėte Klientų atitikmenų auditorijas.</span><span class="sxs-lookup"><span data-stu-id="c9b35-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="c9b35-105">Naudokite šias auditorijas savo reklamos kampanijoms.</span><span class="sxs-lookup"><span data-stu-id="c9b35-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c9b35-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="c9b35-106">Prerequisites</span></span>

-   <span data-ttu-id="c9b35-107">[„Microsoft Advertising“ paskyra](https://ads.microsoft.com/) ir atitinkami administratoriaus kredencialai.</span><span class="sxs-lookup"><span data-stu-id="c9b35-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c9b35-108">Priėmėte „Customer Match” naudojimo sąlygas.</span><span class="sxs-lookup"><span data-stu-id="c9b35-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="c9b35-109">[Sukonfigūruoti segmentai](segments.md) auditorijos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="c9b35-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c9b35-110">Vieningieji klientų profiliai, esantys eksportuotuose segmentuose, ir turintys lauką su el. pašto adresu.</span><span class="sxs-lookup"><span data-stu-id="c9b35-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c9b35-111">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="c9b35-111">Known limitations</span></span>

- <span data-ttu-id="c9b35-112">Vienu metu į „Microsoft Advertising“ galima eksportuoti iki 500 tūkstančių profilių.</span><span class="sxs-lookup"><span data-stu-id="c9b35-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="c9b35-113">Eksportavimas į „Microsoft Advertising“ apsiriboja segmentais.</span><span class="sxs-lookup"><span data-stu-id="c9b35-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="c9b35-114">Iki 500 tūkstančių profilių eksportavimas į „Microsoft Advertising“ gali užtrukti iki 10 minučių.</span><span class="sxs-lookup"><span data-stu-id="c9b35-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="c9b35-115">Ryšio su „Microsoft Advertising” nustatymas</span><span class="sxs-lookup"><span data-stu-id="c9b35-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="c9b35-116">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c9b35-117">Pasirinkite **Įtrauktti ryšį** ir pasirinkite **„Microsoft Advertising“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="c9b35-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="c9b35-118">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c9b35-119">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="c9b35-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c9b35-120">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="c9b35-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c9b35-121">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="c9b35-121">Choose who can use this connection.</span></span> <span data-ttu-id="c9b35-122">Numatytasis parametras yra administratoriai.</span><span class="sxs-lookup"><span data-stu-id="c9b35-122">The default is administrators.</span></span> <span data-ttu-id="c9b35-123">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c9b35-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c9b35-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c9b35-125">Pasirinkite **Prisijungti** ryšio su „Microsoft Advertising“ inicijavimui.</span><span class="sxs-lookup"><span data-stu-id="c9b35-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="c9b35-126">Pažymėkite **Autentifikuoti naudojant „Microsoft Advertising“** ir pateikite savo „Microsoft Advertising“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="c9b35-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="c9b35-127">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="c9b35-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c9b35-128">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="c9b35-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="c9b35-129">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="c9b35-129">Configure an export</span></span>

<span data-ttu-id="c9b35-130">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="c9b35-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c9b35-131">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c9b35-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c9b35-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c9b35-133">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="c9b35-134">Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „Microsoft Advertising“ skyriaus.</span><span class="sxs-lookup"><span data-stu-id="c9b35-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="c9b35-135">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="c9b35-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c9b35-136">Pasirinkite segmentus eksportavimui.</span><span class="sxs-lookup"><span data-stu-id="c9b35-136">Select the segments to export.</span></span> <span data-ttu-id="c9b35-137">Klientų atitikmens auditorijos yra automatiškai sukuriamos „Microsoft Advertising” su eksportavimui pasirinktų segmentų pavadinimu.</span><span class="sxs-lookup"><span data-stu-id="c9b35-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="c9b35-138">Kiekviename segmente bus sukurta atskira Klientų atitikmens auditorija.</span><span class="sxs-lookup"><span data-stu-id="c9b35-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="c9b35-139">Įveskite savo **„Microsoft Advertising” Kliento ID ir Paskyros ID**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="c9b35-140">Galite rasti Kliento ID (`cid`) ir Paskyros ID (`aid`) URL parametruose, kai esate prisijungę prie „Microsoft Advertising”.</span><span class="sxs-lookup"><span data-stu-id="c9b35-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="c9b35-141">Skyriaus **Duomenų gretinimas** lauke **El. paštas** pasirinkite savo vieningojo kliento profilio lauką su kliento el. pašto adresu.</span><span class="sxs-lookup"><span data-stu-id="c9b35-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="c9b35-142">To reikia norint eksportuoti segmentus į „Microsoft Advertising“.</span><span class="sxs-lookup"><span data-stu-id="c9b35-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="c9b35-143">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="c9b35-143">Select **Save**.</span></span>

<span data-ttu-id="c9b35-144">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="c9b35-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c9b35-145">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c9b35-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c9b35-146">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c9b35-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c9b35-147">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="c9b35-147">Data privacy and compliance</span></span>

<span data-ttu-id="c9b35-148">Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „Microsoft Advertising“, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai slaptus duomenis, pavyzdžiui, Asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="c9b35-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c9b35-149">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, jog „Microsoft Advertising“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite.</span><span class="sxs-lookup"><span data-stu-id="c9b35-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c9b35-150">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c9b35-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="c9b35-151">Jūsų „Dynamics 365 Customer Insights“ Administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu tam, kad sustabdytų šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="c9b35-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
