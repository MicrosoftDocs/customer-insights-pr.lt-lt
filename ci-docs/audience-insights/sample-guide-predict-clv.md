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
ms.openlocfilehash: 19c1fbadb79ba22c0dc11aa7c3b5b2415add70a7
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306359"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="5e686-103">Klientų ciklo reikšmės (CLV) prognozės pavyzdinis vadovas</span><span class="sxs-lookup"><span data-stu-id="5e686-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="5e686-104">Šiame vadove pateiktas visapusiškas Klientų ciklo reikšmės (CLV) pavyzdys „Customer Insights” naudojant pavyzdinius duomenis.</span><span class="sxs-lookup"><span data-stu-id="5e686-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="5e686-105">Scenarijus</span><span class="sxs-lookup"><span data-stu-id="5e686-105">Scenario</span></span>

<span data-ttu-id="5e686-106">„Contoso” yra įmonė, kurianti aukštos kokybės kavą ir kavos aparatus.</span><span class="sxs-lookup"><span data-stu-id="5e686-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="5e686-107">Ji parduoda produktus per savo „Contoso Coffee” žiniatinklio svetainę.</span><span class="sxs-lookup"><span data-stu-id="5e686-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="5e686-108">Įmonė nori suprasti vertę (pajamas), kurią jų klientai gali sugeneruoti per artimiausius 12 mėnesių.</span><span class="sxs-lookup"><span data-stu-id="5e686-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="5e686-109">Žinodama numatomą klientų vertę per artimiausius 12 mėnesių, įmonė galės nukreipti savo rinkodaros pastangas vertingiausiems klientams.</span><span class="sxs-lookup"><span data-stu-id="5e686-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e686-110">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="5e686-110">Prerequisites</span></span>

- <span data-ttu-id="5e686-111">Bent [Bendraautoriaus teisės](permissions.md) auditorijos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="5e686-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="5e686-112">Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="5e686-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="5e686-113">Užduotis 1 - Duomenų vartojimas</span><span class="sxs-lookup"><span data-stu-id="5e686-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="5e686-114">Peržiūrėkite straipsnius [apie duomenų įtraukimą](data-sources.md) ir [duomenų šaltinių importavimą naudojant „Power Query” jungtis](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="5e686-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="5e686-115">Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.</span><span class="sxs-lookup"><span data-stu-id="5e686-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="5e686-116">Kliento duomenų naudojimas iš e-komercijos platformos</span><span class="sxs-lookup"><span data-stu-id="5e686-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="5e686-117">Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="5e686-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5e686-118">Įveskite URL e-komercijos kontaktams [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="5e686-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="5e686-119">Redaguodami duomenis pasirinkite **Transformuoti** ir **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="5e686-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e686-120">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="5e686-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="5e686-121">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="5e686-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="5e686-122">**Sukurta**: Data/Laikas/Zona</span><span class="sxs-lookup"><span data-stu-id="5e686-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. <span data-ttu-id="5e686-124">„Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**</span><span class="sxs-lookup"><span data-stu-id="5e686-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="5e686-125">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="5e686-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="5e686-126">Vartokite internete įsigytus duomenis</span><span class="sxs-lookup"><span data-stu-id="5e686-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="5e686-127">Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="5e686-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="5e686-128">Pasirinkite **Tekstas/CSV** jungtis dar kartą.</span><span class="sxs-lookup"><span data-stu-id="5e686-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="5e686-129">Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="5e686-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="5e686-130">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="5e686-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e686-131">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="5e686-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="5e686-132">**Įsigyta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="5e686-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="5e686-133">**Bendra kaina**: Valiuta</span><span class="sxs-lookup"><span data-stu-id="5e686-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="5e686-134">Laukelyje **Pavadinimas** šoninėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.</span><span class="sxs-lookup"><span data-stu-id="5e686-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="5e686-135">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="5e686-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="5e686-136">Kliento duomenų naudojimas iš lojalumo schemos</span><span class="sxs-lookup"><span data-stu-id="5e686-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="5e686-137">Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="5e686-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5e686-138">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="5e686-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="5e686-139">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="5e686-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e686-140">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="5e686-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="5e686-141">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="5e686-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="5e686-142">**Uždirbtitaškai**: Visas skaičius</span><span class="sxs-lookup"><span data-stu-id="5e686-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="5e686-143">**Sukurta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="5e686-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="5e686-144">Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.</span><span class="sxs-lookup"><span data-stu-id="5e686-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="5e686-145">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="5e686-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="5e686-146">Suvartokite kliento duomenis iš svetainės peržiūrų</span><span class="sxs-lookup"><span data-stu-id="5e686-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="5e686-147">Norėdami sukurti duomenų šaltinį pavadinimu **Interneto svetainė**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.</span><span class="sxs-lookup"><span data-stu-id="5e686-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="5e686-148">Įveskite URL e-komercijos kontaktams https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="5e686-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="5e686-149">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="5e686-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="5e686-150">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="5e686-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="5e686-151">**ApžvalgosĮvertinimas**: Dešimtainis skaičius</span><span class="sxs-lookup"><span data-stu-id="5e686-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="5e686-152">**Apžvalgos data**: Data</span><span class="sxs-lookup"><span data-stu-id="5e686-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="5e686-153">Dešinės juostos lauke „Pavadinimas” pervadinkite jūsų duomenų šaltinį iš **Užklausa** į **Apžvalgos**.</span><span class="sxs-lookup"><span data-stu-id="5e686-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="5e686-154">**Įrašykite** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="5e686-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="5e686-155">Užduotis 2 - Duomenų suvienodinimas</span><span class="sxs-lookup"><span data-stu-id="5e686-155">Task 2 - Data unification</span></span>

<span data-ttu-id="5e686-156">Įtraukę duomenis mes pradedame duomenų suvienodinimo procesą, kad sukurtumėte vieningąjį kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="5e686-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="5e686-157">Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5e686-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="5e686-158">Schema</span><span class="sxs-lookup"><span data-stu-id="5e686-158">Map</span></span>

1. <span data-ttu-id="5e686-159">Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus.</span><span class="sxs-lookup"><span data-stu-id="5e686-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="5e686-160">Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.</span><span class="sxs-lookup"><span data-stu-id="5e686-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="5e686-161">Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.</span><span class="sxs-lookup"><span data-stu-id="5e686-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="5e686-162">Tada pasirinkite **Taikyti**.</span><span class="sxs-lookup"><span data-stu-id="5e686-162">Then, select **Apply**.</span></span>

   ![suvienodinti e-komercijos ir lojalumo duomenų šaltinius.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="5e686-164">Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.</span><span class="sxs-lookup"><span data-stu-id="5e686-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Suvienodinkite lojalumo ID kaip pagrindinį raktą.](media/unify-loyaltyid.png)

1. <span data-ttu-id="5e686-166">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5e686-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="5e686-167">Sugretinti</span><span class="sxs-lookup"><span data-stu-id="5e686-167">Match</span></span>

1. <span data-ttu-id="5e686-168">Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.</span><span class="sxs-lookup"><span data-stu-id="5e686-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="5e686-169">Pirminiame **išplečiamajame** sąraše pasirinkite **eCommerceContacts: el. prekyba** pirminis šaltinis ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="5e686-169">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="5e686-170">Išplečiamajame sąraše **Objektas 2** pasirinkite **loyCustomers: LoyaltyScheme** įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="5e686-170">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Suvienodinti e-komercijos atitiktį ir lojalumą.](media/unify-match-order.png)

1. <span data-ttu-id="5e686-172">Pasirinkite **Įtraukti taisyklę**</span><span class="sxs-lookup"><span data-stu-id="5e686-172">Select **Add rule**</span></span>

1. <span data-ttu-id="5e686-173">Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="5e686-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="5e686-174">El. prekyboscontacts išplečiamajame sąraše pažymėkite **Visas vardas**.</span><span class="sxs-lookup"><span data-stu-id="5e686-174">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="5e686-175">loyCustomers išplečiamajame sąraše pažymėkite **Visas vardas**.</span><span class="sxs-lookup"><span data-stu-id="5e686-175">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="5e686-176">Pažymėkite **normalizuoti** išplečiamąjį sąrašą ir pasirinkite **Tipas (Telefonas, Vardas, Adresas, ...)**.</span><span class="sxs-lookup"><span data-stu-id="5e686-176">Select the **Normalize** dropdown and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="5e686-177">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="5e686-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="5e686-178">Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.</span><span class="sxs-lookup"><span data-stu-id="5e686-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="5e686-179">Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**</span><span class="sxs-lookup"><span data-stu-id="5e686-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="5e686-180">Objekto "eCommerceContacts" **išplečiamajame sąraše** pasirinkite "El. paštas".</span><span class="sxs-lookup"><span data-stu-id="5e686-180">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="5e686-181">Objekto loyCustomers **išplečiamajame sąraše** pasirinkite "El. paštas".</span><span class="sxs-lookup"><span data-stu-id="5e686-181">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="5e686-182">Palikite normalizavimą tuščią.</span><span class="sxs-lookup"><span data-stu-id="5e686-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="5e686-183">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="5e686-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.](media/unify-match-rule.png)

1. <span data-ttu-id="5e686-185">Pasirinkite **Atlikta**.</span><span class="sxs-lookup"><span data-stu-id="5e686-185">Select **Done**.</span></span>

1. <span data-ttu-id="5e686-186">Pasirinkite **Įrašyti** ir **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="5e686-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="5e686-187">Sulieti</span><span class="sxs-lookup"><span data-stu-id="5e686-187">Merge</span></span>

1. <span data-ttu-id="5e686-188">Eikite į **Sulieti** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="5e686-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="5e686-189">**Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.</span><span class="sxs-lookup"><span data-stu-id="5e686-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![pervardykite kontakto ID iš lojalumo ID.](media/unify-merge-contactid.png)

1. <span data-ttu-id="5e686-191">Pasirinkite **Įrašyti** ir **Vykdyti suliejimo ir užbaigimo procesus**.</span><span class="sxs-lookup"><span data-stu-id="5e686-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="5e686-192">3 užduotis – Klientų ciklo reikšmės prognozės konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5e686-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="5e686-193">Sutvarkę vieninguosius klientų profilius, galime vykdyti klientų ciklo reikšmės prognozę.</span><span class="sxs-lookup"><span data-stu-id="5e686-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="5e686-194">Išsamius veiksmus rasite [Klientų ciklo reikšmės prognozė (peržiūra)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="5e686-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="5e686-195">Eikite į **Įžvalgos**  > **Prognozės** ir pasirinkite **Klientų ciklo reikšmės modelį**.</span><span class="sxs-lookup"><span data-stu-id="5e686-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="5e686-196">Pereikite per informaciją šoninėje srityje ir pasirinkite **Pradėti**.</span><span class="sxs-lookup"><span data-stu-id="5e686-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="5e686-197">Pavadinkite modelį **„OOB” e-prekybos CLV Prognozė**, o išvesties objektą – **„OOBeCommerceCLVPrediction”**.</span><span class="sxs-lookup"><span data-stu-id="5e686-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="5e686-198">Apibrėžkite CLV modelio nuostatas:</span><span class="sxs-lookup"><span data-stu-id="5e686-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="5e686-199">**Prognozės laikotarpis**: **12 mėnesių arba 1 metai**.</span><span class="sxs-lookup"><span data-stu-id="5e686-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="5e686-200">Šis parametras apibrėžia, kaip toli į ateitį galima prognozuoti klientų ciklo reikšmę.</span><span class="sxs-lookup"><span data-stu-id="5e686-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="5e686-201">**Aktyvūs klientai**: Nurodykite, ką jūsų įmonei reiškia aktyvūs klientai.</span><span class="sxs-lookup"><span data-stu-id="5e686-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="5e686-202">Nustatykite istorinį skirtąjį laiką, per kurį klientas turi atlikti bent vieną operaciją, kad būtų laikomas aktyviu.</span><span class="sxs-lookup"><span data-stu-id="5e686-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="5e686-203">Modelis nuspės tik aktyvių klientų CLV.</span><span class="sxs-lookup"><span data-stu-id="5e686-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="5e686-204">Pasirinkite, ar leisti modeliui apskaičiuoti laiką pagal istorinius operacijų duomenis, arba pateikite konkretų skirtąjį laiką.</span><span class="sxs-lookup"><span data-stu-id="5e686-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="5e686-205">Šiame pavyzdiniame vadove mes **leidžiame modeliui apskaičiuoti pirkimo intervalą**, kuris yra numatytoji parinktis.</span><span class="sxs-lookup"><span data-stu-id="5e686-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="5e686-206">**Didelės vertės klientai**: Apibrėžkite didelės vertės klientus kaip geriausiai mokančių klientų procentilį.</span><span class="sxs-lookup"><span data-stu-id="5e686-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="5e686-207">Modelis naudoja šią įvestį, kad pateiktų rezultatus, atitinkančius jūsų verslo didelės vertės klientų apibrėžimą.</span><span class="sxs-lookup"><span data-stu-id="5e686-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="5e686-208">Galite pasirinkti, jog leidžiate modeliui apibrėžti didelės vertės klientus.</span><span class="sxs-lookup"><span data-stu-id="5e686-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="5e686-209">Jis naudoja euristinę taisyklę, iš kurios išvedamas procentilis.</span><span class="sxs-lookup"><span data-stu-id="5e686-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="5e686-210">Taip pat galite apibrėžti didelės vertės klientus kaip ateityje geriausiai mokėsiančių klientų procentilį.</span><span class="sxs-lookup"><span data-stu-id="5e686-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="5e686-211">Šiame pavyzdiniame vadove rankiniu būdu nustatome didelės vertės klientus kaip **geriausius 30 % aktyvių mokių klientų** ir pažymime **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="5e686-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Nuostatų veiksmas CLV modelio vadovo patirtyje.":::

1. <span data-ttu-id="5e686-213">Veiksme **Būtini duomenys** pasirinkite **Įtraukti duomenis**, kad pateiktumėte operacijų retrospektyvos duomenys.</span><span class="sxs-lookup"><span data-stu-id="5e686-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="5e686-214">Įtraukite **e-prekybosPirkiniai : e-prekyba** objektą ir susiekite atributus, kurių reikalauja modelis:</span><span class="sxs-lookup"><span data-stu-id="5e686-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="5e686-215">Operacijos ID: e-prekyba.e-prekybosPirkiniai.PirkinioId</span><span class="sxs-lookup"><span data-stu-id="5e686-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="5e686-216">Operacijos data: e-prekyba.e-prekybosPirkiniai.ĮjungtasPirkimas</span><span class="sxs-lookup"><span data-stu-id="5e686-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="5e686-217">Operacijos suma: e-prekyba.e-prekybosPirkiniai.BendraKaina</span><span class="sxs-lookup"><span data-stu-id="5e686-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="5e686-218">Produkto ID: e-prekyba.e-prekybosPirkiniai.ProduktoId</span><span class="sxs-lookup"><span data-stu-id="5e686-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="5e686-219">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="5e686-219">Select **Next**.</span></span>

1. <span data-ttu-id="5e686-220">Nustatykite ryšį tarp **e-prekybosPirkiniai : e-prekyba** objekto ir **e-prekybosKontaktai : e-prekyba**.</span><span class="sxs-lookup"><span data-stu-id="5e686-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="5e686-221">Veiksmas **Papildomi duomenys (pasirinktiniai)** leidžia jums įtraukti daugiau klientų veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="5e686-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="5e686-222">Šie duomenys gali padėti gauti daugiau įžvalgų apie klientų sąveiką su jūsų verslu, o tai gali prisidėti prie CLV.</span><span class="sxs-lookup"><span data-stu-id="5e686-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="5e686-223">Pagrindinių kliento sąveikų, tokių kaip žiniatinklio žurnalų, klientų aptarnavimo žurnalų arba apdovanojimų programos retrospektyvos, įtraukimas gali pagerinti prognozių tikslumą.</span><span class="sxs-lookup"><span data-stu-id="5e686-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="5e686-224">Pasirinkite **Įtraukti duomenis**, kad įtrauktumėte daugiau klientų veiklos duomenų.</span><span class="sxs-lookup"><span data-stu-id="5e686-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="5e686-225">Įtraukite kliento veiklos objektą ir susiekite jo laukų pavadinimus su atitinkamais laukais, kurių reikalauja modelis:</span><span class="sxs-lookup"><span data-stu-id="5e686-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="5e686-226">Kliento veiklos objektas: Atsiliepimai:Žiniatinklio svetainė</span><span class="sxs-lookup"><span data-stu-id="5e686-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="5e686-227">Pirminis raktas: Žiniatinklis.Apžvalgos.ApžvalgosId</span><span class="sxs-lookup"><span data-stu-id="5e686-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="5e686-228">Laiko žyma: Svetainė.Apžvalgos.ApžvalgosData</span><span class="sxs-lookup"><span data-stu-id="5e686-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="5e686-229">Įvykis (veiklos pavadinimas): Svetainė.Apžvalgos.RodomasVeiklosTipas</span><span class="sxs-lookup"><span data-stu-id="5e686-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="5e686-230">Išsami informacija (suma arba reikšmė): Svetainė.Apžvalgos.ApžvalgųĮvertinimas</span><span class="sxs-lookup"><span data-stu-id="5e686-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="5e686-231">Pasirinkite **Kitas** ir sukonfigūruokite veiklą bei ryšį tarp operacijos ir kliento duomenų:</span><span class="sxs-lookup"><span data-stu-id="5e686-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="5e686-232">Veiklos tipas: Pasirinkti esamą</span><span class="sxs-lookup"><span data-stu-id="5e686-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="5e686-233">Veiklos žyma: Apžvalga</span><span class="sxs-lookup"><span data-stu-id="5e686-233">Activity label: Review</span></span>
   - <span data-ttu-id="5e686-234">Atitinkama žyma: Žiniatinklis.Apžvalgos.VartotojoId</span><span class="sxs-lookup"><span data-stu-id="5e686-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="5e686-235">Kliento objektas: e-prekybosKontaktai:e-prekyba</span><span class="sxs-lookup"><span data-stu-id="5e686-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="5e686-236">Ryšys: ŽiniatinklioApžvalgos</span><span class="sxs-lookup"><span data-stu-id="5e686-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="5e686-237">Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.</span><span class="sxs-lookup"><span data-stu-id="5e686-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="5e686-238">Modelį reikia reguliariai mokyti, kad jis galėtų išmokti naujus modelius, įvedant naujus duomenis.</span><span class="sxs-lookup"><span data-stu-id="5e686-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="5e686-239">Šiam pavyzdžiui pasirinkite **Mėnesinis**.</span><span class="sxs-lookup"><span data-stu-id="5e686-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="5e686-240">Peržiūrėję visą išsamią informaciją, pasirinkite **Įrašyti ir vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="5e686-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="5e686-241">4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus</span><span class="sxs-lookup"><span data-stu-id="5e686-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="5e686-242">Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą.</span><span class="sxs-lookup"><span data-stu-id="5e686-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="5e686-243">Tada galėsite peržiūrėti CLV modelio rezultatus ir paaiškinimus.</span><span class="sxs-lookup"><span data-stu-id="5e686-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="5e686-244">Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="5e686-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="5e686-245">5 užduotis – Didelės vertės klientų segmento kūrimas</span><span class="sxs-lookup"><span data-stu-id="5e686-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="5e686-246">Paleidus modelį sukuriamas naujas objektas, kuris pateikiamas skiltyje **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="5e686-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="5e686-247">Galite sukurti naują klientų segmentą, pagrįstą modelio sukurtu objektu.</span><span class="sxs-lookup"><span data-stu-id="5e686-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="5e686-248">Eikite į **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="5e686-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="5e686-249">Pasirinkite **Naujas** ir **Sukurti iš** > **Įžvalgų**.</span><span class="sxs-lookup"><span data-stu-id="5e686-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Sukurkite segmentą su modelio išvestimi.](media/segment-intelligence.png)

1. <span data-ttu-id="5e686-251">Pasirinkite **„OOBeCommerceCLVPrediction”** objektą ir apibrėžkite segmentą:</span><span class="sxs-lookup"><span data-stu-id="5e686-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="5e686-252">Laukas: „CLVScore”</span><span class="sxs-lookup"><span data-stu-id="5e686-252">Field: CLVScore</span></span>
  - <span data-ttu-id="5e686-253">Operatorius: didesnis nei</span><span class="sxs-lookup"><span data-stu-id="5e686-253">Operator: greater than</span></span>
  - <span data-ttu-id="5e686-254">Vertė: 1500</span><span class="sxs-lookup"><span data-stu-id="5e686-254">Value: 1500</span></span>

1. <span data-ttu-id="5e686-255">Pasirinkite **Peržiūrėti** ir **Įrašykite** segmentą.</span><span class="sxs-lookup"><span data-stu-id="5e686-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="5e686-256">Dabar turite segmentą, nustatantį klientus, kurie, kaip prognozuojama, sugeneruos daugiau nei $1500 pajamų per artimiausius 12 mėnesių.</span><span class="sxs-lookup"><span data-stu-id="5e686-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="5e686-257">Įterpus daugiau duomenų, šis segmentas atnaujinamas dinamiškai.</span><span class="sxs-lookup"><span data-stu-id="5e686-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="5e686-258">Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5e686-258">For more information, see [Create and manage segments](segments.md).</span></span>
