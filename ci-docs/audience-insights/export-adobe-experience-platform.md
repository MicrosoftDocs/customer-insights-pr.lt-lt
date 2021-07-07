---
title: „Customer Insights” duomenų eksportavimas į „Adobe” patirties platformą
description: Sužinokite, kaip naudoti auditorijų įžvalgų segmentus „Adobe Experience Platform".
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305534"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="bcb98-103">„Customer Insights” segmentų naudojimas „Adobe” patirties platformoje (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="bcb98-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="bcb98-104">Kaip auditorijos įžvalgų vartotojas, galbūt sukūrėte segmentų, kad rinkodaros kampanijos būtų efektyvesnės „Dynamics 365 Customer Insights“ atsižvelgiant į atitinkamas auditorijas.</span><span class="sxs-lookup"><span data-stu-id="bcb98-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="bcb98-105">Norėdami naudoti segmentą iš „Adobe” patirties platformos auditorijos įžvalgų ir programų, pavyzdžiui, „Adobe Campaign Standard”, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="bcb98-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a><span data-ttu-id="bcb98-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="bcb98-107">Prerequisites</span></span>

-   <span data-ttu-id="bcb98-108">„Dynamics 365 Customer Insights“ licencija</span><span class="sxs-lookup"><span data-stu-id="bcb98-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="bcb98-109">„Adobe” patirties platformos licencija</span><span class="sxs-lookup"><span data-stu-id="bcb98-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="bcb98-110">„Adobe Campaign Standard“ licencija</span><span class="sxs-lookup"><span data-stu-id="bcb98-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="bcb98-111">„Azure“ didelių dvejetainių objektų saugyklos abonementas</span><span class="sxs-lookup"><span data-stu-id="bcb98-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="bcb98-112">Kampanijos apžvalga</span><span class="sxs-lookup"><span data-stu-id="bcb98-112">Campaign Overview</span></span>

<span data-ttu-id="bcb98-113">Norėdami geriau suprasti, kaip galite naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje, pažvelkime į fiktyvią pavyzdinę kampaniją.</span><span class="sxs-lookup"><span data-stu-id="bcb98-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="bcb98-114">Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose.</span><span class="sxs-lookup"><span data-stu-id="bcb98-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="bcb98-115">Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos.</span><span class="sxs-lookup"><span data-stu-id="bcb98-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="bcb98-116">Siekdami išlaikyti šiuos klientus, norite nusiųsti jiems reklaminį pasiūlymą el. paštu naudojant „Adobe” patirties platformą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="bcb98-117">Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="bcb98-118">Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="bcb98-119">Atpažinkite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="bcb98-119">Identify your target audience</span></span>

<span data-ttu-id="bcb98-120">Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.</span><span class="sxs-lookup"><span data-stu-id="bcb98-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="bcb98-121">[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

<span data-ttu-id="bcb98-123">Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data.</span><span class="sxs-lookup"><span data-stu-id="bcb98-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="bcb98-124">Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.</span><span class="sxs-lookup"><span data-stu-id="bcb98-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="bcb98-125">Eksportuokite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="bcb98-125">Export your target audience</span></span>

<span data-ttu-id="bcb98-126">Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="bcb98-127">Ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="bcb98-127">Configure a connection</span></span>

1. <span data-ttu-id="bcb98-128">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bcb98-129">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure Blob Storage“**, jei norite konfigūruoti ryšį arba pasirinkite **Nustatyti** plytelėje **„Azure Blob Storage“**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigūracijos plytelė, skirta „Azure“ didelių dvejetainių objektų saugyklai."::: 

1. <span data-ttu-id="bcb98-131">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bcb98-132">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="bcb98-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bcb98-133">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="bcb98-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bcb98-134">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="bcb98-134">Choose who can use this connection.</span></span> <span data-ttu-id="bcb98-135">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="bcb98-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bcb98-136">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bcb98-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bcb98-137">Įveskite **Paskyros pavadinimas**, **Paskyros raktas** ir **Talpykla** savo „Blob Storage“ laikymo paskyroje, į kurią norite eksportuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija."::: 
   
    - <span data-ttu-id="bcb98-139">Jei norite sužinoti daugiau apie didelių dvejetainių objektų „Storage“ paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bcb98-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="bcb98-140">Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="bcb98-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="bcb98-141">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="bcb98-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="bcb98-142">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="bcb98-142">Configure an export</span></span>

<span data-ttu-id="bcb98-143">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="bcb98-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bcb98-144">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bcb98-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bcb98-145">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bcb98-146">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="bcb98-147">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla.</span><span class="sxs-lookup"><span data-stu-id="bcb98-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="bcb98-148">Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="bcb98-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="bcb98-149">Pasirinkite segmentą, kurį norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="bcb98-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="bcb98-150">Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. <span data-ttu-id="bcb98-152">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-152">Select **Save**.</span></span>

<span data-ttu-id="bcb98-153">Išsaugoję eksportavimo paskirties vietą ją rasite pasirinkę **Duomenys** > **Eksportavimai**.</span><span class="sxs-lookup"><span data-stu-id="bcb98-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="bcb98-154">Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bcb98-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="bcb98-155">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).</span><span class="sxs-lookup"><span data-stu-id="bcb98-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bcb98-156">Įsitikinkite, kad eksportuoto segmento įrašų skaičius neviršija leistinos „Adobe Campaign Standard” licencijos ribos.</span><span class="sxs-lookup"><span data-stu-id="bcb98-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="bcb98-157">Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau.</span><span class="sxs-lookup"><span data-stu-id="bcb98-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="bcb98-158">Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:</span><span class="sxs-lookup"><span data-stu-id="bcb98-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="bcb98-159">„*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*”</span><span class="sxs-lookup"><span data-stu-id="bcb98-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="bcb98-160">Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="bcb98-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="bcb98-161">Eksportuotų objektų *„model.json”* išlieka *„%ExportDestinationName%”* lygiu.</span><span class="sxs-lookup"><span data-stu-id="bcb98-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="bcb98-162">Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="bcb98-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="bcb98-163">Patirties duomenų modelio (XDM) apibrėžimas „Adobe” patirties platformoje</span><span class="sxs-lookup"><span data-stu-id="bcb98-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="bcb98-164">Prieš naudojant iš auditorijos įžvalgų eksportuotus duomenis „Adobe” patirties platformoje, turime apibrėžti patirties duomenų modelio schemą ir [konfigūruoti kliento profilio duomenis realiuoju laiku](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="bcb98-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="bcb98-165">Sužinokite, [kas yra XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ir supraskite [schemos struktūros pagrindus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="bcb98-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="bcb98-166">Duomenų importavimas į „Adobe” patirties platformą</span><span class="sxs-lookup"><span data-stu-id="bcb98-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="bcb98-167">Dabar, kai viskas tvarkoje, turime importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į „Adobe” patirties platformą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="bcb98-168">Pirma, [sukurkite „Azure” didelių dvejetainių objektų saugyklos ryšį](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="bcb98-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="bcb98-169">Nustatę šaltinio ryšį, [sukonfigūruokite duomenų srautą](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) debesies saugyklos paketinio ryšiui tam, kad importuotumėte segmento išvestį iš auditorijos įžvalgų į „Adobe” patirties platformą.</span><span class="sxs-lookup"><span data-stu-id="bcb98-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="bcb98-170">Auditorijos kūrimas „Adobe Campaign Standard” platformoje</span><span class="sxs-lookup"><span data-stu-id="bcb98-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="bcb98-171">Jei norite siųsti šios kampanijos el. laišką, naudosime „Adobe Campaign Standard".</span><span class="sxs-lookup"><span data-stu-id="bcb98-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="bcb98-172">Importavę duomenis į „Adobe” patirties platformą, turime [sukurti auditoriją](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) „Adobe Campaign Standard” platformoje naudodami duomenis iš „Adobe” patirties platformos.</span><span class="sxs-lookup"><span data-stu-id="bcb98-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="bcb98-173">Sužinokite, kaip [naudoti segmentų daryklę](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) „Adobe Campaign Standard” platformoje, kad apibrėžtumėte auditoriją pagal „Adobe” patirties platformos duomenis.</span><span class="sxs-lookup"><span data-stu-id="bcb98-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="bcb98-174">El. laiško sukūrimas ir siuntimas naudojant „Adobe Campaign Standard”</span><span class="sxs-lookup"><span data-stu-id="bcb98-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="bcb98-175">Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.</span><span class="sxs-lookup"><span data-stu-id="bcb98-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Pavyzdinis el. laiškas su atnaujinimo pasiūlymu iš Adobe Campaign Standard.":::
