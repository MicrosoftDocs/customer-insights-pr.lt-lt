---
title: Visos duomenų dalys naudojančios prognozes
description: Naudokite prognozes tam, kad užpildytumėte nepilnus kliento duomenis.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595911"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="3d6bf-103">Dalinių duomenų papildymas naudojant prognozes</span><span class="sxs-lookup"><span data-stu-id="3d6bf-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3d6bf-104">Prognozės leidžia lengvai kurti numatomas reikšmes, kurios gali pagerinti jūsų nusimanymą apie klientą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="3d6bf-105">**Protingumas** > **Prognozės** puslapyje galite pasirinkti **Mano prognozės** tam, kad matytumėte prognozes, kurias sukonfigūravote kitose publikos įžvalgų dalyse ir leistumėte sau toliau jas tinkinti.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="3d6bf-106">Šios funkcijos naudoti negalima, jei jūsų aplinka naudoja „Azure Data Lake Gen 2“ saugyklą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="3d6bf-107">Prognozių funkcija naudoja automatizuotas priemones, kad įvertintų duomenis ir pateiktų tais duomenimis pagrįstas prognozes, todėl šią funkciją galima naudoti kaip profiliavimo, kaip ši sąvoka apibrėžta Bendrajame duomenų apsaugos reglamente (BDAR), būdą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="3d6bf-108">Klientui naudojant šią funkciją duomenims tvarkyti gali būti taikomi BDAR arba kiti įstatymai ar kiti teisės aktai.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3d6bf-109">Esate atsakingas už užtikrinimą, kad naudojate „Dynamics 365 Customer Insights“, įskaitant prognozes, atitikimą su visais taikomais teisės aktais ir reglamentais, įskaitant teisės aktus susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir bendravimo konfidencialumu.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3d6bf-110">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="3d6bf-110">Prerequisites</span></span>

<span data-ttu-id="3d6bf-111">Tam, kad jūsų organizacija galėtų naudoti prognozių funkciją, įsitikinkite, kad tenkinamos šios būtinosios sąlygos:</span><span class="sxs-lookup"><span data-stu-id="3d6bf-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="3d6bf-112">Jūsų organizacija turi objektą [nustatykite „Common Data Service“](/ai-builder/build-model#prerequisites) ir jas toje pačioje organizacijoje kaip „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="3d6bf-113">Jūsų aplinka yra pridėta prie jūsų „Common Data Service“ elemento.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="3d6bf-114">Jei [kuriate naują aplinką](manage-environments.md), sukonfigūruokite ją dialogo lange **Kurti aplinką** ir pasirinkite **Išsamiau**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="3d6bf-115">Jei jau sukūrėte aplinką, pereikite prie jos parametrų ir pasirinkite **Išsamiau**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="3d6bf-116">Bet kuriuo būdu, **Naudoti prognozes** skyriuje eikite į „Common Data Service“ elemento URL, prie kurio norite pridėti savo aplinką.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="3d6bf-117">Sukurkite prognozę kliento objekte</span><span class="sxs-lookup"><span data-stu-id="3d6bf-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="3d6bf-118">Publikos įžvalgose, eikite į **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="3d6bf-119">Pasirinkite objektą **Klientas**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="3d6bf-120">Objekte **Klientas: „Customer Insights“** pažymėkite skirtuką **Laukai**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="3d6bf-121">Raskite atributo pavadinimą, kuriam norite prognozuoti reikšmės, tada stulpelyje **Suvestinė** pasirinkite piktogramą **Apžvalga**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d6bf-122">![Apžvalgos piktograma](media/intelligence-overviewicon.png "Apžvalgos piktograma")</span><span class="sxs-lookup"><span data-stu-id="3d6bf-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="3d6bf-123">Jei jūsų atributui priskiriamas didelis kiekis trūkstamų reikšmių, pasirinkite **Numatyti trūkstamas reikšmes**, kad tęstumėte prognozę.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d6bf-124">![Apžvalgos būsena su rodomu numatomų trūkstamų reikšmių mygtuku](media/intelligence-overviewpredictmissingvalues.png "Apžvalgos būsena su rodomu numatomų trūkstamų reikšmių mygtuku")</span><span class="sxs-lookup"><span data-stu-id="3d6bf-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="3d6bf-125">Įrašykite **rodomą pavadinimą** ir **išvesties objekto pavadinimą**, kad peržiūrėtumėte prognozės rezultatus.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3d6bf-126">Iš anksto paruoštame parinkčių sąraše matysite, kur galite susieti reikšmes su numatoma kategorija.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="3d6bf-127">Tokiu atveju jūsų vienintelės kategorijos parinktys bus 0 arba 1, nes šios reikšmės susietos su „teisinga“ / „klaidinga“ arba dvejetainiu prognozės pobūdžiu.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="3d6bf-128">Kategorijos stulpelyje lauko reikšmes, kurios galutinėje prognozėje turėtų būti klasifikuojamos kaip „0“, susiekite su „0“, o elementus, kurie galutinėje prognozėje turėtų būti klasifikuojami kaip „1“, susiekite su „1“.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d6bf-129">![Lauko reikšmių, susietų į kategorijas, pavyzdys](media/intelligence-categorymapping.png "Lauko reikšmių, susietų į kategorijas, pavyzdys")</span><span class="sxs-lookup"><span data-stu-id="3d6bf-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="3d6bf-130">Pažymėkite **Atlikta** ir prognozė bus apdorota.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="3d6bf-131">Atsižvelgiant į duomenų dydį ir sudėtingumą, apdorojimas užtruks šiek tiek laiko.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="3d6bf-132">Rezultatai bus prieinami naujame objekte pagal sukurtos prognozės **išvesties objekto pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="3d6bf-133">Prognozės kūrimas kuriant segmentą</span><span class="sxs-lookup"><span data-stu-id="3d6bf-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="3d6bf-134">Kuriant segmentą taip pat galima prognozuoti trūkstamas konkretaus pasirinkto atributo reikšmes.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="3d6bf-135">Tiksliau sakant, kai sparčiai kuriate segmentą, pagrįstą jūsų vieningu kliento objektu arba „Customer_Measure“ objektu.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="3d6bf-136">Vykdydami šią procedūrą, jūs pasirinksite konkretų atributą, kuris bus segmento pagrindas, pvz., kliento pasitenkinimą arba pirkinio sumą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="3d6bf-137">Sukūrus segmentą, sistema pasiūlys trūkstamų šio atributo reikšmių prognozavimo metodą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="3d6bf-138">Publikos įžvalgose eikite į  **Segmentai** ir pasirinkite **Profiliai** plytą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="3d6bf-139">Pasirinkite **lauką**, kad sukurtumėte segmentą, pasirinkite **operatorių**, tada – **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="3d6bf-140">Nurodykite segmento **pavadinimą** ir **rodomą pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="3d6bf-141">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-141">Select **Save**.</span></span>

5. <span data-ttu-id="3d6bf-142">Jei jūsų sukurtas segmentas turi neišsamius duomenis šaltinio lauke, galite pasirinkti prognozuoti trūkstamas reikšmes.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d6bf-143">![Prognozės mygtukas](media/segments-predictoption.png "Prognozės mygtukas")</span><span class="sxs-lookup"><span data-stu-id="3d6bf-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="3d6bf-144">Įrašykite **rodomą pavadinimą** ir **išvesties objekto pavadinimą**, kad peržiūrėtumėte prognozės rezultatus.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="3d6bf-145">Pasirinkite **Atlikta**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-145">Select **Done**.</span></span> <span data-ttu-id="3d6bf-146">Jūsų prognozė bus netrukus sugeneruota ir prieinama naujame objekte pavadinimu, kurį nurodėte kaip **išvesties objekto pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="3d6bf-147">Prognozės peržiūra</span><span class="sxs-lookup"><span data-stu-id="3d6bf-147">View a prediction</span></span>

1. <span data-ttu-id="3d6bf-148">Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3d6bf-149">Pasirinkite prognozę, kurią norite peržiūrėti.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="3d6bf-150">Pažymėkite elipsę stulpelyje **Veiksmai** ir pasirinkite **Peržiūrėti**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3d6bf-151">Peržiūrint prognozę matysite duomenų taškų skaičių.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3d6bf-152">![Prognozių puslapis](media/intelligence-predictionsviewpage.png "Prognozių puslapis")</span><span class="sxs-lookup"><span data-stu-id="3d6bf-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="3d6bf-153">**Numatomos reikšmės** rodo susiejimą, kurį sukūrėte lauko reikšmės susiejimo į kategoriją fazėje.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="3d6bf-154">Tai yra jūsų duomenų rinkinio reikšmės, susietos su konkrečia kategorija.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="3d6bf-155">-**Labiausiai įtakojantys veiksniai** yra jūsų duomenų rinkinio veiksniai, kurie galėjo turėti daugiausiai įtakos prognozės patikimumui, kai jūsų lauko reikšmė buvo susiejama su konkrečia kategorija.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="3d6bf-156">**Efektyvumas** nurodo, kaip veikia prognozės.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="3d6bf-157">Norėdami sužinoti daugiau, pažymėkite nuorodą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="3d6bf-158">**Peržiūroje** rodomi išvesties duomenų rinkinio pavyzdžiai jūsų prognozėje ir numatomos reikšmės, kai „0“ yra neapibrėžtas, o „1“ yra apibrėžtas, tikėtinumas arba patikimumas.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="3d6bf-159">Prognozės naujinimas</span><span class="sxs-lookup"><span data-stu-id="3d6bf-159">Update a prediction</span></span>

1. <span data-ttu-id="3d6bf-160">Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3d6bf-161">Pažymėkite norimą naujinti prognozę ir pasirinkite piktogramą **Naujinti**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="3d6bf-162">Prognozė bus planuojama apdoroti.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="3d6bf-163">Galite peržiūrėti paskutinio atnaujinimo datą puslapio **Prognozės** stulpelyje **Atnaujinta**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="3d6bf-164">Prognozės redagavimas</span><span class="sxs-lookup"><span data-stu-id="3d6bf-164">Edit a prediction</span></span>

<span data-ttu-id="3d6bf-165">Sukūrę prognozę, modelį galite tinkinti programoje „AI Builder“, kad padidintumėte modelio efektyvumą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="3d6bf-166">Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3d6bf-167">Pažymėkite prognozę, kurią norite redaguoti.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="3d6bf-168">Pažymėkite elipsę stulpelyje **Veiksmai** ir pasirinkite **Peržiūrėti**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="3d6bf-169">Pasirinkite **Tinkinti programoje „AI Builder“**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="3d6bf-170">Atnaujinkite modelį programoje „AI Builder“.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="3d6bf-171">[Sužinokite daugiau apie modelių valdymą programoje „AI Builder“](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="3d6bf-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="3d6bf-172">Kitame jūsų prognozės vykdyme bus naudojamas jūsų sukurtas atnaujintas modelis.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="3d6bf-173">Nauji „AI Builder“ sukurti modeliai nebus rodomi publikos įžvalgos, nebent modelis buvo sukurtas iš toliau nurodytos patirties.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="3d6bf-174">Prognozės pašalinimas</span><span class="sxs-lookup"><span data-stu-id="3d6bf-174">Remove a prediction</span></span>

1. <span data-ttu-id="3d6bf-175">Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="3d6bf-176">Pažymėkite norimą naikinti prognozę.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="3d6bf-177">Pažymėkite elipsę stulpelyje **Veiksmai** ir pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="3d6bf-178">Patvirtinkite naikinimą.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3d6bf-179">Trikčių šalinimas</span><span class="sxs-lookup"><span data-stu-id="3d6bf-179">Troubleshooting</span></span>

<span data-ttu-id="3d6bf-180">Jei dėl klaidos negalite baigti „Common Data Service“ pridėjimo proceso, procesą galite bandyti užbaigti rankiniu būdu.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="3d6bf-181">Yra dvi žinomos problemos, kurios gali kilti pridėjimo procese.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="3d6bf-182">Kliento kortelės papildinio sprendimas nėra įdiegtas.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="3d6bf-183">Vadovaukitės instrukcijomis, kad [įdiegtumėte ir sukonfigūruotumėte sprendimą](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="3d6bf-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="3d6bf-184">Programos leidimai nėra suteikti.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="3d6bf-185">Eikite į [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3d6bf-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="3d6bf-186">Pasirinkti **Aplinkos**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="3d6bf-187">Pažymėkite elipsę šalia aplinkos, į kurią norite įtraukti leidimą, ir pasirinkite **Parametrai**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="3d6bf-188">Išplėskite **Vartotojai ir teisės** ir pasirinkite **Vartotojai**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="3d6bf-189">Pasirinkite **+ Naujas**, tada – **Vartotojas**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="3d6bf-190">Pasirinkite **Programos vartotojas**, jei programos vartotojas dar nepasirinktas, ir įveskite toliau nurodytą informaciją.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="3d6bf-191">**Vartotojo vardas:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d6bf-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="3d6bf-192">**Programos ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="3d6bf-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="3d6bf-193">**Vardas**: Kliento</span><span class="sxs-lookup"><span data-stu-id="3d6bf-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="3d6bf-194">**Pavardė:** įžvalgos</span><span class="sxs-lookup"><span data-stu-id="3d6bf-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="3d6bf-195">**Pagrindinis el. paštas:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="3d6bf-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="3d6bf-196">Pasirinkite **Įrašyti ir uždaryti**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="3d6bf-197">Pasirinkite vartotoją, kurį ką tik sukūrėte.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="3d6bf-198">Viršutinio meniu juostoje pasirinkite **Tvarkyti vaidmenis**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="3d6bf-199">Pasirinkite **Sistemos administratorius**, tada pasirinkite **Gerai**.</span><span class="sxs-lookup"><span data-stu-id="3d6bf-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]