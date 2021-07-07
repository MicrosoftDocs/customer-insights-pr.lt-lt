---
title: „Customer Insights“ duomenų eksportavimas į „ActiveCampaign“
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „ActiveCampaign“.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314647"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="d835d-103">Segmentų eksportavimas į „ActiveCampaign“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="d835d-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="d835d-104">Eksportuokite vieningų klientų profilių segmentus į „ActiveCampaign" ir naudokite juos rinkodaros veiklai.</span><span class="sxs-lookup"><span data-stu-id="d835d-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d835d-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="d835d-105">Prerequisites</span></span>

-   <span data-ttu-id="d835d-106">Turite [„ActiveCampaign“ abonementą](https://www.activecampaign.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="d835d-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d835d-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="d835d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d835d-108">Vieningieji klientų profiliai, esantys eksportuotuose segmentuose, ir turintys lauką su el. pašto adresu.</span><span class="sxs-lookup"><span data-stu-id="d835d-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d835d-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="d835d-109">Known limitations</span></span>

- <span data-ttu-id="d835d-110">Eksportuojant į „ActiveCampaign" galima eksportuoti iki 1 milijonai profilių, jis gali trukti iki 90 minučių.</span><span class="sxs-lookup"><span data-stu-id="d835d-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="d835d-111">Eksportavimas į „ActiveCampaign“ ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="d835d-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="d835d-112">Profilių, kuriuos galite eksportuoti į „ActiveCampaign", skaičius priklauso nuo sutarties su „ActiveCampaign".</span><span class="sxs-lookup"><span data-stu-id="d835d-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="d835d-113">Nustatyti ryšį su „ActiveCampaign“</span><span class="sxs-lookup"><span data-stu-id="d835d-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="d835d-114">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="d835d-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d835d-115">Pasirinkite **Įtraukti ryšį** ir pasirinkite **ActiveCampaign,** kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="d835d-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="d835d-116">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="d835d-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d835d-117">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="d835d-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d835d-118">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="d835d-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d835d-119">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="d835d-119">Choose who can use this connection.</span></span> <span data-ttu-id="d835d-120">Pagal numatytuosius nustatymus, tik administratoriai.</span><span class="sxs-lookup"><span data-stu-id="d835d-120">By default, it's only administrators.</span></span> <span data-ttu-id="d835d-121">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d835d-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d835d-122">Įveskite savo [„ActiveCampaign API" raktą ir REST galinių punktų pagrindinio kompiuterio pavadinimą](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="d835d-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="d835d-123">REST galinio punkto pagrindinio kompiuterio vardas yra tik pagrindinio kompiuterio vardas be https://.</span><span class="sxs-lookup"><span data-stu-id="d835d-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="d835d-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="d835d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d835d-125">Pasirinkite **Prisijungti** siekiant pradėti jungį su „ActiveCampaign“.</span><span class="sxs-lookup"><span data-stu-id="d835d-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="d835d-126">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="d835d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d835d-127">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="d835d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d835d-128">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="d835d-128">Configure an export</span></span>

<span data-ttu-id="d835d-129">Galite sukonfigūruoti eksportavimą, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="d835d-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="d835d-130">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d835d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d835d-131">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="d835d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d835d-132">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="d835d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d835d-133">Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „ActiveCampaign“.</span><span class="sxs-lookup"><span data-stu-id="d835d-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="d835d-134">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="d835d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d835d-135">Įveskite savo [**ActiveCampaign sąrašo ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="d835d-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="d835d-136">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="d835d-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d835d-137">Būtina eksportuoti segmentus į „ActiveCampaign“.</span><span class="sxs-lookup"><span data-stu-id="d835d-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="d835d-138">Arba galite eksportuoti vardas, pavardė ir telefonas sukurtumėte labiau personalizuotus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="d835d-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="d835d-139">Pasirinkite Įtraukti atributą siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="d835d-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="d835d-140">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="d835d-140">Select **Save**.</span></span>

<span data-ttu-id="d835d-141">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="d835d-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d835d-142">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d835d-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d835d-143">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d835d-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d835d-144">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="d835d-144">Data privacy and compliance</span></span>

<span data-ttu-id="d835d-145">Kai leidžiate perduoti duomenis į „Dynamics 365 Customer Insights“ leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis „ActiveCampaign“, „Dynamics 365 Customer Insights“, įskaitant galimai jautrius, tokius kaip asmens.</span><span class="sxs-lookup"><span data-stu-id="d835d-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d835d-146">„Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „ActiveCampaign“ privatumo arba saugos apsauga.</span><span class="sxs-lookup"><span data-stu-id="d835d-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d835d-147">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d835d-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d835d-148">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="d835d-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
