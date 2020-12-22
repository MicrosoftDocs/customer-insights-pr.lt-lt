---
title: Suraskite panašius klientus su „AI“
description: Raskite panašių klientų segmentų, naudodami dirbtinį intelektą.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406409"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="f9cfd-103">Panašūs klientai (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="f9cfd-103">Similar Customers (preview)</span></span>

<span data-ttu-id="f9cfd-104">Naudodamiesi šia funkcija, klientų bazėje rasite panašių klientų, naudodami dirbtinį intelektą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="f9cfd-105">Norint naudotis šia funkcija, būtina sukurti bent vieną segmentą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="f9cfd-106">Išplėtus esamo segmento kriterijus, bus lengviau rasti klientų, panašių į tą segmentą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="f9cfd-107">Naudojant funkciją *Panašių klientų radimas*, taikomos automatinės priemonės duomenims įvertinti ir prognozėms pateikti remiantis minėtais duomenimis, todėl šią funkciją galima naudoti kaip profiliavimo metodą, apibrėžtą Bendrajame duomenų apsaugos reglamente („BDAR“).</span><span class="sxs-lookup"><span data-stu-id="f9cfd-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="f9cfd-108">Jei klientas naudoja šią funkciją apdoroti duomenims, gali būti taikomi BDAR arba kiti įstatymai ir kiti teisės aktai.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="f9cfd-109">Esate atsakingas už užtikrinimą, kad naudojate „Dynamics 365 Customer Insights“, įskaitant numatymus, atitikimą su visais taikomais teisės aktais ir reglamentais, įskaitant teisės aktus susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir bendravimo konfidencialumu.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="f9cfd-110">Panašių klientų radimas</span><span class="sxs-lookup"><span data-stu-id="f9cfd-110">Finding similar customers</span></span>

1. <span data-ttu-id="f9cfd-111">Publikos įžvalgose eikite į **Segmentų** puslapį ir pasirinkite segmentą, kuriuo norite pagrįsti naują savo segmentą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="f9cfd-112">Tai jūsų *šaltinio segmentas*.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="f9cfd-113">Veiksmų juostoje pažymėkite **Panašių klientų radimas**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="f9cfd-114">Peržiūrėkite siūlomą naujo segmento pavadinimą ir, jei reikia, jį pakeiskite.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="f9cfd-115">Peržiūrėkite laukus, kuriuose apibrėžiamas naujas segmentas.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="f9cfd-116">Šiuose laukuose apibrėžiamas pagrindas, pagal kurį sistema bandys rasti į šaltinio segmentą panašių klientų.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="f9cfd-117">Sistema pagal numatytuosius nustatymus pasirenka rekomenduojamus laukus.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="f9cfd-118">Laukai, kurie gali gerokai sumažinti modelio veikimą, automatiškai neįtraukiami.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="f9cfd-119">Laukai, kurių duomenų tipai yra: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="f9cfd-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="f9cfd-120">Laukai, kurių svarba (lauko elementų skaičius) yra mažesnis nei 2 arba didesnis nei 30</span><span class="sxs-lookup"><span data-stu-id="f9cfd-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="f9cfd-121">Pasirinkite, ar į naują segmentą turi būti įtraukti **Visi klientai**, ar tik klientai, esantys **Tam tikrame esamame segmente**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="f9cfd-122">Pašalinkite šaltinio segmento klientus, pažymėdami žymės langelį **Neįtraukti šaltinio segmento klientų**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="f9cfd-123">Pagal numatytuosius nustatymus sistema siūlo į išvestį įtraukti tik 20 % tikslinės auditorijos.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="f9cfd-124">Jei reikia, redaguokite šią ribinę vertę.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-124">Edit this threshold as needed.</span></span> <span data-ttu-id="f9cfd-125">Padidinus ribinę vertę, sumažės tikslumas.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="f9cfd-126">Pasirinkite **Vykdyti** puslapio apačioje ir paleiskite dvejetainio klasifikavimo užduotį (mašininio mokymo metodą), kuria analizuojamas duomenų rinkinys.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="f9cfd-127">Panašaus segmento peržiūra</span><span class="sxs-lookup"><span data-stu-id="f9cfd-127">View the similar segment</span></span>

<span data-ttu-id="f9cfd-128">Apdoroję panašų segmentą, naują segmentą rasite puslapyje **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f9cfd-129">![Panašių klientų segmentas](media/expanded-segment.png "Panašių klientų segmentas")</span><span class="sxs-lookup"><span data-stu-id="f9cfd-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="f9cfd-130">Norėdami atidaryti išsamią informaciją apie segmentą, veiksmų juostoje pasirinkite **Peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="f9cfd-131">Šiame rodinyje pateikiama informacija apie rezultatų paskirstymą remiantis [panašumo įverčiais](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="f9cfd-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="f9cfd-132">Panašumo įverčių reikšmes taip pat rasite pasirinkę **Segmento narių peržiūra**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="f9cfd-133">Panašaus segmento išvesties naudojimas</span><span class="sxs-lookup"><span data-stu-id="f9cfd-133">Use the output of a similar segment</span></span>

<span data-ttu-id="f9cfd-134">Galite [naudoti panašaus segmento išvestį](segments.md) kaip ir kitų segmentų išvestis.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="f9cfd-135">Pavyzdžiui, eksportuokite segmentą arba sukurkite priemonę.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="f9cfd-136">Panašaus segmento atnaujinimas ir redagavimas</span><span class="sxs-lookup"><span data-stu-id="f9cfd-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="f9cfd-137">Jei norite atnaujinti panašų segmentą, pažymėkite jį puslapyje **Segmentai** ir veiksmų juostoje pasirinkite **Atnaujinti**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="f9cfd-138">Redaguojant panašų segmentą, duomenys apdorojami iš naujo.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="f9cfd-139">Anksčiau sukurtas segmentas atnaujinamas įtraukiant atnaujintus duomenis.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="f9cfd-140">Jei norite redaguoti panašų segmentą, pažymėkite jį puslapyje **Segmentai** ir veiksmų juostoje pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="f9cfd-141">Pritaikykite pakeitimus ir pasirinkite **Vykdyti**, kad pradėtumėte apdorojimą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="f9cfd-142">Panašaus segmento naikinimas</span><span class="sxs-lookup"><span data-stu-id="f9cfd-142">Delete a similar segment</span></span>

<span data-ttu-id="f9cfd-143">Pažymėkite segmentą puslapyje **Segmentai** ir veiksmų juostoje pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="f9cfd-144">Paskui patvirtinkite naikinimą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="f9cfd-145">Apie panašumo įverčius</span><span class="sxs-lookup"><span data-stu-id="f9cfd-145">About similarity scores</span></span>

<span data-ttu-id="f9cfd-146">Dvejetainio klasifikavimo mašininio mokymo modelyje panašaus segmento klientams priskiriamas įvertis.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="f9cfd-147">Įvertis grindžiamas panašumu į klientus šaltinio segmente.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="f9cfd-148">Panašumo įverčiai, mažesni nei 0,55, yra klientai, kurie sistemoje klasifikuojami kaip *nepanašūs* į šaltinio segmento klientus</span><span class="sxs-lookup"><span data-stu-id="f9cfd-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="f9cfd-149">Panašumo įverčiai nuo 0,55 iki 0,7 klasifikuojami kaip *šiek tiek panašūs*</span><span class="sxs-lookup"><span data-stu-id="f9cfd-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="f9cfd-150">Panašumo įverčiai nuo 0,7 iki 0,85 klasifikuojami kaip *panašūs*</span><span class="sxs-lookup"><span data-stu-id="f9cfd-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="f9cfd-151">Panašumo įverčiai nuo 0,85 iki 1 yra klientai, kurie sistemoje klasifikuojami kaip *labai panašūs*</span><span class="sxs-lookup"><span data-stu-id="f9cfd-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="f9cfd-152">Klientai, kurių panašumo įverčiai yra mažesni nei 0,4, į modelio išvestį neįtraukiami.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="f9cfd-153">Sistema nelaiko jų pakankamai panašiais į šaltinio segmentą.</span><span class="sxs-lookup"><span data-stu-id="f9cfd-153">The system doesn't consider them similar enough to the source segment.</span></span>
