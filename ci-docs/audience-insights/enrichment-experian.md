---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „Experian“
description: Bendra informacija apie „Experian“ trečiosios šalies praturtinimą.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668822"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="f6f16-103">Klientų profilių papildymas demografiniais duomenimis iš „Experian” (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="f6f16-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="f6f16-104">„Experian“ yra pasaulinis vartotojų ir verslo kreditų ataskaitų bei rinkodaros paslaugų lyderis.</span><span class="sxs-lookup"><span data-stu-id="f6f16-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="f6f16-105">Naudodami „Experian” duomenų papildymo paslaugas, galite geriau suprasti savo klientus, papildydami savo klientų profilius tokiais demografiniais duomenimis kaip namų ūkių dydis, pajamos ir kt.</span><span class="sxs-lookup"><span data-stu-id="f6f16-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6f16-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="f6f16-106">Prerequisites</span></span>

<span data-ttu-id="f6f16-107">Norint sukonfigūruoti „Experian“, reikia atitikti toliau nurodytas būtinąsias sąlygas.</span><span class="sxs-lookup"><span data-stu-id="f6f16-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f6f16-108">Turite aktyvią „Experian“ prenumeratą.</span><span class="sxs-lookup"><span data-stu-id="f6f16-108">You have an active Experian subscription.</span></span> <span data-ttu-id="f6f16-109">Jei norite gauti prenumeratą, [susisiekite su „Experian“](https://www.experian.com/marketing-services/contact) tiesiogiai.</span><span class="sxs-lookup"><span data-stu-id="f6f16-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="f6f16-110">[Sužinokite daugiau apie „Experian“ duomenų papildymą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="f6f16-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="f6f16-111">Turite vartotojo ID, partijos ID ir modelio numerį, skirtus jūsų SSH įjungtame „Secure Transport“ (ST) kliente, kurį „Experian“ sukūrė jums.</span><span class="sxs-lookup"><span data-stu-id="f6f16-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="f6f16-112">Turite [Administratoriaus](permissions.md#administrator) teises publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="f6f16-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="f6f16-113">Konfigūracija</span><span class="sxs-lookup"><span data-stu-id="f6f16-113">Configuration</span></span>

1. <span data-ttu-id="f6f16-114">Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="f6f16-115">„Experian“ plytelėje pasirinkite **Papildyti mano duomenis**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f6f16-116">![„Experian“ plytelė](media/experian-tile.png "„Experian“ plytelė")</span><span class="sxs-lookup"><span data-stu-id="f6f16-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="f6f16-117">Pasirinkite **Pradžia** ir įveskite vartotojo ID, šalies ID ir savo „Experian“ „Secure Transport“ kliento modelio numerį.</span><span class="sxs-lookup"><span data-stu-id="f6f16-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="f6f16-118">Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="f6f16-119">Patvirtinkite visas įvestis pasirinkdami **Taikyti**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="f6f16-120">Susiekite savo laukus</span><span class="sxs-lookup"><span data-stu-id="f6f16-120">Map your fields</span></span>

1. <span data-ttu-id="f6f16-121">Pasirinkite **Įtraukti duomenis** ir pasirinkite savo pagrindinius identifikatorius laukų **Vardas ir adresas**, **El. pašto adresas** arba **Telefono numeris**, kad jie būtų siunčiami „Experian“ tapatybei patvirtinti.</span><span class="sxs-lookup"><span data-stu-id="f6f16-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="f6f16-122">Daugiau pagrindinių identifikatorių atributų siunčiant „Experian“, tikėtina, kad atitikimo rodiklis bus aukštesnis.</span><span class="sxs-lookup"><span data-stu-id="f6f16-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="f6f16-123">Pasirinkite **Toliau** ir susiekite atitinkamus pasirinktų rakto identifikatoriaus laukų atributus iš savo vieningojo kliento objekto.</span><span class="sxs-lookup"><span data-stu-id="f6f16-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="f6f16-124">Pasirinkite **Įtraukti atributą**, kad susietumėte bet kokius papildomus atributus, kuriuos norite siųsti „Experian“.</span><span class="sxs-lookup"><span data-stu-id="f6f16-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="f6f16-125">Spustelėkite **Įrašyti**, kad baigtumėte susieti laukus.</span><span class="sxs-lookup"><span data-stu-id="f6f16-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f6f16-126">![„Experian“ laukų susiejimas](media/experian-field-mapping.png "„Experian“ laukų susiejimas")</span><span class="sxs-lookup"><span data-stu-id="f6f16-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f6f16-127">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="f6f16-127">Enrichment results</span></span>

<span data-ttu-id="f6f16-128">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f6f16-129">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="f6f16-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f6f16-130">Apdorojimo laikas priklausys nuo jūsų kliento duomenų dydžio ir „Experian“ nustatytų jūsų kliento papildymo procesų.</span><span class="sxs-lookup"><span data-stu-id="f6f16-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="f6f16-131">Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f6f16-132">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="f6f16-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f6f16-133">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="f6f16-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6f16-134">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="f6f16-134">Next steps</span></span>

<span data-ttu-id="f6f16-135">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="f6f16-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f6f16-136">Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="f6f16-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f6f16-137">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="f6f16-137">Data privacy and compliance</span></span>

<span data-ttu-id="f6f16-138">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Experian“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="f6f16-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f6f16-139">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Experian“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="f6f16-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f6f16-140">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f6f16-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f6f16-141">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="f6f16-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
