---
title: „Customer Insights” duomenų eksportavimas į „Autopilot”
description: Sužinokite, kaip konfigūruoti ryšį su „Autopilot”.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596141"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="5468c-103">„Autopilot” jungtis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="5468c-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="5468c-104">Eksportuokite vieningųjų klientų profilių segmentus į „Autopilot” kontaktų sąrašus ir naudokite juos el. pašto rinkodarai naudojant „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="5468c-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5468c-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="5468c-105">Prerequisites</span></span>

-   <span data-ttu-id="5468c-106">Turite [„Autopilot” abonementą](https://www.autopilothq.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="5468c-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5468c-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="5468c-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5468c-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="5468c-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="5468c-109">Prisijungti prie „AutoPilot”</span><span class="sxs-lookup"><span data-stu-id="5468c-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="5468c-110">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="5468c-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5468c-111">Dalyje **„Autopilot”**, pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="5468c-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="5468c-112">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="5468c-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Automatinio užbaigimo ryšio konfigūravimo sritis.":::

1. <span data-ttu-id="5468c-114">Įveskite savo **„Autopilot” API raktą** [„Autopilot” API raktas](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="5468c-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="5468c-115">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="5468c-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5468c-116">Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="5468c-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="5468c-117">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="5468c-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5468c-118">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="5468c-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="5468c-119">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5468c-119">Configure the connector</span></span>

1. <span data-ttu-id="5468c-120">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="5468c-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5468c-121">Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.: **Vardas** ar **Pavardė**.</span><span class="sxs-lookup"><span data-stu-id="5468c-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="5468c-122">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="5468c-122">Select the segments you want to export.</span></span> <span data-ttu-id="5468c-123">Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="5468c-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="5468c-124">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5468c-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5468c-125">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="5468c-125">Export the data</span></span>

<span data-ttu-id="5468c-126">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5468c-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5468c-127">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5468c-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5468c-128">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="5468c-128">Known limitations</span></span>

- <span data-ttu-id="5468c-129">Į „Autopilot” iš viso galima eksportuoti iki 100 000 profilių.</span><span class="sxs-lookup"><span data-stu-id="5468c-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="5468c-130">Eksportavimas į „Autopilot” ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="5468c-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="5468c-131">Iki 100 000 profilių eksportavimas į „Autopilot” gali užtrukti iki kelių valandų.</span><span class="sxs-lookup"><span data-stu-id="5468c-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="5468c-132">Profilių, kuriuos galite eksportuoti į „Autopilot”, skaičius yra priklausomas ir apribotas pagal jūsų sutartį su „Autopilot”.</span><span class="sxs-lookup"><span data-stu-id="5468c-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5468c-133">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="5468c-133">Data privacy and compliance</span></span>

<span data-ttu-id="5468c-134">Kai leidžiate perduoti duomenis iš „Dynamics 365 Customer Insights” į „Autopilot”, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="5468c-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5468c-135">„Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „Autopilot” atitiktų privatumo arba saugos reikalavimus.</span><span class="sxs-lookup"><span data-stu-id="5468c-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="5468c-136">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5468c-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5468c-137">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="5468c-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]