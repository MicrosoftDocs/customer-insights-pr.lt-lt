---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „HERE Technologies“
description: Bendra informacija apie „HERE Technologies“ trečiosios šalies papildymą.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668688"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="a381a-103">Tinkintų profilių papildymas su „HERE Technologies“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="a381a-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="a381a-104">„HERE Technologies“ yra vietos platformos bendrovė, kuri pateikia vietos centro duomenis ir paslaugas.</span><span class="sxs-lookup"><span data-stu-id="a381a-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="a381a-105">Su „HERE Technologies“ duomenų praturtinimo paslaugomis galite sukurti tikslesnį supratimą apie jūsų klientų vietą su adreso normalizavimu, pločio ir ilgio išplėtimu ir daugiau.</span><span class="sxs-lookup"><span data-stu-id="a381a-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a381a-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="a381a-106">Prerequisites</span></span>

<span data-ttu-id="a381a-107">Siekiant sukonfigūruoti „HERE Technologies“ papildymus, būtina atitikti tolesnes būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="a381a-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a381a-108">Turite turėti „HERE Technologies“ prenumeratą.</span><span class="sxs-lookup"><span data-stu-id="a381a-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="a381a-109">Norėdami gauti prenumaratą galite [prisijungti čia](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ar [susisiekti su „HERE Technologies“](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tiesiogiai.</span><span class="sxs-lookup"><span data-stu-id="a381a-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="a381a-110">Sužinokite daugiau apie vietos papildymą su „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="a381a-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="a381a-111">Turite „HERE Technologies“ API raktą.</span><span class="sxs-lookup"><span data-stu-id="a381a-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="a381a-112">Turite [Administratoriaus](permissions.md#administrator) teises.</span><span class="sxs-lookup"><span data-stu-id="a381a-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="a381a-113">Konfigūracija</span><span class="sxs-lookup"><span data-stu-id="a381a-113">Configuration</span></span>

1. <span data-ttu-id="a381a-114">Eikite į **Duomenys** > **Papildymas**.</span><span class="sxs-lookup"><span data-stu-id="a381a-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a381a-115">Pasirinkite **Papildykite savo duomenis** apie „HERE Technologies“ plytą.</span><span class="sxs-lookup"><span data-stu-id="a381a-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a381a-116">![„HERE Technologies“ plytą](media/HERE-tile.png "„HERE Technologies“ plytą")</span><span class="sxs-lookup"><span data-stu-id="a381a-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="a381a-117">Įveskite aktyvų **„HERE Technologies“ API raktą**.</span><span class="sxs-lookup"><span data-stu-id="a381a-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="a381a-118">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="a381a-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="a381a-119">Patvirtinkite abi įvestis pasirinkdami **Sujungti su „HERE“**.</span><span class="sxs-lookup"><span data-stu-id="a381a-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="a381a-120">Pasirinkite **Įtraukti duomenis** ir rinkitės, ar norite sukurti laukelių žemėlapį į pirminius ir (arba) antrinius adresus.</span><span class="sxs-lookup"><span data-stu-id="a381a-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="a381a-121">Galite nurodyti laukelio žemėlaį abiem adresams (pavyzdžiui, namų ir verslo adresui) ir papildyti profilius abiem adresais atskirai.</span><span class="sxs-lookup"><span data-stu-id="a381a-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="a381a-122">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="a381a-122">Select **Next**.</span></span>

1. <span data-ttu-id="a381a-123">Nustatykite, kurie laukeliai iš jūsų suvienodintų profilių turi būti naudojami ieškoti atitinkančių vietos duomenų iš „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="a381a-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="a381a-124">**Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą.</span><span class="sxs-lookup"><span data-stu-id="a381a-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="a381a-125">Didesniam atitikties tikslumui, galima įtraukti daugiau laukelių.</span><span class="sxs-lookup"><span data-stu-id="a381a-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a381a-126">![„HERE Technologies“ papildymo konfigūravimo puslapis](media/enrichment-HERE-configuration.png "„HERE Technologies“ papildymo konfigūravimo puslapis")</span><span class="sxs-lookup"><span data-stu-id="a381a-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="a381a-127">Pasirinkite **Taikyti** tam, kad užbaigtumėte laukelio žemėlapio kūrimą.</span><span class="sxs-lookup"><span data-stu-id="a381a-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a381a-128">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="a381a-128">Enrichment results</span></span>

<span data-ttu-id="a381a-129">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="a381a-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a381a-130">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="a381a-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a381a-131">Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio ir API atsakymo laiko iš „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="a381a-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="a381a-132">Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="a381a-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a381a-133">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="a381a-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a381a-134">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="a381a-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a381a-135">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="a381a-135">Next steps</span></span>

<span data-ttu-id="a381a-136">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="a381a-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a381a-137">Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="a381a-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a381a-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="a381a-138">Data privacy and compliance</span></span>

<span data-ttu-id="a381a-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „HERE Technologies“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="a381a-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a381a-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „HERE Technologies“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="a381a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a381a-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a381a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a381a-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="a381a-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
