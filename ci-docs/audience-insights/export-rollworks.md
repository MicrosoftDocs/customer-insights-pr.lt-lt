---
title: „Customer Insights“ duomenų eksportavimas į „RollWorks“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „RollWorks“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760588"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="70a99-103">Segmentų sąrašų eksportavimas į „RollWorks“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="70a99-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="70a99-104">Eksportuokite vieningų klientų profilių segmentus į „RollWorks“ ir naudokite juos reklamai.</span><span class="sxs-lookup"><span data-stu-id="70a99-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="70a99-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="70a99-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="70a99-106">Turite [„RollWorks“ paskyros](https://www.rollworks.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="70a99-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="70a99-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="70a99-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="70a99-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="70a99-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="70a99-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="70a99-109">Known limitations</span></span>

- <span data-ttu-id="70a99-110">Vienu metu į „RollWorks“ galima eksportuoti iki 250 000 profilių.</span><span class="sxs-lookup"><span data-stu-id="70a99-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="70a99-111">Į „RollWorks“ negalima eksportuoti segmentų, kuriuose yra mažiau nei 100 profilių.</span><span class="sxs-lookup"><span data-stu-id="70a99-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="70a99-112">Segmentų eksportavimas į „RollWorks“ ribojamas.</span><span class="sxs-lookup"><span data-stu-id="70a99-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="70a99-113">Iki 250 000 profilių eksportavimas į „RollWorks“ gali užtrukti iki 10 min.</span><span class="sxs-lookup"><span data-stu-id="70a99-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="70a99-114">Profilių, kuriuos galite eksportuoti į „RollWorks“ yra ribojamas ir priklauso nuo jūsų sutarties su „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="70a99-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="70a99-115">Ryšio su „RollWorks“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="70a99-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="70a99-116">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="70a99-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="70a99-117">Pasirinkite **Pridėti ryšį** ir pasirinkite **„RollWorks“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="70a99-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="70a99-118">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="70a99-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="70a99-119">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="70a99-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="70a99-120">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="70a99-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="70a99-121">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="70a99-121">Choose who can use this connection.</span></span> <span data-ttu-id="70a99-122">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="70a99-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="70a99-123">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="70a99-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="70a99-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="70a99-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="70a99-125">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="70a99-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="70a99-126">Pažymėkite **Autentifikuoti naudojant „RollWorks“** ir pateikite savo „RollWorks“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="70a99-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="70a99-127">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="70a99-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="70a99-128">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="70a99-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="70a99-129">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="70a99-129">Configure an export</span></span>

<span data-ttu-id="70a99-130">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="70a99-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="70a99-131">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="70a99-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="70a99-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="70a99-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70a99-133">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="70a99-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="70a99-134">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="70a99-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="70a99-135">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="70a99-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="70a99-136">Įveskite savo **„RollWorks“ reklamuotojo ID** [„RollWorks“ reklama](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="70a99-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="70a99-137">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="70a99-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="70a99-138">To reikia norint segmentus eksportuoti į „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="70a99-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="70a99-139">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="70a99-139">Select the segments you want to export.</span></span> <span data-ttu-id="70a99-140">Pasirinkite segmentą, turintį mažiausiai 100 narių.</span><span class="sxs-lookup"><span data-stu-id="70a99-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="70a99-141">Negalite eksportuoti mažesnių segmentų.</span><span class="sxs-lookup"><span data-stu-id="70a99-141">You can't export smaller segments.</span></span> <span data-ttu-id="70a99-142">Be to, didžiausias eksportuojamo segmento dydis yra 250'000 narių vienam eksportavimui.</span><span class="sxs-lookup"><span data-stu-id="70a99-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="70a99-143">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="70a99-143">Select **Save**.</span></span>

<span data-ttu-id="70a99-144">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="70a99-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="70a99-145">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70a99-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="70a99-146">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="70a99-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="70a99-147">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="70a99-147">Data privacy and compliance</span></span>

<span data-ttu-id="70a99-148">Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „RollWorks“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis.</span><span class="sxs-lookup"><span data-stu-id="70a99-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="70a99-149">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „RollWorks“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="70a99-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="70a99-150">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="70a99-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="70a99-151">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="70a99-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
