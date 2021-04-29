---
title: „Customer Insights“ duomenų eksportavimas į „Constant Contact“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Constant Contact“.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760586"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="e172a-103">Segmentų sąrašų eksportavimas į „Constant Contact“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="e172a-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="e172a-104">Eksportuokite vieningų klientų profilių segmentus į „Constant Contact“ ir naudokite juos rinkodaros veiklai.</span><span class="sxs-lookup"><span data-stu-id="e172a-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e172a-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="e172a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e172a-106">Turite [„Constant Contact“ paskyros](https://www.constantcontact.com/account-home) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="e172a-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e172a-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="e172a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e172a-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="e172a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e172a-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="e172a-109">Known limitations</span></span>

- <span data-ttu-id="e172a-110">Vienu metu į „Constant Contact“ galima eksportuoti iki 1 milijono profilių.</span><span class="sxs-lookup"><span data-stu-id="e172a-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="e172a-111">Segmentų eksportavimas į „Constant Contact“ ribojamas.</span><span class="sxs-lookup"><span data-stu-id="e172a-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="e172a-112">Iki 1 milijono profilių eksportavimas į „Constant Contact“ gali užtrukti iki 1 val.</span><span class="sxs-lookup"><span data-stu-id="e172a-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="e172a-113">Profilių, kuriuos galite eksportuoti į „Constant Contact“ yra ribojamas ir priklauso nuo jūsų sutarties su „Constant Contact“.</span><span class="sxs-lookup"><span data-stu-id="e172a-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="e172a-114">Ryšio su „Constant Contact“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="e172a-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="e172a-115">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="e172a-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e172a-116">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Constant Contact“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="e172a-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="e172a-117">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="e172a-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e172a-118">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="e172a-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e172a-119">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="e172a-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e172a-120">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="e172a-120">Choose who can use this connection.</span></span> <span data-ttu-id="e172a-121">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="e172a-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e172a-122">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e172a-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e172a-123">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="e172a-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e172a-124">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Constant Contact“.</span><span class="sxs-lookup"><span data-stu-id="e172a-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="e172a-125">Pažymėkite **Autentifikuoti naudojant „AdRoll“** ir pateikite savo „Constant Contact“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="e172a-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="e172a-126">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="e172a-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e172a-127">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="e172a-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e172a-128">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="e172a-128">Configure an export</span></span>

<span data-ttu-id="e172a-129">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="e172a-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e172a-130">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e172a-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e172a-131">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="e172a-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e172a-132">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="e172a-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e172a-133">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Constant Contact“.</span><span class="sxs-lookup"><span data-stu-id="e172a-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="e172a-134">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="e172a-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e172a-135">Įveskite savo [**„Constant Contact“ sąrašo ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="e172a-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="e172a-136">Norėdami rasti URL sąrašo ID, atidarykite sąrašą „Constant Contact“.</span><span class="sxs-lookup"><span data-stu-id="e172a-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="e172a-137">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="e172a-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e172a-138">To reikia norint segmentus eksportuoti į „Constant Contact“.</span><span class="sxs-lookup"><span data-stu-id="e172a-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="e172a-139">Pasirinktinai, galite eksportuoti Vardą ir Pavardę kaip papildomus laukelius norėdami sukurti labiau suasmenintus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="e172a-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e172a-140">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="e172a-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e172a-141">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="e172a-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e172a-142">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="e172a-142">Select **Save**.</span></span>

<span data-ttu-id="e172a-143">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="e172a-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e172a-144">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e172a-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e172a-145">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e172a-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e172a-146">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="e172a-146">Data privacy and compliance</span></span>

<span data-ttu-id="e172a-147">Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „Constant Contact“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis.</span><span class="sxs-lookup"><span data-stu-id="e172a-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e172a-148">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „Constant Contact“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="e172a-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e172a-149">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e172a-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e172a-150">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="e172a-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
