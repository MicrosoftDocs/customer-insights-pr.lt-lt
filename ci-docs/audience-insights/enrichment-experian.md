---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „Experian“
description: Bendra informacija apie „Experian“ trečiosios šalies praturtinimą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896383"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="e98ae-103">Klientų profilių papildymas demografiniais duomenimis iš „Experian” (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="e98ae-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="e98ae-104">„Experian“ yra pasaulinis vartotojų ir verslo kreditų ataskaitų bei rinkodaros paslaugų lyderis.</span><span class="sxs-lookup"><span data-stu-id="e98ae-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="e98ae-105">Naudodami „Experian” duomenų papildymo paslaugas, galite geriau suprasti savo klientus, papildydami savo klientų profilius tokiais demografiniais duomenimis kaip namų ūkių dydis, pajamos ir kt.</span><span class="sxs-lookup"><span data-stu-id="e98ae-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e98ae-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="e98ae-106">Prerequisites</span></span>

<span data-ttu-id="e98ae-107">Norint sukonfigūruoti „Experian“, reikia atitikti toliau nurodytas būtinąsias sąlygas.</span><span class="sxs-lookup"><span data-stu-id="e98ae-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e98ae-108">Turite aktyvią „Experian“ prenumeratą.</span><span class="sxs-lookup"><span data-stu-id="e98ae-108">You have an active Experian subscription.</span></span> <span data-ttu-id="e98ae-109">Jei norite gauti prenumeratą, [susisiekite su „Experian“](https://www.experian.com/marketing-services/contact) tiesiogiai.</span><span class="sxs-lookup"><span data-stu-id="e98ae-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="e98ae-110">[Sužinokite daugiau apie „Experian“ duomenų papildymą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="e98ae-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="e98ae-111">„Experian“ ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises.</span><span class="sxs-lookup"><span data-stu-id="e98ae-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="e98ae-112">Taip pat jums reikia naudotojo ID, šalies ID ir modelio numerio jūsų saugaus transportavimo (ST) paskyrai su įjungta SSK, kurią „Experian“ jums sukūrė.</span><span class="sxs-lookup"><span data-stu-id="e98ae-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="e98ae-113">Papildymo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="e98ae-113">Configure the enrichment</span></span>

1. <span data-ttu-id="e98ae-114">Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e98ae-115">„Experian“ plytelėje pasirinkite **Papildyti mano duomenis**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e98ae-116">![„Experian“ plytelė](media/experian-tile.png "„Experian“ plytelė")</span><span class="sxs-lookup"><span data-stu-id="e98ae-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="e98ae-117">Išskleidžiamajame sąraše pasirinkite [ryšį](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e98ae-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="e98ae-118">Jei ryšio nėra, kreipkitės į administratorių.</span><span class="sxs-lookup"><span data-stu-id="e98ae-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="e98ae-119">Jei esate administratorius, ryšį galite sukurti ryšį pasirinkdami **Pridėti ryšį** ir išskleidžiamajame meniu pasirinkite „Experian“.</span><span class="sxs-lookup"><span data-stu-id="e98ae-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="e98ae-120">Norėdami patvirtinti ryšio pasirinkimą pasirinkite **Prisijungti prie „Experian“**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="e98ae-121">Pasirinkite **Toliau** ir pasirinkite **Kliento duomenų rinkinys**, kurį norite papildyti demografiniais duomenimis iš „Experian“.</span><span class="sxs-lookup"><span data-stu-id="e98ae-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="e98ae-122">Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="e98ae-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. <span data-ttu-id="e98ae-124">Pažymėkite **Toliau** ir apibrėžkite, kokio tipo laukelius iš vieningųjų profilių reikėtų naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“.</span><span class="sxs-lookup"><span data-stu-id="e98ae-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e98ae-125">Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="e98ae-126">Kad tikslumas būtų didesnis, galima pridėti iki dviejų kitų laukelių.</span><span class="sxs-lookup"><span data-stu-id="e98ae-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="e98ae-127">Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.</span><span class="sxs-lookup"><span data-stu-id="e98ae-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="e98ae-128">Daugiau pagrindinių identifikatorių atributų siunčiant „Experian“, tikėtina, kad atitikimo rodiklis bus aukštesnis.</span><span class="sxs-lookup"><span data-stu-id="e98ae-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="e98ae-129">Norėdami pradėti laukelių žymėjimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="e98ae-130">Apibrėžkite, kuriuos laukelius iš vieningųjų profilių reikėtų naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“.</span><span class="sxs-lookup"><span data-stu-id="e98ae-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="e98ae-131">Laukeliai, kuriuos būtina užpildyti, pažymėti.</span><span class="sxs-lookup"><span data-stu-id="e98ae-131">Required fields are marked.</span></span>

1. <span data-ttu-id="e98ae-132">Pateikite papildymo pavadinimą ir išvesties objekto pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="e98ae-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="e98ae-133">Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="e98ae-134">„Experian“ ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="e98ae-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="e98ae-135">Jei norite konfigūruoti ryšius, turite būti administratorius.</span><span class="sxs-lookup"><span data-stu-id="e98ae-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="e98ae-136">Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir plytelėje „Experian“ pasirinkite **Sąranka**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="e98ae-137">Pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="e98ae-138">Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="e98ae-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="e98ae-139">Įveskite galiojantį „Experian“ saugaus transportavimo paskyros naudotojo ID, šalies ID ir modelio numerį.</span><span class="sxs-lookup"><span data-stu-id="e98ae-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="e98ae-140">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**</span><span class="sxs-lookup"><span data-stu-id="e98ae-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="e98ae-141">Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="e98ae-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="e98ae-142">Baigę patikrinimą pasirinkite **Išsaugoti**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="„Experian“ ryšio konfigūravimo sritis.":::

## <a name="enrichment-results"></a><span data-ttu-id="e98ae-144">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="e98ae-144">Enrichment results</span></span>

<span data-ttu-id="e98ae-145">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e98ae-146">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="e98ae-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e98ae-147">Apdorojimo laikas priklausys nuo jūsų kliento duomenų dydžio ir „Experian“ nustatytų jūsų kliento papildymo procesų.</span><span class="sxs-lookup"><span data-stu-id="e98ae-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="e98ae-148">Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="e98ae-149">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="e98ae-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e98ae-150">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="e98ae-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e98ae-151">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="e98ae-151">Next steps</span></span>

<span data-ttu-id="e98ae-152">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="e98ae-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e98ae-153">Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="e98ae-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e98ae-154">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="e98ae-154">Data privacy and compliance</span></span>

<span data-ttu-id="e98ae-155">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Experian“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="e98ae-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e98ae-156">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Experian“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="e98ae-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e98ae-157">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e98ae-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e98ae-158">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="e98ae-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
