---
title: Prisijunkite prie „Azure Data Lake Storage Gen2“ paskyros su pagrindinėmis paslaugomis
description: Naudokite „Azure“ pagrindines paslaugas publikos įžvalgoms, kurios prisijungia prie jūsų turimo „Data Lake“ pridedant jį prie publikos įžvalgų.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267732"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="308b8-103">Prijunkite „Azure Data Lake Storage Gen2“ paskyrą prie „Azure“ pagrindinių paslaugų publikos įžvalgoms</span><span class="sxs-lookup"><span data-stu-id="308b8-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="308b8-104">Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus.</span><span class="sxs-lookup"><span data-stu-id="308b8-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="308b8-105">Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="308b8-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="308b8-106">Perskaitykite tam, kad sužinotumėte, kaip prijungti publikos įžvalgas prie „Azure Data Lake Storage Gen2“ paskyros naudojant „Azure“ pagrindines paslaugas, o ne paskyros raktų talpinimą.</span><span class="sxs-lookup"><span data-stu-id="308b8-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="308b8-107">Galite naudoti pagrindinias paslaugas tam, kad saugiai [įtrauktumėte ar redaguotumėte „Common Data Model“ katalogą kaip duomenų šaltinį](connect-common-data-model.md) ar [sukurtumėte naują ar atnaujintumėte esamą aplinką](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="308b8-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="308b8-108">"Azure Data lake Gen2", dėl kurios pagrindinės tarnyba naudojamo, turi būti įjungta hierarchinė vardų sritis [ (SSS). ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="308b8-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="308b8-109">Jums reikia administratoriaus leidimų jūsų „Azure“ prenumeratai siekiant sukurti pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="308b8-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="308b8-110">Sukurti „Azure“ pagrindines paslaugos publikos įžvalgoms</span><span class="sxs-lookup"><span data-stu-id="308b8-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="308b8-111">Prieš sukurdami naujas pagrindines paslaugas publikos įžvalgoms, patikrinkite, ar jos jau yra jūsų organizacijoje.</span><span class="sxs-lookup"><span data-stu-id="308b8-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="308b8-112">Ieškokite esančių pagrindinių paslaugų</span><span class="sxs-lookup"><span data-stu-id="308b8-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="308b8-113">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.</span><span class="sxs-lookup"><span data-stu-id="308b8-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="308b8-114">Pasirinkite **„Azure Active Directory“** iš „Azure“ paslaugų.</span><span class="sxs-lookup"><span data-stu-id="308b8-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="308b8-115">Skyriuje **Valdyti**, pasirinkite **Įmonės programos**.</span><span class="sxs-lookup"><span data-stu-id="308b8-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="308b8-116">Ieškokite publikos įžvalgų pirmosios šalies programos ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar pavadinimo „`Dynamics 365 AI for Customer Insights`“.</span><span class="sxs-lookup"><span data-stu-id="308b8-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="308b8-117">Jei surasite atitinkamą įrašą, reiškia, kad pagrindinės paslaugos publikos įžvalgoms egzistuoja.</span><span class="sxs-lookup"><span data-stu-id="308b8-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="308b8-118">Jums nereikia dar kartą jo sukurti.</span><span class="sxs-lookup"><span data-stu-id="308b8-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Momentinė nuotrauka rodanti esančias pagrindines paslaugas.":::
   
6. <span data-ttu-id="308b8-120">Jei negaunama jokių rezultatų sukurkite naujas pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="308b8-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="308b8-121">Sukurkite naujas pagrindines paslaugas</span><span class="sxs-lookup"><span data-stu-id="308b8-121">Create a new service principal</span></span>

1. <span data-ttu-id="308b8-122">Įdiekite naujausią **„Azure Active Directory PowerShell for Graph“**.</span><span class="sxs-lookup"><span data-stu-id="308b8-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="308b8-123">Dėl daugiau informacijos, žr. [Diegti „Azure Active Directory PowerShell for Graph“](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="308b8-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="308b8-124">Jūsų kompiuteryje pasirinkite „Windows“ mygtuką jūsų klaviatūroje ir ieškokite **„Windows PowerShell“** ir **Vykdyti kaip adminstratoriui**.</span><span class="sxs-lookup"><span data-stu-id="308b8-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="308b8-125">„PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="308b8-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="308b8-126">Sukurkite pagrindines paslaugas publikos įžvalgoms su „Azure AD PowerShell Module“.</span><span class="sxs-lookup"><span data-stu-id="308b8-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="308b8-127">„PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="308b8-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="308b8-128">Pakeiskite „jūsų nuomotojo ID“ esančiu jūsų nuomotojo ID, kuriame norite sukurti pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="308b8-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="308b8-129">Aplinkos pavadinimo parametras `AzureEnvironmentName` yra pasirinktinas.</span><span class="sxs-lookup"><span data-stu-id="308b8-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="308b8-130">Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="308b8-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="308b8-131">Ši komanda sukuria pagrindines paslaugas publikos įžvalgoms pasirinktame nuomotojuje.</span><span class="sxs-lookup"><span data-stu-id="308b8-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="308b8-132">Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros</span><span class="sxs-lookup"><span data-stu-id="308b8-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="308b8-133">Eikite į „Azure“ portalą tam, kad suteiktumėte leidimus pagrindinėms paslaugoms talpinimo paskyroje, kurioje norite naudoti publikos įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="308b8-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="308b8-134">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.</span><span class="sxs-lookup"><span data-stu-id="308b8-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="308b8-135">Atverkite talpinimo paskyrą, kurioje norite pagrindinių paslaugų prieigos prie publikos įžvalgų.</span><span class="sxs-lookup"><span data-stu-id="308b8-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="308b8-136">Pasirinkite **Prieigos valdymas (IAM)** iš naršymo juostos ir pasirinkite **Įtraukti** > **Įtraukti vaidmenis priskyrimą**.</span><span class="sxs-lookup"><span data-stu-id="308b8-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Momentinė ekrano nuotrauka rodanti „Azure“ portalą įtraukiant vaidmens priskyrimą.":::
   
1. <span data-ttu-id="308b8-138">**Įtraukti vaidmens priskyrimo** juostoje nustatykite šias ypatybes:</span><span class="sxs-lookup"><span data-stu-id="308b8-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="308b8-139">Vaidmuo: *„Storage Blob Data Contributor“*</span><span class="sxs-lookup"><span data-stu-id="308b8-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="308b8-140">Priskirkite prieigą prie: *Vartotojo, grupės ar pagrindinių paslaugų*</span><span class="sxs-lookup"><span data-stu-id="308b8-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="308b8-141">Pasirinkite: *„Dynamics 365 AI Customer Insights“* ( [jūsų sukurtos pagrindinės paslaugos](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="308b8-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="308b8-142">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="308b8-142">Select **Save**.</span></span>

<span data-ttu-id="308b8-143">Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.</span><span class="sxs-lookup"><span data-stu-id="308b8-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="308b8-144">Įveskite „Azure“ išteklių ID arba „Azure“ prenumeravimo išsamią informaciją į talpinimo paskyros priedą prie publikos įžvalgų.</span><span class="sxs-lookup"><span data-stu-id="308b8-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="308b8-145">Pridėkite „Azure Data Lake“ talpinimo paskyrą publikos įžvalgose prie [talpinimo išvesties duomenų](manage-environments.md) ar [naudokite juos kaip duomenų šaltinį](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="308b8-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="308b8-146">Pasirinkus „Azure Data Lake“ parinktį ji leidžia jums rinktis tarp ištekliais pagrįstos ar prenumerata pagrįstos prieigos.</span><span class="sxs-lookup"><span data-stu-id="308b8-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="308b8-147">Atlikite tolesnius žingsnius tam, kad gautumėte reikiamą informaciją apie pasirinktą prieigą.</span><span class="sxs-lookup"><span data-stu-id="308b8-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="308b8-148">Saugyklo išteklių paskyros ryšys</span><span class="sxs-lookup"><span data-stu-id="308b8-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="308b8-149">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="308b8-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="308b8-150">Eikite į **Nustatymai** > **Ypatybės** naršymo juostoje.</span><span class="sxs-lookup"><span data-stu-id="308b8-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="308b8-151">Kopijuokite talpinimo paskyros išteklių ID vertę.</span><span class="sxs-lookup"><span data-stu-id="308b8-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopijuokite talpinimo paskyros išteklių ID vertę.":::

1. <span data-ttu-id="308b8-153">Publikos įžvalgose įveskite išteklių ID išteklių laukelyje rodomame talpinimo paskyros jungties ekrane.</span><span class="sxs-lookup"><span data-stu-id="308b8-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::   
   
1. <span data-ttu-id="308b8-155">Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="308b8-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="308b8-156">Prenumerata pagrįstos talpinimo paskyros jungtis</span><span class="sxs-lookup"><span data-stu-id="308b8-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="308b8-157">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="308b8-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="308b8-158">Eikite į **Nustatymai** > **Ypatybės** naršymo juostoje.</span><span class="sxs-lookup"><span data-stu-id="308b8-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="308b8-159">Peržiūrėkite **Prenumerata**, **Išteklių grupė** ir talpinimo paskyros **Pavadinimas** siekiant užsitikrinti, kad pasirinkote tinkamas vertes publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="308b8-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="308b8-160">Publikos įžvalgose pasirinkite vertes arba atitinkamus laukelius pridedant talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="308b8-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="308b8-161">Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="308b8-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]