---
title: Eksportuoti „Customer Insights“ duomenis į „DotDigital“
description: Sužinokite, kaip konfigūruoti jungtį su „DotDigital“.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269110"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="bc275-103">Jungtis „DotDigital“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="bc275-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="bc275-104">Eksportuokite suvienodintų klientų profilio segmentus į „DotDigital“ adresų knygas ir naudokite juos kampanijos, el. pašto reklamavimui ir siekiant kurti tinkintus segmentus su „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="bc275-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="bc275-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="bc275-105">Prerequisites</span></span>

-   <span data-ttu-id="bc275-106">Turite [„DotDigital“ paskyrą](https://dotdigital.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="bc275-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bc275-107">Yra esančių adreso knygų „DotDigital“ ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="bc275-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="bc275-108">ID gali būti prieinamas URL, kurį pasirinkote ir atvėrėte adresų knygoje.</span><span class="sxs-lookup"><span data-stu-id="bc275-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="bc275-109">Dėl daugiau informacijos, žr. [„DotDigital“ adresų knygos](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="bc275-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="bc275-110">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="bc275-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bc275-111">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="bc275-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="bc275-112">Prisijunkite prie „DotDigital“</span><span class="sxs-lookup"><span data-stu-id="bc275-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="bc275-113">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="bc275-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bc275-114">Skyriuje **„DotDigital“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="bc275-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="bc275-115">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="bc275-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigūravimo juosta „DotDigital“ eksportavimui.":::

1. <span data-ttu-id="bc275-117">Įveskite savo **„DotDigital“ vartotojo vardą ir slaptažodį**.</span><span class="sxs-lookup"><span data-stu-id="bc275-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="bc275-118">Įveskite savo **[„DotDigital“ adreso knygos ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="bc275-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="bc275-119">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="bc275-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bc275-120">Pasirinkite **Sujungti** siekiant pradėti sujungimą su „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="bc275-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="bc275-121">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="bc275-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bc275-122">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="bc275-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="bc275-123">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="bc275-123">Configure the connector</span></span>

1. <span data-ttu-id="bc275-124">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="bc275-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bc275-125">Pakartokite tuos pačius žingsnius kitiems pasirenkamiems laukeliams, tokius kaip **Vardas**, **Pavardė**, **Vardas ir pavardė**, **Lytis** ir **Pašto kodas**.</span><span class="sxs-lookup"><span data-stu-id="bc275-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="bc275-126">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="bc275-126">Select the segments you want to export.</span></span> <span data-ttu-id="bc275-127">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="bc275-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="bc275-128">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="bc275-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bc275-129">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="bc275-129">Export the data</span></span>

<span data-ttu-id="bc275-130">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bc275-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bc275-131">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc275-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bc275-132">„DotDigital“ galite dabar surasti savo segmentus skyriuje [„DotDigital“ adresų knygose](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="bc275-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bc275-133">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="bc275-133">Known limitations</span></span>

- <span data-ttu-id="bc275-134">Iki 1 milijono profilių vieno eksportavimo metu į „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="bc275-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="bc275-135">Eksportavimas į „DotDigital“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="bc275-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="bc275-136">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų dėl apribojimų tiekėjo pusėje.</span><span class="sxs-lookup"><span data-stu-id="bc275-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="bc275-137">Profilių skaičius, kurį galite eksportuoti į „DotDigital“ priklauso ir yra apribojtas jūsų sutartimi su „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="bc275-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bc275-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="bc275-138">Data privacy and compliance</span></span>

<span data-ttu-id="bc275-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „DotDigital“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="bc275-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bc275-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „DotDigital“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="bc275-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="bc275-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bc275-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bc275-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="bc275-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]