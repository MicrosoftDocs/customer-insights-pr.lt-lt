---
title: Eksportuoti „Customer Insights“ duomenis į „Google Ads“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Google Ads“.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976328"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="05376-103">Segmentų eksportavimas į „Google Ads“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="05376-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="05376-104">Eksportuoti suvienodintų kliento profilių segmentus į „Google Ads“ publikos sąrašą ir naudoti juos reklamavimui „Google Search“, „Gmail“, „YouTube“ ir „Google Display Network“.</span><span class="sxs-lookup"><span data-stu-id="05376-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="05376-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="05376-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="05376-106">Turite [„Google Ads“ paskyrą](https://ads.google.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="05376-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="05376-107">Turite patvirtintą [„Google Ads“ kūrėjo atpažinimo ženklą](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="05376-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="05376-108">Atitinkate [klientų atitikties politikos](https://support.google.com/adspolicy/answer/6299717) reikalavimus</span><span class="sxs-lookup"><span data-stu-id="05376-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="05376-109">Atitinkate [pakartotinės rinkodaros sąrašo dydžių reikalavimus](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="05376-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="05376-110">Yra esančių publikų „Google Ads“ ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="05376-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="05376-111">Dėl daugiau informacijos, žr. [„Google Ads“ publikos](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="05376-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="05376-112">Turite [konfigūruoti segmentus](segments.md)</span><span class="sxs-lookup"><span data-stu-id="05376-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="05376-113">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelius rodančius el. pašto adresą, vardą ir pavardę</span><span class="sxs-lookup"><span data-stu-id="05376-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="05376-114">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="05376-114">Known limitations</span></span>

- <span data-ttu-id="05376-115">Iki 1 milijono profilių vieno eksportavimo metu į „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="05376-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="05376-116">Eksportavimas į „Google Ads“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="05376-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="05376-117">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 5 minučių dėl apribojimų tiekėjo pusėje.</span><span class="sxs-lookup"><span data-stu-id="05376-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="05376-118">Suderinamumas „Google Ads“ gali trukti iki 48 valandų.</span><span class="sxs-lookup"><span data-stu-id="05376-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="05376-119">Ryšio su „Google Ads“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="05376-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="05376-120">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="05376-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="05376-121">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Google Ads“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="05376-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="05376-122">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="05376-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="05376-123">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="05376-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="05376-124">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="05376-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="05376-125">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="05376-125">Choose who can use this connection.</span></span> <span data-ttu-id="05376-126">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="05376-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="05376-127">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="05376-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="05376-128">Įveskite savo **[„Google Ads“ kliento ID](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="05376-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="05376-129">Įveskite savo **[„Google Ads“ patvirtinto kūrėjo žymą](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="05376-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="05376-130">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="05376-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="05376-131">Pasirinkite **Autentifikuoti su „Google Ads“** ir pateikti savo „Google Ads“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="05376-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="05376-132">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="05376-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="05376-133">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="05376-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="05376-134">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="05376-134">Configure an export</span></span>

<span data-ttu-id="05376-135">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="05376-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="05376-136">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="05376-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="05376-137">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="05376-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="05376-138">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="05376-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="05376-139">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="05376-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="05376-140">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="05376-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="05376-141">Įveskite savo **[„Google Ads“ publikos ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ir pasirinkite **Sujungti** tam, kad pradėtumėte sujungimą su „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="05376-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="05376-142">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="05376-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="05376-143">Pakartokite tuos pačius žingsnius **Vardo** ir **Pavardės** laukeliams.</span><span class="sxs-lookup"><span data-stu-id="05376-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="05376-144">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="05376-144">Select the segments you want to export.</span></span> <span data-ttu-id="05376-145">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Google Ads“.</span><span class="sxs-lookup"><span data-stu-id="05376-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="05376-146">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="05376-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="05376-147">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="05376-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="05376-148">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="05376-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="05376-149">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="05376-149">Data privacy and compliance</span></span>

<span data-ttu-id="05376-150">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Google Ads“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="05376-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="05376-151">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Google Ads“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="05376-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="05376-152">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="05376-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="05376-153">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="05376-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
