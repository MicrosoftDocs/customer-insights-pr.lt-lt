---
title: „Customer Insights” duomenų eksportavimas į „Adobe Campaign Standard”
description: Sužinokite, kaip naudoti auditorijos įžvalgų segmentus „Adobe Campaign Standard”.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596325"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="44810-103">„Customer Insights” segmentų naudojimas „Adobe Campaign Standard” (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="44810-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="44810-104">Kaip „Dynamics 365 Customer Insights” auditorijos įžvalgos vartotojas galbūt sukūrėte segmentus, kad jūsų rinkodaros kampanijos būtų efektyvesnės taikydami pagal atitinkamas auditorijas.</span><span class="sxs-lookup"><span data-stu-id="44810-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="44810-105">Norėdami naudoti segmentą iš „Adobe” patirties platformos auditorijos įžvalgų ir programų, pavyzdžiui, „Adobe Campaign Standard”, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="44810-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a><span data-ttu-id="44810-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="44810-107">Prerequisites</span></span>

-   <span data-ttu-id="44810-108">„Dynamics 365 Customer Insights“ licencija</span><span class="sxs-lookup"><span data-stu-id="44810-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="44810-109">„Adobe Campaign Standard“ licencija</span><span class="sxs-lookup"><span data-stu-id="44810-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="44810-110">„Azure“ didelių dvejetainių objektų saugyklos abonementas</span><span class="sxs-lookup"><span data-stu-id="44810-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="44810-111">Kampanijos apžvalga</span><span class="sxs-lookup"><span data-stu-id="44810-111">Campaign Overview</span></span>

<span data-ttu-id="44810-112">Norėdami geriau suprasti, kaip galite naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje, pažvelkime į fiktyvią pavyzdinę kampaniją.</span><span class="sxs-lookup"><span data-stu-id="44810-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="44810-113">Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose.</span><span class="sxs-lookup"><span data-stu-id="44810-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="44810-114">Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos.</span><span class="sxs-lookup"><span data-stu-id="44810-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="44810-115">Siekdami išlaikyti šiuos klientus, norite nusiųsti jiems reklaminį pasiūlymą el. paštu naudojant „Adobe Campaign Standard”.</span><span class="sxs-lookup"><span data-stu-id="44810-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="44810-116">Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="44810-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="44810-117">Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="44810-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="44810-118">Tačiau auditorijos įžvalgas ir „Adobe Campaign Standard” galima sukonfigūruoti taip, kad veiktų ir pasikartojančios kampanijos scenarijuje.</span><span class="sxs-lookup"><span data-stu-id="44810-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="44810-119">Atpažinkite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="44810-119">Identify your target audience</span></span>

<span data-ttu-id="44810-120">Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.</span><span class="sxs-lookup"><span data-stu-id="44810-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="44810-121">[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.</span><span class="sxs-lookup"><span data-stu-id="44810-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

<span data-ttu-id="44810-123">Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data.</span><span class="sxs-lookup"><span data-stu-id="44810-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="44810-124">Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.</span><span class="sxs-lookup"><span data-stu-id="44810-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="44810-125">Eksportuokite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="44810-125">Export your target audience</span></span>

<span data-ttu-id="44810-126">Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.</span><span class="sxs-lookup"><span data-stu-id="44810-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="44810-127">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="44810-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="44810-128">Plytelėje **„Adobe” kampanija** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="44810-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigūracijos plytelė, skirta Adobe Campaign Standard.":::

1. <span data-ttu-id="44810-130">Pateikite šios naujos eksportavimo vietos **Rodomą pavadinimą** ir tada įveskite **Abonemento pavadinimą**, **Abonemento raktą** ir **Talpyklę**„Azure“ didelių dvejetainių objektų saugyklai, į kurią norite eksportuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="44810-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija."::: 

   - <span data-ttu-id="44810-132">Jei norite sužinoti daugiau apie tai, kaip rasti „Azure“ didelių dvejetainių objektų saugyklos kliento pavadinimą ir kliento raktą, žr. [Saugyklos kliento parametrų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="44810-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="44810-133">Norėdami sužinoti, kaip sukurti konteinerį, žr. [Konteinerio kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="44810-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="44810-134">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="44810-134">Select **Next**.</span></span>

1. <span data-ttu-id="44810-135">Pasirinkite segmentą, kurį norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="44810-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="44810-136">Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.</span><span class="sxs-lookup"><span data-stu-id="44810-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. <span data-ttu-id="44810-138">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="44810-138">Select **Next**.</span></span>

1. <span data-ttu-id="44810-139">Dabar mes susiejame **Šaltinio** laukus iš auditorijos įžvalgų segmento su **Paskirties** laukų pavadinimais „Adobe Campaign Standard” profilio schemoje.</span><span class="sxs-lookup"><span data-stu-id="44810-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Laukų susiejimas, skirtas Adobe Campaign Standard jungčiai.":::

   <span data-ttu-id="44810-141">Jeigu norite įtraukti daugiau atributų, pasirinkite **Įtraukti atributą**.</span><span class="sxs-lookup"><span data-stu-id="44810-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="44810-142">Paskirties pavadinimas gali skirtis nuo šaltinio lauko pavadinimo, todėl vis tiek galite susieti segmento išvestį iš auditorijos įžvalgų į „Adobe Campaign Standard”, jei laukų pavadinimai dvejuose sistemose nėra tokie patys.</span><span class="sxs-lookup"><span data-stu-id="44810-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="44810-143">El. pašto adresas naudojamas kaip tapatybės laukas, tačiau galite naudoti bet kurį kitą identifikatorių iš jūsų auditorijos įžvalgų kliento profilio, kad susietumėte duomenis su „Adobe Campaign Standard”.</span><span class="sxs-lookup"><span data-stu-id="44810-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="44810-144">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="44810-144">Select **Save**.</span></span>

<span data-ttu-id="44810-145">Įrašę eksportavimo paskirties vietą, ją rasite **Administravimas** > **Eksportavimai** > **Mano eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="44810-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Ekrano kopija su eksportavimų sąrašu ir paryškintu pavyzdžio segmentu.":::

<span data-ttu-id="44810-147">Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="44810-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="44810-148">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).</span><span class="sxs-lookup"><span data-stu-id="44810-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="44810-149">Įsitikinkite, kad eksportuoto segmento įrašų skaičius neviršija leistinos „Adobe Campaign Standard” licencijos ribos.</span><span class="sxs-lookup"><span data-stu-id="44810-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="44810-150">Eksportuoti duomenys saugomi „Azure“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau.</span><span class="sxs-lookup"><span data-stu-id="44810-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="44810-151">Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:</span><span class="sxs-lookup"><span data-stu-id="44810-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="44810-152">„*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*”</span><span class="sxs-lookup"><span data-stu-id="44810-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="44810-153">Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="44810-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="44810-154">„Adobe Campaign Standard“ konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="44810-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="44810-155">Kai eksportuojamas segmentas iš auditorijos įžvalgų, jame yra stulpeliai, kuriuos pasirinkote nustatydami eksportavimo paskirties vietą ankstesniame veiksme.</span><span class="sxs-lookup"><span data-stu-id="44810-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="44810-156">Šiuos duomenis galima naudoti [kuriant profilius „Adobe Campaign Standard” platformoje](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="44810-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="44810-157">Norėdami naudoti segmentą „Adobe Campaign Standard” platformoje, turime išplėsti profilio schemą „Adobe Campaign Standard”, kad įtrauktume du papildomus laukus.</span><span class="sxs-lookup"><span data-stu-id="44810-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="44810-158">Sužinokite, kaip [išplėsti profilio išteklius](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) su naujais „Adobe Campaign Standard” laukais.</span><span class="sxs-lookup"><span data-stu-id="44810-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="44810-159">Mūsų pavyzdyje šie laukai yra *Segmento pavadinimas ir Segmento data (pasirenkama).*</span><span class="sxs-lookup"><span data-stu-id="44810-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="44810-160">Šiuos laukus naudosime atpažinti „Adobe Campaign Standard” profiliams, kuriems norime taikyti šią kampaniją.</span><span class="sxs-lookup"><span data-stu-id="44810-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="44810-161">Jei „Adobe Campaign Standard” nėra kitų įrašų, išskyrus tuos, kuriuos ketinate importuoti, galite praleisti šį veiksmą.</span><span class="sxs-lookup"><span data-stu-id="44810-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="44810-162">Duomenų importavimas į „Adobe Campaign Standard”</span><span class="sxs-lookup"><span data-stu-id="44810-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="44810-163">Dabar, kai viskas tvarkoje, turime importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į „Adobe Campaign Standard” profilių kūrimui.</span><span class="sxs-lookup"><span data-stu-id="44810-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="44810-164">Sužinokite, [kaip importuoti „Adobe Campaign Standard” profilius](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) naudojant darbo eigą.</span><span class="sxs-lookup"><span data-stu-id="44810-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="44810-165">Toliau pateiktame paveikslėlyje pavaizduota darbo eiga buvo sukonfigūruota veikti kas 8 valandas ir ieško eksportuotų auditorijos įžvalgų segmentų (.csv failo „Azure“ didelių dvejetainių objektų saugykloje).</span><span class="sxs-lookup"><span data-stu-id="44810-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="44810-166">Darbo eiga išskleidžia .csv failo turinį nustatyta stulpelių tvarka.</span><span class="sxs-lookup"><span data-stu-id="44810-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="44810-167">Ši darbo eiga buvo sukurta atlikti pagrindiniam klaidų tvarkymui ir užtikrinti, kad kiekvienas įrašas turi el. pašto adresą, prieš drėkinant „Adobe Campaign Standard” duomenis.</span><span class="sxs-lookup"><span data-stu-id="44810-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="44810-168">Darbo eiga taip pat išskleidžia segmento pavadinimą iš failo vardo, prieš naujinant arba įterpiant į ACS profilio duomenis.</span><span class="sxs-lookup"><span data-stu-id="44810-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importavimo darbo eigos Adobe Campaign Standard vartotojo sąsajoje ekrano kopija.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="44810-170">Auditorijos nuskaitymas „Adobe Campaign Standard” platformoje</span><span class="sxs-lookup"><span data-stu-id="44810-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="44810-171">Kai duomenys bus importuoti į Adobe „Campaign Standard”, jūs [galėsite sukurti darbo eigą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ir [pateikti užklausą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientams pagal *Segmento pavadinimą* ir *Segmento datą* pasirinkti profiliams, kurie buvo identifikuoti mūsų pavyzdinėje kampanijoje.</span><span class="sxs-lookup"><span data-stu-id="44810-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="44810-172">El. laiško sukūrimas ir siuntimas naudojant „Adobe Campaign Standard”</span><span class="sxs-lookup"><span data-stu-id="44810-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="44810-173">Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.</span><span class="sxs-lookup"><span data-stu-id="44810-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Pavyzdinis el. laiškas su atnaujinimo pasiūlymu iš Adobe Campaign Standard.":::