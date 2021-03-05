---
title: Eksportuoti „Customer Insights“ duomenis į „Google Ads“
description: Sužinokite, kaip konfigūruoti jungtį su „Google Ads“.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268972"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="c964a-103">Jungtis „Google Ads“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="c964a-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="c964a-104">Eksportuoti suvienodintų kliento profilių segmentus į „Google Ads“ publikos sąrašą ir naudoti juos reklamavimui „Google Search“, „Gmail“, „YouTube“ ir „Google Display Network“.</span><span class="sxs-lookup"><span data-stu-id="c964a-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c964a-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="c964a-105">Prerequisites</span></span>

-   <span data-ttu-id="c964a-106">Turite [„Google Ads“ paskyrą](https://ads.google.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="c964a-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c964a-107">Yra esančių publikų „Google Ads“ ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="c964a-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="c964a-108">Dėl daugiau informacijos, žr. [„Google Ads“ publikos](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="c964a-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="c964a-109">Turite [konfigūruoti segmentus](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c964a-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c964a-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelius rodančius el. pašto adresą, vardą ir pavardę</span><span class="sxs-lookup"><span data-stu-id="c964a-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="c964a-111">Prisijungti prie „Google Ads“</span><span class="sxs-lookup"><span data-stu-id="c964a-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="c964a-112">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="c964a-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c964a-113">Skyriuje **„Google Ads“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="c964a-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="c964a-114">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="c964a-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c964a-115">Įveskite savo **[„Google Ads“ kliento ID](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="c964a-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="c964a-116">Įveskite savo **[„Google Ads“ patvirtinto kūrėjo žymą](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="c964a-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="c964a-117">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="c964a-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c964a-118">Įveskite savo **[„Google Ads“ publikos ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ir pasirinkite **Sujungti** tam, kad pradėtumėte sujungimą su „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="c964a-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="c964a-119">Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="c964a-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="c964a-120">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="c964a-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Eksportuoti momentinę nuotrauką „Google Ads“ jungčiai":::

1. <span data-ttu-id="c964a-122">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="c964a-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c964a-123">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="c964a-123">Configure the connector</span></span>

1. <span data-ttu-id="c964a-124">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="c964a-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c964a-125">Pakartokite tuos pačius žingsnius **Vardo** ir **Pavardės** laukeliams.</span><span class="sxs-lookup"><span data-stu-id="c964a-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="c964a-126">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="c964a-126">Select the segments you want to export.</span></span> <span data-ttu-id="c964a-127">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="c964a-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="c964a-128">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="c964a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c964a-129">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="c964a-129">Export the data</span></span>

<span data-ttu-id="c964a-130">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c964a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c964a-131">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c964a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c964a-132">„Google Ads“ galite dabar surasti savo segmentus skyriuje [„Google Ads“ publikos](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="c964a-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c964a-133">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="c964a-133">Known limitations</span></span>

- <span data-ttu-id="c964a-134">Iki 1 milijono profilių vieno eksportavimo metu į „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="c964a-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="c964a-135">Eksportavimas į „Google Ads“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="c964a-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="c964a-136">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 5 minučių dėl apribojimų tiekėjo pusėje.</span><span class="sxs-lookup"><span data-stu-id="c964a-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="c964a-137">Suderinamumas „Google Ads“ gali trukti iki 48 valandų.</span><span class="sxs-lookup"><span data-stu-id="c964a-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c964a-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="c964a-138">Data privacy and compliance</span></span>

<span data-ttu-id="c964a-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Google Ads“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="c964a-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c964a-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Google Ads“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="c964a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c964a-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c964a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c964a-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="c964a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]