---
title: Bendrovės profilių praturtinimas su trečiosios šalies praturtinimo „Leadspace“
description: Bendra informacija apie „Leadspace“ trečiosios šalies praturtinimą.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597659"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="956bd-103">Įmonių profilių papildymas su „Leadspace“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="956bd-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="956bd-104">„Leadspace“ yra duomenų mokslo įmonė, teikianti B2B klientų duomenų platformą.</span><span class="sxs-lookup"><span data-stu-id="956bd-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="956bd-105">Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis.</span><span class="sxs-lookup"><span data-stu-id="956bd-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="956bd-106">Praturtinimai apima papildomos atributus, tokius kaip bendrovės dydis, vieta, pramonė ir daugiau.</span><span class="sxs-lookup"><span data-stu-id="956bd-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="956bd-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="956bd-107">Prerequisites</span></span>

<span data-ttu-id="956bd-108">Norint konfigūruoti „Leadspace“, turi būti tenkinamos šios būtinosios sąlygos:</span><span class="sxs-lookup"><span data-stu-id="956bd-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="956bd-109">Turite aktyvią „Leadspace“ licenciją ir „nuolatinį raktą“ (vadinamą **„Leadspace“ žyma**).</span><span class="sxs-lookup"><span data-stu-id="956bd-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="956bd-110">Susisiekite tiesiogiai su [„Leadspace“](https://www.leadspace.com/products/leadspace-on-demand/), norėdami gauti informacijos apie jų produktą.</span><span class="sxs-lookup"><span data-stu-id="956bd-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="956bd-111">Turite [Administratoriaus](permissions.md#administrator) teises.</span><span class="sxs-lookup"><span data-stu-id="956bd-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="956bd-112">Turite įmonių [vieningus klientų profilius](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="956bd-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="956bd-113">Konfigūracija</span><span class="sxs-lookup"><span data-stu-id="956bd-113">Configuration</span></span>

1. <span data-ttu-id="956bd-114">Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.</span><span class="sxs-lookup"><span data-stu-id="956bd-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="956bd-115">Pažymėkite **Papildyti mano duomenis** plytelėje „Leadspace“.</span><span class="sxs-lookup"><span data-stu-id="956bd-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace plytos momentinė ekrano nuotrauka.":::

1. <span data-ttu-id="956bd-117">Pasirinkite **Pradėti** ir tada įveskite aktyvią **„Leadspace“ žymą** (nuolatinį raktą).</span><span class="sxs-lookup"><span data-stu-id="956bd-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="956bd-118">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="956bd-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="956bd-119">Patvirtinkite abi įvestis pasirinkdami **Sujungti su „Leadspace“**.</span><span class="sxs-lookup"><span data-stu-id="956bd-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="956bd-120">Pasirinkite **Įtraukti duomenis** ir pasirinkite kliento duomenų rinkinį, kurį norite papildyti demografiniais duomenimis iš „Leadspace“.</span><span class="sxs-lookup"><span data-stu-id="956bd-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="956bd-121">Galite pažymėti objektą *Klientas*, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="956bd-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Pasirinkite tarp kliento profilio ir segmento papildymo.":::

1. <span data-ttu-id="956bd-123">Spustelėkite **Kitas** ir apibrėžkite, kurie laukai iš jūsų vieningų profilių turi būti naudojami norint ieškoti sutampančių įmonės duomenų iš „LeadSpace”.</span><span class="sxs-lookup"><span data-stu-id="956bd-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="956bd-124">**Bendrovės pavadinimo** laukelis yra būtinas.</span><span class="sxs-lookup"><span data-stu-id="956bd-124">The **Name of company** field is required.</span></span> <span data-ttu-id="956bd-125">Didesniam atitikties tikslumui, gali būti įtraukti ne daugiau du laukeliai **Bendrovės interneto svetainė** ir **Bendrovės vieta**.</span><span class="sxs-lookup"><span data-stu-id="956bd-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace laukelio žemėlapio sukūrimo juosta.":::
   
1. <span data-ttu-id="956bd-127">Pasirinkite **Taikyti** tam, kad užbaigtumėte laukelio žemėlapio kūrimą.</span><span class="sxs-lookup"><span data-stu-id="956bd-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="956bd-128">Pasirinkite **Vykdyti**, kad papildytumėte įmonės profilius.</span><span class="sxs-lookup"><span data-stu-id="956bd-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="956bd-129">Kiek praturtinimas užtrunka priklauso nuo suvienodintų kliento profilių skaičiaus.</span><span class="sxs-lookup"><span data-stu-id="956bd-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="956bd-130">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="956bd-130">Enrichment results</span></span>

<span data-ttu-id="956bd-131">Atnaujinę papildymą naujai papildytus įmonės duomenis galite peržiūrėti dalyje [Mano papildymai](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="956bd-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="956bd-132">Galite rasti paskutinio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="956bd-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="956bd-133">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="956bd-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="956bd-134">Daugiau informacijos žr. [„Leadspace“ API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="956bd-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="956bd-135">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="956bd-135">Next steps</span></span>

<span data-ttu-id="956bd-136">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="956bd-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="956bd-137">Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="956bd-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="956bd-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="956bd-138">Data privacy and compliance</span></span>

<span data-ttu-id="956bd-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Leadspace“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="956bd-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="956bd-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Leadspace“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="956bd-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="956bd-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="956bd-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="956bd-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="956bd-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]