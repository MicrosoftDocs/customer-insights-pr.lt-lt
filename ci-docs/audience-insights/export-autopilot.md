---
title: "\"Customer Insights\" duomenų eksportavimas į \"Autopilot\""
description: Sužinokite, kaip konfigūruoti ryšį su  "Autopilot".
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269248"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="c265a-103">"Autopilot" jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="c265a-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="c265a-104">Eksportuokite vieningųjų klientų profilių segmentus į "Autopilot" kontaktų sąrašus ir naudokite juos el. pašto rinkodarai naudojant "Autopilot".</span><span class="sxs-lookup"><span data-stu-id="c265a-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c265a-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="c265a-105">Prerequisites</span></span>

-   <span data-ttu-id="c265a-106">Turite [Autopilot abonementą ir atitinkamus](https://www.autopilothq.com/) administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="c265a-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c265a-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="c265a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="c265a-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="c265a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="c265a-109">Prisijungti prie „AutoPilot“</span><span class="sxs-lookup"><span data-stu-id="c265a-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="c265a-110">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="c265a-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c265a-111">Dalyje **Autopilot**, pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="c265a-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="c265a-112">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="c265a-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Automatinio užbaigimo ryšio konfigūravimo sritis.":::

1. <span data-ttu-id="c265a-114">Įveskite savo **"Autopilot" API raktą**["Autopilot" API raktas](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="c265a-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="c265a-115">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="c265a-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c265a-116">Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su Autopilot.</span><span class="sxs-lookup"><span data-stu-id="c265a-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="c265a-117">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="c265a-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="c265a-118">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="c265a-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c265a-119">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="c265a-119">Configure the connector</span></span>

1. <span data-ttu-id="c265a-120">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="c265a-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="c265a-121">Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.: **Vardas** ar **Pavardė**.</span><span class="sxs-lookup"><span data-stu-id="c265a-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="c265a-122">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="c265a-122">Select the segments you want to export.</span></span> <span data-ttu-id="c265a-123">Primygtinai **rekomenduojame į "Autopilot" eksportuoti ne daugiau nei 100 000 klientų profilių**.</span><span class="sxs-lookup"><span data-stu-id="c265a-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="c265a-124">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="c265a-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c265a-125">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="c265a-125">Export the data</span></span>

<span data-ttu-id="c265a-126">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c265a-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c265a-127">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c265a-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c265a-128">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="c265a-128">Known limitations</span></span>

- <span data-ttu-id="c265a-129">"Autopilot" iš viso galima eksportuoti iki 100 000 profilių.</span><span class="sxs-lookup"><span data-stu-id="c265a-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="c265a-130">Eksportavimas į Autopilot ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="c265a-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="c265a-131">Iki 100 000 profilių eksportavimas į Autopilot gali užtrukti iki kelių valandų.</span><span class="sxs-lookup"><span data-stu-id="c265a-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="c265a-132">Profilių, kuriuos galite eksportuoti į Autopilot, skaičius yra priklausomas ir priklauso nuo jūsų sutarties su Autopilot.</span><span class="sxs-lookup"><span data-stu-id="c265a-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c265a-133">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="c265a-133">Data privacy and compliance</span></span>

<span data-ttu-id="c265a-134">Kai leidžiate perduoti duomenis iš Dynamics 365 Customer Insights į Autopilot, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus Dynamics 365 Customer Insights duomenis, pvz.: asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="c265a-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c265a-135">"Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad Autopilot atitiktų privatumo arba saugos reikalavimus.</span><span class="sxs-lookup"><span data-stu-id="c265a-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c265a-136">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c265a-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c265a-137">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="c265a-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]