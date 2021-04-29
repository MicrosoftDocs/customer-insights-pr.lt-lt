---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „HERE Technologies“
description: Bendra informacija apie „HERE Technologies“ trečiosios šalies papildymą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896061"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="3ebf5-103">Tinkintų profilių papildymas su „HERE Technologies“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="3ebf5-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="3ebf5-104">„HERE Technologies“ yra vietos platformos bendrovė, kuri pateikia vietos centro duomenis ir paslaugas.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="3ebf5-105">Su „HERE Technologies“ duomenų praturtinimo paslaugomis galite sukurti tikslesnį supratimą apie jūsų klientų vietą su adreso normalizavimu, pločio ir ilgio išplėtimu ir daugiau.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ebf5-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="3ebf5-106">Prerequisites</span></span>

<span data-ttu-id="3ebf5-107">Siekiant sukonfigūruoti „HERE Technologies“ papildymus, būtina atitikti tolesnes būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="3ebf5-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3ebf5-108">Turite turėti „HERE Technologies“ prenumeratą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="3ebf5-109">Norėdami gauti prenumeratą galite [prisijungti čia](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ar [susisiekti su „HERE Technologies“](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tiesiogiai.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="3ebf5-110">Sužinokite daugiau apie vietos papildymą su „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="3ebf5-111">Galima naudoti HERE [ryšį](connections.md) *arba* reikia turėti [administratoriaus](permissions.md#administrator) teises ir „HERE Technologies“ API raktą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-111">There is a HERE [connection](connections.md) available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3ebf5-112">Papildymo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="3ebf5-112">Configure the enrichment</span></span>

1. <span data-ttu-id="3ebf5-113">Eikite į **Duomenys** > **Papildymas**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="3ebf5-114">„HERE Technologies“ plytelėje pasirinkite **Papildyti mano duomenis** ir pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3ebf5-115">![„HERE Technologies“ plytą](media/HERE-tile.png "„HERE Technologies“ plytą")</span><span class="sxs-lookup"><span data-stu-id="3ebf5-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="3ebf5-116">Išskleidžiamajame sąraše pasirinkite [ryšį](connections.md).</span><span class="sxs-lookup"><span data-stu-id="3ebf5-116">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="3ebf5-117">Jei ryšio nėra, kreipkitės į administratorių.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="3ebf5-118">Jei esate administratorius, ryšį galite nustatyti pasirinkdami **Pridėti ryšį**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="3ebf5-119">Išskleidžiamajame meniu pasirinkite **„HERE Technologies“**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-119">Choose **HERE Technologies** from the drop-down.</span></span> 

1. <span data-ttu-id="3ebf5-120">Norėdami patvirtinti pasirinkimą rinkitės **Jungtis prie „HERE Technologies“**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="3ebf5-121">Pasirinkite **Toliau** ir rinkitės tą **kliento duomenų rinkinį**, kurį norite papildyti vietos duomenimis iš „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="3ebf5-122">Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. <span data-ttu-id="3ebf5-124">Pasirinkite, ar laukus norite susieti su pirminiu ir (arba) antriniu adresu.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="3ebf5-125">Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="3ebf5-126">Pavyzdžiui, jei yra namų ir įmonės adresas.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="3ebf5-127">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-127">Select **Next**.</span></span>

1. <span data-ttu-id="3ebf5-128">Nustatykite, kurie laukeliai iš jūsų suvienodintų profilių turi būti naudojami ieškoti atitinkančių vietos duomenų iš „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="3ebf5-129">**Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="3ebf5-130">Didesniam atitikties tikslumui, galima įtraukti daugiau laukelių.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3ebf5-131">![„HERE Technologies“ papildymo konfigūravimo puslapis](media/enrichment-HERE-configuration.png "„HERE Technologies“ papildymo konfigūravimo puslapis")</span><span class="sxs-lookup"><span data-stu-id="3ebf5-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="3ebf5-132">Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="3ebf5-133">Nurodykite papildymo pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-133">Provide a name for the enrichment.</span></span> 

<span data-ttu-id="3ebf5-134">1. Peržiūrėję savo pasirinkimus pasirinkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-134">1.Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="3ebf5-135">„HERE Technologies“ ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="3ebf5-135">Configure the connection for HERE technologies</span></span> 

<span data-ttu-id="3ebf5-136">Jei norite konfigūruoti ryšius, turite būti administratorius.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3ebf5-137">Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir plytelėje „HERE Technologies“ pasirinkite **Sąranka**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="3ebf5-138">Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3ebf5-139">Pateikite galiojantį „HERE Technologijų“ API raktą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="3ebf5-140">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**</span><span class="sxs-lookup"><span data-stu-id="3ebf5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="3ebf5-141">Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3ebf5-142">Baigę patikrinimą pasirinkite **Išsaugoti**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-142">After completing the verification, select **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="3ebf5-143">![„HERE Technologies“ ryšio konfigūravimo puslapis](media/enrichment-HERE-connection.png "„HERE Technologies“ ryšio konfigūravimo puslapis")</span><span class="sxs-lookup"><span data-stu-id="3ebf5-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3ebf5-144">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="3ebf5-144">Enrichment results</span></span>

<span data-ttu-id="3ebf5-145">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3ebf5-146">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3ebf5-147">Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio ir API atsakymo laiko iš „HERE Technologies“.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="3ebf5-148">Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3ebf5-149">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3ebf5-150">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ebf5-151">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="3ebf5-151">Next steps</span></span>

<span data-ttu-id="3ebf5-152">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3ebf5-153">Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3ebf5-154">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="3ebf5-154">Data privacy and compliance</span></span>

<span data-ttu-id="3ebf5-155">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „HERE Technologies“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3ebf5-156">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „HERE Technologies“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3ebf5-157">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3ebf5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3ebf5-158">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="3ebf5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
