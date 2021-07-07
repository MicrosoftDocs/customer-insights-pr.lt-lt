---
title: Išplėstinio adreso papildymas
description: Papildykite ir normalizuokite klientų profilių adresų informaciją naudodami „Microsoft” modelius.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305442"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="42ea0-103">Klientų profilių papildymas išplėstiniais adresais</span><span class="sxs-lookup"><span data-stu-id="42ea0-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="42ea0-104">Adresai jūsų duomenyse gali būti nesusisteminti, neišsamūs arba neteisingi.</span><span class="sxs-lookup"><span data-stu-id="42ea0-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="42ea0-105">Naudokite „Microsoft” modelius, kad normalizuotumėte ir papildytumėte savo adresus į [„Common Data Model” formatą](/common-data-model/schema/core/applicationcommon/address) geresniam tikslumui ir įžvalgoms.</span><span class="sxs-lookup"><span data-stu-id="42ea0-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="42ea0-106">Kaip išplečiame adresus</span><span class="sxs-lookup"><span data-stu-id="42ea0-106">How we enhance addresses</span></span>

<span data-ttu-id="42ea0-107">Mūsų modelis adreso papildymui naudoja dviejų veiksmų procesą.</span><span class="sxs-lookup"><span data-stu-id="42ea0-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="42ea0-108">Pirma, jis išanalizuoja adresą, kad galėtų identifikuoti jo komponentus ir pateikti juos susistemintu formatu.</span><span class="sxs-lookup"><span data-stu-id="42ea0-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="42ea0-109">Tada AI naudojame adreso reikšmėms pataisyti, užbaigti ir standartizuoti.</span><span class="sxs-lookup"><span data-stu-id="42ea0-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="42ea0-110">Pavyzdžiui</span><span class="sxs-lookup"><span data-stu-id="42ea0-110">Example</span></span>

<span data-ttu-id="42ea0-111">Adreso informacija gali būti non pavadinimo formatu ir jame yra rašybos klaidų.</span><span class="sxs-lookup"><span data-stu-id="42ea0-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="42ea0-112">Modelis gali išspręsti šias problemas ir sukurti nuoseklius adresus vieninguosiuose klientų profiliuose.</span><span class="sxs-lookup"><span data-stu-id="42ea0-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="42ea0-113">Apribojimai</span><span class="sxs-lookup"><span data-stu-id="42ea0-113">Limitations</span></span>

<span data-ttu-id="42ea0-114">Išplėstiniai adresai veikia tik su tomis reikšmėmis, kurios jau yra jūsų įtrauktų adresų duomenyse.</span><span class="sxs-lookup"><span data-stu-id="42ea0-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="42ea0-115">Modelis neatlieka šių veiksmų:</span><span class="sxs-lookup"><span data-stu-id="42ea0-115">The model doesn't:</span></span> 

1. <span data-ttu-id="42ea0-116">Netikrina, ar adresas yra tinkamas.</span><span class="sxs-lookup"><span data-stu-id="42ea0-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="42ea0-117">Netikrina, ar konkrečios reikšmės, pavyzdžiui, pašto kodai ar gatvių pavadinimai, yra tinkami.</span><span class="sxs-lookup"><span data-stu-id="42ea0-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="42ea0-118">Nekeičia reikšmių, kurių neatpažįsta.</span><span class="sxs-lookup"><span data-stu-id="42ea0-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="42ea0-119">Siekiant papildyti adresus, modelis naudoja mašininio mokymo metodus.</span><span class="sxs-lookup"><span data-stu-id="42ea0-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="42ea0-120">Nors modeliui pakeičiant įvesties reikšmę taikoma aukšta ribinė reikšmė, kaip ir naudojant mašininį mokomosios sistemos modelį, 100 procentų tikslumas nėra tarpusavio tikslumas.</span><span class="sxs-lookup"><span data-stu-id="42ea0-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="42ea0-121">Palaikomos šalys arba regionai</span><span class="sxs-lookup"><span data-stu-id="42ea0-121">Supported countries or regions</span></span>

<span data-ttu-id="42ea0-122">Šiuo metu palaikome adresų papildymus šiose šalyse ar regionuose:</span><span class="sxs-lookup"><span data-stu-id="42ea0-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="42ea0-123">Australija</span><span class="sxs-lookup"><span data-stu-id="42ea0-123">Australia</span></span>
- <span data-ttu-id="42ea0-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="42ea0-124">Canada</span></span>
- <span data-ttu-id="42ea0-125">Jungtinė Karalystė</span><span class="sxs-lookup"><span data-stu-id="42ea0-125">United Kingdom</span></span>
- <span data-ttu-id="42ea0-126">Jungtinės Valstijos</span><span class="sxs-lookup"><span data-stu-id="42ea0-126">United States</span></span>

<span data-ttu-id="42ea0-127">Adresuose turi būti šalies/regiono reikšmė.</span><span class="sxs-lookup"><span data-stu-id="42ea0-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="42ea0-128">Mes neapdorojame nepalaikomų šalių ar regionų adresų ir tų adresų, kuriems nepateikta šalis arba regionas.</span><span class="sxs-lookup"><span data-stu-id="42ea0-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="42ea0-129">Papildymo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="42ea0-129">Configure the enrichment</span></span>

1. <span data-ttu-id="42ea0-130">Eikite į **Duomenys** > **Papildymas**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="42ea0-131">Pasirinkite **Papildyti mano duomenis** plytelėje **Papildyti adresai**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Papildytų adresų plytelės vaizdas.":::

1. <span data-ttu-id="42ea0-133">Pažymėkite **Kliento duomenų rinkinį** ir pasirinkite objektą, kuriame yra norimi papildyti adresai.</span><span class="sxs-lookup"><span data-stu-id="42ea0-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="42ea0-134">Galite pasirinkti *Kliento* objektą, kad adresai būtų papildyti visuose jūsų klientų profiliuose, arba pasirinkti segmento objektą, kad adresai būtų papildyti tik to segmento klientų profiliuose.</span><span class="sxs-lookup"><span data-stu-id="42ea0-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="42ea0-135">Pasirinkite, kaip jūsų duomenų rinkinyje yra formatuojami adresai.</span><span class="sxs-lookup"><span data-stu-id="42ea0-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="42ea0-136">Pasirinkite **Adresas su vienu atributu**, jei jūsų duomenų adresuose naudojamas vienas laukas.</span><span class="sxs-lookup"><span data-stu-id="42ea0-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="42ea0-137">Pasirinkite **Adresas su keliais atributais**, jei jūsų duomenų adresuose naudojamas daugiau nei vienas duomenų laukas.</span><span class="sxs-lookup"><span data-stu-id="42ea0-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="42ea0-138">Šalis / regionas privalomai nurodomas ir vieno, ir kelių atributų adresuose.</span><span class="sxs-lookup"><span data-stu-id="42ea0-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="42ea0-139">Adresai, kuriuose nėra galiojančių arba palaikomų šalies/regiono reikšmių, nebus papildyti.</span><span class="sxs-lookup"><span data-stu-id="42ea0-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="42ea0-140">Susiekite adreso laukus iš jūsų vieningojo kliento objekto.</span><span class="sxs-lookup"><span data-stu-id="42ea0-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Išplėstinio adreso laukų susiejimo puslapis.":::

1. <span data-ttu-id="42ea0-142">Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="42ea0-143">Pateikite papildymo ir išvesties objekto pavadinimus.</span><span class="sxs-lookup"><span data-stu-id="42ea0-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="42ea0-144">Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="42ea0-145">Papildymo rezultatai</span><span class="sxs-lookup"><span data-stu-id="42ea0-145">Enrichment results</span></span>

<span data-ttu-id="42ea0-146">Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="42ea0-147">Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį.</span><span class="sxs-lookup"><span data-stu-id="42ea0-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="42ea0-148">Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.</span><span class="sxs-lookup"><span data-stu-id="42ea0-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="42ea0-149">Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="42ea0-150">Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.</span><span class="sxs-lookup"><span data-stu-id="42ea0-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="42ea0-151">Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.</span><span class="sxs-lookup"><span data-stu-id="42ea0-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="42ea0-152">Tolesni veiksmai</span><span class="sxs-lookup"><span data-stu-id="42ea0-152">Next steps</span></span>

<span data-ttu-id="42ea0-153">Atlikite veiksmus su papildytais klientų duomenimis.</span><span class="sxs-lookup"><span data-stu-id="42ea0-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="42ea0-154">Kurkite [segmentus](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.</span><span class="sxs-lookup"><span data-stu-id="42ea0-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
