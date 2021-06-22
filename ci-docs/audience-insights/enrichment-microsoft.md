---
title: Klientų profilių papildymas naudojant „Microsoft“ duomenis
description: Norėdami savo kliento duomenis papildyti prekės ženklo ir pomėgių savybėmis, naudokite bendrovės „Microsoft“ duomenis.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245717"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="b8c8c-103">Klientų profilių papildymas informacija apie susidomėjimą prekių ženklais ir pomėgiais (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b8c8c-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="b8c8c-104">Norėdami savo kliento duomenis papildyti prekės ženklo ir pomėgių savybėmis, naudokite bendrovės „Microsoft“ duomenis.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="b8c8c-105">Šis susidomėjimas nustatomas pagal žmonių, kurių demografiniai rodikliai yra panašūs į jūsų klientų rodiklius, duomenis.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="b8c8c-106">Ši informacija padeda geriau suprasti ir skirstyti klientus pagal jų susidomėjimą tam tikrais prekių ženklais ir pomėgiais.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="b8c8c-107">Auditorijos įžvalgose eikite į **Duomenys** > **Papildymas** ir [konfigūruokite bei peržiūrėkite papildymus](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b8c8c-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="b8c8c-108">Norėdami konfigūruoti prekės ženklo panašumo papildymą, eikite į skirtuką **Atrasti** ir pasirinkite **Praturtinti mano duomenis** plytelėje **Prekių ženklai**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="b8c8c-109">Norėdami konfigūruoti pomėgio panašumo papildymą, eikite į skirtuką **Atrasti** ir pasirinkite **Praturtinti mano duomenis** plytelėje **Pomėgiai**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b8c8c-110">![Prekių ženklų ir pomėgių plytelės](media/BrandsInterest-tile-Hub.png "Prekių ženklų ir pomėgių plytelės")</span><span class="sxs-lookup"><span data-stu-id="b8c8c-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="b8c8c-111">Kaip apibrėžiame savybes</span><span class="sxs-lookup"><span data-stu-id="b8c8c-111">How we determine affinities</span></span>

<span data-ttu-id="b8c8c-112">„Microsoft“ internetinės paieškos duomenis naudojame prekės ženklų ir pomėgių savybėms rasti įvairiuose demografiniuose segmentuose (apibrėžiamuose pagal amžių, lytį arba vietą).</span><span class="sxs-lookup"><span data-stu-id="b8c8c-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="b8c8c-113">Pagal prekių ženklo ar pomėgio paieškos internete apimtį nustatoma, koks yra demografinio segmento susidomėjimas tuo prekių ženklu ar pomėgiu, palyginti su kitais segmentais.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="b8c8c-114">Priskyrimo lygis ir balas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-114">Affinity level and score</span></span>

<span data-ttu-id="b8c8c-115">Kiekviename praturtintame kliento profilyje teikiame dvi susijusias reikšmes – priskyrimo lygį ir balą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="b8c8c-116">Šios reikšmės padeda nustatyti, koks yra šio profilio demografinio segmento susidomėjimas tam tikrą prekės ženklą ar susidomėjimą, palyginti su kitais demografiniais segmentais.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="b8c8c-117">*Priskyrimo lygį* sudaro keturi lygiai, o *priskyrimo balas* apskaičiuojamas 100 balų skalėje, kuri susieta su priskyrimo lygiais.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="b8c8c-118">Priskyrimo lygis</span><span class="sxs-lookup"><span data-stu-id="b8c8c-118">Affinity level</span></span> |<span data-ttu-id="b8c8c-119">Patrauklumo balas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="b8c8c-120">Labai aukštą</span><span class="sxs-lookup"><span data-stu-id="b8c8c-120">Very high</span></span>     | <span data-ttu-id="b8c8c-121">85-100</span><span class="sxs-lookup"><span data-stu-id="b8c8c-121">85-100</span></span>       |
|<span data-ttu-id="b8c8c-122">Aukštas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-122">High</span></span>     | <span data-ttu-id="b8c8c-123">70-84</span><span class="sxs-lookup"><span data-stu-id="b8c8c-123">70-84</span></span>        |
|<span data-ttu-id="b8c8c-124">Vidutinį</span><span class="sxs-lookup"><span data-stu-id="b8c8c-124">Medium</span></span>     | <span data-ttu-id="b8c8c-125">35-69</span><span class="sxs-lookup"><span data-stu-id="b8c8c-125">35-69</span></span>        |
|<span data-ttu-id="b8c8c-126">Žemą</span><span class="sxs-lookup"><span data-stu-id="b8c8c-126">Low</span></span>     | <span data-ttu-id="b8c8c-127">1-34</span><span class="sxs-lookup"><span data-stu-id="b8c8c-127">1-34</span></span>        |

<span data-ttu-id="b8c8c-128">Priklausomai nuo to, kaip norite matuoti priskyrimą, galite naudoti arba priskyrimo lygį, arba balą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="b8c8c-129">Priskyrimo balas suteikia tikslesnį valdymą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b8c8c-130">Palaikomos šalys ir (arba) regionai</span><span class="sxs-lookup"><span data-stu-id="b8c8c-130">Supported countries/regions</span></span>

<span data-ttu-id="b8c8c-131">Šiuo metu palaikomos šių šalių ir (arba) regionų parinktys: Australija, Kanada (anglų k.), Prancūzija, Vokietija, Jungtinė Karalystė arba Jungtinės Amerikos Valstijos (anglų k.).</span><span class="sxs-lookup"><span data-stu-id="b8c8c-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="b8c8c-132">Norėdami pasirinkti šalį, atidarykite **Prekių ženklų papildymas** arba **Pomėgių papildymas** ir pasirinkite **Keisti** šalia **Šalis ir (arba) regionas**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="b8c8c-133">Srityje **Šalies ir (arba) regiono parametrai** pasirinkite parinktį ir pasirinkite **Taikyti**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="b8c8c-134">Padariniai, susiję su šalies pasirinkimu</span><span class="sxs-lookup"><span data-stu-id="b8c8c-134">Implications related to country selection</span></span>

- <span data-ttu-id="b8c8c-135">Kai [pasirenkate savo prekių ženklus, ](#define-your-brands-or-interests), sistema teikia pasiūlymus pagal pasirinktą šalį arba regioną.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="b8c8c-136">Pasirinkę [pramonės šaką](#define-your-brands-or-interests), gausite svarbiausius prekės ženklus arba susiesite pagal pasirinktą šalį arba regioną.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="b8c8c-137">[Praturtindami profilius](#refresh-enrichment), praturtinsime visus klientų profilius, pagal kuriuos gauname duomenis apie pasirinktus prekių ženklus ir susies klientus.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="b8c8c-138">Įtraukti profilius, kurių nėra parinktoje šalyje ar regione.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="b8c8c-139">Pvz., jei pasirinkote Vokietiją, papildysime JAV esančius duomenis, jei gausime duomenų apie pasirinktus prekių ženklus ir pomėgius JAV.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="b8c8c-140">Papildymo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-140">Configure Enrichment</span></span>

<span data-ttu-id="b8c8c-141">Vedama patirtis leidžia peržiūrėti konfigūraciją ir papildymus.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="b8c8c-142">Prekių ženklų arba pomėgių apibrėžimas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-142">Define your brands or interests</span></span>

<span data-ttu-id="b8c8c-143">Pasirinkite ne daugiau kaip penkis prekių ženklus ar pomėgius naudodami vieną iš šių parinkčių arba jas abi:</span><span class="sxs-lookup"><span data-stu-id="b8c8c-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="b8c8c-144">**Sektorius**: Išplečiamajame sąraše pasirinkite sektorių, o tada išsirinkite to sektoriaus geriausius prekės ženklus arba pomėgius.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="b8c8c-145">**Pasirinkite savo**: Įveskite jūsų organizacijai aktualų prekės ženklą arba pomėgį, o tada išsirinkite iš atitinkančių pasiūlymų.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="b8c8c-146">Jei jūsų ieškomo prekių ženklo ar pomėgio nėra, atsiųskite mums atsiliepimą naudodami nuorodą **Pasiūlyti**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="b8c8c-147">Papildymo nuostatos</span><span class="sxs-lookup"><span data-stu-id="b8c8c-147">Review enrichment preferences</span></span>

<span data-ttu-id="b8c8c-148">Peržiūrėkite numatytąsias pratinimo nuostatas ir prireikus atnaujinkite jas.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Pratinimo nuostatų lango papildymas.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="b8c8c-150">Pasirinkti objektą susiejimui</span><span class="sxs-lookup"><span data-stu-id="b8c8c-150">Select entity to enrich</span></span>

<span data-ttu-id="b8c8c-151">Pasirinkite **Papildytas objektas** ir pasirinkite duomenų rinkinį, kurį norite papildyti įmonės duomenimis iš „Microsoft“.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="b8c8c-152">Galite pažymėti objektą Klientas, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="b8c8c-153">Susiekite savo laukus</span><span class="sxs-lookup"><span data-stu-id="b8c8c-153">Map your fields</span></span>

<span data-ttu-id="b8c8c-154">Susiekite laukus iš vieningojo kliento objekto ir apibrėžkite demografinį segmentą, kurį sistema turėtų naudoti savo klientų duomenims papildyti.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="b8c8c-155">Susiekite šalį / regioną ir bent gimimo datą arba lyties atributus.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="b8c8c-156">Turite susieti šalį / regioną. Taip pat turite susieti bent vieną miestą (ir rajoną / apskritį) arba pašto indeksą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="b8c8c-157">Pasirinkite **Redaguoti**, norėdami apibrėžti laukų susiejimą, ir baigę pasirinkite **Taikyti**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="b8c8c-158">Spustelėkite **Įrašyti**, kad baigtumėte susieti laukus.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="b8c8c-159">Palaikomi toliau nurodyti formatai ir reikšmės; reikšmėse didžiosios ir mažosios raidės neskiriamos.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="b8c8c-160">**Gimimo data**: rekomenduojama, kad duomenų įtraukimo metu gimimo data būtų konvertuota į „DateTime“ formatą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="b8c8c-161">Arba ji gali būti eilutė pagal [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu „YYYY-MM-DD“ arba „yyyy-MM-ddTHH:mm:ssZ“.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="b8c8c-162">**Lytis**: vyras, moteris, nežinoma</span><span class="sxs-lookup"><span data-stu-id="b8c8c-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="b8c8c-163">**Pašto kodas**: penkiaženklis pašto kodas JAV, standartinis pašto kodas visur kitur</span><span class="sxs-lookup"><span data-stu-id="b8c8c-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="b8c8c-164">**Miestas**: miesto pavadinimas anglų k.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-164">**City**: City name in English</span></span>
- <span data-ttu-id="b8c8c-165">**Valstija / provincija**: dviejų raidžių santrumpa JAV ir Kanadoje.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="b8c8c-166">Dviejų ar trijų raidžių santrumpa Australijoje.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="b8c8c-167">Netaikoma Prancūzijai, Vokietijai ir JK.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="b8c8c-168">**Šalis / regionas**:</span><span class="sxs-lookup"><span data-stu-id="b8c8c-168">**Country/Region**:</span></span>

  - <span data-ttu-id="b8c8c-169">JAV: Jungtinės Amerikos Valstijos, Jungtinės Valstijos, JAV, Amerika</span><span class="sxs-lookup"><span data-stu-id="b8c8c-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="b8c8c-170">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="b8c8c-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="b8c8c-171">GB: Jungtinė Karalystė, JK, Didžioji Britanija, GB, Jungtinė Didžiosios Britanijos ir Šiaurės Airijos Karalystė, Jungtinė Didžiosios Britanijos Karalystė</span><span class="sxs-lookup"><span data-stu-id="b8c8c-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="b8c8c-172">AU: Australija, Australijos Sandrauga</span><span class="sxs-lookup"><span data-stu-id="b8c8c-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="b8c8c-173">FR: Prancūzija, FR, Prancūzijos Respublika</span><span class="sxs-lookup"><span data-stu-id="b8c8c-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="b8c8c-174">DE: Vokietija, vokiečių, Deutschland, DE, Vokietijos Federacinė Respublika, Vokietijos Respublika</span><span class="sxs-lookup"><span data-stu-id="b8c8c-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="b8c8c-175">Papildymo peržiūra ir pavadinimas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-175">Review and name the enrichment</span></span>

<span data-ttu-id="b8c8c-176">Galiausiai galite peržiūrėti informaciją ir nurodyti papildymo pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pomėgių peržiūros ir pavadinimo suteikimo puslapis.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="b8c8c-178">Papildymo atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="b8c8c-178">Refresh enrichment</span></span>

<span data-ttu-id="b8c8c-179">Papildymą vykdykite sukonfigūravę prekių ženklus, pomėgius ir demografinių duomenų laukų susiejimą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="b8c8c-180">Norėdami pradėti procesą, prekės ženklo arba pomėgio konfigūravimo puslapyje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="b8c8c-181">Be to, galite leisti sistemai automatiškai vykdyti papildymą, kai vykdomas suplanuotas atnaujinimas.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="b8c8c-182">Priklausomai nuo jūsų klientų duomenų apimties, papildymas gali užtrukti kelias minutes.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="b8c8c-183">Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b8c8c-184">Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b8c8c-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b8c8c-185">Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b8c8c-186">Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b8c8c-187">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="b8c8c-187">Enrichment results</span></span>

<span data-ttu-id="b8c8c-188">Įvykdę papildymo procesą, eikite į **Mano papildymai** ir peržiūrėkite bendrą papildytų klientų skaičių bei prekių ženklų arba pomėgių pasiskirstymą papildytuose klientų profiliuose.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą":::

<span data-ttu-id="b8c8c-190">Peržiūrėkite papildytus duomenis diagramoje spustelėdami **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="b8c8c-191">Papildyti prekių ženklų duomenys yra objekte **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b8c8c-192">Pomėgių duomenys yra objekte **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b8c8c-193">Šiuos objektus taip pat rasite grupėje **Papildymas**, esančioje **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="b8c8c-194">Žr. papildymo duomenis kliento kortelėje</span><span class="sxs-lookup"><span data-stu-id="b8c8c-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="b8c8c-195">Susidomėjimą prekių ženklais ir pomėgiais taip pat galima peržiūrėti atskirose klientų kortelėse.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="b8c8c-196">Eikite į **Klientai** ir pasirinkite kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="b8c8c-197">Kliento kortelėje rasite prekių ženklų arba prekių ženklų, kurie traukia žmones kliento demografiniame profilyje, diagramas.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis":::

## <a name="next-steps"></a><span data-ttu-id="b8c8c-199">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="b8c8c-199">Next steps</span></span>

<span data-ttu-id="b8c8c-200">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b8c8c-201">Kurkite [Segmentai](segments.md), [Matavimai](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.</span><span class="sxs-lookup"><span data-stu-id="b8c8c-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
