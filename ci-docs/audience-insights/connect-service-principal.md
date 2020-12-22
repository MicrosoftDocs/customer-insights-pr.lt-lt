---
title: Prisijunkite prie „Azure Data Lake Storage Gen2“ paskyros su pagrindinėmis paslaugomis
description: Naudokite „Azure“ pagrindines paslaugas publikos įžvalgoms, kurios prisijungia prie jūsų turimo „Data Lake“ pridedant jį prie publikos įžvalgų.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644098"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="e0875-103">Prijunkite „Azure Data Lake Storage Gen2“ paskyrą prie „Azure“ pagrindinių paslaugų publikos įžvalgoms</span><span class="sxs-lookup"><span data-stu-id="e0875-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="e0875-104">Automatizuoti įrankiai, naudojantys „Azure“ paslaugas visada turėtų turėti apribotus leidimus.</span><span class="sxs-lookup"><span data-stu-id="e0875-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="e0875-105">Vietoje programų prisijungimo kaip vartotojui su teisėmis, „Azure“ siūlo pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="e0875-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="e0875-106">Perskaitykite tam, kad sužinotumėte, kaip prijungti publikos įžvalgas prie „Azure Data Lake Storage Gen2“ paskyros naudojant „Azure“ pagrindines paslaugas, o ne paskyros raktų talpinimą.</span><span class="sxs-lookup"><span data-stu-id="e0875-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="e0875-107">Galite naudoti pagrindinias paslaugas tam, kad saugiai [įtrauktumėte ar redaguotumėte „Common Data Model“ katalogą kaip duomenų šaltinį](connect-common-data-model.md) ar [sukurtumėte naują ar atnaujintumėte esamą aplinką](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="e0875-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="e0875-108">Jums reikia administratoriaus leidimų jūsų „Azure“ prenumeratai siekiant sukurti pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="e0875-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="e0875-109">Sukurti „Azure“ pagrindines paslaugos publikos įžvalgoms</span><span class="sxs-lookup"><span data-stu-id="e0875-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="e0875-110">Prieš sukurdami naujas pagrindines paslaugas publikos įžvalgoms, patikrinkite, ar jos jau yra jūsų organizacijoje.</span><span class="sxs-lookup"><span data-stu-id="e0875-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="e0875-111">Ieškokite esančių pagrindinių paslaugų</span><span class="sxs-lookup"><span data-stu-id="e0875-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="e0875-112">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.</span><span class="sxs-lookup"><span data-stu-id="e0875-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="e0875-113">Pasirinkite **„Azure Active Directory“** iš „Azure“ paslaugų.</span><span class="sxs-lookup"><span data-stu-id="e0875-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="e0875-114">Skyriuje **Valdyti**, pasirinkite **Įmonės programos**.</span><span class="sxs-lookup"><span data-stu-id="e0875-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="e0875-115">Ieškokite publikos įžvalgų pirmosios šalies programos ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ar pavadinimo „`Dynamics 365 AI for Customer Insights`“.</span><span class="sxs-lookup"><span data-stu-id="e0875-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="e0875-116">Jei surasite atitinkamą įrašą, reiškia, kad pagrindinės paslaugos publikos įžvalgoms egzistuoja.</span><span class="sxs-lookup"><span data-stu-id="e0875-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="e0875-117">Jums nereikia dar kartą jo sukurti.</span><span class="sxs-lookup"><span data-stu-id="e0875-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Momentinė nuotrauka rodanti esančias pagrindines paslaugas.":::
   
6. <span data-ttu-id="e0875-119">Jei negaunama jokių rezultatų sukurkite naujas pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="e0875-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="e0875-120">Sukurkite naujas pagrindines paslaugas</span><span class="sxs-lookup"><span data-stu-id="e0875-120">Create a new service principal</span></span>

1. <span data-ttu-id="e0875-121">Įdiekite naujausią **„Azure Active Directory PowerShell for Graph“**.</span><span class="sxs-lookup"><span data-stu-id="e0875-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="e0875-122">Dėl daugiau informacijos, žr. [Diegti „Azure Active Directory PowerShell for Graph“](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="e0875-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="e0875-123">Jūsų kompiuteryje pasirinkite „Windows“ mygtuką jūsų klaviatūroje ir ieškokite **„Windows PowerShell“** ir **Vykdyti kaip adminstratoriui**.</span><span class="sxs-lookup"><span data-stu-id="e0875-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="e0875-124">„PowerShell“ atsivėrusiame lange įveskite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="e0875-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="e0875-125">Sukurkite pagrindines paslaugas publikos įžvalgoms su „Azure AD PowerShell Module“.</span><span class="sxs-lookup"><span data-stu-id="e0875-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="e0875-126">„PowerShell“ atsivėrusiame lange įveskite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="e0875-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="e0875-127">Pakeiskite „jūsų nuomotojo ID“ esančiu jūsų nuomotojo ID, kuriame norite sukurti pagrindines paslaugas.</span><span class="sxs-lookup"><span data-stu-id="e0875-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="e0875-128">Aplinkos pavadinimo parametras `AzureEnvironmentName` yra pasirinktinas.</span><span class="sxs-lookup"><span data-stu-id="e0875-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="e0875-129">Įveskite `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="e0875-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="e0875-130">Ši komanda sukuria pagrindines paslaugas publikos įžvalgoms pasirinktame nuomotojuje.</span><span class="sxs-lookup"><span data-stu-id="e0875-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="e0875-131">Suteikite leidimus pagrindinėms paslaugoms, kad jos prieitų prie talpinimo paskyros</span><span class="sxs-lookup"><span data-stu-id="e0875-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="e0875-132">Eikite į „Azure“ portalą tam, kad suteiktumėte leidimus pagrindinėms paslaugoms talpinimo paskyroje, kurioje norite naudoti publikos įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="e0875-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="e0875-133">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo organizacijos.</span><span class="sxs-lookup"><span data-stu-id="e0875-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="e0875-134">Atverkite talpinimo paskyrą, kurioje norite pagrindinių paslaugų prieigos prie publikos įžvalgų.</span><span class="sxs-lookup"><span data-stu-id="e0875-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="e0875-135">Pasirinkite **Prieigos valdymas (IAM)** iš naršymo juostos ir pasirinkite **Įtraukti** > **Įtraukti vaidmenis priskyrimą**.</span><span class="sxs-lookup"><span data-stu-id="e0875-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Momentinė ekrano nuotrauka rodanti „Azure“ portalą įtraukiant vaidmens priskyrimą.":::
   
1. <span data-ttu-id="e0875-137">**Įtraukti vaidmens priskyrimo** juostoje nustatykite šias ypatybes:</span><span class="sxs-lookup"><span data-stu-id="e0875-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="e0875-138">Vaidmuo: *„Storage Blob Data Contributor“*</span><span class="sxs-lookup"><span data-stu-id="e0875-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="e0875-139">Priskirkite prieigą prie: *Vartotojo, grupės ar pagrindinių paslaugų*</span><span class="sxs-lookup"><span data-stu-id="e0875-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="e0875-140">Pasirinkite: *„Dynamics 365 AI Customer Insights“* ( [jūsų sukurtos pagrindinės paslaugos](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="e0875-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="e0875-141">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="e0875-141">Select **Save**.</span></span>

<span data-ttu-id="e0875-142">Gali užtrukti iki 15 minučių, kol keitimai bus atlikti.</span><span class="sxs-lookup"><span data-stu-id="e0875-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="e0875-143">Įveskite „Azure“ išteklių ID arba „Azure“ prenumeravimo išsamią informaciją į talpinimo paskyros priedą prie publikos įžvalgų.</span><span class="sxs-lookup"><span data-stu-id="e0875-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="e0875-144">Pridėkite „Azure Data Lake“ talpinimo paskyrą publikos įžvalgose prie [talpinimo išvesties duomenų](manage-environments.md) ar [naudokite juos kaip duomenų šaltinį](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="e0875-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="e0875-145">Pasirinkus „Azure Data Lake“ parinktį ji leidžia jums rinktis tarp ištekliais pagrįstos ar prenumerata pagrįstos prieigos.</span><span class="sxs-lookup"><span data-stu-id="e0875-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="e0875-146">Atlikite tolesnius žingsnius tam, kad gautumėte reikiamą informaciją apie pasirinktą prieigą.</span><span class="sxs-lookup"><span data-stu-id="e0875-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="e0875-147">Ištekliais pagrįstos talpinimo paskyros jungtis</span><span class="sxs-lookup"><span data-stu-id="e0875-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="e0875-148">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="e0875-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="e0875-149">Eikite į **Nustatymai** > **Ypatybės** naršymo juostoje.</span><span class="sxs-lookup"><span data-stu-id="e0875-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="e0875-150">Kopijuokite talpinimo paskyros išteklių ID vertę.</span><span class="sxs-lookup"><span data-stu-id="e0875-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Kopijuokite talpinimo paskyros išteklių ID vertę.":::

1. <span data-ttu-id="e0875-152">Publikos įžvalgose įveskite išteklių ID išteklių laukelyje rodomame talpinimo paskyros jungties ekrane.</span><span class="sxs-lookup"><span data-stu-id="e0875-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::   
   
1. <span data-ttu-id="e0875-154">Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="e0875-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="e0875-155">Prenumerata pagrįstos talpinimo paskyros jungtis</span><span class="sxs-lookup"><span data-stu-id="e0875-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="e0875-156">Eikite į [„Azure“ administratoriaus portalą](https://portal.azure.com) ir prisijunkite prie savo prenumeratos ir atverkite talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="e0875-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="e0875-157">Eikite į **Nustatymai** > **Ypatybės** naršymo juostoje.</span><span class="sxs-lookup"><span data-stu-id="e0875-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="e0875-158">Peržiūrėkite **Prenumerata**, **Išteklių grupė** ir talpinimo paskyros **Pavadinimas** siekiant užsitikrinti, kad pasirinkote tinkamas vertes publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="e0875-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="e0875-159">Publikos įžvalgose pasirinkite vertes arba atitinkamus laukelius pridedant talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="e0875-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Įveskite talpinimo paskyros išteklių ID informaciją.":::
   
1. <span data-ttu-id="e0875-161">Tęskite likusius žingsnius publikos įžvalgose tam, kad pridėtumėte talpinimo paskyrą.</span><span class="sxs-lookup"><span data-stu-id="e0875-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
