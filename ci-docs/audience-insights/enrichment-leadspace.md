---
title: Bendrovės profilių praturtinimas su trečiosios šalies praturtinimo „Leadspace“
description: Bendra informacija apie „Leadspace“ trečiosios šalies praturtinimą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895923"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="80d63-103">Įmonių profilių papildymas su „Leadspace“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="80d63-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="80d63-104">„Leadspace“ yra duomenų mokslo įmonė, teikianti B2B klientų duomenų platformą.</span><span class="sxs-lookup"><span data-stu-id="80d63-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="80d63-105">Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis.</span><span class="sxs-lookup"><span data-stu-id="80d63-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="80d63-106">Papildymai apima daugiau atributų, pvz., įmonės dydį, vietą, pramonės šaką ir daugiau.</span><span class="sxs-lookup"><span data-stu-id="80d63-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80d63-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="80d63-107">Prerequisites</span></span>

<span data-ttu-id="80d63-108">Norint konfigūruoti „Leadspace“, turi būti tenkinamos šios būtinosios sąlygos:</span><span class="sxs-lookup"><span data-stu-id="80d63-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="80d63-109">Turite aktyvią „Leadspace“ licenciją.</span><span class="sxs-lookup"><span data-stu-id="80d63-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="80d63-110">Turite įmonių [vieningus klientų profilius](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="80d63-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="80d63-111">„LeadSpace“ ryšį jau sukonfigūravo administratorius arba turite [administratoriaus](permissions.md#administrator) teises bei „neribotą raktą“ (vadinamą **„LeadSpace“ atpažinimo ženklu**).</span><span class="sxs-lookup"><span data-stu-id="80d63-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="80d63-112">Norėdami gauti išsamios informacijos apie jų produktą, kreipkitės tiesiogiai į [„Leadspace“](https://www.leadspace.com/products/leadspace-on-demand/).</span><span class="sxs-lookup"><span data-stu-id="80d63-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="80d63-113">Papildymo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="80d63-113">Configure the enrichment</span></span>

1. <span data-ttu-id="80d63-114">Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.</span><span class="sxs-lookup"><span data-stu-id="80d63-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="80d63-115">„Leadspace“ plytelėje pasirinkite **Papildyti mano duomenis** ir pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="80d63-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace plytos momentinė ekrano nuotrauka.":::

1. <span data-ttu-id="80d63-117">Išskleidžiamajame sąraše pasirinkite [ryšį](connections.md).</span><span class="sxs-lookup"><span data-stu-id="80d63-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="80d63-118">Jei ryšio nėra, kreipkitės į administratorių.</span><span class="sxs-lookup"><span data-stu-id="80d63-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="80d63-119">Jei esate administratorius, ryšį galite sukurti pasirinkdami **Pridėti ryšį** ir **„Leadspace“**.</span><span class="sxs-lookup"><span data-stu-id="80d63-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="80d63-120">Norėdami patvirtinti ryšį pasirinkite **Prisijungti prie „Leadspace“**.</span><span class="sxs-lookup"><span data-stu-id="80d63-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="80d63-121">Pasirinkite **Toliau** ir pasirinkite **Kliento duomenų rinkinys**, kurį norite papildyti įmonės duomenimis iš „Leadspace“.</span><span class="sxs-lookup"><span data-stu-id="80d63-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="80d63-122">Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="80d63-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. <span data-ttu-id="80d63-124">Pažymėkite **Toliau** ir apibrėžkite, kurie laukeliai iš vieningųjų profilių naudojami ieškant sutampančių įmonės duomenų iš „Leadspace“.</span><span class="sxs-lookup"><span data-stu-id="80d63-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="80d63-125">**Bendrovės pavadinimo** laukelis yra būtinas.</span><span class="sxs-lookup"><span data-stu-id="80d63-125">The **Name of company** field is required.</span></span> <span data-ttu-id="80d63-126">Didesniam atitikties tikslumui, gali būti įtraukti ne daugiau du laukeliai **Bendrovės interneto svetainė** ir **Bendrovės vieta**.</span><span class="sxs-lookup"><span data-stu-id="80d63-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace laukelio žemėlapio sukūrimo juosta.":::

1. <span data-ttu-id="80d63-128">Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="80d63-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="80d63-129">Nurodykite papildymo pavadinimą ir peržiūrėję pasirinkimus pažymėkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="80d63-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="80d63-130">„Leadspace“ ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="80d63-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="80d63-131">Jei norite konfigūruoti ryšius, turite būti administratorius.</span><span class="sxs-lookup"><span data-stu-id="80d63-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="80d63-132">Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir plytelėje „Leadspace“ pasirinkite **Sąranka**.</span><span class="sxs-lookup"><span data-stu-id="80d63-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="80d63-133">Pasirinkite **Darbo pradžia**</span><span class="sxs-lookup"><span data-stu-id="80d63-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="80d63-134">Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="80d63-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="80d63-135">Nurodykite galiojantį „Leadspace“ atpažinimo ženklą.</span><span class="sxs-lookup"><span data-stu-id="80d63-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="80d63-136">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**</span><span class="sxs-lookup"><span data-stu-id="80d63-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="80d63-137">Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="80d63-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="80d63-138">Baigę patikrinimą pasirinkite **Išsaugoti**.</span><span class="sxs-lookup"><span data-stu-id="80d63-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="„Leadspace“ ryšio konfigūravimo puslapis.":::

## <a name="enrichment-results"></a><span data-ttu-id="80d63-140">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="80d63-140">Enrichment results</span></span>

<span data-ttu-id="80d63-141">Atnaujinę papildymą naujai papildytus įmonės duomenis galite peržiūrėti dalyje [Mano papildymai](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="80d63-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="80d63-142">Galite rasti paskutinio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="80d63-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="80d63-143">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="80d63-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="80d63-144">Daugiau informacijos žr. [„Leadspace“ API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="80d63-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="80d63-145">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="80d63-145">Next steps</span></span>

<span data-ttu-id="80d63-146">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="80d63-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="80d63-147">Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="80d63-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="80d63-148">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="80d63-148">Data privacy and compliance</span></span>

<span data-ttu-id="80d63-149">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Leadspace“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="80d63-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="80d63-150">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Leadspace“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="80d63-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="80d63-151">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="80d63-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="80d63-152">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="80d63-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
