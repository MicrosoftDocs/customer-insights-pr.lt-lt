---
title: „Customer Insights“ duomenų eksportavimas į „Snapchat“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Snapchat“.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760585"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="0a390-103">Segmentų sąrašų eksportavimas į „Snapchat“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="0a390-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="0a390-104">Eksportuokite vieningų klientų profilių segmentus į „Snapchat“ ir naudokite juos reklamai.</span><span class="sxs-lookup"><span data-stu-id="0a390-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="0a390-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="0a390-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="0a390-106">Turite [„Snapchat“ įmonės paskyrą](https://business.snapchat.com/), [„Snapchat Ads“ paskyrą](https://ads.snapchat.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="0a390-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0a390-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="0a390-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="0a390-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="0a390-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0a390-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="0a390-109">Known limitations</span></span>

- <span data-ttu-id="0a390-110">Segmentų eksportavimas į „Snapchat“ ribojamas.</span><span class="sxs-lookup"><span data-stu-id="0a390-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="0a390-111">Iki 1 milijono profilių eksportavimas į „Snapchat“ gali užtrukti iki 15 min.</span><span class="sxs-lookup"><span data-stu-id="0a390-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="0a390-112">Ryšio su „Snapchat“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="0a390-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="0a390-113">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="0a390-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0a390-114">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Snapchat“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="0a390-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="0a390-115">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="0a390-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0a390-116">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="0a390-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0a390-117">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="0a390-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0a390-118">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="0a390-118">Choose who can use this connection.</span></span> <span data-ttu-id="0a390-119">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="0a390-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0a390-120">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0a390-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0a390-121">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="0a390-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0a390-122">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Snapchat“.</span><span class="sxs-lookup"><span data-stu-id="0a390-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="0a390-123">Pažymėkite **Autentifikuoti naudojant „Snapchat“** ir pateikite savo „Snapchat“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="0a390-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="0a390-124">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="0a390-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0a390-125">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="0a390-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0a390-126">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="0a390-126">Configure an export</span></span>

<span data-ttu-id="0a390-127">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="0a390-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0a390-128">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0a390-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0a390-129">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="0a390-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0a390-130">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="0a390-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0a390-131">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Snapchat“.</span><span class="sxs-lookup"><span data-stu-id="0a390-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="0a390-132">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="0a390-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0a390-133">Įveskite [**„Snapchat“ auditorijos ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="0a390-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="0a390-134">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="0a390-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="0a390-135">To reikia norint segmentus eksportuoti į „Snapchat“.</span><span class="sxs-lookup"><span data-stu-id="0a390-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="0a390-136">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="0a390-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="0a390-137">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="0a390-137">Select **Save**.</span></span>

<span data-ttu-id="0a390-138">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="0a390-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0a390-139">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a390-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a390-140">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0a390-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a390-141">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="0a390-141">Data privacy and compliance</span></span>

<span data-ttu-id="0a390-142">Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „Snapchat“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis.</span><span class="sxs-lookup"><span data-stu-id="0a390-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a390-143">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „Snapchat“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="0a390-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a390-144">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a390-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="0a390-145">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="0a390-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
