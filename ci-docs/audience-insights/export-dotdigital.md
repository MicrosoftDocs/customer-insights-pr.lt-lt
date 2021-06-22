---
title: Eksportuoti „Customer Insights“ duomenis į „DotDigital“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „DotDigital“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124421"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="ec8a4-103">Segmentų eksportavimas į „DotDigital“ (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="ec8a4-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="ec8a4-104">Eksportuokite suvienodintų klientų profilio segmentus į „DotDigital“ adresų knygas ir naudokite juos kampanijos, el. pašto reklamavimui ir siekiant kurti tinkintus segmentus su „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ec8a4-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="ec8a4-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ec8a4-106">Turite [„DotDigital“ paskyrą](https://dotdigital.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ec8a4-107">Yra esančių adreso knygų „DotDigital“ ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="ec8a4-108">ID gali būti prieinamas URL, kurį pasirinkote ir atvėrėte adresų knygoje.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="ec8a4-109">Dėl daugiau informacijos, žr. [„DotDigital“ adresų knygos](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="ec8a4-110">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ec8a4-111">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ec8a4-112">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="ec8a4-112">Known limitations</span></span>

- <span data-ttu-id="ec8a4-113">Iki 1 milijono profilių vieno eksportavimo metu į „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="ec8a4-114">Eksportavimas į „DotDigital“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="ec8a4-115">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų dėl apribojimų tiekėjo pusėje.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ec8a4-116">Profilių skaičius, kurį galite eksportuoti į „DotDigital“ priklauso ir yra apribotas jūsų sutartimi su „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="ec8a4-117">„DotDigital“ ryšio sąranka</span><span class="sxs-lookup"><span data-stu-id="ec8a4-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="ec8a4-118">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ec8a4-119">Pasirinkite **Pridėti ryšį** ir pasirinkite **„DotDigital“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="ec8a4-120">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ec8a4-121">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ec8a4-122">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ec8a4-123">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-123">Choose who can use this connection.</span></span> <span data-ttu-id="ec8a4-124">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ec8a4-125">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ec8a4-126">Įveskite savo **„DotDigital“ vartotojo vardą ir slaptažodį**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="ec8a4-127">Įveskite savo **[„DotDigital“ adreso knygos ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="ec8a4-128">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ec8a4-129">Pasirinkite **Sujungti** siekiant pradėti sujungimą su „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="ec8a4-130">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ec8a4-131">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ec8a4-132">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="ec8a4-132">Configure an export</span></span>

<span data-ttu-id="ec8a4-133">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ec8a4-134">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ec8a4-135">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ec8a4-136">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ec8a4-137">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="ec8a4-138">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="ec8a4-139">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ec8a4-140">Pakartokite tuos pačius žingsnius kitiems pasirenkamiems laukeliams, tokius kaip **Vardas**, **Pavardė**, **Vardas ir pavardė**, **Lytis** ir **Pašto kodas**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="ec8a4-141">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-141">Select the segments you want to export.</span></span> <span data-ttu-id="ec8a4-142">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „DotDigital“.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="ec8a4-143">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-143">Select **Save**.</span></span>

<span data-ttu-id="ec8a4-144">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ec8a4-145">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ec8a4-146">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="ec8a4-147">„DotDigital“ galite dabar surasti savo segmentus skyriuje [„DotDigital“ adresų knygose](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ec8a4-148">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="ec8a4-148">Data privacy and compliance</span></span>

<span data-ttu-id="ec8a4-149">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „DotDigital“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ec8a4-150">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „DotDigital“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ec8a4-151">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ec8a4-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ec8a4-152">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="ec8a4-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
