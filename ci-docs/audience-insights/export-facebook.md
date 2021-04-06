---
title: Eksportuoti „Customer Insights“ duomenis į „Facebook“ reklamos tvarkytuvą
description: Sužinokite, kaip sukonfigūruoti ryšį su „Facebook“ reklamos tvarkytuvu.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596693"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="3e588-103">„Facebook“ reklamos tvarkytuvo jungtis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="3e588-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="3e588-104">Eksportuokite sujungtų klientų profilių segmentus į „Facebook“ reklamos tvarkytuvą, kad sukurtumėte kampanijas „Facebook“ ir „Instagram“.</span><span class="sxs-lookup"><span data-stu-id="3e588-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e588-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="3e588-105">Prerequisites</span></span>

- <span data-ttu-id="3e588-106">Jums reikia turėti [**„Facebook“ reklamos paskyrą**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) apimančią [**„Facebook“ verslo paskyrą**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="3e588-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="3e588-107">Jums reikia būti administratoriumi [**„Facebook“ reklamos paskyroje**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="3e588-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="3e588-108">Prisijungimas prie „Facebook“ reklamos tvarkytuvo</span><span class="sxs-lookup"><span data-stu-id="3e588-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="3e588-109">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="3e588-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3e588-110">Dalyje **„Facebook“ reklamos tvarkytuvas** pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="3e588-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="3e588-111">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="3e588-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3e588-112">Pasirinkite **Tęsti naudojant „Facebook“**, kad prisijungtumėte prie „Facebook“ reklamos kliento.</span><span class="sxs-lookup"><span data-stu-id="3e588-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="3e588-113">Leiskite **reklamos_valdymu** leidimą po autentifikavimo su „Facebook“.</span><span class="sxs-lookup"><span data-stu-id="3e588-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="3e588-114">Pasirinkite **„Facebook“ reklamos klientą**, kurį norite naudoti.</span><span class="sxs-lookup"><span data-stu-id="3e588-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="3e588-115">Išplečiamajame sąraše pasirinkite **Esama pasirinktinė auditorija** arba sukurkite **Nauja pasirinktinė auditorija**.</span><span class="sxs-lookup"><span data-stu-id="3e588-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="3e588-116">Norėdami gauti daugiau informacijos, žr. [**„Facebook“ reklamos tvarkytuvo auditorijos**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="3e588-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="3e588-117">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="3e588-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3e588-118">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="3e588-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3e588-119">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="3e588-119">Configure the connector</span></span>

1. <span data-ttu-id="3e588-120">Lauke **Pasirinkite rakto identifikatorių**, pasirinkite **El. paštas**, **Vardas ir adresas** arba **Telefonas**, siųstiną į „Facebook“ reklamos tvarkytuvą.</span><span class="sxs-lookup"><span data-stu-id="3e588-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="3e588-121">Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="3e588-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="3e588-122">[PATARIMAS] Labiausiai tikėtina, kad bus atitikimų, jei pažymėsite rakto identifikatorių **El. paštas**.</span><span class="sxs-lookup"><span data-stu-id="3e588-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="3e588-123">Įtraukus papildomų identifikatorių, gali pagerėti atitikimų nustatymas.</span><span class="sxs-lookup"><span data-stu-id="3e588-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="3e588-124">Pažymėkite **Įtraukti atributą**, kad susietumėte papildomų atributų, siųstinų į „Facebook“ reklamos tvarkytuvą.</span><span class="sxs-lookup"><span data-stu-id="3e588-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="3e588-125">„Facebook“ reklamos tvarkytuvo atributai siejami su toliau pateikiamais vartotojui patogiais pavadinimais: **VD** = **Vardas**, **PV** = **Pavardė**, **PR** = **Pirmoji raidė**, **TEL** = **Telefonas**, **LYT** = **Lytis**, **GD** = **Gimimo data**, **VS** = **Valstija**, **MT** = **Miestas**, **IND** = **Pašto indeksas**, **ŠALIS** = **Šalis / regionas**</span><span class="sxs-lookup"><span data-stu-id="3e588-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="3e588-126">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="3e588-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="3e588-127">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="3e588-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3e588-128">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="3e588-128">Export the data</span></span>

<span data-ttu-id="3e588-129">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3e588-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3e588-130">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3e588-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3e588-131">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="3e588-131">Known limitations</span></span>

- <span data-ttu-id="3e588-132">Iki 10 mln. klientų profilių vienam eksportavimui į „Facebook" reklamos tvarkytuvas</span><span class="sxs-lookup"><span data-stu-id="3e588-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="3e588-133">Eksportavimas į „Facebook” reklamos tvarkytuvą ribojamas segmentais</span><span class="sxs-lookup"><span data-stu-id="3e588-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="3e588-134">Norint eksportuoti segmentus, kurių bendra suma yra 10 mln. profilių, gali trukti iki 90 minučių</span><span class="sxs-lookup"><span data-stu-id="3e588-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3e588-135">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="3e588-135">Data privacy and compliance</span></span>

<span data-ttu-id="3e588-136">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Facebook“ reklamos tvarkytuvą, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights“, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="3e588-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3e588-137">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Facebook“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="3e588-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="3e588-138">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3e588-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3e588-139">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="3e588-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]