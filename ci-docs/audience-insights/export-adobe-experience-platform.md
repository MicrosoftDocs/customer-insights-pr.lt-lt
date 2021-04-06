---
title: „Customer Insights” duomenų eksportavimas į „Adobe” patirties platformą
description: Sužinokite, kaip naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596279"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="262c8-103">„Customer Insights” segmentų naudojimas „Adobe” patirties platformoje (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="262c8-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="262c8-104">Kaip „Dynamics 365 Customer Insights” auditorijos įžvalgos vartotojas galbūt sukūrėte segmentus, kad jūsų rinkodaros kampanijos būtų efektyvesnės taikydami pagal atitinkamas auditorijas.</span><span class="sxs-lookup"><span data-stu-id="262c8-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="262c8-105">Norėdami naudoti segmentą iš „Adobe” patirties platformos auditorijos įžvalgų ir programų, pavyzdžiui, „Adobe Campaign Standard”, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="262c8-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a><span data-ttu-id="262c8-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="262c8-107">Prerequisites</span></span>

-   <span data-ttu-id="262c8-108">„Dynamics 365 Customer Insights“ licencija</span><span class="sxs-lookup"><span data-stu-id="262c8-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="262c8-109">„Adobe” patirties platformos licencija</span><span class="sxs-lookup"><span data-stu-id="262c8-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="262c8-110">„Adobe Campaign Standard“ licencija</span><span class="sxs-lookup"><span data-stu-id="262c8-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="262c8-111">„Azure“ didelių dvejetainių objektų saugyklos abonementas</span><span class="sxs-lookup"><span data-stu-id="262c8-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="262c8-112">Kampanijos apžvalga</span><span class="sxs-lookup"><span data-stu-id="262c8-112">Campaign Overview</span></span>

<span data-ttu-id="262c8-113">Norėdami geriau suprasti, kaip galite naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje, pažvelkime į fiktyvią pavyzdinę kampaniją.</span><span class="sxs-lookup"><span data-stu-id="262c8-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="262c8-114">Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose.</span><span class="sxs-lookup"><span data-stu-id="262c8-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="262c8-115">Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos.</span><span class="sxs-lookup"><span data-stu-id="262c8-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="262c8-116">Siekdami išlaikyti šiuos klientus, norite nusiųsti jiems reklaminį pasiūlymą el. paštu naudojant „Adobe” patirties platformą.</span><span class="sxs-lookup"><span data-stu-id="262c8-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="262c8-117">Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="262c8-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="262c8-118">Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.</span><span class="sxs-lookup"><span data-stu-id="262c8-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="262c8-119">Atpažinkite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="262c8-119">Identify your target audience</span></span>

<span data-ttu-id="262c8-120">Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.</span><span class="sxs-lookup"><span data-stu-id="262c8-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="262c8-121">[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.</span><span class="sxs-lookup"><span data-stu-id="262c8-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

<span data-ttu-id="262c8-123">Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data.</span><span class="sxs-lookup"><span data-stu-id="262c8-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="262c8-124">Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.</span><span class="sxs-lookup"><span data-stu-id="262c8-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="262c8-125">Eksportuokite savo tikslinę auditoriją</span><span class="sxs-lookup"><span data-stu-id="262c8-125">Export your target audience</span></span>

<span data-ttu-id="262c8-126">Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.</span><span class="sxs-lookup"><span data-stu-id="262c8-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="262c8-127">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="262c8-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="262c8-128">Plytelėje **„Azure“ didelių dvejetainių objektų saugykla** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="262c8-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigūracijos plytelė, skirta „Azure“ didelių dvejetainių objektų saugyklai.":::

1. <span data-ttu-id="262c8-130">Pateikite šios naujos eksportavimo vietos **Rodomą pavadinimą** ir tada įveskite **Abonemento pavadinimą**, **Abonemento raktą** ir **Talpyklę**„Azure“ didelių dvejetainių objektų saugyklai, į kurią norite eksportuoti segmentą.</span><span class="sxs-lookup"><span data-stu-id="262c8-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija."::: 

   - <span data-ttu-id="262c8-132">Jei norite sužinoti daugiau apie tai, kaip rasti „Azure“ didelių dvejetainių objektų saugyklos kliento pavadinimą ir kliento raktą, žr. [Saugyklos kliento parametrų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="262c8-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="262c8-133">Norėdami sužinoti, kaip sukurti konteinerį, žr. [Konteinerio kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="262c8-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="262c8-134">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="262c8-134">Select **Next**.</span></span>

1. <span data-ttu-id="262c8-135">Pasirinkite segmentą, kurį norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="262c8-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="262c8-136">Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.</span><span class="sxs-lookup"><span data-stu-id="262c8-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. <span data-ttu-id="262c8-138">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="262c8-138">Select **Save**.</span></span>

<span data-ttu-id="262c8-139">Įrašę eksportavimo paskirties vietą, ją rasite **Administravimas** > **Eksportavimai** > **Mano eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="262c8-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Ekrano kopija su eksportavimų sąrašu ir paryškintu pavyzdžio segmentu.":::

<span data-ttu-id="262c8-141">Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="262c8-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="262c8-142">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).</span><span class="sxs-lookup"><span data-stu-id="262c8-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="262c8-143">Įsitikinkite, kad eksportuoto segmento įrašų skaičius neviršija leistinos „Adobe Campaign Standard” licencijos ribos.</span><span class="sxs-lookup"><span data-stu-id="262c8-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="262c8-144">Eksportuoti duomenys saugomi „Azure“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau.</span><span class="sxs-lookup"><span data-stu-id="262c8-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="262c8-145">Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:</span><span class="sxs-lookup"><span data-stu-id="262c8-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="262c8-146">„*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*”</span><span class="sxs-lookup"><span data-stu-id="262c8-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="262c8-147">Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="262c8-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="262c8-148">Eksportuotų objektų *„model.json”* išlieka *„%ExportDestinationName%”* lygiu.</span><span class="sxs-lookup"><span data-stu-id="262c8-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="262c8-149">Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="262c8-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="262c8-150">Patirties duomenų modelio (XDM) apibrėžimas „Adobe” patirties platformoje</span><span class="sxs-lookup"><span data-stu-id="262c8-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="262c8-151">Prieš naudojant iš auditorijos įžvalgų eksportuotus duomenis „Adobe” patirties platformoje, turime apibrėžti patirties duomenų modelio schemą ir [konfigūruoti kliento profilio duomenis realiuoju laiku](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="262c8-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="262c8-152">Sužinokite, [kas yra XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ir supraskite [schemos struktūros pagrindus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="262c8-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="262c8-153">Duomenų importavimas į „Adobe” patirties platformą</span><span class="sxs-lookup"><span data-stu-id="262c8-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="262c8-154">Dabar, kai viskas tvarkoje, turime importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į „Adobe” patirties platformą.</span><span class="sxs-lookup"><span data-stu-id="262c8-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="262c8-155">Pirma, [sukurkite „Azure” didelių dvejetainių objektų saugyklos ryšį](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="262c8-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="262c8-156">Nustatę šaltinio ryšį, [sukonfigūruokite duomenų srautą](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) debesies saugyklos paketinio ryšiui tam, kad importuotumėte segmento išvestį iš auditorijos įžvalgų į „Adobe” patirties platformą.</span><span class="sxs-lookup"><span data-stu-id="262c8-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="262c8-157">Auditorijos kūrimas „Adobe Campaign Standard” platformoje</span><span class="sxs-lookup"><span data-stu-id="262c8-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="262c8-158">Norėdami siųsti šios kampanijos el. laiškus, naudosime „Adobe Campaign Standard”.</span><span class="sxs-lookup"><span data-stu-id="262c8-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="262c8-159">Importavę duomenis į „Adobe” patirties platformą, turime [sukurti auditoriją](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) „Adobe Campaign Standard” platformoje naudodami duomenis iš „Adobe” patirties platformos.</span><span class="sxs-lookup"><span data-stu-id="262c8-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="262c8-160">Sužinokite, kaip [naudoti segmentų daryklę](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) „Adobe Campaign Standard” platformoje, kad apibrėžtumėte auditoriją pagal „Adobe” patirties platformos duomenis.</span><span class="sxs-lookup"><span data-stu-id="262c8-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="262c8-161">El. laiško sukūrimas ir siuntimas naudojant „Adobe Campaign Standard”</span><span class="sxs-lookup"><span data-stu-id="262c8-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="262c8-162">Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.</span><span class="sxs-lookup"><span data-stu-id="262c8-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Pavyzdinis el. laiškas su atnaujinimo pasiūlymu iš Adobe Campaign Standard.":::