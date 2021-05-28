---
title: Siūlomi segmentai, pagrįsti veikla.
description: Leiskite mašininiam mokymui padėti jums surasti naujus ir įdomius segmentus, pagrįstus klientų veikla.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034095"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="6a58e-103">Siūlomi segmentai, pagrįsti veiklos duomenimis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="6a58e-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="6a58e-104">Atraskite jūsų klientų įdomius segmentus pagal klientų veiklos duomenis, įtrauktus į „Customer Insights”.</span><span class="sxs-lookup"><span data-stu-id="6a58e-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="6a58e-105">Veiklos duomenų pavyzdžiai yra operacijos, palaikymo skambučio trukmė, pirkimai ar grąžinimai.</span><span class="sxs-lookup"><span data-stu-id="6a58e-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="6a58e-106">Siekiant pasiūlyti segmentus, veiklos duomenys yra analizuojami pagal naujumą, dažnumą ir piniginę vertę (arba trukmę).</span><span class="sxs-lookup"><span data-stu-id="6a58e-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="6a58e-107">Taip pat galite sugeneruoti [siūlomus segmentus, kad pagerintumėte priemonę, ar geriau suprastumėte, kas sąlygoja atributą](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="6a58e-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Siūlomų segmentų skirtukas, kuriame rodomi segmentų pasiūlymai pagal veiklą ir atributais pagrįsti segmentai.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="6a58e-109">Klientų skirstymas į kategorijas pagal veiklą</span><span class="sxs-lookup"><span data-stu-id="6a58e-109">Categorize customers by activity</span></span>

<span data-ttu-id="6a58e-110">Naudodami [veiklos duomenis](activities.md), pasiekiamus „Customer Insights”, galime sugeneruoti pasiūlymus, kurie atitinka klientų grupes:</span><span class="sxs-lookup"><span data-stu-id="6a58e-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="6a58e-111">aktyviausi klientai</span><span class="sxs-lookup"><span data-stu-id="6a58e-111">most active customers</span></span> 
- <span data-ttu-id="6a58e-112">klientai, kurie atliko daugiausia pirkimų</span><span class="sxs-lookup"><span data-stu-id="6a58e-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="6a58e-113">klientai, kurie sugeneravo daugiausia pajamų</span><span class="sxs-lookup"><span data-stu-id="6a58e-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="6a58e-114">klientai, kurie pastaruoju metu nebuvo aktyvūs</span><span class="sxs-lookup"><span data-stu-id="6a58e-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="6a58e-115">klientai, kurie dažnai sąveikauja su jūsų verslu</span><span class="sxs-lookup"><span data-stu-id="6a58e-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="6a58e-116">Jei turite mažmeninės prekybos įmonę, galite sužinoti, kurie klientai sugeneruoja daugiausia pajamų ir apdovanoti juos kuponu.</span><span class="sxs-lookup"><span data-stu-id="6a58e-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="6a58e-117">Taip pat, galite identifikuoti nenuolatinius klientus ir pasiūlyti jiems prisijungti prie apdovanojimų programos, kad jie dažniau lankytų jūsų įmonę.</span><span class="sxs-lookup"><span data-stu-id="6a58e-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="6a58e-118">Jei jūs esate sveikatos priežiūros versle ir suteikiate visuomenės sveikatos priežiūrą, o jūsų tikslas yra sumažinti atskirų pacientų išlaidas.</span><span class="sxs-lookup"><span data-stu-id="6a58e-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="6a58e-119">Būdas tai padaryti galėtų būti sumažinti vizitų dažnumą suteikiant geriausią įmanomą priežiūrą per kiek įmanoma mažiau vizitų.</span><span class="sxs-lookup"><span data-stu-id="6a58e-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="6a58e-120">Tokiu atveju jūsų tikslas yra išlaikyti žemą vizitų dažnumą ir sumažinti pasikartojančias pacientų išlaidas.</span><span class="sxs-lookup"><span data-stu-id="6a58e-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="6a58e-121">Taip pat galite nustatyti pacientų, turinčių dažnus vizitus ir dideles pasikartojančias išlaidas, segmentus bei išanalizuoti tuos atvejus, kad patobulintumėte asmeninį gydymą.</span><span class="sxs-lookup"><span data-stu-id="6a58e-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="6a58e-122">Būtini duomenys</span><span class="sxs-lookup"><span data-stu-id="6a58e-122">Required data</span></span>

<span data-ttu-id="6a58e-123">Pasiūlymai yra generuojami pagal pasirinktus įvesties duomenis.</span><span class="sxs-lookup"><span data-stu-id="6a58e-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="6a58e-124">Klientų profiliai: Visi klientai arba konkretaus segmento nariai.</span><span class="sxs-lookup"><span data-stu-id="6a58e-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="6a58e-125">Laikotarpis: Pastarasis mėnuo, Pastarieji metai arba bet kuris kitas pasirinktinis skirtasis laikas.</span><span class="sxs-lookup"><span data-stu-id="6a58e-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="6a58e-126">Veiklos tipas: Pirkimai, mažmeninės prekybos operacijos, internetinės operacijos, klientų palaikymo atvejai, prenumeratos ir kita.</span><span class="sxs-lookup"><span data-stu-id="6a58e-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="6a58e-127">„Customer Insights” objektas, kuriame yra veiklos duomenys: Suvienodintos arba konkrečios veiklos objektas.</span><span class="sxs-lookup"><span data-stu-id="6a58e-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="6a58e-128">Įtrauktinos dimensijos: Naujumo, dažnumo arba piniginė dimensija, priklausomai nuo jūsų veiklos reikalavimų.</span><span class="sxs-lookup"><span data-stu-id="6a58e-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="6a58e-129">Kurti siūlomus segmentus</span><span class="sxs-lookup"><span data-stu-id="6a58e-129">Generate suggested segments</span></span>

1. <span data-ttu-id="6a58e-130">Eikite į **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="6a58e-131">Pažymėkite skirtuką **Pasiūlymai**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="6a58e-132">Pažymėkite **Rasti naujus pasiūlymus** ir pasirinkite **Peržiūrėti arba numatyti klientų elgesį**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="6a58e-133">Pažymėkite **Pradėti**, kad būtų vykdoma interaktyvioji patirtis.</span><span class="sxs-lookup"><span data-stu-id="6a58e-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Pirmasis veikla pagrįsto segmento konfigūravimo vedlio veiksmas.":::

1. <span data-ttu-id="6a58e-135">Pateikite reikiamus įvesties duomenis ir pažymėkite **Toliau**, kad tęstumėte.</span><span class="sxs-lookup"><span data-stu-id="6a58e-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="6a58e-136">Klientų pasirinkimas: Įtraukite visus klientus arba konkretų segmentą.</span><span class="sxs-lookup"><span data-stu-id="6a58e-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="6a58e-137">Veiklos pasirinkimas: Pažymėkite veiklos tipą ir veiklą apibūdinančius objektus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="6a58e-138">Nuostatos: Nustatykite į kurį laikotarpį reikia atsižvelgti ir pasiūlymų veiksnius, bei susiekite atributus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="6a58e-139">Peržiūrėkite savo įvestį ir pasirinkite **Vykdyti**, kad paleistumėte modelį ir sugeneruotumėte pasiūlymus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="6a58e-140">Priklausomai nuo klientų profilių ir pasirinktų veiklų skaičiaus, tai gali užtrukti kelias minutes.</span><span class="sxs-lookup"><span data-stu-id="6a58e-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="6a58e-141">Sugeneravę pasiūlymus, galite juos filtruoti pagal labiausiai dominantį aspektą arba reikšmę.</span><span class="sxs-lookup"><span data-stu-id="6a58e-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="6a58e-142">Peržiūrėkite siūlomo segmento informaciją</span><span class="sxs-lookup"><span data-stu-id="6a58e-142">View details of a suggested segment</span></span>

<span data-ttu-id="6a58e-143">Sugeneruoti pasiūlymai bus pateikti parinktyse **Segmentai** > **Pasiūlymai (peržiūros versija)**, esančiose **Veikla pagrįsti pasiūlymai** skyriuje.</span><span class="sxs-lookup"><span data-stu-id="6a58e-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Išplėstinė šoninė sritis, rodanti išsamius siūlomo segmento duomenis.":::

<span data-ttu-id="6a58e-145">Siūlomam segmentui pasirinkite **Peržiūrėti pasiūlymą**, kad peržiūrėtumėte to segmento išsamią informaciją.</span><span class="sxs-lookup"><span data-stu-id="6a58e-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="6a58e-146">Šoninėje srityje pateikiama išsami informacija, pavyzdžiui, kiekvienos dimensijos apimtis, palyginus su tiksline grupe.</span><span class="sxs-lookup"><span data-stu-id="6a58e-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="6a58e-147">Be to, joje akcentuojamas potencialių segmento narių skaičius ir atitinkama visų klientų procentinė dalis.</span><span class="sxs-lookup"><span data-stu-id="6a58e-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="6a58e-148">Jei pasiūlymą norite išsaugoti kaip segmentą, pažymėkite **Kurti segmentą**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="6a58e-149">Įrašykite siūlymą kaip segmentą</span><span class="sxs-lookup"><span data-stu-id="6a58e-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="6a58e-150">Eikite į **Segmentai** > **Pasiūlymai (peržiūra)**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="6a58e-151">Pasirinkite norimą įrašyti segmentą.</span><span class="sxs-lookup"><span data-stu-id="6a58e-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="6a58e-152">Šoninėje srityje pasirinkite **Kurti segmentą**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="6a58e-153">Įrašius segmentą, jis bus rodomas segmentų sąraše, esančiame **Visų segmentų** skirtuke ir dabar jį galima [atnaujinti arba panaikinti kaip ir bet kurį kitą segmentą](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6a58e-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="6a58e-154">Jūs negalite redaguoti segmento išsamios informacijos.</span><span class="sxs-lookup"><span data-stu-id="6a58e-154">You can't edit the segment details.</span></span> <span data-ttu-id="6a58e-155">Tačiau galite pakeisti pasiūlymų įvesties kriterijus ir sugeneruoti skirtingus pasiūlymus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="6a58e-156">Pasiūlymų rinkinio atnaujinimas arba redagavimas</span><span class="sxs-lookup"><span data-stu-id="6a58e-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="6a58e-157">Eikite į **Segmentai** > **Pasiūlymai (peržiūros versija)** ir ieškokite segmento skyriuje **Veikla pagrįsti pasiūlymai**.</span><span class="sxs-lookup"><span data-stu-id="6a58e-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="6a58e-158">Pasirinkite **Atnaujinti pasiūlymus,** kad išlikdami sukonfigūruoti atributai būtų atnaujinti pasiūlymus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="6a58e-159">Taip pat galite pasirinkti **Redaguoti pasiūlymus**, jei norite modifikuoti sukonfigūruotus atributus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="6a58e-160">Sistema iš naujo paleis procesą, sugeneruos segmentų pasiūlymus pagal naujausius duomenis, ir pakeis dabartinius pasiūlymus.</span><span class="sxs-lookup"><span data-stu-id="6a58e-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
