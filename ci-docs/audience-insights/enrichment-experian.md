---
title: Papildymas trečiųjų šalių pratinimas „Experian“
description: Bendroji informacija apie „Experian“ trečiosios šalies pratinimą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309830"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="64463-103">Klientų profilių pagerinimo naudojant demografijas „Experian“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="64463-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="64463-104">„Experian“ yra visuotinis vartotojų ir verslo kredito ataskaitų ir rinkodaros paslaugų lyderis.</span><span class="sxs-lookup"><span data-stu-id="64463-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="64463-105">Savo duomenų gerinimo paslaugomis galite geriau suprasti savo klientus, praturtindami savo klientų profilius demografiniais duomenimis, pvz., dėl demografinių duomenų, pvz., dėl demografinių priežasčių dydžio, pajamų ir „Experian“ kt.</span><span class="sxs-lookup"><span data-stu-id="64463-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="64463-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="64463-106">Prerequisites</span></span>

<span data-ttu-id="64463-107">Norint konfigūruoti „Experian“, reikia įvykdyti šias būtinąsias sąlygas:</span><span class="sxs-lookup"><span data-stu-id="64463-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="64463-108">Turite turėti aktyvią „Experian“ prenumeratą.</span><span class="sxs-lookup"><span data-stu-id="64463-108">You have an active Experian subscription.</span></span> <span data-ttu-id="64463-109">Norėdami gauti prenumeratą, [kreipkitės„ Experian“](https://www.experian.com/marketing-services/contact) tiesiai.</span><span class="sxs-lookup"><span data-stu-id="64463-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="64463-110">[Sužinokite daugiau apie „Experian“ duomenų praturtinimą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="64463-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="64463-111">„Experian“ ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises.</span><span class="sxs-lookup"><span data-stu-id="64463-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="64463-112">Taip pat jums reikia sukurto jūsų SSH apsaugoto transportavimo (ST) abonemento vartotojo ID, šalies ID ir „Experian“ modelio numerio.</span><span class="sxs-lookup"><span data-stu-id="64463-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="64463-113">Palaikomos šalys ir (arba) regionai</span><span class="sxs-lookup"><span data-stu-id="64463-113">Supported countries/regions</span></span>

<span data-ttu-id="64463-114">Šiuo metu palaikome tik Jungtinių Amerikos Valstijų klientų profilių gerinimo palaikymą.</span><span class="sxs-lookup"><span data-stu-id="64463-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="64463-115">Papildymo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="64463-115">Configure the enrichment</span></span>

1. <span data-ttu-id="64463-116">Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="64463-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="64463-117">Plytelėje pažymėkite **Papildyti mano**, kuris yra „Experian“ duomenis.</span><span class="sxs-lookup"><span data-stu-id="64463-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64463-118">![Experian plytele](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="64463-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="64463-119">Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo.</span><span class="sxs-lookup"><span data-stu-id="64463-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="64463-120">Jei ryšio nėra, kreipkitės į administratorių.</span><span class="sxs-lookup"><span data-stu-id="64463-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="64463-121">Jei esate administratorius, galite sukurti ryšį pasirinkdami **Įtraukti ryšį** ir „Experian“ pasirinkdami iš išplečiamojo sąrašo.</span><span class="sxs-lookup"><span data-stu-id="64463-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="64463-122">Pasirinkite **Prisijungti ir Experian** patvirtinkite pasirinktą ryšį.</span><span class="sxs-lookup"><span data-stu-id="64463-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="64463-123">Pasirinkite **Kitas** ir rinkitės **Kliento duomenų rinkinys** , kurį norite papildyti demografiniais duomenimis iš „Experian“.</span><span class="sxs-lookup"><span data-stu-id="64463-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="64463-124">Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="64463-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. <span data-ttu-id="64463-126">Pažymėkite **Kitas** ir apibrėžkite, kokio tipo laukus iš vieningųjų profilių reikia naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“.</span><span class="sxs-lookup"><span data-stu-id="64463-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="64463-127">Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**.</span><span class="sxs-lookup"><span data-stu-id="64463-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="64463-128">Kad tikslumas būtų didesnis, galima pridėti iki dviejų kitų laukelių.</span><span class="sxs-lookup"><span data-stu-id="64463-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="64463-129">Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.</span><span class="sxs-lookup"><span data-stu-id="64463-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="64463-130">Daugiau pagrindinių identifikatoriaus atributų, siunčiamų „Experian“ taip, kad atitikties lygis tikriausiai būtų didesnis.</span><span class="sxs-lookup"><span data-stu-id="64463-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="64463-131">Norėdami pradėti laukelių žymėjimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="64463-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="64463-132">Nustatykite laukus ir apibrėžkite, kokio tipo laukus iš vieningųjų profilių reikia naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“.</span><span class="sxs-lookup"><span data-stu-id="64463-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="64463-133">Laukeliai, kuriuos būtina užpildyti, pažymėti.</span><span class="sxs-lookup"><span data-stu-id="64463-133">Required fields are marked.</span></span>

1. <span data-ttu-id="64463-134">Pateikite papildymo pavadinimą ir išvesties objekto pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="64463-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="64463-135">Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="64463-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="64463-136">Ryšio konfigūravimas „Experian“</span><span class="sxs-lookup"><span data-stu-id="64463-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="64463-137">Jei norite konfigūruoti ryšius, turite būti administratorius.</span><span class="sxs-lookup"><span data-stu-id="64463-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="64463-138">Rinkitės **Įtraukti ryšį** kai konfigūruojate papildymą *ar* eikite į **Administratorius** > **ryšiai** ir rinkitės **Nustatyti** esantį „Experian“ plytelėje.</span><span class="sxs-lookup"><span data-stu-id="64463-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="64463-139">Pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="64463-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="64463-140">Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="64463-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="64463-141">Įveskite galiojantį apsaugoto transportavimo abonemento vartotojo ID, šalies ID „Experian“ ir modelio numerį.</span><span class="sxs-lookup"><span data-stu-id="64463-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="64463-142">Pasirinkdami Sutinku, peržiūrėkite **ir pateikite savo sutikimą dėl** duomenų privatumo ir sąlygų **sutinku**.</span><span class="sxs-lookup"><span data-stu-id="64463-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="64463-143">Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="64463-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="64463-144">Baigę patikrinimą pasirinkite **Išsaugoti**.</span><span class="sxs-lookup"><span data-stu-id="64463-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ryšio konfigūravimo juosta.":::

## <a name="enrichment-results"></a><span data-ttu-id="64463-146">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="64463-146">Enrichment results</span></span>

<span data-ttu-id="64463-147">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="64463-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="64463-148">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="64463-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="64463-149">Apdorojimo laikas priklauso nuo kliento duomenų dydžio ir jūsų klientui nustatytų gerinimo „Experian“ procesų.</span><span class="sxs-lookup"><span data-stu-id="64463-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="64463-150">Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="64463-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="64463-151">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="64463-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="64463-152">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="64463-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="64463-153">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="64463-153">Next steps</span></span>

<span data-ttu-id="64463-154">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="64463-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="64463-155">Kurkite [segmentus](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.</span><span class="sxs-lookup"><span data-stu-id="64463-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="64463-156">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="64463-156">Data privacy and compliance</span></span>

<span data-ttu-id="64463-157">Kai leidžiate perduoti duomenis į, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis, „Dynamics 365 Customer Insights“ ir „Experian“ bei „Dynamics 365 Customer Insights“ pvz., Asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="64463-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="64463-158">„Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Experian“ privatumo arba saugos apsauga.</span><span class="sxs-lookup"><span data-stu-id="64463-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="64463-159">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="64463-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="64463-160">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="64463-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
