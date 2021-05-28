---
title: Eksportuoti „Customer Insights“ duomenis į „Facebook“ reklamos tvarkytuvą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Facebook „Ads Manager“.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976052"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="a0ae5-103">Segmentų sąrašo eksportavimas į Facebook „Ads Manager“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="a0ae5-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="a0ae5-104">Eksportuokite sujungtų klientų profilių segmentus į „Facebook“ reklamos tvarkytuvą, kad sukurtumėte kampanijas „Facebook“ ir „Instagram“.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a0ae5-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="a0ae5-105">Prerequisites for connection</span></span>

- <span data-ttu-id="a0ae5-106">Turite turėti [**Facebook reklamos paskyrą**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kuroje yra [**Facebook įmonės paskyra**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="a0ae5-107">Jums reikia būti administratoriumi [**„Facebook“ reklamos paskyroje**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a0ae5-108">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="a0ae5-108">Known limitations</span></span>

- <span data-ttu-id="a0ae5-109">Iki 10 mln. klientų profilių vienam eksportavimui į Facebook „Ads Manager“.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="a0ae5-110">Eksportavimas į Facebook „Ads Manager“ ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="a0ae5-111">Sukurkite arba įkelkite pasirenkamas auditorijas tik Facebook tipo *klientų sąraše*.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="a0ae5-112">Segmentų, kurių bendra suma yra 10 mln. profilių, eksportavimas gali trukti iki 90 minučių.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="a0ae5-113">Ryšio su Facebook „Ads Manager“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="a0ae5-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="a0ae5-114">Kad naudotojai galėtų sukurti eksportavimą, administratorius turi sukonfigūruoti ryšį su paslauga ir bendradarbiams leisti naudoti ryšį.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="a0ae5-115">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a0ae5-116">Pasirinkite **Pridėti ryšį** ir pasirinkite **Facebook „Ads Manager“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="a0ae5-117">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a0ae5-118">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a0ae5-119">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a0ae5-120">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-120">Choose who can use this connection.</span></span> <span data-ttu-id="a0ae5-121">Jei jokio veiksmo neimsite, numatytasis parametras bus **Administratoriai**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="a0ae5-122">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a0ae5-123">Autentifikuoti naudojant Facebook reklamą:</span><span class="sxs-lookup"><span data-stu-id="a0ae5-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="a0ae5-124">Pasirinkite **Tęsti naudojant „Facebook“**, kad prisijungtumėte prie „Facebook“ reklamos kliento.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="a0ae5-125">Leiskite **reklamos_valdymu** leidimą po autentifikavimo su „Facebook“.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="a0ae5-126">Pasirinkite **„Facebook“ reklamos klientą**, kurį norite naudoti.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="a0ae5-127">Išplečiamajame sąraše pasirinkite **Esama pasirinktinė auditorija** arba sukurkite **Nauja pasirinktinė auditorija**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="a0ae5-128">Norėdami gauti daugiau informacijos, žr. [**„Facebook“ reklamos tvarkytuvo auditorijos**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="a0ae5-129">Su šiuo eksportavimu galima sukurti arba atnaujinti pasirenkamas auditorijas Facebook tipo *klientų sąraše*.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="a0ae5-130">Kai kuriais atvejais išskleidžiamajame sąraše matote skirtingų tipų pasirinktines auditorijas.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="a0ae5-131">Pasirinkus kitą tipą, o ne *klientų sąrašą*, eksportavimas bus nevykdomas.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="a0ae5-132">Peržiūrėkite **Duomenų privatumas ir suderinamumas** ir pasirinkite **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="a0ae5-133">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a0ae5-134">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="a0ae5-134">Configure an export</span></span>

<span data-ttu-id="a0ae5-135">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a0ae5-136">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a0ae5-137">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a0ae5-138">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="a0ae5-139">Srityje **Eksportavimo ryšys** pasirinkite ryšį iš skilties **Facebook „Ads Manager“**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="a0ae5-140">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a0ae5-141">Lauke **Pasirinkite rakto identifikatorių**, pasirinkite **El. paštas**, **Vardas ir adresas** arba **Telefonas**, siųstiną į „Facebook“ reklamos tvarkytuvą.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="a0ae5-142">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a0ae5-143">Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="a0ae5-144">[PATARIMAS] Labiausiai tikėtina, kad bus atitikimų, jei pažymėsite rakto identifikatorių **El. paštas**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="a0ae5-145">Įtraukus papildomų identifikatorių, gali pagerėti atitikimų nustatymas.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="a0ae5-146">Pasirinkite **Pridėti atributą**, kad žymėtumėte daugiau atributų siuntimui į Facebook „Ads Manager“.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="a0ae5-147">Atributai iš Facebook „Ads Manager“ žymimi šiais naudotojams draugiškais pavadinimais: **FN** = **vardas**, **LN** = **pavardė**, **FI** = **vardo inicialas**, **PHONE** = **telefonas**, **GEN** = **lytis**, **DOB** = **gimimo data**, **ST** = **vastija**, **CT** = **miestas**, **ZIP** = **pašto kodas / indeksas**, **COUNTRY** = **šalis / regionas**</span><span class="sxs-lookup"><span data-stu-id="a0ae5-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="a0ae5-148">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="a0ae5-149">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-149">Select **Save**.</span></span>

<span data-ttu-id="a0ae5-150">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a0ae5-151">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a0ae5-152">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a0ae5-153">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="a0ae5-153">Data privacy and compliance</span></span>

<span data-ttu-id="a0ae5-154">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Facebook“ reklamos tvarkytuvą, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights“, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a0ae5-155">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Facebook“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a0ae5-156">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a0ae5-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a0ae5-157">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="a0ae5-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
