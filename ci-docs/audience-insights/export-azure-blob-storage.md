---
title: Eksportuoti „ Customer Insights“ duomenis į „Azure Blob“ talpinimą
description: Sužinokite, kaip sukonfigūruoti ryšį su „Azure“ didelių dvejetainių objektų saugykla.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667149"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="01e90-103">„Azure“ didelių dvejetainių objektų saugyklos jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="01e90-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="01e90-104">Talpinkite savo „ Customer Insights“ duomenis į „Azure Blob“ talpinimą ar naudokite jį jūsų duomenų perdavimui į kitas programas.</span><span class="sxs-lookup"><span data-stu-id="01e90-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="01e90-105">„Azure“ didelių dvejetainių objektų saugyklos jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="01e90-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="01e90-106">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="01e90-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="01e90-107">Dalyje **„Azure“ didelių dvejetainių objektų saugykla** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="01e90-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="01e90-108">Įveskite „Azure“ didelių dvejetainių objektų saugyklos **Kliento pavadinimą**, **Kliento raktą** ir **Konteinerį**.</span><span class="sxs-lookup"><span data-stu-id="01e90-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="01e90-109">Jei norite sužinoti daugiau apie tai, kaip rasti „Azure“ didelių dvejetainių objektų saugyklos kliento pavadinimą ir kliento raktą, žr. [Saugyklos kliento parametrų valdymas „Azure“ portale](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="01e90-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="01e90-110">Norėdami sužinoti, kaip sukurti konteinerį, žr. [Konteinerio kūrimas](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="01e90-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="01e90-111">Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="01e90-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="01e90-112">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="01e90-112">Select **Next**.</span></span>

1. <span data-ttu-id="01e90-113">Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="01e90-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="01e90-114">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="01e90-114">Select **Save**.</span></span>

<span data-ttu-id="01e90-115">Eksportuoti duomenys saugomi sukonfigūruotoje „Azure“ didelių dvejetainių objektų saugykloje.</span><span class="sxs-lookup"><span data-stu-id="01e90-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="01e90-116">Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:</span><span class="sxs-lookup"><span data-stu-id="01e90-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="01e90-117">Šaltinio objektams ir objektams sukurtiems sistemos: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="01e90-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="01e90-118">Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="01e90-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="01e90-119">Eksportuotų objektų modelis .json išliks lygiu %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="01e90-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="01e90-120">Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="01e90-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="01e90-121">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="01e90-121">Export the data</span></span>

<span data-ttu-id="01e90-122">Galite [eksportuoti duomenis pareikalavus](/export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="01e90-122">You can [export data on demand](/export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="01e90-123">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01e90-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
