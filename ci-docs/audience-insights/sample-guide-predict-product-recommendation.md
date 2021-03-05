---
title: Produkto rekomendacijų prognozės pavyzdžio gairės
description: Šiame pavyzdyje pateiktame vadove išbandykite iš anksto pateiktą produkto prognozė modelį.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270514"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="3c1eb-103">Produkto rekomendacijų prognozės (peržiūros) pavyzdžio gairės</span><span class="sxs-lookup"><span data-stu-id="3c1eb-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="3c1eb-104">Paaiškinsime, kad galutinis produkto rekomendacijų pavyzdys pateiktas prognozė toliau pateiktą duomenų pavyzdį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="3c1eb-105">Scenarijus</span><span class="sxs-lookup"><span data-stu-id="3c1eb-105">Scenario</span></span>

<span data-ttu-id="3c1eb-106">„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="3c1eb-107">Jų tikslas yra suprasti, kuriuos produktus jie turėtų rekomenduoja savo pasikartojančiams klientams.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="3c1eb-108">Žinodami, kokie klientai **labiau tikėtina,** kad juos įsigys, jie galės sutaupyti rinkodaros pastangų susitelkdami į konkrečius elementus.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c1eb-109">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="3c1eb-109">Prerequisites</span></span>

- <span data-ttu-id="3c1eb-110">Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="3c1eb-111">Rekomenduojame jums atlikti šiuos žingsnius [naujojoe aplinkoje](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="3c1eb-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="3c1eb-112">Užduotis 1 - Duomenų vartojimas</span><span class="sxs-lookup"><span data-stu-id="3c1eb-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="3c1eb-113">Peržiūrėti straipsnius [apie duomenų vartojimą](data-sources.md) ir [importuoti duomenų šaltinius naudojant „Power Query“ jungtis](connect-power-query.md) konkrečiai.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="3c1eb-114">Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="3c1eb-115">Kliento duomenų naudojimas iš e-komercijos platformos</span><span class="sxs-lookup"><span data-stu-id="3c1eb-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="3c1eb-116">Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3c1eb-117">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="3c1eb-118">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3c1eb-119">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="3c1eb-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3c1eb-120">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="3c1eb-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3c1eb-121">**Sukurta**: Data/Laikas/Zona</span><span class="sxs-lookup"><span data-stu-id="3c1eb-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą":::

5. <span data-ttu-id="3c1eb-123">„Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**</span><span class="sxs-lookup"><span data-stu-id="3c1eb-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="3c1eb-124">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="3c1eb-125">Vartokite internete įsigytus duomenis</span><span class="sxs-lookup"><span data-stu-id="3c1eb-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="3c1eb-126">Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="3c1eb-127">Pasirinkite **Tekstas/CSV** jungtis dar kartą.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="3c1eb-128">Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="3c1eb-129">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3c1eb-130">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="3c1eb-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3c1eb-131">**Įsigyta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="3c1eb-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="3c1eb-132">**Bendra kaina**: Valiuta</span><span class="sxs-lookup"><span data-stu-id="3c1eb-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="3c1eb-133">Laukelyje **Pavadinimas** šoninėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="3c1eb-134">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="3c1eb-135">Kliento duomenų naudojimas iš lojalumo schemos</span><span class="sxs-lookup"><span data-stu-id="3c1eb-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="3c1eb-136">Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="3c1eb-137">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="3c1eb-138">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="3c1eb-139">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="3c1eb-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="3c1eb-140">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="3c1eb-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="3c1eb-141">**Uždirbtitaškai**: Visas skaičius</span><span class="sxs-lookup"><span data-stu-id="3c1eb-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="3c1eb-142">**Sukurta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="3c1eb-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="3c1eb-143">Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="3c1eb-144">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="3c1eb-145">Užduotis 2 - Duomenų suvienodinimas</span><span class="sxs-lookup"><span data-stu-id="3c1eb-145">Task 2 - Data unification</span></span>

<span data-ttu-id="3c1eb-146">Po duomenų suvartojimo dabar pradėsime **Žemėlapis, Atitiktis, Sulieti** procesą siekiant sukurti suvienodintą kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="3c1eb-147">Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3c1eb-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="3c1eb-148">Schema</span><span class="sxs-lookup"><span data-stu-id="3c1eb-148">Map</span></span>

1. <span data-ttu-id="3c1eb-149">Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="3c1eb-150">Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="3c1eb-151">Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![suvienodinti e-komercijos ir lojalumo duomenų šaltinius.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="3c1eb-153">Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Suvienodinkite lojalumo ID kaip pagrindinį raktą.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="3c1eb-155">Sugretinti</span><span class="sxs-lookup"><span data-stu-id="3c1eb-155">Match</span></span>

1. <span data-ttu-id="3c1eb-156">Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="3c1eb-157">**Pagrindiniame** iškrentančiame meniu sąraše pasirinkite **e-komercijos kontaktai : e-komercija** kaip pagrindinį šaltinį ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="3c1eb-158">**Objektas 2** iškrentančiame sąraše pasirinkite **lojalūs klientai : lojalumo schemą** ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Suvienodinti e-komercijos atitiktį ir lojalumą.](media/unify-match-order.png)

4. <span data-ttu-id="3c1eb-160">Pasirinkite **Sukurkite naują taisyklę**</span><span class="sxs-lookup"><span data-stu-id="3c1eb-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="3c1eb-161">Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="3c1eb-162">E-komercijos kontaktams pasirinkite **Visas pavadinimas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="3c1eb-163">Lojalumo klientams pasirinkite **Visas pavadinimas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="3c1eb-164">Pasirinkite **Normalizuoti** iškrentantį meniu ir pasirinkite **Tipas (Telefonas, Pavadinimas, Adresas, ...)**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="3c1eb-165">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="3c1eb-166">Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="3c1eb-167">Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**</span><span class="sxs-lookup"><span data-stu-id="3c1eb-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="3c1eb-168">Objekto e-komercijos kontaktams, pasirinkite **El. paštas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="3c1eb-169">Lojalių klientų objektui pasirinkite **El. paštas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="3c1eb-170">Palikite normalizavimą tuščią.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="3c1eb-171">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.](media/unify-match-rule.png)

7. <span data-ttu-id="3c1eb-173">Pasirinkite **Įrašyti** ir **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="3c1eb-174">Sulieti</span><span class="sxs-lookup"><span data-stu-id="3c1eb-174">Merge</span></span>

1. <span data-ttu-id="3c1eb-175">Eikite į **Sulieti** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="3c1eb-176">**Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![pervardykite kontakto ID iš lojalumo ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="3c1eb-178">Pasirinkite **Įrašyti** ir **Vykdyti** tam, kad pradėtumėte suliejimo procesą.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="3c1eb-179">3 užduotis – produktų rekomendacijų konfigūravimas prognozė</span><span class="sxs-lookup"><span data-stu-id="3c1eb-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="3c1eb-180">Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="3c1eb-181">Eikite į **Žvalgyba** > **Prognozėje** rinkitės **Produkto rekomendacijos**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="3c1eb-182">Pasirinkite **Pradėti**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-182">Select **Get started**.</span></span>

1. <span data-ttu-id="3c1eb-183">Pavadinkite modelio **OOB produkto rekomendacijų modelį prognozė** ir išvesties objektą **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="3c1eb-184">Apibrėžkite tris modelio sąlygas:</span><span class="sxs-lookup"><span data-stu-id="3c1eb-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="3c1eb-185">**Produktų skaičius**: nustatykite šią reikšmę į **5**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="3c1eb-186">Šis parametras apibrėžia, kiek produktų norite rekomenduojama klientams.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="3c1eb-187">**Siūlyti produktus, kuriuos klientai neseniai įsigijo?** : Pasirinkite **Taip** ir nurodykite, kad į klientų anksčiau įsigytą rekomendaciją norite įtraukti produktų.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="3c1eb-188">**Atsidarę langą:** pažymėkite bent **365 dienas**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="3c1eb-189">Šie nustatymai nurodo, kiek toli modelis žiūrės į praeitį kliento veikloje, kuri buvo naudojama kaip įvestis rekomendacijoms.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelio pirmenybės produkto rekomendacijų modeliui.":::

1. <span data-ttu-id="3c1eb-191">Pasirinkite **Būtini duomenys** ir pasirinkite **Įtraukti duomenis** pirkimo retrospektyvai.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="3c1eb-192">Įtraukite **e-komercijos įsigijimai : e-komerciją** objektą ir nustatykite laukelių žemėlapį iš e-komercijos į atitinkamus laukelius būtinus modeliui.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="3c1eb-193">Prisijunkite prie **e-komercijos įsigijimų : e-komercijos** objekto su **e-komercijos kontaktais : e-komercija**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Prijunkite e-komercijos objektus.](media/model-purchase-join.png)

1. <span data-ttu-id="3c1eb-195">Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="3c1eb-196">Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="3c1eb-197">Šiam pavyzdžiui, rinkitės **Kas mėnesį**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="3c1eb-198">Peržiūrėją visą išsamią informaciją, rinkitės **Įrašyti ir vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="3c1eb-199">Užduotis 4 - Peržiūrėti modelio rezultatus ir paaiškinimus</span><span class="sxs-lookup"><span data-stu-id="3c1eb-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="3c1eb-200">Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="3c1eb-201">Dabar galite peržiūrėti produkto rekomendacijų modelio paaiškinimus.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="3c1eb-202">Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="3c1eb-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="3c1eb-203">5 užduotis – aukštų įsigytų produktų segmento kūrimas</span><span class="sxs-lookup"><span data-stu-id="3c1eb-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="3c1eb-204">Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="3c1eb-205">Galite sukurti naują segmentą pagal modelio sukurtą objektą.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="3c1eb-206">Eikite į **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-206">Go to **Segments**.</span></span> <span data-ttu-id="3c1eb-207">Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**.</span><span class="sxs-lookup"><span data-stu-id="3c1eb-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Sukurkite segmentą su modelio išvestimi.](media/segment-intelligence.png)

1. <span data-ttu-id="3c1eb-209">Pažymėkite **OOBProductRecommendationModelPrediction** galinį punktą ir apibrėžkite segmentą:</span><span class="sxs-lookup"><span data-stu-id="3c1eb-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="3c1eb-210">Laukelis: Produkto ID</span><span class="sxs-lookup"><span data-stu-id="3c1eb-210">Field: ProductID</span></span>
   - <span data-ttu-id="3c1eb-211">Operatorius: reikšmė</span><span class="sxs-lookup"><span data-stu-id="3c1eb-211">Operator: Value</span></span>
   - <span data-ttu-id="3c1eb-212">Reikšmė: pažymėkite tris geriausius produkto ID</span><span class="sxs-lookup"><span data-stu-id="3c1eb-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Kurkite segmentą iš modelio rezultatų.":::

<span data-ttu-id="3c1eb-214">Dabar turite dinamiškai atnaujintą segmentą, kuris nustato klientus, labiau noriusius įsigyti tris labiausiai rekomenduojamus produktus</span><span class="sxs-lookup"><span data-stu-id="3c1eb-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="3c1eb-215">Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3c1eb-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]