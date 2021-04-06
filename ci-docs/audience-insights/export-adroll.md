---
title: „Customer Insights” duomenų eksportavimas į „AdRoll”
description: Sužinokite, kaip konfigūruoti ryšį su „AdRoll”.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697084"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="6f7eb-103">„AdRoll” jungtis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="6f7eb-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="6f7eb-104">Eksportuokite vieningųjų klientų profilių segmentus į „AdRoll” ir naudokite juos reklamai.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6f7eb-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="6f7eb-105">Prerequisites</span></span>

-   <span data-ttu-id="6f7eb-106">Turite [„AdRoll” abonementą](https://www.adroll.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6f7eb-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6f7eb-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="6f7eb-109">Prisijungti prie „AdRoll“</span><span class="sxs-lookup"><span data-stu-id="6f7eb-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="6f7eb-110">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6f7eb-111">Dalyje **„AdRoll”** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="6f7eb-112">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRoll ryšio konfigūravimo sritis.":::

1. <span data-ttu-id="6f7eb-114">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6f7eb-115">Pasirinkite **Prisijungti** ryšio su „AdRoll” inicijavimui.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="6f7eb-116">Pasirinkite **Autentifikuoti su „AdRoll”** ir pateikite savo administratoriaus kredencialus, skirtus „AdRoll”.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="6f7eb-117">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6f7eb-118">Įveskite savo **„AdRoll” reklamuotojo ID**[„AdRoll” reklamuotojas](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="6f7eb-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="6f7eb-119">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="6f7eb-120">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="6f7eb-120">Configure the connector</span></span>

1. <span data-ttu-id="6f7eb-121">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6f7eb-122">Būtina eksportuoti segmentus į „AdRoll”.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="6f7eb-123">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-123">Select the segments you want to export.</span></span> <span data-ttu-id="6f7eb-124">Pasirinkite segmentą, turintį mažiausiai 100 narių.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="6f7eb-125">Negalite eksportuoti mažesnių segmentų.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-125">You can't export smaller segments.</span></span> <span data-ttu-id="6f7eb-126">Be to, didžiausias eksportuojamo segmento dydis yra 250'000 narių vienam eksportavimui.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="6f7eb-127">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6f7eb-128">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="6f7eb-128">Export the data</span></span>

<span data-ttu-id="6f7eb-129">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6f7eb-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6f7eb-130">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6f7eb-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6f7eb-131">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="6f7eb-131">Known limitations</span></span>

- <span data-ttu-id="6f7eb-132">Į „AdRoll” galite eksportuoti iki 250'000 profilių per vieną eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="6f7eb-133">Į „AdRoll” negalite eksportuoti segmentų, kuriuose yra mažiau nei 100 profilių.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="6f7eb-134">Eksportavimas į „AdRoll” ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="6f7eb-135">Iki 250'000 profilių eksportavimas į „AdRoll” gali užtrukti iki 10 minučių.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="6f7eb-136">Profilių skaičius, kurį galite eksportuoti į „AdRoll“ priklauso ir yra apribotas jūsų sutartimi su „AdRoll“.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6f7eb-137">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="6f7eb-137">Data privacy and compliance</span></span>

<span data-ttu-id="6f7eb-138">Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „AdRoll”, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai konfidencialius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6f7eb-139">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „AdRoll“ atitiktų visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6f7eb-140">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6f7eb-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6f7eb-141">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="6f7eb-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
