---
title: Klientų ciklo reikšmės prognozės pavyzdinis vadovas
description: Naudokite šį pavyzdinį vadovą, kad išbandytumėte klientų ciklo reikšmės prognozės modelį.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129955"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="f1323-103">Klientų ciklo reikšmės (CLV) prognozės pavyzdinis vadovas</span><span class="sxs-lookup"><span data-stu-id="f1323-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="f1323-104">Šiame vadove pateiktas visapusiškas Klientų ciklo reikšmės (CLV) pavyzdys „Customer Insights” naudojant pavyzdinius duomenis.</span><span class="sxs-lookup"><span data-stu-id="f1323-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="f1323-105">Scenarijus</span><span class="sxs-lookup"><span data-stu-id="f1323-105">Scenario</span></span>

<span data-ttu-id="f1323-106">„Contoso” yra įmonė, kurianti aukštos kokybės kavą ir kavos aparatus.</span><span class="sxs-lookup"><span data-stu-id="f1323-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="f1323-107">Ji parduoda produktus per savo „Contoso Coffee” žiniatinklio svetainę.</span><span class="sxs-lookup"><span data-stu-id="f1323-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="f1323-108">Įmonė nori suprasti vertę (pajamas), kurią jų klientai gali sugeneruoti per artimiausius 12 mėnesių.</span><span class="sxs-lookup"><span data-stu-id="f1323-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="f1323-109">Žinodama numatomą klientų vertę per artimiausius 12 mėnesių, įmonė galės nukreipti savo rinkodaros pastangas vertingiausiems klientams.</span><span class="sxs-lookup"><span data-stu-id="f1323-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1323-110">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="f1323-110">Prerequisites</span></span>

- <span data-ttu-id="f1323-111">Bent [Bendraautoriaus teisės](permissions.md) auditorijos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="f1323-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="f1323-112">Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f1323-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f1323-113">Užduotis 1 - Duomenų vartojimas</span><span class="sxs-lookup"><span data-stu-id="f1323-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="f1323-114">Peržiūrėkite straipsnius [apie duomenų įtraukimą](data-sources.md) ir [duomenų šaltinių importavimą naudojant „Power Query” jungtis](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f1323-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="f1323-115">Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.</span><span class="sxs-lookup"><span data-stu-id="f1323-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f1323-116">Kliento duomenų naudojimas iš e-komercijos platformos</span><span class="sxs-lookup"><span data-stu-id="f1323-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f1323-117">Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="f1323-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f1323-118">Įveskite URL e-komercijos kontaktams [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="f1323-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="f1323-119">Redaguodami duomenis pasirinkite **Transformuoti** ir **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="f1323-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f1323-120">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="f1323-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f1323-121">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="f1323-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="f1323-122">**Sukurta**: Data/Laikas/Zona</span><span class="sxs-lookup"><span data-stu-id="f1323-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. <span data-ttu-id="f1323-124">„Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**</span><span class="sxs-lookup"><span data-stu-id="f1323-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f1323-125">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="f1323-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="f1323-126">Vartokite internete įsigytus duomenis</span><span class="sxs-lookup"><span data-stu-id="f1323-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="f1323-127">Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="f1323-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="f1323-128">Pasirinkite **Tekstas/CSV** jungtis dar kartą.</span><span class="sxs-lookup"><span data-stu-id="f1323-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="f1323-129">Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="f1323-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="f1323-130">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="f1323-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f1323-131">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="f1323-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f1323-132">**Įsigyta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="f1323-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="f1323-133">**Bendra kaina**: Valiuta</span><span class="sxs-lookup"><span data-stu-id="f1323-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="f1323-134">Laukelyje **Pavadinimas** šoninėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.</span><span class="sxs-lookup"><span data-stu-id="f1323-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="f1323-135">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="f1323-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f1323-136">Kliento duomenų naudojimas iš lojalumo schemos</span><span class="sxs-lookup"><span data-stu-id="f1323-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f1323-137">Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="f1323-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f1323-138">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="f1323-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f1323-139">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="f1323-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f1323-140">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="f1323-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="f1323-141">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="f1323-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f1323-142">**Uždirbtitaškai**: Visas skaičius</span><span class="sxs-lookup"><span data-stu-id="f1323-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f1323-143">**Sukurta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="f1323-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f1323-144">Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.</span><span class="sxs-lookup"><span data-stu-id="f1323-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f1323-145">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="f1323-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="f1323-146">Suvartokite kliento duomenis iš svetainės peržiūrų</span><span class="sxs-lookup"><span data-stu-id="f1323-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="f1323-147">Norėdami sukurti duomenų šaltinį pavadinimu **Interneto svetainė**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.</span><span class="sxs-lookup"><span data-stu-id="f1323-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f1323-148">Įveskite URL e-komercijos kontaktams https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="f1323-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="f1323-149">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="f1323-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f1323-150">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="f1323-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f1323-151">**ApžvalgosĮvertinimas**: Dešimtainis skaičius</span><span class="sxs-lookup"><span data-stu-id="f1323-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="f1323-152">**Apžvalgos data**: Data</span><span class="sxs-lookup"><span data-stu-id="f1323-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="f1323-153">Dešinės juostos lauke „Pavadinimas” pervadinkite jūsų duomenų šaltinį iš **Užklausa** į **Apžvalgos**.</span><span class="sxs-lookup"><span data-stu-id="f1323-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="f1323-154">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="f1323-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="f1323-155">Užduotis 2 - Duomenų suvienodinimas</span><span class="sxs-lookup"><span data-stu-id="f1323-155">Task 2 - Data unification</span></span>

<span data-ttu-id="f1323-156">Įtraukę duomenis mes pradedame duomenų suvienodinimo procesą, kad sukurtumėte vieningąjį kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="f1323-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="f1323-157">Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f1323-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f1323-158">Schema</span><span class="sxs-lookup"><span data-stu-id="f1323-158">Map</span></span>

1. <span data-ttu-id="f1323-159">Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus.</span><span class="sxs-lookup"><span data-stu-id="f1323-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f1323-160">Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.</span><span class="sxs-lookup"><span data-stu-id="f1323-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f1323-161">Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.</span><span class="sxs-lookup"><span data-stu-id="f1323-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="f1323-162">Tada pasirinkite **Taikyti**.</span><span class="sxs-lookup"><span data-stu-id="f1323-162">Then, select **Apply**.</span></span>

   ![suvienodinti e-komercijos ir lojalumo duomenų šaltinius.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="f1323-164">Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.</span><span class="sxs-lookup"><span data-stu-id="f1323-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Suvienodinkite lojalumo ID kaip pagrindinį raktą.](media/unify-loyaltyid.png)

1. <span data-ttu-id="f1323-166">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="f1323-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="f1323-167">Sugretinti</span><span class="sxs-lookup"><span data-stu-id="f1323-167">Match</span></span>

1. <span data-ttu-id="f1323-168">Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.</span><span class="sxs-lookup"><span data-stu-id="f1323-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f1323-169">**Pagrindiniame** iškrentančiame meniu sąraše pasirinkite **e-komercijos kontaktai : e-komercija** kaip pagrindinį šaltinį ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="f1323-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f1323-170">**Objektas 2** iškrentančiame sąraše pasirinkite **lojalūs klientai : lojalumo schemą** ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="f1323-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Suvienodinti e-komercijos atitiktį ir lojalumą.](media/unify-match-order.png)

1. <span data-ttu-id="f1323-172">Pasirinkite **Įtraukti taisyklę**</span><span class="sxs-lookup"><span data-stu-id="f1323-172">Select **Add rule**</span></span>

1. <span data-ttu-id="f1323-173">Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="f1323-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="f1323-174">E-komercijos kontaktams pasirinkite **Visas pavadinimas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="f1323-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="f1323-175">Lojalumo klientams pasirinkite **Visas pavadinimas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="f1323-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="f1323-176">Pasirinkite **Normalizuoti** išplečiamąjį meniu ir pasirinkite **Tipas (Telefonas, Pavadinimas, Adresas, ...)**.</span><span class="sxs-lookup"><span data-stu-id="f1323-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="f1323-177">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="f1323-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f1323-178">Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.</span><span class="sxs-lookup"><span data-stu-id="f1323-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="f1323-179">Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**</span><span class="sxs-lookup"><span data-stu-id="f1323-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="f1323-180">Objekto e-komercijos kontaktams, pasirinkite **El. paštas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="f1323-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="f1323-181">Lojalių klientų objektui pasirinkite **El. paštas** iškrentančiame meniu.</span><span class="sxs-lookup"><span data-stu-id="f1323-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="f1323-182">Palikite normalizavimą tuščią.</span><span class="sxs-lookup"><span data-stu-id="f1323-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="f1323-183">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="f1323-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.](media/unify-match-rule.png)

1. <span data-ttu-id="f1323-185">Pasirinkite **Atlikta**.</span><span class="sxs-lookup"><span data-stu-id="f1323-185">Select **Done**.</span></span>

1. <span data-ttu-id="f1323-186">Pasirinkite **Įrašyti** ir **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="f1323-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f1323-187">Sulieti</span><span class="sxs-lookup"><span data-stu-id="f1323-187">Merge</span></span>

1. <span data-ttu-id="f1323-188">Eikite į **Sulieti** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="f1323-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f1323-189">**Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.</span><span class="sxs-lookup"><span data-stu-id="f1323-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![pervardykite kontakto ID iš lojalumo ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="f1323-191">Pasirinkite **Įrašyti** ir **Vykdyti suliejimo ir užbaigimo procesus**.</span><span class="sxs-lookup"><span data-stu-id="f1323-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="f1323-192">3 užduotis – Klientų ciklo reikšmės prognozės konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="f1323-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="f1323-193">Sutvarkę vieninguosius klientų profilius, galime vykdyti klientų ciklo reikšmės prognozę.</span><span class="sxs-lookup"><span data-stu-id="f1323-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="f1323-194">Išsamius veiksmus rasite [Klientų ciklo reikšmės prognozė (peržiūra)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="f1323-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="f1323-195">Eikite į **Įžvalgos**  > **Prognozės** ir pasirinkite **Klientų ciklo reikšmės modelį**.</span><span class="sxs-lookup"><span data-stu-id="f1323-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="f1323-196">Pereikite per informaciją šoninėje srityje ir pasirinkite **Pradėti**.</span><span class="sxs-lookup"><span data-stu-id="f1323-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="f1323-197">Pavadinkite modelį **„OOB” e-prekybos CLV Prognozė**, o išvesties objektą – **„OOBeCommerceCLVPrediction”**.</span><span class="sxs-lookup"><span data-stu-id="f1323-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="f1323-198">Apibrėžkite CLV modelio nuostatas:</span><span class="sxs-lookup"><span data-stu-id="f1323-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="f1323-199">**Prognozės laikotarpis**: **12 mėnesių arba 1 metai**.</span><span class="sxs-lookup"><span data-stu-id="f1323-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="f1323-200">Šis parametras apibrėžia, kaip toli į ateitį galima prognozuoti klientų ciklo reikšmę.</span><span class="sxs-lookup"><span data-stu-id="f1323-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="f1323-201">**Aktyvūs klientai**: Nurodykite, ką jūsų įmonei reiškia aktyvūs klientai.</span><span class="sxs-lookup"><span data-stu-id="f1323-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="f1323-202">Nustatykite istorinį skirtąjį laiką, per kurį klientas turi atlikti bent vieną operaciją, kad būtų laikomas aktyviu.</span><span class="sxs-lookup"><span data-stu-id="f1323-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="f1323-203">Modelis nuspės tik aktyvių klientų CLV.</span><span class="sxs-lookup"><span data-stu-id="f1323-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="f1323-204">Pasirinkite, ar leisti modeliui apskaičiuoti laiką pagal istorinius operacijų duomenis, arba pateikite konkretų skirtąjį laiką.</span><span class="sxs-lookup"><span data-stu-id="f1323-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="f1323-205">Šiame pavyzdiniame vadove mes **leidžiame modeliui apskaičiuoti pirkimo intervalą**, kuris yra numatytoji parinktis.</span><span class="sxs-lookup"><span data-stu-id="f1323-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="f1323-206">**Didelės vertės klientai**: Apibrėžkite didelės vertės klientus kaip geriausiai mokančių klientų procentilį.</span><span class="sxs-lookup"><span data-stu-id="f1323-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="f1323-207">Modelis naudoja šią įvestį, kad pateiktų rezultatus, atitinkančius jūsų verslo didelės vertės klientų apibrėžimą.</span><span class="sxs-lookup"><span data-stu-id="f1323-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="f1323-208">Galite pasirinkti, jog leidžiate modeliui apibrėžti didelės vertės klientus.</span><span class="sxs-lookup"><span data-stu-id="f1323-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="f1323-209">Jis naudoja euristinę taisyklę, iš kurios išvedamas procentilis.</span><span class="sxs-lookup"><span data-stu-id="f1323-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="f1323-210">Taip pat galite apibrėžti didelės vertės klientus kaip ateityje geriausiai mokėsiančių klientų procentilį.</span><span class="sxs-lookup"><span data-stu-id="f1323-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="f1323-211">Šiame pavyzdiniame vadove rankiniu būdu nustatome didelės vertės klientus kaip **geriausius 30 % aktyvių mokių klientų** ir pažymime **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="f1323-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Nuostatų veiksmas CLV modelio vadovo patirtyje.":::

1. <span data-ttu-id="f1323-213">Veiksme **Būtini duomenys** pasirinkite **Įtraukti duomenis**, kad pateiktumėte operacijų retrospektyvos duomenys.</span><span class="sxs-lookup"><span data-stu-id="f1323-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="f1323-214">Įtraukite **e-prekybosPirkiniai : e-prekyba** objektą ir susiekite atributus, kurių reikalauja modelis:</span><span class="sxs-lookup"><span data-stu-id="f1323-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="f1323-215">Operacijos ID: e-prekyba.e-prekybosPirkiniai.PirkinioId</span><span class="sxs-lookup"><span data-stu-id="f1323-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="f1323-216">Operacijos data: e-prekyba.e-prekybosPirkiniai.ĮjungtasPirkimas</span><span class="sxs-lookup"><span data-stu-id="f1323-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="f1323-217">Operacijos suma: e-prekyba.e-prekybosPirkiniai.BendraKaina</span><span class="sxs-lookup"><span data-stu-id="f1323-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="f1323-218">Produkto ID: e-prekyba.e-prekybosPirkiniai.ProduktoId</span><span class="sxs-lookup"><span data-stu-id="f1323-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="f1323-219">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="f1323-219">Select **Next**.</span></span>

1. <span data-ttu-id="f1323-220">Nustatykite ryšį tarp **e-prekybosPirkiniai : e-prekyba** objekto ir **e-prekybosKontaktai : e-prekyba**.</span><span class="sxs-lookup"><span data-stu-id="f1323-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="f1323-221">Veiksmas **Papildomi duomenys (pasirinktiniai)** leidžia jums įtraukti daugiau klientų veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="f1323-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="f1323-222">Šie duomenys gali padėti gauti daugiau įžvalgų apie klientų sąveiką su jūsų verslu, o tai gali prisidėti prie CLV.</span><span class="sxs-lookup"><span data-stu-id="f1323-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="f1323-223">Pagrindinių kliento sąveikų, tokių kaip žiniatinklio žurnalų, klientų aptarnavimo žurnalų arba apdovanojimų programos retrospektyvos, įtraukimas gali pagerinti prognozių tikslumą.</span><span class="sxs-lookup"><span data-stu-id="f1323-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="f1323-224">Pasirinkite **Įtraukti duomenis**, kad įtrauktumėte daugiau klientų veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="f1323-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="f1323-225">Įtraukite kliento veiklos objektą ir susiekite jo laukų pavadinimus su atitinkamais laukais, kurių reikalauja modelis:</span><span class="sxs-lookup"><span data-stu-id="f1323-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="f1323-226">Kliento veiklos objektas: Atsiliepimai:Žiniatinklio svetainė</span><span class="sxs-lookup"><span data-stu-id="f1323-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="f1323-227">Pirminis raktas: Žiniatinklis.Apžvalgos.ApžvalgosId</span><span class="sxs-lookup"><span data-stu-id="f1323-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="f1323-228">Laiko žyma: Svetainė.Apžvalgos.ApžvalgosData</span><span class="sxs-lookup"><span data-stu-id="f1323-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="f1323-229">Įvykis (veiklos pavadinimas): Svetainė.Apžvalgos.RodomasVeiklosTipas</span><span class="sxs-lookup"><span data-stu-id="f1323-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="f1323-230">Išsami informacija (suma arba reikšmė): Svetainė.Apžvalgos.ApžvalgųĮvertinimas</span><span class="sxs-lookup"><span data-stu-id="f1323-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="f1323-231">Pasirinkite **Kitas** ir sukonfigūruokite veiklą bei ryšį tarp operacijos ir kliento duomenų:</span><span class="sxs-lookup"><span data-stu-id="f1323-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="f1323-232">Veiklos tipas: Pasirinkti esamą</span><span class="sxs-lookup"><span data-stu-id="f1323-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="f1323-233">Veiklos žyma: Apžvalga</span><span class="sxs-lookup"><span data-stu-id="f1323-233">Activity label: Review</span></span>
   - <span data-ttu-id="f1323-234">Atitinkama žyma: Žiniatinklis.Apžvalgos.VartotojoId</span><span class="sxs-lookup"><span data-stu-id="f1323-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="f1323-235">Kliento objektas: e-prekybosKontaktai:e-prekyba</span><span class="sxs-lookup"><span data-stu-id="f1323-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="f1323-236">Ryšys: ŽiniatinklioApžvalgos</span><span class="sxs-lookup"><span data-stu-id="f1323-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="f1323-237">Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.</span><span class="sxs-lookup"><span data-stu-id="f1323-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f1323-238">Modelį reikia reguliariai mokyti, kad jis galėtų išmokti naujus modelius, įvedant naujus duomenis.</span><span class="sxs-lookup"><span data-stu-id="f1323-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="f1323-239">Šiam pavyzdžiui pasirinkite **Mėnesinis**.</span><span class="sxs-lookup"><span data-stu-id="f1323-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="f1323-240">Peržiūrėję visą išsamią informaciją, pasirinkite **Įrašyti ir vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="f1323-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f1323-241">4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus</span><span class="sxs-lookup"><span data-stu-id="f1323-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f1323-242">Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą.</span><span class="sxs-lookup"><span data-stu-id="f1323-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f1323-243">Tada galėsite peržiūrėti CLV modelio rezultatus ir paaiškinimus.</span><span class="sxs-lookup"><span data-stu-id="f1323-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="f1323-244">Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="f1323-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="f1323-245">5 užduotis – Didelės vertės klientų segmento kūrimas</span><span class="sxs-lookup"><span data-stu-id="f1323-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="f1323-246">Paleidus modelį sukuriamas naujas objektas, kuris pateikiamas skiltyje **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="f1323-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="f1323-247">Galite sukurti naują klientų segmentą, pagrįstą modelio sukurtu objektu.</span><span class="sxs-lookup"><span data-stu-id="f1323-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="f1323-248">Eikite į **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="f1323-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="f1323-249">Pasirinkite **Naujas** ir **Sukurti iš** > **Įžvalgų**.</span><span class="sxs-lookup"><span data-stu-id="f1323-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Sukurkite segmentą su modelio išvestimi.](media/segment-intelligence.png)

1. <span data-ttu-id="f1323-251">Pasirinkite **„OOBeCommerceCLVPrediction”** objektą ir apibrėžkite segmentą:</span><span class="sxs-lookup"><span data-stu-id="f1323-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="f1323-252">Laukas: „CLVScore”</span><span class="sxs-lookup"><span data-stu-id="f1323-252">Field: CLVScore</span></span>
  - <span data-ttu-id="f1323-253">Operatorius: didesnis nei</span><span class="sxs-lookup"><span data-stu-id="f1323-253">Operator: greater than</span></span>
  - <span data-ttu-id="f1323-254">Vertė: 1500</span><span class="sxs-lookup"><span data-stu-id="f1323-254">Value: 1500</span></span>

1. <span data-ttu-id="f1323-255">Pasirinkite **Peržiūrėti** ir **Įrašykite** segmentą.</span><span class="sxs-lookup"><span data-stu-id="f1323-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="f1323-256">Dabar turite segmentą, nustatantį klientus, kurie, kaip prognozuojama, sugeneruos daugiau nei $1500 pajamų per artimiausius 12 mėnesių.</span><span class="sxs-lookup"><span data-stu-id="f1323-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="f1323-257">Įterpus daugiau duomenų, šis segmentas atnaujinamas dinamiškai.</span><span class="sxs-lookup"><span data-stu-id="f1323-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="f1323-258">Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f1323-258">For more information, see [Create and manage segments](segments.md).</span></span>
