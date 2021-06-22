---
title: „Customer Insights” duomenų eksportavimas į „AdRoll”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „AdRoll“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124375"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="69c69-103">Segmentų eksportavimas į „AdRoll“ (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="69c69-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="69c69-104">Eksportuokite vieningųjų klientų profilių segmentus į „AdRoll” ir naudokite juos reklamai.</span><span class="sxs-lookup"><span data-stu-id="69c69-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="69c69-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="69c69-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="69c69-106">Turite [„AdRoll” abonementą](https://www.adroll.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="69c69-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="69c69-107">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="69c69-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="69c69-108">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="69c69-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="69c69-109">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="69c69-109">Known limitations</span></span>

- <span data-ttu-id="69c69-110">Į „AdRoll” galite eksportuoti iki 250'000 profilių per vieną eksportavimą.</span><span class="sxs-lookup"><span data-stu-id="69c69-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="69c69-111">Į „AdRoll” negalite eksportuoti segmentų, kuriuose yra mažiau nei 100 profilių.</span><span class="sxs-lookup"><span data-stu-id="69c69-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="69c69-112">Eksportavimas į „AdRoll” ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="69c69-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="69c69-113">Iki 250'000 profilių eksportavimas į „AdRoll” gali užtrukti iki 10 minučių.</span><span class="sxs-lookup"><span data-stu-id="69c69-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="69c69-114">Profilių skaičius, kurį galite eksportuoti į „AdRoll“ priklauso ir yra apribotas jūsų sutartimi su „AdRoll“.</span><span class="sxs-lookup"><span data-stu-id="69c69-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="69c69-115">Ryšio su „AdRoll“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="69c69-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="69c69-116">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="69c69-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="69c69-117">Pasirinkite **Pridėti ryšį** ir pasirinkite **„AdRoll“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="69c69-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="69c69-118">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="69c69-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="69c69-119">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="69c69-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="69c69-120">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="69c69-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="69c69-121">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="69c69-121">Choose who can use this connection.</span></span> <span data-ttu-id="69c69-122">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="69c69-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="69c69-123">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="69c69-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="69c69-124">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="69c69-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="69c69-125">Pasirinkite **Prisijungti** ryšio su „AdRoll” inicijavimui.</span><span class="sxs-lookup"><span data-stu-id="69c69-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="69c69-126">Pasirinkite **Autentifikuoti su „AdRoll”** ir pateikite savo administratoriaus kredencialus, skirtus „AdRoll”.</span><span class="sxs-lookup"><span data-stu-id="69c69-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="69c69-127">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="69c69-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="69c69-128">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="69c69-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="69c69-129">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="69c69-129">Configure an export</span></span>

<span data-ttu-id="69c69-130">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="69c69-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="69c69-131">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="69c69-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="69c69-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="69c69-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="69c69-133">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="69c69-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="69c69-134">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „AdRoll“.</span><span class="sxs-lookup"><span data-stu-id="69c69-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="69c69-135">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="69c69-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="69c69-136">Įveskite savo **„AdRoll“ reklamuotojo ID** Daugiau informacijos žr. [„AdRoll“ reklamuotojo profiliai](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="69c69-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="69c69-137">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="69c69-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="69c69-138">Būtina eksportuoti segmentus į „AdRoll”.</span><span class="sxs-lookup"><span data-stu-id="69c69-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="69c69-139">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="69c69-139">Select the segments you want to export.</span></span> <span data-ttu-id="69c69-140">Pasirinkite segmentą, turintį mažiausiai 100 narių.</span><span class="sxs-lookup"><span data-stu-id="69c69-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="69c69-141">Negalite eksportuoti mažesnių segmentų.</span><span class="sxs-lookup"><span data-stu-id="69c69-141">You can't export smaller segments.</span></span> <span data-ttu-id="69c69-142">Be to, didžiausias eksportuojamo segmento dydis yra 250'000 narių vienam eksportavimui.</span><span class="sxs-lookup"><span data-stu-id="69c69-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="69c69-143">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="69c69-143">Select **Save**.</span></span>

<span data-ttu-id="69c69-144">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="69c69-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="69c69-145">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="69c69-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="69c69-146">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="69c69-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="69c69-147">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="69c69-147">Data privacy and compliance</span></span>

<span data-ttu-id="69c69-148">Kai įgalinate „Dynamics 365 Customer Insights” perduoti duomenis į „AdRoll”, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights” atitikties ribų, įskaitant galimai konfidencialius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="69c69-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="69c69-149">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „AdRoll“ atitiktų visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="69c69-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="69c69-150">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="69c69-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="69c69-151">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="69c69-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
