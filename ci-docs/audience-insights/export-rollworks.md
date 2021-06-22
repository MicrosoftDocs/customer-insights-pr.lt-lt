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
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124099"
---
# <a name="export-segments-to-rollworks-preview"></a><span data-ttu-id="5a50b-103">Segmentų eksportavimas į „RollWorks“ (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="5a50b-103">Export segments to RollWorks (preview)</span></span>

<span data-ttu-id="5a50b-104">Eksportuokite vieningų klientų profilių segmentus į „RollWorks“ ir naudokite juos reklamai.</span><span class="sxs-lookup"><span data-stu-id="5a50b-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="5a50b-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="5a50b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="5a50b-106">Turite [„RollWorks“ paskyros](https://www.rollworks.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="5a50b-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5a50b-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="5a50b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="5a50b-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="5a50b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5a50b-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="5a50b-109">Known limitations</span></span>

- <span data-ttu-id="5a50b-110">Vienu metu į „RollWorks“ galima eksportuoti iki 250 000 profilių.</span><span class="sxs-lookup"><span data-stu-id="5a50b-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="5a50b-111">Į „RollWorks“ negalima eksportuoti segmentų, kuriuose yra mažiau nei 100 profilių.</span><span class="sxs-lookup"><span data-stu-id="5a50b-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="5a50b-112">Segmentų eksportavimas į „RollWorks“ ribojamas.</span><span class="sxs-lookup"><span data-stu-id="5a50b-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="5a50b-113">Iki 250 000 profilių eksportavimas į „RollWorks“ gali užtrukti iki 10 min.</span><span class="sxs-lookup"><span data-stu-id="5a50b-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="5a50b-114">Profilių, kuriuos galite eksportuoti į „RollWorks“ yra ribojamas ir priklauso nuo jūsų sutarties su „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="5a50b-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="5a50b-115">Ryšio su „RollWorks“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="5a50b-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="5a50b-116">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="5a50b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5a50b-117">Pasirinkite **Pridėti ryšį** ir pasirinkite **„RollWorks“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a50b-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="5a50b-118">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="5a50b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5a50b-119">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a50b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5a50b-120">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="5a50b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5a50b-121">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a50b-121">Choose who can use this connection.</span></span> <span data-ttu-id="5a50b-122">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="5a50b-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5a50b-123">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5a50b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5a50b-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="5a50b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="5a50b-125">Pasirinkite **Prisijungti** ir inicijuokite ryšį su „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="5a50b-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="5a50b-126">Pažymėkite **Autentifikuoti naudojant „RollWorks“** ir pateikite savo „RollWorks“ administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="5a50b-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="5a50b-127">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="5a50b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5a50b-128">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a50b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5a50b-129">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5a50b-129">Configure an export</span></span>

<span data-ttu-id="5a50b-130">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="5a50b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5a50b-131">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5a50b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5a50b-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="5a50b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5a50b-133">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="5a50b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5a50b-134">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="5a50b-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="5a50b-135">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="5a50b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5a50b-136">Įveskite savo **„RollWorks“ reklamuotojo ID** [„RollWorks“ reklama](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="5a50b-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="5a50b-137">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="5a50b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="5a50b-138">To reikia norint segmentus eksportuoti į „RollWorks“.</span><span class="sxs-lookup"><span data-stu-id="5a50b-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="5a50b-139">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="5a50b-139">Select the segments you want to export.</span></span> <span data-ttu-id="5a50b-140">Pasirinkite segmentą, turintį mažiausiai 100 narių.</span><span class="sxs-lookup"><span data-stu-id="5a50b-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="5a50b-141">Negalite eksportuoti mažesnių segmentų.</span><span class="sxs-lookup"><span data-stu-id="5a50b-141">You can't export smaller segments.</span></span> <span data-ttu-id="5a50b-142">Be to, didžiausias eksportuojamo segmento dydis yra 250'000 narių vienam eksportavimui.</span><span class="sxs-lookup"><span data-stu-id="5a50b-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="5a50b-143">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5a50b-143">Select **Save**.</span></span>

<span data-ttu-id="5a50b-144">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="5a50b-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5a50b-145">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a50b-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5a50b-146">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5a50b-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a50b-147">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="5a50b-147">Data privacy and compliance</span></span>

<span data-ttu-id="5a50b-148">Kai sistemai Dynamics 365 Customer Insights leidžiate perduoti duomenis į „RollWorks“, leidžiate perduoti duomenis už Dynamics 365 Customer Insights atitikties ribų, įskaitant galima neskelbtinus duomenis, pvz., asmens duomenis.</span><span class="sxs-lookup"><span data-stu-id="5a50b-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a50b-149">„Microsoft“ tokius duomenis perduos jums leidus, tačiau jūs esate atsakingi už tai, kad užtikrintumėte, jog „RollWorks“ atitinka galimai jūsų turimus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="5a50b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a50b-150">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a50b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="5a50b-151">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="5a50b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
