---
title: „Customer Insights“ duomenų eksportavimas į „Azure“ didelių dvejetainių objektų saugyklą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į didelių dvejetainių objektų saugyklą.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976191"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="86636-103">Segmentų sąrašo ir kitų duomenų eksportavimas į „Azure“ didelių dvejetainių objektų saugyklą (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="86636-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="86636-104">Saugokite savo „Customer Insights“ duomenis didelių dvejetainių objektų saugykloje arba naudokite ją norėdami perkelti duomenis į kitas programas.</span><span class="sxs-lookup"><span data-stu-id="86636-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="86636-105">Ryšio su didelių dvejetainių objektų saugykla nustatymas</span><span class="sxs-lookup"><span data-stu-id="86636-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="86636-106">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="86636-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="86636-107">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure” didelių dvejetainių objektų saugykla**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="86636-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="86636-108">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="86636-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="86636-109">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="86636-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="86636-110">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="86636-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="86636-111">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="86636-111">Choose who can use this connection.</span></span> <span data-ttu-id="86636-112">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="86636-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="86636-113">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="86636-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="86636-114">Įveskite savo „Azure” didelių dvejetainių objektų saugyklos **paskyros pavadinimą**, **paskyros raktą** ir **talpyklą**.</span><span class="sxs-lookup"><span data-stu-id="86636-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="86636-115">Jei norite sužinoti daugiau apie didelių dvejetainių objektų saugyklos paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="86636-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="86636-116">Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="86636-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="86636-117">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="86636-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="86636-118">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="86636-118">Configure an export</span></span>

<span data-ttu-id="86636-119">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="86636-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="86636-120">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="86636-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="86636-121">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="86636-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="86636-122">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="86636-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="86636-123">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla.</span><span class="sxs-lookup"><span data-stu-id="86636-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="86636-124">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="86636-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="86636-125">Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="86636-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="86636-126">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="86636-126">Select **Save**.</span></span>

<span data-ttu-id="86636-127">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="86636-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="86636-128">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="86636-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="86636-129">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="86636-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="86636-130">Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Azure” didelių dvejetainių objektų saugyklos talpyklėje.</span><span class="sxs-lookup"><span data-stu-id="86636-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="86636-131">Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:</span><span class="sxs-lookup"><span data-stu-id="86636-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="86636-132">Šaltinio objektams ir objektams sukurtiems sistemos: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="86636-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="86636-133">Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="86636-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="86636-134">Eksportuotiems objektams model.json bus nurodytas %ExportDestinationName% lygiu</span><span class="sxs-lookup"><span data-stu-id="86636-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="86636-135">Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="86636-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
