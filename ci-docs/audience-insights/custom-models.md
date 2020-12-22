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
# <a name="custom-machine-learning-models"></a>Pasirinktiniai mašininio mokymo modeliai

**Įžvalga** > **Tinkinti modeliai** leidžia jums valdyti darbo eigas pagrįstas „Azure“ mašininio mokymosi modeliais. Darbo eigos padeda jums pasirinkti duomenis, iš kurių norite sukurti įžvalgas ir padaryti žemėlapių rezultatus į jūsų suvienodinto kliento duomenis. Dėl išsamesnės informacijos apie tinkintų ML modelių kūrimą, žr. [Naudoti „Azure“ mašininiu mokymusi pagrįstus modelius](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Atsakingas AI

Prognozės siūlo galimybes kurti geresnes kliento patirtis, pagerinti verslo galimybes ir pelno srautus. Primygtinai rekomenduojame jums subalansuoti jūsų prognozės vertę lyginant su poveikiu, kurį ji turi ir tendencijas, kurios gali būti pristatytos etiniu požiūriu. Sužinokite daugiau apie tai, kaip „Microsoft“ [rekomenduoja atsakingą AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Galite taip pat sužinoti apie [mašininio mokymosi procesų atsakomybę ir technikas](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) būdingas „Azure“ mašininiam mokymuisi.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Šiuo metu ši funkcija palaiko žiniatinklio paslaugas publikuotas per [mašininio mokymosi studiją (įprastą versiją)](https://studio.azureml.net) ir [„Azure“ mašininio mokymosi bendrus vamzdynus](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Jums reikia „Azure Data Lake Gen2“ talpinimo paskyros susietos su „Azure“ studijos elementu siekiant naudoti šią funkciją. Daugiau informacijos žr. [„Azure Data Lake Storage Gen2“ saugyklos kliento kūrimas](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Naujos darbo eigos įtraukimas

1. Eikite į **Įžvalgą** > **Tinkinti modeliai** ir pasirinkite **Naują darbo eigą**.

1. Pasirinktiniam modeliui suteikite atpažįstamą pavadinimą lauke **Pavadinimas**.

   > [!div class="mx-imgBorder"]
   > ![Naujos darbo eigos srities ekrano kopija](media/new-workflowv2.png "Naujos darbo eigos srities ekrano kopija")

1. Pasirinkite organizaciją, kurioje **Nuomininkas, kuriame yra jūsų žiniatinklio tarnyba** yra žiniatinklio tarnyba.

1. Jei jūsų „Azure Machine Learning“ prenumerata yra kitame nuomininke nei „Customer Insights“, pasirinktai organizacijai pasirinkite **Prisijungti** naudodami savo kredencialus.

1. Pasirinkite **Darbo aplinkas** susietas su jūsų žiniatinklio paslaugomis. Esama dviejų išvardytų skyrių, „Azure“ mašininio mokymosi v1 (mašininio mokymosi studijos (įprastos versijos)) ir „Azure“ mašininio mokymosi v2 („Azure“ mašininio mokymosi). Jei nesate tikras, kuri darbo aplinka tinka jūsų mašininio mokymosi studijai (įprastos) versijos žiniatinklio paslaugoms, pasirinkite **Bet kuris**.

1. Pasirinkite mašininio mokymosi studijos (įprastos versijos) žiniatinklio paslaugas arba „Azure“ mašininio mokymosi vamzdyną **Žiniatinklio paslaugos, turinčios jūsų modelio** iškrentantį meniu. Tada pasirinkite **Toliau**.
   - Sužinokite apie [žiniatinklio paslaugų publikavimą mašininio mokymosi studijoje (įprastoje versijoje)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Sužinokite apie [„Azure“ mašininio mokymosi vamzdyno publikavimą naudojant kūrimo įrankį](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ar [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). 
     > [!NOTE]
     > Jūsų vamzdynas turi būti publikuojamas skyriuje [vamzdyno galutinis taškas](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Kiekvienai **Žiniatinklio paslaugos įvesčiai**, pasirinkite atitinkantį **Objektą** iš publikos įžvalgų ir pasirinkite **Kitas**.

   > [!div class="mx-imgBorder"]
   > ![Darbo eigos konfigūravimas](media/intelligence-screen2-updated.png "Darbo eigos konfigūravimas")

1. **Modelio išvesties parametrų** žingsnyje nustatykite tolesnes ypatybes:
   - Mašininio mokymosi studija (įprasta versija)
      1. Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti žiniatinklio išvesties rezultatus.
   - „Azure“ mašininis mokymas
      1. Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti vamzdyno išvestį.
      1. Pasirinkite jūsų bendro vamzdyno iš iškrentančio meniu **Išvesties duomenų talpinimo parametro pavadinimas**.
      1. Pasirinkite jūsų bendro vamzdyno iš iškrentančio meniu **Išvesties kelio parametro pavadinimas**.
      
      > [!div class="mx-imgBorder"]
      > ![Modelio išvesties parametro juosta](media/intelligence-screen3-outputparameters.png "Modelio išvesties parametro juosta")

1. Pasirinkite atitikties atributą iš **Kliento ID rezultatuose** iškrentančio meniu, kuris nurodo klientus ir pasirinkite **Įrašyti**.
   
   > [!div class="mx-imgBorder"]
   > ![Susiekite rezultatus su kliento duomenų juosta](media/intelligence-screen4-relatetocustomer.png "Susiekite rezultatus su kliento duomenų juosta")

1. Matysite ekraną **Darbo eiga įrašyta** su informacija apie darbo eigą.    
   Jei konfigūruojate darbo eigą „Azure“ mašininio mokymosi vamzdynui, publikos įžvalgos bus pridėtos prie darbo aplinkos, kuri turi vamzdyną. Publikos įžvalgos įgaus  **Prisidėjusiojo** vaidmenį „Azure“ darbo aplinkoje.

1. Pasirinkite **Atlikta**.

1. Dabar galite vykdyti darbo eigą iš **Tinkintų modelių** puslapio.

## <a name="edit-a-workflow"></a>Darbo eigos redagavimas

1. Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos ir pasirinkite **Redaguoti**.

1. Galite naujinti jūsų darbo eigos atpažįstamą pavadinimą **Rodomo pavadinimo** laukelyje, bet jūs negalite keisti konfigūruoto žiniatinklio paslaugų ar vamzdyno. Pasirinkite **Toliau**.

1. Kiekvienai **Žiniatinklio paslaugos įvesčiai**, galite naujinti atitikties **Objektą** iš publikos įžvalgų. Tada pasirinkite **Toliau**.

1. **Modelio išvesties parametrų** žingsnyje nustatykite tolesnes ypatybes:
   - Mašininio mokymosi studija (įprasta versija)
      1. Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti žiniatinklio išvesties rezultatus.
   - „Azure“ mašininis mokymas
      1. Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti vamzdyno išvestį.
      1. Pasirinkite **Išvesties duomenų talpinimo parametro pavadinimą** jūsų bandymo vamzdynui.
      1. Pasirinkite **Išvesties kelio parametro pavadinimą** jūsų bandymo vamzdynui.

1. Pasirinkite atitikties atributą iš **Kliento ID rezultatuose** iškrentančio meniu, kuris nurodo klientus ir pasirinkite **Įrašyti**.
   Jums reikia pasirinkti atributą iš išvados išvesties su vertėmis panašiomis į kliento objekto kliento ID stulpelį. Jei neturite tokio stulpelio savo duomenų rinkinyje, pasirinkite atributą, kuris atskirai atpažįsta eilutę.

## <a name="run-a-workflow"></a>Darbo eigos vykdymas

1. Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos.

1. Pasirinkite **Vykdyti**.

Jūsų darbo eiga taip pat vykdoma automatiškai kartu su visais suplanuotais atnaujinimais. Sužinokite daugiau apie [suplanuotų atnaujinimų nustatymą](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Darbo eigos naikinimas

1. Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos.

1. Pasirinkite **Naikinti** ir patvirtinkite naikinimo veiksmą.

Jūsų darbo eiga bus panaikinta. [Objektas](entities.md), sukurtas kuriant darbo eigą, išliks ir gali būti peržiūrimas puslapyje **Objektai**.
