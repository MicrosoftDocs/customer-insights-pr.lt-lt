---
title: Eksportuoti „ Customer Insights“ duomenis į „Azure Blob“ talpyklą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Blob“ talpyklą.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760199"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="09133-103">Segmentų sąrašo ir kitų duomenų eksportavimas į „Azure Blob“ talpyklą (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="09133-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="09133-104">Saugokite savo „Customer Insights“ duomenis „Blob“ saugykloje arba naudokite ją norėdami perkelti duomenis į kitas programas.</span><span class="sxs-lookup"><span data-stu-id="09133-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="09133-105">Ryšio su „Blob“ talpyklą nustatymas</span><span class="sxs-lookup"><span data-stu-id="09133-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="09133-106">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="09133-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="09133-107">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure Blob“ talpykla**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="09133-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="09133-108">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="09133-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="09133-109">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="09133-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="09133-110">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="09133-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="09133-111">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="09133-111">Choose who can use this connection.</span></span> <span data-ttu-id="09133-112">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="09133-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="09133-113">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="09133-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="09133-114">Įveskite savo „Blob“ talpyklos **paskyros pavadinimą**, **paskyros raktą** ir **talpyklą**.</span><span class="sxs-lookup"><span data-stu-id="09133-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="09133-115">Jei norite sužinoti daugiau apie „Blob“ talpyklos paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="09133-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="09133-116">Norėdami sužinoti, kaip sukurti konteinerį, žr. [Konteinerio kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="09133-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="09133-117">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="09133-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="09133-118">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="09133-118">Configure an export</span></span>

<span data-ttu-id="09133-119">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="09133-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="09133-120">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="09133-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="09133-121">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="09133-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="09133-122">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="09133-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="09133-123">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure Blob“ talpykla.</span><span class="sxs-lookup"><span data-stu-id="09133-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="09133-124">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="09133-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="09133-125">Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="09133-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="09133-126">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="09133-126">Select **Save**.</span></span>

<span data-ttu-id="09133-127">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="09133-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="09133-128">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="09133-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="09133-129">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="09133-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="09133-130">Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Blob“ talpyklos saugykloje.</span><span class="sxs-lookup"><span data-stu-id="09133-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="09133-131">Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:</span><span class="sxs-lookup"><span data-stu-id="09133-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="09133-132">Šaltinio objektams ir objektams sukurtiems sistemos: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="09133-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="09133-133">Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="09133-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="09133-134">Eksportuotiems objektams model.json bus nurodytas %ExportDestinationName% lygiu</span><span class="sxs-lookup"><span data-stu-id="09133-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="09133-135">Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="09133-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
