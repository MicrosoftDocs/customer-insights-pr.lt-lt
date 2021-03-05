---
title: Eksportuoti „Customer Insights“ duomenis į „Mailchimp“
description: Sužinokite, kaip konfigūruoti jungtį su „Mailchimp“.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267183"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="b4561-103">Jungtis „Mailchimp“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b4561-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="b4561-104">Eksportuoti suvienodintų kliento profilių segmentus į „Mailchimp“ siekiant sukurti naujienlaiškius ir el. pašto kampanijas.</span><span class="sxs-lookup"><span data-stu-id="b4561-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4561-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="b4561-105">Prerequisites</span></span>

-   <span data-ttu-id="b4561-106">Turite [„Mailchimp“ paskyrą](https://mailchimp.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="b4561-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b4561-107">Yra esančių publikų „Mailchimp“ iar atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="b4561-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="b4561-108">Dėl daugiau informacijos, žr. [„Mailchimp“ publikos](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="b4561-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="b4561-109">Turite [konfigūruoti segmentus](segments.md)</span><span class="sxs-lookup"><span data-stu-id="b4561-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="b4561-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="b4561-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="b4561-111">Prisijungti prie „MailChimp“</span><span class="sxs-lookup"><span data-stu-id="b4561-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="b4561-112">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="b4561-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b4561-113">Skyriuje **„Mailchimp“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="b4561-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="b4561-114">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="b4561-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b4561-115">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="b4561-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b4561-116">Įveskite savo **[„Mailchimp“ publikos ID](https://mailchimp.com/help/find-audience-id/)** ir pasirinkite **Sujungti** tam, kad pradėtumėte sujungimą su „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="b4561-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="b4561-117">Pasirinkite **Autentifikuoti su „Mailchimp“** ir pateikti savo „Mailchimp“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="b4561-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="b4561-118">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="b4561-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Eksportuoti momentinę nuotrauką „Mailchimp“ jungčiai":::

1. <span data-ttu-id="b4561-120">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="b4561-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b4561-121">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b4561-121">Configure the connector</span></span>

1. <span data-ttu-id="b4561-122">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="b4561-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="b4561-123">Pasirinktinai, galite eksportuoti **Vardą** ir **Pavardę** kaip papildomus laukelius norėdami sukurti labiau suasmenintus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="b4561-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="b4561-124">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="b4561-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="b4561-125">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="b4561-125">Select the segments you want to export.</span></span> <span data-ttu-id="b4561-126">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="b4561-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Pasirinkite laukelius ir segmentus eksportavimui į „Mailchimp“":::

1. <span data-ttu-id="b4561-128">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="b4561-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b4561-129">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="b4561-129">Export the data</span></span>

<span data-ttu-id="b4561-130">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b4561-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b4561-131">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b4561-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b4561-132">„Mailchimp“ galite dabar surasti savo segmentus skyriuje [„Mailchimp“ publikos](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="b4561-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b4561-133">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="b4561-133">Known limitations</span></span>

- <span data-ttu-id="b4561-134">Iki 1 milijono profilių vieno eksportavimo metu į „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="b4561-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="b4561-135">Eksportavimas į „Mailchimp“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="b4561-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="b4561-136">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki trijų valandų dėl apribojimų tiekėjo pusėje.</span><span class="sxs-lookup"><span data-stu-id="b4561-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="b4561-137">Profilių skaičius, kurį galite eksportuoti į „Mailchimp“ priklauso ir yra apribojtas jūsų sutartimi su „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="b4561-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b4561-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="b4561-138">Data privacy and compliance</span></span>

<span data-ttu-id="b4561-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Mailchimp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="b4561-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b4561-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Mailchimp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="b4561-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b4561-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b4561-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b4561-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="b4561-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]