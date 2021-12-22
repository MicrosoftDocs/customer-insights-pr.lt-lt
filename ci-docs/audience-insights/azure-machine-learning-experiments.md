---
title: „Azure Machine Learning“ eksperimentai
description: Naudokite „Azure Machine Learning“ pagrįstus modelius „Dynamics 365 Customer Insights“.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881748"
---
# <a name="use-azure-machine-learning-based-models"></a>Naudokite „Azure Machine Learning“ pagrįstus modelius

Suvienodinti duomenys „Dynamics 365 Customer Insights“ yra šaltinis skirtas sukurti mašininio mokymosi modelius, kurie gali sukurti papildomas verslo įžvalgas. „Customer Insights” integruojamas su „Azure“ mašininiu mokymu, kad galėtumėte naudoti pasirinktinius modelius.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Prieiga prie „Customer Insights“
- Aktyvi „Azure Enterprise“ prenumerata
- [Sujungti klientų profiliai](data-unification.md)
- [Objekto eksportavimas į „Azure Blob“ talpinimą](export-azure-blob-storage.md) sukonfigūruotas

## <a name="set-up-azure-machine-learning-workspace"></a>Nustatykite „Azure Machine Learning“ darbo aplinką

1. Žr. [sukurti „Azure Machine Learning“ darbo aplinką](/azure/machine-learning/concept-workspace#-create-a-workspace) skirtingoms parinktims siekiant sukurti darbo aplinką. Geriausiam vykdymui, sukurkite darbo aplinką „Azure“ regione, kuris yra geografiškai artimiausias jūsų „Customer Insights“ aplinkai.

1. Prieikite prie savo darbo aplinkos per [„Azure Machine Learning Studio“](https://ml.azure.com/). Yra keletas būdų [būdų sąveikauti](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) su jūsų darbo aplinka.

## <a name="work-with-azure-machine-learning-designer"></a>Dirbkite su „Azure Machine Learning“ kūrėju

"Azure mašininis mokymas designer" pateikia vaizdinę drobę, kurioje galite vilkti ir numesti duomenų rinkinius ir modulius. Bendras vamzdynas sukurtas iš kūrėjo gali būti integruojamas į „Customer Insights“, jei jos yra atitinkamai sukonfigūruotos. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Darbas su „Azure Machine Learning“ SDK

Duomenų mokslininkai ir AI kūrėjai naudoja [„Azure Machine Learning“ SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) tam, kad sukurtų mašininio mokymosi darbo eigas. Šiuo metu modeliai ištreniruoti naudoti SDK negali būti integruoti tiesiogiai su „Customer Insights“. Bendros išvesties vamzdynas vartoja modelį, kuris turi būti integruotas su „Customer Insights“.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Bendri vamzdyno reikalavimai integravimui su „Customer Insights“

### <a name="dataset-configuration"></a>Duomenų rinkinio konfigūravimas

Jums reikia kurti duomenų rinkinius tam, kad naudotumėte objekto duomenis iš „Customer Insights“ į savo bendrą išvesties vamzdyną. Šie duomenų rinkiniai turi būti registruoti darbo aplinkoje. Šiuo metu palaikome tik [lentelės duomenų rinkinius](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) .csv formatu. Duomenų rinkiniai atitinka objekto duomenis turi būti su nustatytais parametrais kaip vamzdyno parametrai.
   
* Duomenų rinkinio parametrai kūrimo įrankyje
   
     Kūrimo įrankyje atverkite **Pasirinkti stulpelius duomenų rinkinyje** ir pasirinkite **Nustatyti kaip vamzdyno parametrą**, kai pateikiate parametrui pavadinimą.

     > [!div class="mx-imgBorder"]
     > ![Duomenų rinkinio parametrai kūrimo įrankyje.](media/intelligence-designer-dataset-parameters.png "Duomenų rinkinio parametrai kūrimo įrankyje")
   
* Duomenų rinkinio parametrai SDK („Python“)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Bendros išvesties vamzdynas
  
* Kūrimo įrankyje mokymo vamzdynas gali būti naudojamas siekiant sukurti ar atnaujinti išvesties vamzdyną. Šiuo metu tik bendri išvesties vamzdynai yra palaikomi.

* Naudojant SDK galite publikuoti vamzdyną į galutinį tašką. Šiuo metu „Customer Insights“ integruojamos su nustatytu vamzdynu bendro vamzdyno galutiniame taške mašininio mokymosi darbo aplinkoje.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importuokite vamzdyno duomenis į „Customer Insights“

* Kūrimo įrankis pateikia [Duomenų eksportavimo modulį](/azure/machine-learning/algorithm-module-reference/export-data) leidžiantį vamzdyno išvesčiai būti eksportuotai į „Azure“ talpinimą. Šiuo metu modulis turi naudoti duomenų talpinimo tipą **„Azure Blob Storage“** ir nustatyti parametrus **Duomenų talpinime** ir atitinkamą **Kelią**. „Customer Insights“ perrašo abu šiuos parametrus vamzdyno vykdymo metu su duomenų talpinimu ir keliu, kuris prieinamas produktui.
   > [!div class="mx-imgBorder"]
   > ![Eksportuoti duomenų modulio konfigūravimą.](media/intelligence-designer-importdata.png "Eksportuoti duomenų modulio konfigūravimą")
   
* Rašant išvesties išvestį su kodu, galite įkelti išvestį į kelią su *registruotu duomenų talpinimu* darbo aplinkoje. Jei keliui ir duomenų talpinimui vamzdyne yra nustatomi parametrai, tinkintos „Customer Insights“ galės nuskaityti ir importuoti išvesties išvestį. Šiuo metu yra palaikoma atskira lentelės išvestis csv formatu. Kelias turi apimti katalogą ir failo pavadinimą.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]