---
title: Eksportuoti „Customer Insights“ duomenis į „Marketo“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Marketo“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759831"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="dca1b-103">Segmentų eksportavimas į „Marketo“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="dca1b-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="dca1b-104">Eksportuokite suvienodintų klientų profilio segmentus siekiant sugeneruoti kampanijas, pateikti el. pašto reklamavimą ir naudoti konkrečias klientų grupes su „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="dca1b-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="dca1b-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="dca1b-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="dca1b-106">Turite [„Marketo“ paskyrą](https://login.marketo.com/) ir atitinkančius administratoriaus prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="dca1b-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="dca1b-107">Yra esančių sąrašų „Marketo“ ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="dca1b-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="dca1b-108">Dėl daugiau informacijos, žr. [„Marketo“ sąrašus](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="dca1b-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="dca1b-109">Turite [konfigūruoti segmentus](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dca1b-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="dca1b-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="dca1b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dca1b-111">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="dca1b-111">Known limitations</span></span>

- <span data-ttu-id="dca1b-112">Iki 1 milijono profilių vieno eksportavimo metu į „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="dca1b-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="dca1b-113">Eksportavimas į „Marketo“ yra apribotas segmentais.</span><span class="sxs-lookup"><span data-stu-id="dca1b-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="dca1b-114">Eksportuojant segmentus su bendrai 1 milijonu profilių gali užimti iki 3 valandų.</span><span class="sxs-lookup"><span data-stu-id="dca1b-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="dca1b-115">Profilių skaičius, kurį galite eksportuoti į „Marketo“ priklauso ir yra apribotas jūsų sutartimi su „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="dca1b-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="dca1b-116">Ryšio su „Marketo“ sąranka</span><span class="sxs-lookup"><span data-stu-id="dca1b-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="dca1b-117">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="dca1b-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dca1b-118">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Marketo“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="dca1b-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="dca1b-119">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="dca1b-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dca1b-120">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="dca1b-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dca1b-121">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="dca1b-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dca1b-122">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="dca1b-122">Choose who can use this connection.</span></span> <span data-ttu-id="dca1b-123">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="dca1b-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dca1b-124">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dca1b-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dca1b-125">Įveskite savo **[„Marketo“ kliento ID, kliento slapyvardį ir REST galutinio taško pagrindinio kompiuterio pavadinimą](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="dca1b-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="dca1b-126">Pasirinkite **Sutikti** siekiant patvirtinti **Duomenų privatumą ir atitiktį** ir pasirinkite **Sujungti** siekiant pradėti ryšį su „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="dca1b-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="dca1b-127">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="dca1b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="dca1b-128">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="dca1b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dca1b-129">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="dca1b-129">Configure an export</span></span>

<span data-ttu-id="dca1b-130">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="dca1b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dca1b-131">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dca1b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dca1b-132">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="dca1b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dca1b-133">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="dca1b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dca1b-134">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="dca1b-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="dca1b-135">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="dca1b-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dca1b-136">Įveskite savo **[„Marketo“ sąrašo ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="dca1b-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="dca1b-137">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="dca1b-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="dca1b-138">Taip pat galite eksportuoti **vardą**, **pavardę**, **miestą**, **valstiją** ir **šalį / regioną**, jei norite sukurti labiau personalizuotus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="dca1b-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="dca1b-139">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="dca1b-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="dca1b-140">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="dca1b-140">Select the segments you want to export.</span></span> <span data-ttu-id="dca1b-141">Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Marketo“.</span><span class="sxs-lookup"><span data-stu-id="dca1b-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="dca1b-142">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="dca1b-142">Select **Save**.</span></span>

<span data-ttu-id="dca1b-143">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="dca1b-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dca1b-144">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dca1b-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dca1b-145">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dca1b-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="dca1b-146">„Marketo“ galite dabar surasti savo segmentus skyriuje [„Marketo“ sąrašus](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="dca1b-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dca1b-147">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="dca1b-147">Data privacy and compliance</span></span>

<span data-ttu-id="dca1b-148">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Marketo“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="dca1b-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dca1b-149">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Marketo“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="dca1b-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dca1b-150">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dca1b-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dca1b-151">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="dca1b-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]