---
title: „Customer Insights” duomenų eksportavimas į „Azure Data Lake Storage Gen2”
description: Sužinokite, kaip konfigūruoti ryšį su „Azure Data Lake Storage Gen2”.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760061"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="f9463-103">Ryšio su Azure Data Lake Storage Gen2 nustatymas (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="f9463-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="f9463-104">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="f9463-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f9463-105">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure Data Lake Gen 2“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="f9463-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="f9463-106">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="f9463-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f9463-107">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="f9463-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f9463-108">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="f9463-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f9463-109">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="f9463-109">Choose who can use this connection.</span></span> <span data-ttu-id="f9463-110">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="f9463-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f9463-111">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f9463-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f9463-112">Įveskite **Paskyros vardą**, **Kliento raktą** ir **Konteinerį** savo „Azure Data Lake Storage Gen2”.</span><span class="sxs-lookup"><span data-stu-id="f9463-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="f9463-113">Norėdami sužinoti, kaip sukurti saugyklos paskyrą su „Azure Data Lake Storage Gen2”, žr. [Saugyklos paskyros kūrimas](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="f9463-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="f9463-114">Jei norite sužinoti daugiau apie „Azure Data Lake Gen2“ talpyklos paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f9463-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="f9463-115">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="f9463-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f9463-116">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="f9463-116">Configure an export</span></span>

<span data-ttu-id="f9463-117">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="f9463-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f9463-118">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f9463-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f9463-119">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="f9463-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f9463-120">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.</span><span class="sxs-lookup"><span data-stu-id="f9463-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="f9463-121">Laukelyje **Ryšys su eksportavimu** pasirinkite ryšį iš laukelio **„Azure Data Lake“**.</span><span class="sxs-lookup"><span data-stu-id="f9463-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="f9463-122">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="f9463-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f9463-123">Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.</span><span class="sxs-lookup"><span data-stu-id="f9463-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="f9463-124">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="f9463-124">Select **Save**.</span></span>

<span data-ttu-id="f9463-125">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="f9463-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f9463-126">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f9463-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f9463-127">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f9463-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="f9463-128">Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Azure Data Lake Gen 2“ talpyklos saugykloje.</span><span class="sxs-lookup"><span data-stu-id="f9463-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
