---
title: „Customer Insights“ duomenų eksportavimas į „Sendinblue“
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Sendinblue“.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314646"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="9e2eb-103">Segmentų eksportavimas į „Sendinblue“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="9e2eb-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="9e2eb-104">Eksportuoti vieningųjų kliento profilių segmentus siekiant kurti kampanijas, teikti rinkodaros el. laiškus ir naudoti konkrečias klientų grupes su „Sendinblue“.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9e2eb-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="9e2eb-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9e2eb-106">Turite [„Sendinblue“ abonementą](https://www.sendinblue.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9e2eb-107">„Sendinblue“ yra esamų sąrašų ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="9e2eb-108">Turite [konfigūruoti segmentus](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9e2eb-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="9e2eb-109">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9e2eb-110">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="9e2eb-110">Known limitations</span></span>

- <span data-ttu-id="9e2eb-111">Iki 1 milijonai profilių eksportuojant į „Sendinblue“.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="9e2eb-112">Eksportavimas į „Sendinblue“ ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="9e2eb-113">Eksportuojant segmentus, kurių bendra 1 milijonai profilių, gali trukti iki 90 minučių.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="9e2eb-114">Profilių, kuriuos galite eksportuoti į „Sendinblue", skaičius priklauso nuo sutarties su „Sendinblue" ir yra apribotas.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="9e2eb-115">Nustatyti ryšį su „Sendinblue“</span><span class="sxs-lookup"><span data-stu-id="9e2eb-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="9e2eb-116">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9e2eb-117">Pasirinkite **Įtraukti ryšį** ir pasirinkite **Sendinblue,** kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="9e2eb-118">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9e2eb-119">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9e2eb-120">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9e2eb-121">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-121">Choose who can use this connection.</span></span> <span data-ttu-id="9e2eb-122">Pagal numatytuosius nustatymus, tik administratoriai.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-122">By default it's only administrators.</span></span> <span data-ttu-id="9e2eb-123">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9e2eb-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9e2eb-124">Įveskite savo **[SendinBlue API raktą](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="9e2eb-125">Pasirinkite **Sutinku** patvirtinti duomenų privatumą ir susiskirstyti duomenis ir pasirinkite **Prisijungti**, kad būtų **inicijuotas** ryšys su „Sendinblue".</span><span class="sxs-lookup"><span data-stu-id="9e2eb-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="9e2eb-126">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9e2eb-127">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9e2eb-128">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="9e2eb-128">Configure an export</span></span>

<span data-ttu-id="9e2eb-129">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9e2eb-130">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9e2eb-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9e2eb-131">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9e2eb-132">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9e2eb-133">Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „Sendinblue“.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="9e2eb-134">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9e2eb-135">Įveskite savo **Sendinblue sąrašo ID**</span><span class="sxs-lookup"><span data-stu-id="9e2eb-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="9e2eb-136">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9e2eb-137">Arba galite eksportuoti **vardas**, **pavardė** ir **telefonas** sukurtumėte labiau personalizuotus el. laiškus.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="9e2eb-138">Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9e2eb-139">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="9e2eb-140">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-140">Select **Save**.</span></span>

<span data-ttu-id="9e2eb-141">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9e2eb-142">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9e2eb-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9e2eb-143">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9e2eb-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9e2eb-144">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="9e2eb-144">Data privacy and compliance</span></span>

<span data-ttu-id="9e2eb-145">Kai leidžiate perduoti duomenis į „Dynamics 365 Customer Insights“ leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis „Sedinblue“, „Dynamics 365 Customer Insights“, įskaitant galimai jautrius, tokius kaip asmens.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9e2eb-146">„Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Sendinblue“ privatumo arba saugos apsauga.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9e2eb-147">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9e2eb-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9e2eb-148">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="9e2eb-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
