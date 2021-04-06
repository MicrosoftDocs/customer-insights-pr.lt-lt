---
title: Prenumeratos atsisakymo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad bandytumėte nestandartinį prenumeravimo atsisakymo prognozės modelį.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595528"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="10e0b-103">Prenumeravimo atsisakymo prognozės (peržiūros) pavyzdžio vedlys</span><span class="sxs-lookup"><span data-stu-id="10e0b-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="10e0b-104">Praeisime kartu pro prenumeravimo nutraukimo prognozės pavyzdį nuo pradžios iki galo naudodami toliau pateiktus pavyzdžio duomenis.</span><span class="sxs-lookup"><span data-stu-id="10e0b-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="10e0b-105">Scenarijus</span><span class="sxs-lookup"><span data-stu-id="10e0b-105">Scenario</span></span>

<span data-ttu-id="10e0b-106">„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę.</span><span class="sxs-lookup"><span data-stu-id="10e0b-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="10e0b-107">Jie neseniai pradėjo prenumeravimo verslą savo klientams tam, kad jie reguliariai gautų kavos.</span><span class="sxs-lookup"><span data-stu-id="10e0b-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="10e0b-108">Jų tikslas yra suprasti, kurie prenumeruojantys klientai gali atšaukti savo prenumeratą per kelis ateinančius mėnesius.</span><span class="sxs-lookup"><span data-stu-id="10e0b-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="10e0b-109">Žinojimas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.</span><span class="sxs-lookup"><span data-stu-id="10e0b-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10e0b-110">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="10e0b-110">Prerequisites</span></span>

- <span data-ttu-id="10e0b-111">Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="10e0b-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="10e0b-112">Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="10e0b-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="10e0b-113">Užduotis 1 - Duomenų vartojimas</span><span class="sxs-lookup"><span data-stu-id="10e0b-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="10e0b-114">Peržiūrėti straipsnius [apie duomenų vartojimą](data-sources.md) ir [importuoti duomenų šaltinius naudojant „Power Query“ jungtis](connect-power-query.md) konkrečiai.</span><span class="sxs-lookup"><span data-stu-id="10e0b-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="10e0b-115">Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.</span><span class="sxs-lookup"><span data-stu-id="10e0b-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="10e0b-116">Kliento duomenų naudojimas iš e-komercijos platformos</span><span class="sxs-lookup"><span data-stu-id="10e0b-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="10e0b-117">Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="10e0b-118">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="10e0b-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="10e0b-119">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="10e0b-120">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="10e0b-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="10e0b-121">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="10e0b-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="10e0b-122">**Sukurta**: Data/Laikas/Zona</span><span class="sxs-lookup"><span data-stu-id="10e0b-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. <span data-ttu-id="10e0b-124">Lauke **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**</span><span class="sxs-lookup"><span data-stu-id="10e0b-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="10e0b-125">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="10e0b-126">Kliento duomenų naudojimas iš lojalumo schemos</span><span class="sxs-lookup"><span data-stu-id="10e0b-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="10e0b-127">Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="10e0b-128">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="10e0b-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="10e0b-129">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="10e0b-130">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="10e0b-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="10e0b-131">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="10e0b-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="10e0b-132">**Uždirbtitaškai**: Visas skaičius</span><span class="sxs-lookup"><span data-stu-id="10e0b-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="10e0b-133">**Sukurta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="10e0b-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="10e0b-134">Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="10e0b-135">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="10e0b-136">Suvartojama prenumeratos informacija</span><span class="sxs-lookup"><span data-stu-id="10e0b-136">Ingest subscription information</span></span>

1. <span data-ttu-id="10e0b-137">Sukurti duomenų šaltinį pavadinimus **Prenumeravimo istorija**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.</span><span class="sxs-lookup"><span data-stu-id="10e0b-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="10e0b-138">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="10e0b-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="10e0b-139">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="10e0b-140">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="10e0b-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="10e0b-141">**Prenumeravimo ID**: Visas numeris</span><span class="sxs-lookup"><span data-stu-id="10e0b-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="10e0b-142">**Prenumeravimo suma**: Valiuta</span><span class="sxs-lookup"><span data-stu-id="10e0b-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="10e0b-143">**Prenumeravimo galutinė data**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="10e0b-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="10e0b-144">**Prenumeravimo pradžios data**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="10e0b-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="10e0b-145">**Perlaidos data**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="10e0b-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="10e0b-146">**Pasikartoja**: Tiesa/Netiesa</span><span class="sxs-lookup"><span data-stu-id="10e0b-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="10e0b-147">**Yra_automatiškai_atnaujinama**: Tiesa/Netiesa</span><span class="sxs-lookup"><span data-stu-id="10e0b-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="10e0b-148">**Atnaujinimo dažnis mėnesiai**: Visas numeris</span><span class="sxs-lookup"><span data-stu-id="10e0b-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="10e0b-149">Laukelyje **Pavadinimas** dešinėje juostoje, pervardykite savo duomenų šaltinį iš **Laukiama** į **Prenumeravimo istorija**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="10e0b-150">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="10e0b-151">Suvartokite kliento duomenis iš svetainės peržiūrų</span><span class="sxs-lookup"><span data-stu-id="10e0b-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="10e0b-152">Norėdami sukurti duomenų šaltinį pavadinimu **Interneto svetainė**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.</span><span class="sxs-lookup"><span data-stu-id="10e0b-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="10e0b-153">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="10e0b-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="10e0b-154">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="10e0b-155">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="10e0b-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="10e0b-156">**Peržiūros reitingas**: Visas numeris</span><span class="sxs-lookup"><span data-stu-id="10e0b-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="10e0b-157">**Peržiūros data**: Data</span><span class="sxs-lookup"><span data-stu-id="10e0b-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="10e0b-158">„Pavadinimas“ laukelyje dešinėje juostoje, pervardykite savo duomenų šaltinį iš **Laukiama** į **Žiniatinklio peržiūros**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="10e0b-159">Užduotis 2 - Duomenų suvienodinimas</span><span class="sxs-lookup"><span data-stu-id="10e0b-159">Task 2 - Data unification</span></span>

<span data-ttu-id="10e0b-160">Po duomenų suvartojimo dabar pradėsime **Žemėlapis, Atitiktis, Sulieti** procesą siekiant sukurti suvienodintą kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="10e0b-161">Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="10e0b-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="10e0b-162">Schema</span><span class="sxs-lookup"><span data-stu-id="10e0b-162">Map</span></span>

1. <span data-ttu-id="10e0b-163">Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus.</span><span class="sxs-lookup"><span data-stu-id="10e0b-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="10e0b-164">Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="10e0b-165">Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Suvienodinti e-komercijos ir lojalumo duomenų šaltinius.":::

1. <span data-ttu-id="10e0b-167">Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Suvienodinti lojalumo ID kaip pagrindinį raktą.":::

### <a name="match"></a><span data-ttu-id="10e0b-169">Sugretinti</span><span class="sxs-lookup"><span data-stu-id="10e0b-169">Match</span></span>

1. <span data-ttu-id="10e0b-170">Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="10e0b-171">**Pagrindiniame** iškrentančiame meniu sąraše pasirinkite **e-komercijos kontaktai : e-komercija** kaip pagrindinį šaltinį ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="10e0b-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="10e0b-172">**Objektas 2** iškrentančiame sąraše pasirinkite **lojalūs klientai : lojalumo schemą** ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="10e0b-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Suvienodinti e-komercijos atitiktį ir lojalumą.":::

1. <span data-ttu-id="10e0b-174">Pasirinkite **Sukurkite naują taisyklę**</span><span class="sxs-lookup"><span data-stu-id="10e0b-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="10e0b-175">Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="10e0b-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="10e0b-176">E-komercijos kontaktams pasirinkite **Visas pavadinimas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="10e0b-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="10e0b-177">Lojalumo klientams pasirinkite **Visas pavadinimas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="10e0b-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="10e0b-178">Pasirinkite **Normalizuoti** iškrentantį meniu ir pasirinkite **Tipas (Telefonas, Pavadinimas, Adresas, ...)**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="10e0b-179">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="10e0b-180">Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.</span><span class="sxs-lookup"><span data-stu-id="10e0b-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="10e0b-181">Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**</span><span class="sxs-lookup"><span data-stu-id="10e0b-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="10e0b-182">Objekto e-komercijos kontaktams, pasirinkite **El. paštas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="10e0b-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="10e0b-183">Lojalių klientų objektui pasirinkite **El. paštas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="10e0b-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="10e0b-184">Palikite normalizavimą tuščią.</span><span class="sxs-lookup"><span data-stu-id="10e0b-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="10e0b-185">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Suvienodinti atitikties taisyklę pavadinimui ir el. paštui.":::

7. <span data-ttu-id="10e0b-187">Pasirinkite **Įrašyti** ir **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="10e0b-188">Sulieti</span><span class="sxs-lookup"><span data-stu-id="10e0b-188">Merge</span></span>

1. <span data-ttu-id="10e0b-189">Eikite į **Sulieti** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="10e0b-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="10e0b-190">**Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.</span><span class="sxs-lookup"><span data-stu-id="10e0b-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="pervardykite kontakto ID iš lojalumo ID.":::

1. <span data-ttu-id="10e0b-192">Pasirinkite **Įrašyti** ir **Vykdyti** tam, kad pradėtumėte suliejimo procesą.</span><span class="sxs-lookup"><span data-stu-id="10e0b-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="10e0b-193">Užduotis 3 - Konfigūruoti prenumeravimo nutraukimo prognozę</span><span class="sxs-lookup"><span data-stu-id="10e0b-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="10e0b-194">Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę.</span><span class="sxs-lookup"><span data-stu-id="10e0b-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="10e0b-195">Išsamiems žingsniams, žr. [Prenumeravimo nutraukimo prognozė (peržiūra)](predict-subscription-churn.md) straipsnį.</span><span class="sxs-lookup"><span data-stu-id="10e0b-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="10e0b-196">Eikite į **Įžvalga** > **Atrasti** ir pasirinkite norėdami naudoti **Kliento nutraukimo modelį**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="10e0b-197">Pasirinkite **Pernumeravimo** parinktį ir pasirinkite **Pradėti**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="10e0b-198">Pavadinkite modelį **OOB prenumeravimo nutraukimo prognozė** ir išvesties objektą **OOBprenumeravimonutraukimoprognozė**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="10e0b-199">Nustatykite dvi sąlygas nutraukimo modeliui:</span><span class="sxs-lookup"><span data-stu-id="10e0b-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="10e0b-200">**Dienos iki pasibaigs prenumerata**: **mažiausiai 60** dienų.</span><span class="sxs-lookup"><span data-stu-id="10e0b-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="10e0b-201">Jei klientas neatnaujina prenumeratos per šį laikotarpį po to, kai baigsis prenumerata, laikoma, kad jis atsisakė paslaugų.</span><span class="sxs-lookup"><span data-stu-id="10e0b-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="10e0b-202">**Atsisakymo sąvoka**: **mažiausiai 93** dienų.</span><span class="sxs-lookup"><span data-stu-id="10e0b-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="10e0b-203">Modelio nuspėjama trukmė, per kurį klientai gali atsisakyti.</span><span class="sxs-lookup"><span data-stu-id="10e0b-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="10e0b-204">Kuo toliau žvelgiate į ateitį, tuo rezultatai bus netikslesni.</span><span class="sxs-lookup"><span data-stu-id="10e0b-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pasirinkite modelio išlyginimo prognozės langą ir nutraukimo sąvoką.":::

1. <span data-ttu-id="10e0b-206">Pasirinkite **Įtraukti būtinus duomenis** ir pasirinkite **Įtraukite duomenis** prenumeratos istorijai.</span><span class="sxs-lookup"><span data-stu-id="10e0b-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="10e0b-207">Įtraukite **Prenumeratą : prenumeravimo istorija** objektą ir sudarykite laukelių žemėlapį iš e-komercijos pagal atitinkamus modeliui būtinus laukelius.</span><span class="sxs-lookup"><span data-stu-id="10e0b-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="10e0b-208">Prisijunkite prie **Prenumerata : Prenumeravimo istorija** objekto su **E-komercijos kontaktų : e-komercija**, pavadinkite ryšius **e-komercijos prenumerata**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Sujunkite e-komercijos objektus.":::

1. <span data-ttu-id="10e0b-210">Kliento veiklos skyriuje įtraukite **Žiniatinklio peržiūros: interneto svetainės** objektą ir sudarykite laukelių žemėlapį iš žiniatinklio peržiūros pagal atitinkamus modeliui būtinus laukelius.</span><span class="sxs-lookup"><span data-stu-id="10e0b-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="10e0b-211">Pirminis raktas: Peržiūros ID</span><span class="sxs-lookup"><span data-stu-id="10e0b-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="10e0b-212">Laiko juostos antspaudas: Peržiūros data</span><span class="sxs-lookup"><span data-stu-id="10e0b-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="10e0b-213">Įvykis: Peržiūros reitingavimas</span><span class="sxs-lookup"><span data-stu-id="10e0b-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="10e0b-214">Konfigūruokite veiklą interneto svetainės peržiūroms.</span><span class="sxs-lookup"><span data-stu-id="10e0b-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="10e0b-215">Pasirinkite veiklą **Peržiūrėti** ir prisijungti prie **Žiniatinklio peržiūrų : interneto svetainės** objektą su **e-komercijos kontaktų : e-komercija**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="10e0b-216">Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.</span><span class="sxs-lookup"><span data-stu-id="10e0b-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="10e0b-217">Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų.</span><span class="sxs-lookup"><span data-stu-id="10e0b-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="10e0b-218">Šiam pavyzdžiui, rinkitės **Kas mėnesį**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="10e0b-219">Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="10e0b-220">Užduotis 4 - Peržiūrėti modelio rezultatus ir paaiškinimus</span><span class="sxs-lookup"><span data-stu-id="10e0b-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="10e0b-221">Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą.</span><span class="sxs-lookup"><span data-stu-id="10e0b-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="10e0b-222">Galite dabar peržiūrėti prenumeravimo atsisakymo modelio paaiškinimus.</span><span class="sxs-lookup"><span data-stu-id="10e0b-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="10e0b-223">Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="10e0b-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="10e0b-224">Užduotis 5 - Sukurti didelės atsisakymo rizikos klientų segmentą</span><span class="sxs-lookup"><span data-stu-id="10e0b-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="10e0b-225">Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="10e0b-226">Galite sukurti naują segmentą pagal modelio sukurtą objektą.</span><span class="sxs-lookup"><span data-stu-id="10e0b-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="10e0b-227">Eikite į **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-227">Go to **Segments**.</span></span> <span data-ttu-id="10e0b-228">Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**.</span><span class="sxs-lookup"><span data-stu-id="10e0b-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Sukurkite segmentą su modelio išvestimi.":::

1. <span data-ttu-id="10e0b-230">Pasirinkite **„OOBSubscriptionChurnPrediction“** galutinį tašką ir nustatykite segmentą:</span><span class="sxs-lookup"><span data-stu-id="10e0b-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="10e0b-231">Laukelis: Nutraukimo balas</span><span class="sxs-lookup"><span data-stu-id="10e0b-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="10e0b-232">Operatorius: didesnis nei</span><span class="sxs-lookup"><span data-stu-id="10e0b-232">Operator: greater than</span></span>
   - <span data-ttu-id="10e0b-233">Vertė: 0,6</span><span class="sxs-lookup"><span data-stu-id="10e0b-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nustatykite prenumeravimo atsisakymo segmentą.":::

<span data-ttu-id="10e0b-235">Dabar turite segmentą, kuris dinamiškai naujinamas ir nustato didelės rizikos klientų atsisakymą šiam prenumeratos verslui.</span><span class="sxs-lookup"><span data-stu-id="10e0b-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="10e0b-236">Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="10e0b-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]