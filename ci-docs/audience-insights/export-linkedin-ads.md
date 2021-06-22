---
title: „Customer Insights“ duomenų eksportavimas į „LinkedIn Ads”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „LinkedIn Ads”.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124524"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="5d066-103">Segmentų eksportavimas į „LinkedIn Ads” (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="5d066-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="5d066-104">Eksportuokite vieningųjų klientų profilius į „LinkedIn Ads”, kad sukurtumėte „matched audiences”.</span><span class="sxs-lookup"><span data-stu-id="5d066-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="5d066-105">Naudokite „matched audiences”, kad būtų galima taikyti pagal įmonę ir pagal kontaktus.</span><span class="sxs-lookup"><span data-stu-id="5d066-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d066-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="5d066-106">Prerequisites</span></span>

-   <span data-ttu-id="5d066-107">Turite [„LinkedIn Campaign Manager” paskyrą](https://business.linkedin.com/marketing-solutions/ads) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="5d066-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5d066-108">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="5d066-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5d066-109">Klientų profiliuose, esančiuose eksportuotuose segmentuose, yra laukas su el. pašto adresu.</span><span class="sxs-lookup"><span data-stu-id="5d066-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5d066-110">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="5d066-110">Known limitations</span></span>

- <span data-ttu-id="5d066-111">Vienu metu į „LinkedIn Ads“ galite eksportuoti iki 100 tūkstančių profilių.</span><span class="sxs-lookup"><span data-stu-id="5d066-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="5d066-112">Eksportavimas į „LinkedIn Ads“ apsiriboja segmentais.</span><span class="sxs-lookup"><span data-stu-id="5d066-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="5d066-113">Iki 100 tūkstančių profilių eksportavimas į „LinkedIn Ads“ gali užtrukti iki 10 minučių.</span><span class="sxs-lookup"><span data-stu-id="5d066-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="5d066-114">Ryšio su „LinkedIn Ads” nustatymas</span><span class="sxs-lookup"><span data-stu-id="5d066-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="5d066-115">Auditorijos įžvalgose eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="5d066-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5d066-116">Pasirinkite **Įtrauktti ryšį** ir pasirinkite **„LinkedIn Ads“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="5d066-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="5d066-117">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="5d066-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5d066-118">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="5d066-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5d066-119">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="5d066-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5d066-120">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="5d066-120">Choose who can use this connection.</span></span> <span data-ttu-id="5d066-121">Jei neatliksite jokio veiksmo, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="5d066-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="5d066-122">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5d066-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5d066-123">Pateikite savo [„LinkedIn Campaign Manager” paskyros ID](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="5d066-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="5d066-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="5d066-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5d066-125">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Campaign Monitor“.</span><span class="sxs-lookup"><span data-stu-id="5d066-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="5d066-126">Pažymėkite **Autentifikuoti naudojant „LinkedIn“** ir pateikite savo „LinkedIn Campaign Manager“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="5d066-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="5d066-127">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="5d066-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5d066-128">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="5d066-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5d066-129">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5d066-129">Configure an export</span></span>

<span data-ttu-id="5d066-130">Galite sukonfigūruoti eksportavimą, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="5d066-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="5d066-131">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5d066-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5d066-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="5d066-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5d066-133">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="5d066-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5d066-134">Lauke **Ryšys eksportavimui** pasirinkite ryšį iš „LinkedIn Ads“ skyriaus.</span><span class="sxs-lookup"><span data-stu-id="5d066-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="5d066-135">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="5d066-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5d066-136">Pasirinkite, ar norite eksportuoti duomenis [taikymui pagal kontaktą](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ar [taikymui pagal įmonę](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) „LinkedIn” platformoje.</span><span class="sxs-lookup"><span data-stu-id="5d066-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="5d066-137">Skyriuje **Duomenų gretinimas** pasirinkite savo vieningojo kliento profilio lauką, atitinkantį kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="5d066-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5d066-138">To reikia norint eksportuoti segmentus į „LinkedIn Ads“.</span><span class="sxs-lookup"><span data-stu-id="5d066-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="5d066-139">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="5d066-139">Select the segments you want to export.</span></span> <span data-ttu-id="5d066-140">„Matched Audiences” bus automatiškai sukurtos „LinkedIn Campaign Manager” platformoje su eksportavimui pasirinktų segmentų pavadinimu.</span><span class="sxs-lookup"><span data-stu-id="5d066-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="5d066-141">Kiekviename segmente bus sukurta atskira „matched audience”.</span><span class="sxs-lookup"><span data-stu-id="5d066-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="5d066-142">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5d066-142">Select **Save**.</span></span>

<span data-ttu-id="5d066-143">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="5d066-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5d066-144">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5d066-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5d066-145">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5d066-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5d066-146">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="5d066-146">Data privacy and compliance</span></span>

<span data-ttu-id="5d066-147">Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „LinkedIn Ads“, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai slaptus duomenis, pavyzdžiui, Asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="5d066-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5d066-148">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už užtikrinimą, jog „LinkedIn Ads“ atitinka privatumo ir saugos įsipareigojimus, kuriuos jūs galimai turite.</span><span class="sxs-lookup"><span data-stu-id="5d066-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5d066-149">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5d066-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5d066-150">Jūsų „Dynamics 365 Customer Insights“ Administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad sustabdytų šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="5d066-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
