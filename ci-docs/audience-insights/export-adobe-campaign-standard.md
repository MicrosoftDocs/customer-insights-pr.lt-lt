---
title: „Customer Insights” duomenų eksportavimas į „Adobe Campaign Standard”
description: Sužinokite, kaip naudoti auditorijos įžvalgų segmentus „Adobe Campaign Standard”.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305396"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="5a144-103">„Customer Insights” segmentų naudojimas „Adobe Campaign Standard” (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="5a144-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="5a144-104">Kaip auditorijos įžvalgų vartotojas, galbūt sukūrėte segmentų, kad rinkodaros kampanijos būtų efektyvesnės „Dynamics 365 Customer Insights“ atsižvelgiant į atitinkamas auditorijas.</span><span class="sxs-lookup"><span data-stu-id="5a144-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="5a144-105">Norėdami naudoti segmentą iš „Adobe” patirties platformos auditorijos įžvalgų ir programų, pavyzdžiui, „Adobe Campaign Standard”, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="5a144-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a><span data-ttu-id="5a144-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="5a144-107">Prerequisites</span></span>

-   <span data-ttu-id="5a144-108">„Dynamics 365 Customer Insights“ licencija</span><span class="sxs-lookup"><span data-stu-id="5a144-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="5a144-109">„Adobe Campaign Standard“ licencija</span><span class="sxs-lookup"><span data-stu-id="5a144-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="5a144-110">„Azure“ didelių dvejetainių objektų saugyklos abonementas</span><span class="sxs-lookup"><span data-stu-id="5a144-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="5a144-111">Kampanijos apžvalga</span><span class="sxs-lookup"><span data-stu-id="5a144-111">Campaign overview</span></span>

<span data-ttu-id="5a144-112">Norėdami geriau suprasti, kaip galite naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje, pažvelkime į fiktyvią pavyzdinę kampaniją.</span><span class="sxs-lookup"><span data-stu-id="5a144-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="5a144-113">Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose.</span><span class="sxs-lookup"><span data-stu-id="5a144-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="5a144-114">Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos.</span><span class="sxs-lookup"><span data-stu-id="5a144-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="5a144-115">Siekdami išlaikyti šiuos klientus, norite nusiųsti jiems reklaminį pasiūlymą el. paštu naudojant „Adobe Campaign Standard”.</span><span class="sxs-lookup"><span data-stu-id="5a144-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="5a144-116">Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="5a144-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="5a144-117">Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="5a144-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="5a144-118">Tačiau auditorijos įžvalgas ir „Adobe Campaign Standard” galima sukonfigūruoti taip, kad veiktų ir pasikartojančios kampanijos scenarijuje.</span><span class="sxs-lookup"><span data-stu-id="5a144-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="5a144-119">Atpažinkite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="5a144-119">Identify your target audience</span></span>

<span data-ttu-id="5a144-120">Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.</span><span class="sxs-lookup"><span data-stu-id="5a144-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="5a144-121">[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.</span><span class="sxs-lookup"><span data-stu-id="5a144-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

<span data-ttu-id="5a144-123">Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data.</span><span class="sxs-lookup"><span data-stu-id="5a144-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="5a144-124">Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.</span><span class="sxs-lookup"><span data-stu-id="5a144-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="5a144-125">Eksportuokite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="5a144-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="5a144-126">Ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5a144-126">Configure a connection</span></span>

<span data-ttu-id="5a144-127">Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.</span><span class="sxs-lookup"><span data-stu-id="5a144-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="5a144-128">Auditorijos įžvalgose eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="5a144-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5a144-129">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Adobe Campaign“**, jei norite konfigūruoti ryšį arba pasirinkite **Sąranka** plytelėje **„Adobe Campaign“**</span><span class="sxs-lookup"><span data-stu-id="5a144-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigūracijos plytelė, skirta Adobe Campaign Standard.":::

1. <span data-ttu-id="5a144-131">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="5a144-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5a144-132">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a144-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5a144-133">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="5a144-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5a144-134">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a144-134">Choose who can use this connection.</span></span> <span data-ttu-id="5a144-135">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="5a144-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5a144-136">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5a144-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5a144-137">Įveskite **Paskyros pavadinimas**, **Paskyros raktas** ir **Talpykla** paskyroje „Azure Blob Storage“, į kurią norite eksportuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="5a144-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija."::: 

   - <span data-ttu-id="5a144-139">Jei norite sužinoti daugiau apie tai, kaip rasti „Azure Blob Storage“ didelių dvejetainių objektų saugyklos kliento pavadinimą ir kliento raktą, žr. [Saugyklos kliento parametrų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="5a144-139">To learn more about how to find the Azure Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="5a144-140">Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="5a144-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="5a144-141">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="5a144-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="5a144-142">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5a144-142">Configure an export</span></span>

<span data-ttu-id="5a144-143">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="5a144-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5a144-144">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5a144-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5a144-145">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="5a144-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5a144-146">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.</span><span class="sxs-lookup"><span data-stu-id="5a144-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="5a144-147">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Adobe Campaign“.</span><span class="sxs-lookup"><span data-stu-id="5a144-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="5a144-148">Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="5a144-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="5a144-149">Pasirinkite segmentą, kurį norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="5a144-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="5a144-150">Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.</span><span class="sxs-lookup"><span data-stu-id="5a144-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. <span data-ttu-id="5a144-152">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="5a144-152">Select **Next**.</span></span>

1. <span data-ttu-id="5a144-153">Dabar mes susiejame **Šaltinio** laukus iš auditorijos įžvalgų segmento su **Paskirties** laukų pavadinimais „Adobe Campaign Standard” profilio schemoje.</span><span class="sxs-lookup"><span data-stu-id="5a144-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Laukų susiejimas, skirtas Adobe Campaign Standard jungčiai.":::

   <span data-ttu-id="5a144-155">Jeigu norite įtraukti daugiau atributų, pasirinkite **Įtraukti atributą**.</span><span class="sxs-lookup"><span data-stu-id="5a144-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="5a144-156">Paskirties pavadinimas gali skirtis nuo šaltinio lauko pavadinimo, todėl vis tiek galite susieti segmento išvestį iš auditorijos įžvalgų į „Adobe Campaign Standard”, jei laukų pavadinimai dvejuose sistemose nėra tokie patys.</span><span class="sxs-lookup"><span data-stu-id="5a144-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5a144-157">El. pašto adresas naudojamas kaip tapatybės laukas, tačiau galite naudoti bet kurį kitą identifikatorių iš jūsų auditorijos įžvalgų kliento profilio, kad susietumėte duomenis su „Adobe Campaign Standard”.</span><span class="sxs-lookup"><span data-stu-id="5a144-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="5a144-158">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="5a144-158">Select **Save**.</span></span>

<span data-ttu-id="5a144-159">Išsaugoję eksportavimo paskirties vietą ją rasite pasirinkę **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="5a144-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="5a144-160">Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5a144-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="5a144-161">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).</span><span class="sxs-lookup"><span data-stu-id="5a144-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5a144-162">Įsitikinkite, kad eksportuoto segmento įrašų skaičius neviršija leistinos „Adobe Campaign Standard” licencijos ribos.</span><span class="sxs-lookup"><span data-stu-id="5a144-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="5a144-163">Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau.</span><span class="sxs-lookup"><span data-stu-id="5a144-163">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="5a144-164">Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:</span><span class="sxs-lookup"><span data-stu-id="5a144-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="5a144-165">„*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*”</span><span class="sxs-lookup"><span data-stu-id="5a144-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="5a144-166">Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="5a144-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="5a144-167">„Adobe Campaign Standard“ konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="5a144-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="5a144-168">Kai eksportuojamas segmentas iš auditorijos įžvalgų, jame yra stulpeliai, kuriuos pasirinkote nustatydami eksportavimo paskirties vietą ankstesniame veiksme.</span><span class="sxs-lookup"><span data-stu-id="5a144-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="5a144-169">Šiuos duomenis galima naudoti [kuriant profilius „Adobe Campaign Standard” platformoje](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="5a144-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="5a144-170">Norėdami naudoti segmentą „Adobe Campaign Standard” platformoje, turime išplėsti profilio schemą „Adobe Campaign Standard”, kad įtrauktume du papildomus laukus.</span><span class="sxs-lookup"><span data-stu-id="5a144-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="5a144-171">Sužinokite, kaip [išplėsti profilio išteklius](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) su naujais „Adobe Campaign Standard” laukais.</span><span class="sxs-lookup"><span data-stu-id="5a144-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="5a144-172">Mūsų pavyzdyje šie laukai yra *Segmento pavadinimas ir Segmento data (pasirenkama)*.</span><span class="sxs-lookup"><span data-stu-id="5a144-172">In our example, these fields are *Segment Name and Segment Date (optional)*.</span></span>

<span data-ttu-id="5a144-173">Šiuos laukus naudosime atpažinti „Adobe Campaign Standard” profiliams, kuriems norime taikyti šią kampaniją.</span><span class="sxs-lookup"><span data-stu-id="5a144-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="5a144-174">Jei „Adobe Campaign Standard” nėra kitų įrašų, išskyrus tuos, kuriuos ketinate importuoti, galite praleisti šį veiksmą.</span><span class="sxs-lookup"><span data-stu-id="5a144-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="5a144-175">Duomenų importavimas į „Adobe Campaign Standard”</span><span class="sxs-lookup"><span data-stu-id="5a144-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="5a144-176">Dabar, kai viskas tvarkoje, turime importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į „Adobe Campaign Standard” profilių kūrimui.</span><span class="sxs-lookup"><span data-stu-id="5a144-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="5a144-177">Sužinokite, [kaip importuoti „Adobe Campaign Standard” profilius](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) naudojant darbo eigą.</span><span class="sxs-lookup"><span data-stu-id="5a144-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="5a144-178">Toliau pateiktame paveikslėlyje importavimo darbo eiga sukonfigūruota taip, kad ji būtų vykdoma kas aštuonias valandas ir ieškoma eksportuotų auditorijos įžvalgų segmentų (.csv failo „Azure Blob Storage").</span><span class="sxs-lookup"><span data-stu-id="5a144-178">The import workflow in the image below has been configured to run every eight hours and look for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="5a144-179">Darbo eiga išskleidžia .csv failo turinį nustatyta stulpelių tvarka.</span><span class="sxs-lookup"><span data-stu-id="5a144-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="5a144-180">Ši darbo eiga buvo sukurta atlikti pagrindiniam klaidų tvarkymui ir užtikrinti, kad kiekvienas įrašas turi el. pašto adresą, prieš drėkinant „Adobe Campaign Standard” duomenis.</span><span class="sxs-lookup"><span data-stu-id="5a144-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="5a144-181">Darbo eiga taip pat iš failo pavadinimo išskleisti segmento pavadinimą prieš ją perrašant į „Adobe Campaign Standard" profilio duomenis.</span><span class="sxs-lookup"><span data-stu-id="5a144-181">The workflow also extracts the segment name from the filename before upserting into Adobe Campaign Standard profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importavimo darbo eigos Adobe Campaign Standard vartotojo sąsajoje ekrano kopija.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="5a144-183">Auditorijos nuskaitymas „Adobe Campaign Standard” platformoje</span><span class="sxs-lookup"><span data-stu-id="5a144-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="5a144-184">Kai duomenys bus importuoti į Adobe „Campaign Standard”, jūs [galėsite sukurti darbo eigą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ir [pateikti užklausą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientams pagal *Segmento pavadinimą* ir *Segmento datą* pasirinkti profiliams, kurie buvo identifikuoti mūsų pavyzdinėje kampanijoje.</span><span class="sxs-lookup"><span data-stu-id="5a144-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="5a144-185">El. laiško sukūrimas ir siuntimas naudojant „Adobe Campaign Standard”</span><span class="sxs-lookup"><span data-stu-id="5a144-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="5a144-186">Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.</span><span class="sxs-lookup"><span data-stu-id="5a144-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Pavyzdinis el. laiškas su atnaujinimo pasiūlymu iš Adobe Campaign Standard.":::
