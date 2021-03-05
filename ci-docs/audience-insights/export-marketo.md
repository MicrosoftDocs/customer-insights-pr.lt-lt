---
title: Eksportuoti „Customer Insights“ duomenis į „Marketo“
description: Sužinokite, kaip konfigūruoti jungtį su „Marketo“.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267091"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="4e7ce-103">Jungtis „Marketo“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="4e7ce-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="4e7ce-104">Eksportuokite suvienodintų klientų profilio segmentus siekiant sugeneruoti kampanijas, pateikti el. pašto reklamavimą ir naudoti konkrečias klientų grupes su „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4e7ce-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="4e7ce-105">Prerequisites</span></span>

-   <span data-ttu-id="4e7ce-106">Turite [„Marketo“ paskyrą](https://login.marketo.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4e7ce-107">Yra esančių sąrašų „Marketo“ ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="4e7ce-108">Dėl daugiau informacijos, žr. [„Marketo“ sąrašus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="4e7ce-109">Turite [konfigūruoti segmentus](segments.md).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="4e7ce-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="4e7ce-111">Prisijunkite prie „Marketo“</span><span class="sxs-lookup"><span data-stu-id="4e7ce-111">Connect to Marketo</span></span>

1. <span data-ttu-id="4e7ce-112">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4e7ce-113">Skyriuje **„Marketo“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="4e7ce-114">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="4e7ce-115">Įveskite savo **[„Marketo“ kliento ID, Kliento saugų ir REST galutinio taško šeimininko pavadinimą](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="4e7ce-116">Įveskite savo **[„Marketo“ sąrašo ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="4e7ce-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="4e7ce-117">Pasirinkite **Sutikti** siekiant patvirtinti **Duomenų privatumą ir atitiktį** ir pasirinkite **Sujungti** siekiant pradėti jungį su „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="4e7ce-118">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Eksportuoti momentinę nuotrauką „Marketo“ jungčiai":::

1. <span data-ttu-id="4e7ce-120">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="4e7ce-121">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="4e7ce-121">Configure the connector</span></span>

1. <span data-ttu-id="4e7ce-122">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="4e7ce-123">Pasirinktinai, galite eksportuoti **Vardą**, **Pavardę**, **Miestą**, **Valstiją** ir **Šalį/Regioną**  kaip papildomus laukelius siekiant sukurti labiau suasmenintus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="4e7ce-124">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="4e7ce-125">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-125">Select the segments you want to export.</span></span> <span data-ttu-id="4e7ce-126">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Pasirinkite laukelius ir segmentus eksportavimui į „Marketo“":::

1. <span data-ttu-id="4e7ce-128">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4e7ce-129">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="4e7ce-129">Export the data</span></span>

<span data-ttu-id="4e7ce-130">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4e7ce-131">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4e7ce-132">„Marketo“ galite dabar surasti savo segmentus skyriuje [„Marketo“ sąrašus](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4e7ce-133">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="4e7ce-133">Known limitations</span></span>

- <span data-ttu-id="4e7ce-134">Iki 1 milijono profilių vieno eksportavimo metu į „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="4e7ce-135">Eksportavimas į „Marketo“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="4e7ce-136">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="4e7ce-137">Profilių skaičius, kurį galite eksportuoti į „Marketo“ priklauso ir yra apribojtas jūsų sutartimi su „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4e7ce-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="4e7ce-138">Data privacy and compliance</span></span>

<span data-ttu-id="4e7ce-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Marketo“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4e7ce-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Marketo“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4e7ce-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4e7ce-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4e7ce-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="4e7ce-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]