---
title: Eksportuoti „Customer Insights“ duomenis į „Mailchimp“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Mailchimp“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976165"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="8e314-103">Segmentų sąrašų eksportavimas į „Mailchimp“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="8e314-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="8e314-104">Eksportuoti suvienodintų kliento profilių segmentus į „Mailchimp“ siekiant sukurti naujienlaiškius ir el. pašto kampanijas.</span><span class="sxs-lookup"><span data-stu-id="8e314-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8e314-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="8e314-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="8e314-106">Turite [„Mailchimp“ paskyrą](https://mailchimp.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="8e314-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8e314-107">Yra esančių publikų „Mailchimp“ ar atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="8e314-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="8e314-108">Dėl daugiau informacijos, žr. [„Mailchimp“ publikos](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8e314-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="8e314-109">Turite [konfigūruoti segmentus](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8e314-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8e314-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="8e314-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8e314-111">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="8e314-111">Known limitations</span></span>

- <span data-ttu-id="8e314-112">Iki 1 milijono profilių vieno eksportavimo metu į „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="8e314-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="8e314-113">Eksportavimas į „Mailchimp“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="8e314-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="8e314-114">1 milijono profilių segmentų eksportavimas gali trukti iki trijų valandų.</span><span class="sxs-lookup"><span data-stu-id="8e314-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="8e314-115">Profilių skaičius, kurį galite eksportuoti į „Mailchimp“ priklauso ir yra apribotas jūsų sutartimi su „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="8e314-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="8e314-116">Ryšio su „Mailchimp“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="8e314-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="8e314-117">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="8e314-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8e314-118">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Autopilot“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="8e314-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="8e314-119">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="8e314-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8e314-120">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="8e314-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8e314-121">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="8e314-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8e314-122">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="8e314-122">Choose who can use this connection.</span></span> <span data-ttu-id="8e314-123">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="8e314-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8e314-124">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8e314-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8e314-125">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="8e314-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8e314-126">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="8e314-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="8e314-127">Pasirinkite **Autentifikuoti su „Mailchimp“** ir pateikti savo „Mailchimp“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="8e314-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="8e314-128">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="8e314-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8e314-129">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="8e314-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="8e314-130">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="8e314-130">Configure the connector</span></span>

<span data-ttu-id="8e314-131">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="8e314-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8e314-132">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8e314-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8e314-133">Eikite į **Duomenys**> **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="8e314-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="8e314-134">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="8e314-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8e314-135">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="8e314-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="8e314-136">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="8e314-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8e314-137">Įveskite savo **[„Mailchimp“ auditorijos ID](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="8e314-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="8e314-138">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="8e314-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8e314-139">Taip pat galite eksportuoti **vardą** ir **pavardę**, jei norite sukurti labiau personalizuotus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="8e314-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="8e314-140">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="8e314-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8e314-141">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="8e314-141">Select the segments you want to export.</span></span> <span data-ttu-id="8e314-142">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Mailchimp“.</span><span class="sxs-lookup"><span data-stu-id="8e314-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="8e314-143">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="8e314-143">Select **Save**.</span></span>

<span data-ttu-id="8e314-144">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="8e314-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8e314-145">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e314-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8e314-146">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8e314-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8e314-147">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="8e314-147">Data privacy and compliance</span></span>

<span data-ttu-id="8e314-148">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Mailchimp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="8e314-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8e314-149">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Mailchimp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="8e314-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8e314-150">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8e314-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8e314-151">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="8e314-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
