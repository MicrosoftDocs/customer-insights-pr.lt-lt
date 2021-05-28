---
title: „Customer Insights“ duomenų eksportavimas į „Azure Synapse Analytics“
description: Sužinokite, kaip sukonfigūruoti ryšį į „Azure Synapse Analytics”.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977387"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="6c64e-103">Duomenų eksportavimas į „Azure Synapse Analytics” (Peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="6c64e-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="6c64e-104">„Azure Synapse” yra analizės tarnyba, kuri paspartina duomenų sandėlių ir didelių duomenų sistemų įžvalgų atlikimo laiką.</span><span class="sxs-lookup"><span data-stu-id="6c64e-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="6c64e-105">Galite įtraukti ir naudoti savo „Customer Insights” duomenis [„Azure Synapse](/azure/synapse-analytics/overview-what-is) tarnyboje.</span><span class="sxs-lookup"><span data-stu-id="6c64e-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c64e-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="6c64e-106">Prerequisites</span></span>

<span data-ttu-id="6c64e-107">Turite atitikti toliau pateiktas būtinąsias sąlygas, kad sukonfigūruotumėte ryšį iš „Customer Insights” į „Azure Synapse”.</span><span class="sxs-lookup"><span data-stu-id="6c64e-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="6c64e-108">Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.</span><span class="sxs-lookup"><span data-stu-id="6c64e-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="6c64e-109">Būtinosios „Customer Insights“ sąlygos</span><span class="sxs-lookup"><span data-stu-id="6c64e-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="6c64e-110">Auditorijos įžvalgose turite **Administratoriaus** vaidmenį.</span><span class="sxs-lookup"><span data-stu-id="6c64e-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="6c64e-111">Sužinokite daugiau apie [vartotojų teisių nustatymą auditorijos įžvalgose](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="6c64e-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="6c64e-112">„Azure“ tarnyboje:</span><span class="sxs-lookup"><span data-stu-id="6c64e-112">In Azure:</span></span> 

- <span data-ttu-id="6c64e-113">Aktyvi „Azure“ prenumerata.</span><span class="sxs-lookup"><span data-stu-id="6c64e-113">An active Azure subscription.</span></span>

- <span data-ttu-id="6c64e-114">Jei naudojate naują „Azure Data Lake Storage Gen2” klientą, *pagrindinei auditorijos įžvalgų tarnybai* reikalingos **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisės.</span><span class="sxs-lookup"><span data-stu-id="6c64e-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="6c64e-115">Sužinokite daugiau skyriuje [prisijungimas prie „Azure Data Lake Storage Gen2” kliento su pagrindine auditorijos įžvalgų „Azure” tarnyba](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6c64e-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="6c64e-116">„Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="6c64e-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="6c64e-117">Išteklių grupėje, kurioje yra „Azure Synapse” darbo sritis, *pagrindinei tarnybai* ir *auditorijų įžvalgų vartotojui* turi būti priskirtos bent **Skaitytojo** teisės.</span><span class="sxs-lookup"><span data-stu-id="6c64e-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="6c64e-118">Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="6c64e-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="6c64e-119">*Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi.</span><span class="sxs-lookup"><span data-stu-id="6c64e-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="6c64e-120">Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="6c64e-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="6c64e-121">*[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi.</span><span class="sxs-lookup"><span data-stu-id="6c64e-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="6c64e-122">Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="6c64e-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="6c64e-123">„Azure Synapse” darbo srityje *pagrindinei auditorijos įžvalgų tarnybai* reikia priskirti **„Synapse” administratoriaus** vaidmenį.</span><span class="sxs-lookup"><span data-stu-id="6c64e-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="6c64e-124">Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="6c64e-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="6c64e-125">Ryšio nustatymas ir eksportavimas į „Azure Synapse”</span><span class="sxs-lookup"><span data-stu-id="6c64e-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="6c64e-126">Ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="6c64e-126">Configure a connection</span></span>

1. <span data-ttu-id="6c64e-127">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6c64e-128">Pasirinkite **Įtraukti ryšį** ir **„Azure Synapse Analytics”** arba pasirinkite **Nustatyti** plytelėje **„Azure Synapse Analytics”**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="6c64e-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="6c64e-129">Nurodykite atpažįstamą ryšio pavadinimą laukelyje Rodyti pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="6c64e-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="6c64e-130">Ryšio pavadinimas ir tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="6c64e-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="6c64e-131">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="6c64e-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6c64e-132">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="6c64e-132">Choose who can use this connection.</span></span> <span data-ttu-id="6c64e-133">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="6c64e-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6c64e-134">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6c64e-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6c64e-135">Pasirinkite arba ieškokite prenumeratos, kurioje norite naudoti „Customer Insights” duomenis.</span><span class="sxs-lookup"><span data-stu-id="6c64e-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="6c64e-136">Pasirinkę prenumeratą, taip pat galėsite pasirinkti **Darbo sritis**, **Saugyklos klientas** ir **Talpyklė**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="6c64e-137">Pasirinkite **Įrašyti** ryšio įrašymui.</span><span class="sxs-lookup"><span data-stu-id="6c64e-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="6c64e-138">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="6c64e-138">Configure an export</span></span>

<span data-ttu-id="6c64e-139">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="6c64e-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6c64e-140">Daugiau informacijos rasite [eksportavimo konfigūravimui reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6c64e-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6c64e-141">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c64e-142">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="6c64e-143">Lauke **Ryšys eksportavimui** pasirinkite ryšį iš **„Azure Synapse Analytics”** skyriaus.</span><span class="sxs-lookup"><span data-stu-id="6c64e-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="6c64e-144">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo [ryšių](connections.md).</span><span class="sxs-lookup"><span data-stu-id="6c64e-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="6c64e-145">Savo eksportavimui pateikite atpažįstamą **Rodomą pavadinimą** ir **Duomenų bazės pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="6c64e-146">Pasirinkite objektus, kuriuos norite eksportuoti į „Azure Synapse Analytics”.</span><span class="sxs-lookup"><span data-stu-id="6c64e-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="6c64e-147">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-147">Select **Save**.</span></span>

<span data-ttu-id="6c64e-148">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="6c64e-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6c64e-149">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c64e-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c64e-150">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6c64e-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="6c64e-151">Eksportavimo naujinimas</span><span class="sxs-lookup"><span data-stu-id="6c64e-151">Update an export</span></span>

1. <span data-ttu-id="6c64e-152">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="6c64e-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c64e-153">Pasirinkite **Redaguoti** norimą atnaujinti redagavimą.</span><span class="sxs-lookup"><span data-stu-id="6c64e-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="6c64e-154">**Įtraukite** arba **Pašalinkite** objektus iš pasirinkimo.</span><span class="sxs-lookup"><span data-stu-id="6c64e-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="6c64e-155">Jei objektai yra pašalinami iš pasirinkimo, jie nėra panaikinami iš „Synapse Analytics” duomenų bazės.</span><span class="sxs-lookup"><span data-stu-id="6c64e-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="6c64e-156">Tačiau būsimi duomenų atnaujinimai nenaujins tos duomenų bazės objektų.</span><span class="sxs-lookup"><span data-stu-id="6c64e-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="6c64e-157">**Pakeitus duomenų bazės pavadinimą**, sukuriama nauja „Synapse Analytics” duomenų bazė.</span><span class="sxs-lookup"><span data-stu-id="6c64e-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="6c64e-158">Duomenų bazė, kurios pavadinimas buvo sukonfigūruotas prieš tai, ateityje nebus atnaujinta.</span><span class="sxs-lookup"><span data-stu-id="6c64e-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
