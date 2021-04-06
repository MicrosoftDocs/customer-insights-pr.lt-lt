---
title: „Customer Insights” duomenų eksportavimas į „SendGrid”
description: Sužinokite, kaip konfigūruoti ryšį su „SendGrid”.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597291"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="63900-103">„SendGrid” jungtis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="63900-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="63900-104">Eksportuokite vieningųjų klientų profilių segmentus į „SendGrid” kontaktų sąrašus ir naudokite juos kampanijoms bei el. pašto rinkodarą naudojant „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="63900-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="63900-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="63900-105">Prerequisites</span></span>

-   <span data-ttu-id="63900-106">Turite [„SendGrid” abonementą](https://sendgrid.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="63900-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="63900-107">„SendGrid” yra kontaktų sąrašų ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="63900-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="63900-108">Daugiau informacijos žr. [„SendGrid“ – Kontaktų tvarkymas](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="63900-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="63900-109">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="63900-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="63900-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="63900-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="63900-111">Prisijungti prie „SendGrid“</span><span class="sxs-lookup"><span data-stu-id="63900-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="63900-112">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="63900-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="63900-113">Dalyje **„SendGrid”** pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="63900-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="63900-114">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="63900-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGrid eksportavimo konfigūracijos sritis.":::

1. <span data-ttu-id="63900-116">Įveskite savo **„SendGrid” API raktą**[„SendGrid” API raktas](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="63900-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="63900-117">Įveskite **[„SendGrid” sąrašo ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="63900-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="63900-118">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="63900-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="63900-119">Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="63900-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="63900-120">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="63900-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="63900-121">Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="63900-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="63900-122">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="63900-122">Configure the connector</span></span>

1. <span data-ttu-id="63900-123">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="63900-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="63900-124">Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.:**Vardas**, **Pavardė**, **Šalis / regionas**, **Valstija**, **Miestas**, **Pašto kodas**.</span><span class="sxs-lookup"><span data-stu-id="63900-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="63900-125">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="63900-125">Select the segments you want to export.</span></span> <span data-ttu-id="63900-126">Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="63900-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="63900-127">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="63900-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="63900-128">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="63900-128">Export the data</span></span>

<span data-ttu-id="63900-129">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="63900-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="63900-130">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="63900-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="63900-131">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="63900-131">Known limitations</span></span>

- <span data-ttu-id="63900-132">Iš viso iki 100 000 profilių į „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="63900-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="63900-133">Eksportavimas į „SendGrid” ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="63900-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="63900-134">Iki 100 000 profilių eksportavimas į „SendGrid” gali užtrukti iki kelių valandų.</span><span class="sxs-lookup"><span data-stu-id="63900-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="63900-135">Profilių, kuriuos galite eksportuoti į „SendGrid”, skaičius yra priklausomas ir apribotas pagal jūsų sutartį su „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="63900-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="63900-136">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="63900-136">Data privacy and compliance</span></span>

<span data-ttu-id="63900-137">Kai leidžiate perduoti duomenis į „SendGrid”, leidžiate perduoti duomenis už tos „Dynamics 365 Customer Insights” sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="63900-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="63900-138">„Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „SendGrid” atitiktų privatumo arba saugos reikalavimus.</span><span class="sxs-lookup"><span data-stu-id="63900-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="63900-139">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="63900-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="63900-140">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="63900-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]