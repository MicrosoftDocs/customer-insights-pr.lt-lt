---
title: „Azure Machine Learning“ eksperimentai
description: Naudokite „Azure Machine Learning“ pagrįstus modelius „Dynamics 365 Customer Insights“.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668778"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="fe536-103">Naudokite „Azure Machine Learning“ pagrįstus modelius</span><span class="sxs-lookup"><span data-stu-id="fe536-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="fe536-104">Suvienodinti duomenys „Dynamics 365 Customer Insights“ yra šaltinis skirtas sukurti mašininio mokymosi modelius, kurie gali sukurti papildomas verslo įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="fe536-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="fe536-105">„Customer Insights“ integruojamos su „Machine Learning Studio“ (klasikine programa) ir „Azure Machine Learning“ siekiant naudoti jūsų turimus tinkintus modelius.</span><span class="sxs-lookup"><span data-stu-id="fe536-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="fe536-106">Žiūrėkite [„Machine Learning Studio“ (klasikinės programos) eksperimentus](machine-learning-studio-experiments.md) pavyzdžiams sukurtiems „Machine Learning Studio“ (klasikinėje programoje).</span><span class="sxs-lookup"><span data-stu-id="fe536-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="fe536-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="fe536-107">Prerequisites</span></span>

- <span data-ttu-id="fe536-108">Prieiga prie „Customer Insights“</span><span class="sxs-lookup"><span data-stu-id="fe536-108">Access to Customer Insights</span></span>
- <span data-ttu-id="fe536-109">Aktyvi „Azure Enterprise“ prenumerata</span><span class="sxs-lookup"><span data-stu-id="fe536-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="fe536-110">Sujungti klientų profiliai</span><span class="sxs-lookup"><span data-stu-id="fe536-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="fe536-111">[Objekto eksportavimas į „Azure Blob“ talpinimą](export-azure-blob-storage.md) sukonfigūruotas</span><span class="sxs-lookup"><span data-stu-id="fe536-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="fe536-112">Nustatyktie „Azure Machine Learning“ darbo aplinką</span><span class="sxs-lookup"><span data-stu-id="fe536-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="fe536-113">Žr. [sukurti „Azure Machine Learning“ darbo aplinką](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) skirtingoms parinktims siekiant sukurti darbo aplinką.</span><span class="sxs-lookup"><span data-stu-id="fe536-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="fe536-114">Geriausiam vykdymui, sukurkite darbo aplinką „Azure“ regione, kuris yra geografiškai artimiausias jūsų „Customer Insights“ aplinkai.</span><span class="sxs-lookup"><span data-stu-id="fe536-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="fe536-115">Prieikite prie savo darbo aplinkos per [„Azure Machine Learning Studio“](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="fe536-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="fe536-116">Yra keletas būdų [būdų sąveikauti](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) su jūsų darbo aplinka.</span><span class="sxs-lookup"><span data-stu-id="fe536-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="fe536-117">Dirbkite su „Azure Machine Learning“ kūrėju</span><span class="sxs-lookup"><span data-stu-id="fe536-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="fe536-118">„Azure Machine Learning“ kūrėjas pateikia vaizdinę drobę ten, kur galite nutempti ir numesti duomenų rinkinius ir modulius, panašius į „Machine Learning Studio“ (klasikinę programą).</span><span class="sxs-lookup"><span data-stu-id="fe536-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="fe536-119">Bendras vamzdynas sukurtas iš kūrėjo gali būti integruojamas į „Customer Insights“, jei jos yra atitinkamai sukonfigūruotos.</span><span class="sxs-lookup"><span data-stu-id="fe536-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="fe536-120">Darbas su „Azure Machine Learning“ SDK</span><span class="sxs-lookup"><span data-stu-id="fe536-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="fe536-121">Duomenų mokslininkai ir AI kūrėjai naudoja [„Azure Machine Learning“ SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) ttam, kad sukurtų mašininio mokymosi darbo eigas.</span><span class="sxs-lookup"><span data-stu-id="fe536-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="fe536-122">Šiuo metu modeliai ištreniruoti naudoti SDK negali būti integruoti tiesiogiai su „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="fe536-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="fe536-123">Bendros išvesties vamzdynas vartoja modelį, kuris turi būti integruotas su „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="fe536-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="fe536-124">Bendri vamzdyno reikalavimai integravimui su „Customer Insights“</span><span class="sxs-lookup"><span data-stu-id="fe536-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="fe536-125">Duomenų rinkinio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="fe536-125">Dataset Configuration</span></span>

<span data-ttu-id="fe536-126">Jums reikia kurti duomenų rinkinius tam, kad naudotumėte objekto duomenis iš „Customer Insights“ į savo bendrą išvesties vamzdyną.</span><span class="sxs-lookup"><span data-stu-id="fe536-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="fe536-127">Šie duomenų rinkiniai turi būti registruoti darbo aplinkoje.</span><span class="sxs-lookup"><span data-stu-id="fe536-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="fe536-128">Šiuo metu palaikome tik [lentelės duomenų rinkinius](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) .csv formatu.</span><span class="sxs-lookup"><span data-stu-id="fe536-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="fe536-129">Duomenų rinkiniai atitinka objekto duomenis turi būti su nustatytais parametrais kaip vamzdyno parametrai.</span><span class="sxs-lookup"><span data-stu-id="fe536-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="fe536-130">Duomenų rinkinio parametrai kūrimo įrankyje</span><span class="sxs-lookup"><span data-stu-id="fe536-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="fe536-131">Kūrimo įrankyje atverkite **Pasirinkti stulpelius duomenų rinkinyje** ir pasirinkite **Nustatyti kaip vamzdyno parametrą**, kai pateikiate parametrui pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="fe536-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="fe536-132">![Duomenų rinkinio parametrai kūrimo įrankyje](media/intelligence-designer-dataset-parameters.png "Duomenų rinkinio parametrai kūrimo įrankyje")</span><span class="sxs-lookup"><span data-stu-id="fe536-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="fe536-133">Duomenų rinkinio parametrai SDK („Python“)</span><span class="sxs-lookup"><span data-stu-id="fe536-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="fe536-134">Bendros išvesties vamzdynas</span><span class="sxs-lookup"><span data-stu-id="fe536-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="fe536-135">Kūrimo įrankyje mokymo vamzdynas gali būti naudojamas siekiant sukurti ar atnaujinti išvesties vamzdyną.</span><span class="sxs-lookup"><span data-stu-id="fe536-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="fe536-136">Šiuo metu tik bendri išvesties vamzdynai yra palaikomi.</span><span class="sxs-lookup"><span data-stu-id="fe536-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="fe536-137">Naudojant SDK galite publikuoti vamzdyną į galutinį tašką.</span><span class="sxs-lookup"><span data-stu-id="fe536-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="fe536-138">Šiuo metu „Customer Insights“ integruojamos su nustatytu vamzdynu bendro vamzdyno galutiniame taške mašininio mokymosi darbo aplinkoje.</span><span class="sxs-lookup"><span data-stu-id="fe536-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="fe536-139">Importuokite vamzdyno duomenis į „Customer Insights“</span><span class="sxs-lookup"><span data-stu-id="fe536-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="fe536-140">Kūrimo įrankis pateikia [Duomenų eksportavimo modulį](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) leidžiantį vamzdyno išvesčiai būti eksportuotai į „Azure“ talpinimą.</span><span class="sxs-lookup"><span data-stu-id="fe536-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="fe536-141">Šiuo metu modulis turi naudoti duomenų talpinimo tipą **„Azure Blob Storage“** ir nustatyti parametrus **Duomenų talpinime** ir atitinkamą **Kelią**.</span><span class="sxs-lookup"><span data-stu-id="fe536-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="fe536-142">„Customer Insights“ viršyja abu šiuos parametrus vamzdyno vykdymo metu su duomenų talpinimu ir keliu, kuris prieinamas produktui.</span><span class="sxs-lookup"><span data-stu-id="fe536-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fe536-143">![Eksportuoti duomenų modulio konfigūravimą](media/intelligence-designer-importdata.png "Eksportuoti duomenų modulio konfigūravimą")</span><span class="sxs-lookup"><span data-stu-id="fe536-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="fe536-144">Rašant išvesties išvestį su kodu, galite įkelti išvestį į kelią su *registruotu duomenų talpinimu* darbo aplinkoje.</span><span class="sxs-lookup"><span data-stu-id="fe536-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="fe536-145">Jei keliui ir duomenų talpinimui vamzdyne yra nustatomi parametrai, tinkintos „Customer Insights“ galės nuskaityti ir importuoti išvesties išvestį.</span><span class="sxs-lookup"><span data-stu-id="fe536-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="fe536-146">Šiuo metu yra palaikoma atskira lentelės išvestis csv formatu.</span><span class="sxs-lookup"><span data-stu-id="fe536-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="fe536-147">Kelias turi apimti katalogą ir failo pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="fe536-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```
