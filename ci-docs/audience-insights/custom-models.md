---
title: Pasirinktiniai mašininio mokymo modeliai | „Microsoft Docs“
description: Darbas su pasirinktiniais modeliais iš „Azure“ mašininio mokymosi „Dynamics 365 Customer Insights“.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668913"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="1fd01-103">Pasirinktiniai mašininio mokymo modeliai</span><span class="sxs-lookup"><span data-stu-id="1fd01-103">Custom machine learning models</span></span>

<span data-ttu-id="1fd01-104">**Įžvalga** > **Tinkinti modeliai** leidžia jums valdyti darbo eigas pagrįstas „Azure“ mašininio mokymosi modeliais.</span><span class="sxs-lookup"><span data-stu-id="1fd01-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="1fd01-105">Darbo eigos padeda jums pasirinkti duomenis, iš kurių norite sukurti įžvalgas ir padaryti žemėlapių rezultatus į jūsų suvienodinto kliento duomenis.</span><span class="sxs-lookup"><span data-stu-id="1fd01-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="1fd01-106">Dėl išsamesnės informacijos apie tinkintų ML modelių kūrimą, žr. [Naudoti „Azure“ mašininiu mokymusi pagrįstus modelius](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="1fd01-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="1fd01-107">Atsakingas AI</span><span class="sxs-lookup"><span data-stu-id="1fd01-107">Responsible AI</span></span>

<span data-ttu-id="1fd01-108">Prognozės siūlo galimybes kurti geresnes kliento patirtis, pagerinti verslo galimybes ir pelno srautus.</span><span class="sxs-lookup"><span data-stu-id="1fd01-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="1fd01-109">Primygtinai rekomenduojame jums subalansuoti jūsų prognozės vertę lyginant su poveikiu, kurį ji turi ir tendencijas, kurios gali būti pristatytos etiniu požiūriu.</span><span class="sxs-lookup"><span data-stu-id="1fd01-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="1fd01-110">Sužinokite daugiau apie tai, kaip „Microsoft“ [rekomenduoja atsakingą AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="1fd01-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="1fd01-111">Galite taip pat sužinoti apie [mašininio mokymosi procesų atsakomybę ir technikas](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) būdingas „Azure“ mašininiam mokymuisi.</span><span class="sxs-lookup"><span data-stu-id="1fd01-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fd01-112">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="1fd01-112">Prerequisites</span></span>

- <span data-ttu-id="1fd01-113">Šiuo metu ši funkcija palaiko žiniatinklio paslaugas publikuotas per [mašininio mokymosi studiją (įprastą versiją)](https://studio.azureml.net) ir [„Azure“ mašininio mokymosi bendrus vamzdynus](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="1fd01-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="1fd01-114">Jums reikia „Azure Data Lake Gen2“ talpinimo paskyros susietos su „Azure“ studijos elementu siekiant naudoti šią funkciją.</span><span class="sxs-lookup"><span data-stu-id="1fd01-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="1fd01-115">Daugiau informacijos žr. [„Azure Data Lake Storage Gen2“ saugyklos kliento kūrimas](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="1fd01-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="1fd01-116">Naujos darbo eigos įtraukimas</span><span class="sxs-lookup"><span data-stu-id="1fd01-116">Add a new workflow</span></span>

1. <span data-ttu-id="1fd01-117">Eikite į **Įžvalgą** > **Tinkinti modeliai** ir pasirinkite **Naują darbo eigą**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="1fd01-118">Pasirinktiniam modeliui suteikite atpažįstamą pavadinimą lauke **Pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fd01-119">![Naujos darbo eigos srities ekrano kopija](media/new-workflowv2.png "Naujos darbo eigos srities ekrano kopija")</span><span class="sxs-lookup"><span data-stu-id="1fd01-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="1fd01-120">Pasirinkite organizaciją, kurioje **Nuomininkas, kuriame yra jūsų žiniatinklio tarnyba** yra žiniatinklio tarnyba.</span><span class="sxs-lookup"><span data-stu-id="1fd01-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="1fd01-121">Jei jūsų „Azure Machine Learning“ prenumerata yra kitame nuomininke nei „Customer Insights“, pasirinktai organizacijai pasirinkite **Prisijungti** naudodami savo kredencialus.</span><span class="sxs-lookup"><span data-stu-id="1fd01-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="1fd01-122">Pasirinkite **Darbo aplinkas** susietas su jūsų žiniatinklio paslaugomis.</span><span class="sxs-lookup"><span data-stu-id="1fd01-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="1fd01-123">Esama dviejų išvardytų skyrių, „Azure“ mašininio mokymosi v1 (mašininio mokymosi studijos (įprastos versijos)) ir „Azure“ mašininio mokymosi v2 („Azure“ mašininio mokymosi).</span><span class="sxs-lookup"><span data-stu-id="1fd01-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="1fd01-124">Jei nesate tikras, kuri darbo aplinka tinka jūsų mašininio mokymosi studijai (įprastos) versijos žiniatinklio paslaugoms, pasirinkite **Bet kuris**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="1fd01-125">Pasirinkite mašininio mokymosi studijos (įprastos versijos) žiniatinklio paslaugas arba „Azure“ mašininio mokymosi vamzdyną **Žiniatinklio paslaugos, turinčios jūsų modelio** iškrentantį meniu.</span><span class="sxs-lookup"><span data-stu-id="1fd01-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="1fd01-126">Tada pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="1fd01-127">Sužinokite apie [žiniatinklio paslaugų publikavimą mašininio mokymosi studijoje (įprastoje versijoje)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="1fd01-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="1fd01-128">Sužinokite apie [„Azure“ mašininio mokymosi vamzdyno publikavimą naudojant kūrimo įrankį](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ar [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="1fd01-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="1fd01-129">Jūsų vamzdynas turi būti publikuojamas skyriuje [vamzdyno galutinis taškas](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="1fd01-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="1fd01-130">Kiekvienai **Žiniatinklio paslaugos įvesčiai**, pasirinkite atitinkantį **Objektą** iš publikos įžvalgų ir pasirinkite **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fd01-131">![Darbo eigos konfigūravimas](media/intelligence-screen2-updated.png "Darbo eigos konfigūravimas")</span><span class="sxs-lookup"><span data-stu-id="1fd01-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="1fd01-132">**Modelio išvesties parametrų** žingsnyje nustatykite tolesnes ypatybes:</span><span class="sxs-lookup"><span data-stu-id="1fd01-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1fd01-133">Mašininio mokymosi studija (įprasta versija)</span><span class="sxs-lookup"><span data-stu-id="1fd01-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1fd01-134">Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti žiniatinklio išvesties rezultatus.</span><span class="sxs-lookup"><span data-stu-id="1fd01-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1fd01-135">„Azure“ mašininis mokymas</span><span class="sxs-lookup"><span data-stu-id="1fd01-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1fd01-136">Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti vamzdyno išvestį.</span><span class="sxs-lookup"><span data-stu-id="1fd01-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1fd01-137">Pasirinkite jūsų bendro vamzdyno iš iškrentančio meniu **Išvesties duomenų talpinimo parametro pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="1fd01-138">Pasirinkite jūsų bendro vamzdyno iš iškrentančio meniu **Išvesties kelio parametro pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1fd01-139">![Modelio išvesties parametro juosta](media/intelligence-screen3-outputparameters.png "Modelio išvesties parametro juosta")</span><span class="sxs-lookup"><span data-stu-id="1fd01-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="1fd01-140">Pasirinkite atitikties atributą iš **Kliento ID rezultatuose** iškrentančio meniu, kuris nurodo klientus ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fd01-141">![Susiekite rezultatus su kliento duomenų juosta](media/intelligence-screen4-relatetocustomer.png "Susiekite rezultatus su kliento duomenų juosta")</span><span class="sxs-lookup"><span data-stu-id="1fd01-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="1fd01-142">Matysite ekraną **Darbo eiga įrašyta** su informacija apie darbo eigą.</span><span class="sxs-lookup"><span data-stu-id="1fd01-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="1fd01-143">Jei konfigūruojate darbo eigą „Azure“ mašininio mokymosi vamzdynui, publikos įžvalgos bus pridėtos prie darbo aplinkos, kuri turi vamzdyną.</span><span class="sxs-lookup"><span data-stu-id="1fd01-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="1fd01-144">Publikos įžvalgos įgaus  **Prisidėjusiojo** vaidmenį „Azure“ darbo aplinkoje.</span><span class="sxs-lookup"><span data-stu-id="1fd01-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="1fd01-145">Pasirinkite **Atlikta**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-145">Select **Done**.</span></span>

1. <span data-ttu-id="1fd01-146">Dabar galite vykdyti darbo eigą iš **Tinkintų modelių** puslapio.</span><span class="sxs-lookup"><span data-stu-id="1fd01-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="1fd01-147">Darbo eigos redagavimas</span><span class="sxs-lookup"><span data-stu-id="1fd01-147">Edit a workflow</span></span>

1. <span data-ttu-id="1fd01-148">Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos ir pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="1fd01-149">Galite naujinti jūsų darbo eigos atpažįstamą pavadinimą **Rodomo pavadinimo** laukelyje, bet jūs negalite keisti konfigūruoto žiniatinklio paslaugų ar vamzdyno.</span><span class="sxs-lookup"><span data-stu-id="1fd01-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="1fd01-150">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-150">Select **Next**.</span></span>

1. <span data-ttu-id="1fd01-151">Kiekvienai **Žiniatinklio paslaugos įvesčiai**, galite naujinti atitikties **Objektą** iš publikos įžvalgų.</span><span class="sxs-lookup"><span data-stu-id="1fd01-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="1fd01-152">Tada pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="1fd01-153">**Modelio išvesties parametrų** žingsnyje nustatykite tolesnes ypatybes:</span><span class="sxs-lookup"><span data-stu-id="1fd01-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1fd01-154">Mašininio mokymosi studija (įprasta versija)</span><span class="sxs-lookup"><span data-stu-id="1fd01-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1fd01-155">Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti žiniatinklio išvesties rezultatus.</span><span class="sxs-lookup"><span data-stu-id="1fd01-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1fd01-156">„Azure“ mašininis mokymas</span><span class="sxs-lookup"><span data-stu-id="1fd01-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1fd01-157">Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti vamzdyno išvestį.</span><span class="sxs-lookup"><span data-stu-id="1fd01-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1fd01-158">Pasirinkite **Išvesties duomenų talpinimo parametro pavadinimą** jūsų bandymo vamzdynui.</span><span class="sxs-lookup"><span data-stu-id="1fd01-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="1fd01-159">Pasirinkite **Išvesties kelio parametro pavadinimą** jūsų bandymo vamzdynui.</span><span class="sxs-lookup"><span data-stu-id="1fd01-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="1fd01-160">Pasirinkite atitikties atributą iš **Kliento ID rezultatuose** iškrentančio meniu, kuris nurodo klientus ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="1fd01-161">Jums reikia pasirinkti atributą iš išvados išvesties su vertėmis panašiomis į kliento objekto kliento ID stulpelį.</span><span class="sxs-lookup"><span data-stu-id="1fd01-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="1fd01-162">Jei neturite tokio stulpelio savo duomenų rinkinyje, pasirinkite atributą, kuris atskirai atpažįsta eilutę.</span><span class="sxs-lookup"><span data-stu-id="1fd01-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="1fd01-163">Darbo eigos vykdymas</span><span class="sxs-lookup"><span data-stu-id="1fd01-163">Run a workflow</span></span>

1. <span data-ttu-id="1fd01-164">Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos.</span><span class="sxs-lookup"><span data-stu-id="1fd01-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1fd01-165">Pasirinkite **Vykdyti**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-165">Select **Run**.</span></span>

<span data-ttu-id="1fd01-166">Jūsų darbo eiga taip pat vykdoma automatiškai kartu su visais suplanuotais atnaujinimais.</span><span class="sxs-lookup"><span data-stu-id="1fd01-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="1fd01-167">Sužinokite daugiau apie [suplanuotų atnaujinimų nustatymą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1fd01-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="1fd01-168">Darbo eigos naikinimas</span><span class="sxs-lookup"><span data-stu-id="1fd01-168">Delete a workflow</span></span>

1. <span data-ttu-id="1fd01-169">Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos.</span><span class="sxs-lookup"><span data-stu-id="1fd01-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1fd01-170">Pasirinkite **Naikinti** ir patvirtinkite naikinimo veiksmą.</span><span class="sxs-lookup"><span data-stu-id="1fd01-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="1fd01-171">Jūsų darbo eiga bus panaikinta.</span><span class="sxs-lookup"><span data-stu-id="1fd01-171">Your workflow will be deleted.</span></span> <span data-ttu-id="1fd01-172">[Objektas](entities.md), sukurtas kuriant darbo eigą, išliks ir gali būti peržiūrimas puslapyje **Objektai**.</span><span class="sxs-lookup"><span data-stu-id="1fd01-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
