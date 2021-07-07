---
title: Perlaidos nutraukimo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad pabandytumėte nestandartinį perlaidos nutraukimo prognozės modelį.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306130"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="cf8a2-103">Perlaidos nutraukimo prognozės (peržiūra) pavyzdžio vedlys</span><span class="sxs-lookup"><span data-stu-id="cf8a2-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="cf8a2-104">Šis vedlys jus supažindins nuo pradžios iki galo su perlaidos nutraukimo prognozės pavyzdžiu tinkintose „Customer Insights“ naudojant toliau pateiktus duomenis.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="cf8a2-105">Visi šiame gide naudojami duomenys nėra realūs klientų duomenys, o dalis „Contoso“ duomenų rinkinio esančio *Demo* aplinkoje Jūsų „Customer Insights“ prenumeratoje.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="cf8a2-106">Scenarijus</span><span class="sxs-lookup"><span data-stu-id="cf8a2-106">Scenario</span></span>

<span data-ttu-id="cf8a2-107">„Contoso” yra įmonė, kurianti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda savo „Contoso Coffee” svetainėje.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="cf8a2-108">Jų tikslas yra sužinoti, kurie klientai dažniausiai įsigiję produktus reguliariai ir nustos būti aktyviais klientais per artimiausias 60 dienų.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="cf8a2-109">Žinojimas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cf8a2-110">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="cf8a2-110">Prerequisites</span></span>

- <span data-ttu-id="cf8a2-111">Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="cf8a2-112">Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="cf8a2-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="cf8a2-113">Užduotis 1 - Duomenų vartojimas</span><span class="sxs-lookup"><span data-stu-id="cf8a2-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="cf8a2-114">Peržiūrėti straipsnius [apie duomenų vartojimą](data-sources.md) ir [importuoti duomenų šaltinius naudojant „Power Query“ jungtis](connect-power-query.md) konkrečiai.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="cf8a2-115">Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="cf8a2-116">Kliento duomenų naudojimas iš e-komercijos platformos</span><span class="sxs-lookup"><span data-stu-id="cf8a2-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="cf8a2-117">Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cf8a2-118">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="cf8a2-119">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf8a2-120">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="cf8a2-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cf8a2-121">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="cf8a2-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="cf8a2-122">**Sukurta**: Data/Laikas/Zona</span><span class="sxs-lookup"><span data-stu-id="cf8a2-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="cf8a2-123">![Keisti gimimo dieną į datą](media/ecommerce-dob-date.PNG "transformuoti gimimo datą į datą")</span><span class="sxs-lookup"><span data-stu-id="cf8a2-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="cf8a2-124">Lauke **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**</span><span class="sxs-lookup"><span data-stu-id="cf8a2-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="cf8a2-125">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="cf8a2-126">Vartokite internete įsigytus duomenis</span><span class="sxs-lookup"><span data-stu-id="cf8a2-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="cf8a2-127">Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="cf8a2-128">Pasirinkite **Tekstas/CSV** jungtis dar kartą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="cf8a2-129">Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="cf8a2-130">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf8a2-131">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="cf8a2-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cf8a2-132">**Įsigyta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="cf8a2-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="cf8a2-133">**Bendra kaina**: Valiuta</span><span class="sxs-lookup"><span data-stu-id="cf8a2-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="cf8a2-134">Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="cf8a2-135">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="cf8a2-136">Kliento duomenų naudojimas iš lojalumo schemos</span><span class="sxs-lookup"><span data-stu-id="cf8a2-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="cf8a2-137">Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="cf8a2-138">Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="cf8a2-139">Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="cf8a2-140">Naujinti duomenų tipą toliau išvardytiems stulpeliams:</span><span class="sxs-lookup"><span data-stu-id="cf8a2-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="cf8a2-141">**Gimimo data**: Data</span><span class="sxs-lookup"><span data-stu-id="cf8a2-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="cf8a2-142">**Uždirbtitaškai**: Visas skaičius</span><span class="sxs-lookup"><span data-stu-id="cf8a2-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="cf8a2-143">**Sukurta**: Data/Laikas</span><span class="sxs-lookup"><span data-stu-id="cf8a2-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="cf8a2-144">Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="cf8a2-145">Įrašykite duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="cf8a2-146">Užduotis 2 - Duomenų suvienodinimas</span><span class="sxs-lookup"><span data-stu-id="cf8a2-146">Task 2 - Data unification</span></span>

<span data-ttu-id="cf8a2-147">Po duomenų suvartojimo dabar pradėsime **Žemėlapis, Atitiktis, Sulieti** procesą siekiant sukurti suvienodintą kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="cf8a2-148">Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="cf8a2-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="cf8a2-149">Schema</span><span class="sxs-lookup"><span data-stu-id="cf8a2-149">Map</span></span>

1. <span data-ttu-id="cf8a2-150">Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="cf8a2-151">Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="cf8a2-152">Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="Suvienodinti e-komercijos ir lojalumo duomenų šaltinius.":::

1. <span data-ttu-id="cf8a2-154">Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Suvienodinti lojalumo ID kaip pagrindinį raktą.":::

### <a name="match"></a><span data-ttu-id="cf8a2-156">Sugretinti</span><span class="sxs-lookup"><span data-stu-id="cf8a2-156">Match</span></span>

1. <span data-ttu-id="cf8a2-157">Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="cf8a2-158">Pirminiame **išplečiamajame** sąraše pasirinkite **eCommerceContacts: el. prekyba** pirminis šaltinis ir įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="cf8a2-159">Išplečiamajame sąraše **Objektas 2** pasirinkite **loyCustomers: LoyaltyScheme** įtraukite visus įrašus.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Suvienodinti e-komercijos atitiktį ir lojalumą.":::

1. <span data-ttu-id="cf8a2-161">Pasirinkite **Sukurkite naują taisyklę**</span><span class="sxs-lookup"><span data-stu-id="cf8a2-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="cf8a2-162">Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="cf8a2-163">El. prekyboscontacts išplečiamajame sąraše pažymėkite **Visas vardas**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="cf8a2-164">loyCustomers išplečiamajame sąraše pažymėkite **Visas vardas**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="cf8a2-165">Pasirinkite **Normalizuoti** iškrentantį meniu ir pasirinkite **Tipas (Telefonas, Pavadinimas, Adresas, ...)**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="cf8a2-166">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="cf8a2-167">Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="cf8a2-168">Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**</span><span class="sxs-lookup"><span data-stu-id="cf8a2-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="cf8a2-169">Objekto "eCommerceContacts" **išplečiamajame sąraše** pasirinkite "El. paštas".</span><span class="sxs-lookup"><span data-stu-id="cf8a2-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="cf8a2-170">Objekto loyCustomers **išplečiamajame sąraše** pasirinkite "El. paštas".</span><span class="sxs-lookup"><span data-stu-id="cf8a2-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="cf8a2-171">Palikite normalizavimą tuščią.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="cf8a2-172">Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Suvienodinti atitikties taisyklę pavadinimui ir el. paštui.":::

7. <span data-ttu-id="cf8a2-174">Pasirinkite **Įrašyti** ir **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="cf8a2-175">Sulieti</span><span class="sxs-lookup"><span data-stu-id="cf8a2-175">Merge</span></span>

1. <span data-ttu-id="cf8a2-176">Eikite į **Sulieti** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="cf8a2-177">**Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="pervardykite kontakto ID iš lojalumo ID.":::

1. <span data-ttu-id="cf8a2-179">Pasirinkite **Įrašyti** ir **Vykdyti** tam, kad pradėtumėte suliejimo procesą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="cf8a2-180">Užduotis 3 - Konfigūruoti perlaidos nutraukimo prognozę</span><span class="sxs-lookup"><span data-stu-id="cf8a2-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="cf8a2-181">Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="cf8a2-182">Išsamiems žingsniams, žr. [Prenumeravimo nutraukimo prognozė (peržiūra)](predict-subscription-churn.md) straipsnį.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="cf8a2-183">Eikite į **Įžvalga** > **Atrasti** ir pasirinkite norėdami naudoti **Kliento nutraukimo modelį**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="cf8a2-184">Pasirinkite **Perlaidos** parinktį ir rinkitės **Pradėti**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="cf8a2-185">Įvardykite modelį **OOB e-komercijos perlaidos nutraukimo prognozė** ir išvesties objektą **„OOBeCommerceChurnPrediction“**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="cf8a2-186">Nustatykite dvi sąlygas nutraukimo modeliui:</span><span class="sxs-lookup"><span data-stu-id="cf8a2-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="cf8a2-187">**Prognozės langas**: **mažiausiai 60** dienų.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="cf8a2-188">Šis nustatymas nustato, kaip toli į ateitį norime prognozuoti kliento nutraukimą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="cf8a2-189">**Nutraukimo sąvoka**: **mažiausiai 60** dienų.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="cf8a2-190">Trukmė be įsigijimo, po kurio klientas laikomas nutraukusiu paslaugas.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Pasirinkite modelio išlyginimo prognozės langą ir nutraukimo sąvoką.":::

1. <span data-ttu-id="cf8a2-192">Pasirinkite **Pirkimo retrospektyva (būtina)** ir pasirinkite **Įtraukti duomenis** pirkimo retrospektyvai.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="cf8a2-193">Įtraukite **e-komercijos įsigijimai : e-komerciją** objektą ir nustatykite laukelių žemėlapį iš e-komercijos į atitinkamus laukelius būtinus modeliui.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="cf8a2-194">Prisijunkite prie **e-komercijos įsigijimų : e-komercijos** objekto su **e-komercijos kontaktais : e-komercija**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Prijunkite e-komercijos objektus.":::

1. <span data-ttu-id="cf8a2-196">Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="cf8a2-197">Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="cf8a2-198">Šiam pavyzdžiui, rinkitės **Kas mėnesį**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="cf8a2-199">Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="cf8a2-200">4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus</span><span class="sxs-lookup"><span data-stu-id="cf8a2-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="cf8a2-201">Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="cf8a2-202">Galite dabar peržiūrėti prenumeravimo atsisakymo modelio paaiškinimus.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="cf8a2-203">Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="cf8a2-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="cf8a2-204">Užduotis 5 - Sukurti didelės atsisakymo rizikos klientų segmentą</span><span class="sxs-lookup"><span data-stu-id="cf8a2-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="cf8a2-205">Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="cf8a2-206">Galite sukurti naują segmentą pagal modelio sukurtą objektą.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="cf8a2-207">Eikite į **Segmentai**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-207">Go to **Segments**.</span></span> <span data-ttu-id="cf8a2-208">Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Sukurkite segmentą su modelio išvestimi.":::

1. <span data-ttu-id="cf8a2-210">Pasirinkite **„OOBSubscriptionChurnPrediction“** galutinį tašką ir nustatykite segmentą:</span><span class="sxs-lookup"><span data-stu-id="cf8a2-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="cf8a2-211">Laukelis: Nutraukimo balas</span><span class="sxs-lookup"><span data-stu-id="cf8a2-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="cf8a2-212">Operatorius: didesnis nei</span><span class="sxs-lookup"><span data-stu-id="cf8a2-212">Operator: greater than</span></span>
   - <span data-ttu-id="cf8a2-213">Vertė: 0,6</span><span class="sxs-lookup"><span data-stu-id="cf8a2-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nustatykite prenumeravimo atsisakymo segmentą.":::

<span data-ttu-id="cf8a2-215">Dabar turite segmentą, kuris dinamiškai naujinamas ir nustato didelės rizikos klientų atsisakymą šiam prenumeratos verslui.</span><span class="sxs-lookup"><span data-stu-id="cf8a2-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="cf8a2-216">Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cf8a2-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]