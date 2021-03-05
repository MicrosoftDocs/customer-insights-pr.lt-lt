---
title: "\"Customer Insights\" duomenų eksportavimas į Azure Data Lake Storage \"Gen2\""
description: Sužinokite, kaip konfigūruoti ryšį su Azure Data Lake Storage "Gen2".
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477189"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="3bc55-103">Azure Data Lake Storage"Gen2" jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="3bc55-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="3bc55-104">Saugokite savo „Customer Insights“ duomenis saugykloje Azure Data Lake Storage "Gen 2" arba naudokite ją norėdami perkelti duomenis į kitas programas.</span><span class="sxs-lookup"><span data-stu-id="3bc55-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="3bc55-105">Azure Data Lake Storage "Gen2" jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="3bc55-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="3bc55-106">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="3bc55-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3bc55-107">Dalyje **Azure Data Lake Storage "Gen2"** pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="3bc55-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="3bc55-108">Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="3bc55-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3bc55-109">Įveskite **Paskyros vardą**, **Kliento raktą** ir **Konteinerį** savo Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="3bc55-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="3bc55-110">Norėdami sužinoti, kaip sukurti saugyklos paskyrą su Azure Data Lake Storage "Gen2", [žr. Saugyklos paskyros](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account) kūrimas.</span><span class="sxs-lookup"><span data-stu-id="3bc55-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="3bc55-111">Jei norite sužinoti daugiau apie tai, kaip rasti "Azure Data Lake Gen2" saugyklos kliento pavadinimą ir kliento raktą, [žr. Saugyklos paskyros parametrų valdymas "Azure" portale](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3bc55-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="3bc55-112">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="3bc55-112">Select **Next**.</span></span>

1. <span data-ttu-id="3bc55-113">Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="3bc55-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="3bc55-114">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="3bc55-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3bc55-115">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="3bc55-115">Export the data</span></span>

<span data-ttu-id="3bc55-116">Galite [eksportuoti duomenis pareikalavus](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3bc55-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="3bc55-117">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3bc55-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
