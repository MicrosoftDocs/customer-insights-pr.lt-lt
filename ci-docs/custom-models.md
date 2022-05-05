---
title: Pasirinktiniai mašininio mokymo modeliai | „Microsoft Docs“
description: Darbas su pasirinktiniais modeliais iš „Azure“ mašininio mokymosi „Dynamics 365 Customer Insights“.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: f392c5cc5ac88a971565f0ccaf309ce89ce12660
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643201"
---
# <a name="custom-machine-learning-models"></a>Pasirinktiniai mašininio mokymo modeliai

> [!NOTE]
> "mašininis mokymas Studio" (klasikinis) palaikymas baigsis 2024 m. rugpjūčio 31 d. Rekomenduojame iki tos datos pereiti prie ["Azure mašininis mokymas](/azure/machine-learning/overview-what-is-azure-machine-learning)".
>
> Nuo 1 gruodžio 2021 negalėsite sukurti naujų mašininis mokymas Studijos (klasikinių) išteklių. Iki rugpjūčio 31 d. 2024 m. galite toliau naudoti esamus "mašininis mokymas Studio" (klasikinius) išteklius. Daugiau informacijos ieškokite [Migrate to Azure mašininis mokymas](/azure/machine-learning/migrate-overview).


**Įžvalga** > **Tinkinti modeliai** leidžia jums valdyti darbo eigas pagrįstas „Azure“ mašininio mokymosi modeliais. Darbo eigos padeda jums pasirinkti duomenis, iš kurių norite sukurti įžvalgas ir padaryti žemėlapių rezultatus į jūsų suvienodinto kliento duomenis. Dėl išsamesnės informacijos apie tinkintų ML modelių kūrimą, žr. [Naudoti „Azure“ mašininiu mokymusi pagrįstus modelius](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Atsakingas AI

Prognozės siūlo galimybes kurti geresnes kliento patirtis, pagerinti verslo galimybes ir pelno srautus. Primygtinai rekomenduojame jums subalansuoti jūsų prognozės vertę lyginant su poveikiu, kurį ji turi ir tendencijas, kurios gali būti pristatytos etiniu požiūriu. Sužinokite daugiau apie tai, kaip „Microsoft“ [rekomenduoja atsakingą AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Galite taip pat sužinoti apie [mašininio mokymosi procesų atsakomybę ir technikas](/azure/machine-learning/concept-responsible-ml) būdingas „Azure“ mašininiam mokymuisi.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Ši funkcija palaiko žiniatinklio tarnybas, paskelbtas naudojant ["Azure" mašininis mokymas paketinius vamzdynus](/azure/machine-learning/concept-ml-pipelines).

- Jums reikia „Azure Data Lake Gen2“ talpinimo paskyros susietos su „Azure“ studijos elementu siekiant naudoti šią funkciją. Daugiau informacijos rasite [„Azure Data Lake Storage Gen2“ saugyklos abonemento kūrimas](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Norint naudoti „Azure” mašininio mokymo darbo sritis su srautais, jums reikia savininko arba vartotojo prieigos administratoriaus teisių į „Azure” mašininio mokymo darbo sritį.

   > [!NOTE]
   > Duomenys perduodami tarp jūsų „Customer Insights” egzempliorių ir pasirinktų „Azure” žiniatinklio paslaugų arba srautų darbo eigoje. Kai perduodate duomenis į „Azure“ tarnybą, įsitikinkite, kad tarnyba sukonfigūruota taip, kad duomenų apdorojimas ir vieta atitiktų visus tokiems jūsų organizacijos duomenims taikomus teisinius arba norminius reikalavimus.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Naujos darbo eigos įtraukimas

1. Eikite į **Įžvalgą** > **Tinkinti modeliai** ir pasirinkite **Naują darbo eigą**.

1. Pasirinktiniam modeliui suteikite atpažįstamą pavadinimą lauke **Pavadinimas**.

   > [!div class="mx-imgBorder"]
   > ![Naujos darbo eigos srities ekrano kopija.](media/new-workflowv2.png "Naujos darbo eigos srities ekrano kopija")

1. Pasirinkite organizaciją, kurioje **Nuomininkas, kuriame yra jūsų žiniatinklio tarnyba** yra žiniatinklio tarnyba.

1. Jei jūsų „Azure Machine Learning“ prenumerata yra kitame nuomininke nei „Customer Insights“, pasirinktai organizacijai pasirinkite **Prisijungti** naudodami savo kredencialus.

1. Pasirinkite **Darbo aplinkas** susietas su jūsų žiniatinklio paslaugomis. 

1. Žiniatinklio tarnyboje, kurioje yra jūsų modelio **išplečiamasis sąrašas, pasirinkite**"Azure" mašininis mokymas. Tada pasirinkite **Toliau**.    
   Sužinokite apie [„Azure“ mašininio mokymosi vamzdyno publikavimą naudojant kūrimo įrankį](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ar [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Jūsų vamzdynas turi būti publikuojamas skyriuje [vamzdyno galutinis taškas](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Kiekvienai **Žiniatinklio tarnybos įvesčiai** pasirinkite atitinkamą **Objektą** iš „Customer Insights“ ir pasirinkite **Pirmyn**.
   > [!NOTE]
   > Pasirinktinio modelio darbo eiga taisys atributus, kuriuos naudojant žiniatinklio tarnybos įvesties laukai bus susieti su objekto atributais pagal lauko pavadinimą ir duomenų tipą. Matysite klaidą, jei žiniatinklio tarnybos lauko negalima susieti su objektu.

   > [!div class="mx-imgBorder"]
   > ![Darbo eigos konfigūravimas.](media/intelligence-screen2-updated.png "Darbo eigos konfigūravimas")

1. **Modelio išvesties parametrų** žingsnyje nustatykite tolesnes ypatybes:
      1. Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti vamzdyno išvestį.
      1. Pasirinkite jūsų bendro vamzdyno iš iškrentančio meniu **Išvesties duomenų talpinimo parametro pavadinimas**.
      1. Pasirinkite jūsų bendro vamzdyno iš iškrentančio meniu **Išvesties kelio parametro pavadinimas**.

      > [!div class="mx-imgBorder"]
      > ![Modelio išvesties parametro juosta.](media/intelligence-screen3-outputparameters.png "Modelio išvesties parametro juosta")

1. Pasirinkite gretinimo atributą iš **Kliento ID rezultatuose** išplečiamojo sąrašo, kuris nustato klientus ir rinkitės **Įrašyti**.

   > [!div class="mx-imgBorder"]
   > ![Susiekite rezultatus su kliento duomenų juosta.](media/intelligence-screen4-relatetocustomer.png "Susiekite rezultatus su kliento duomenų juosta")

1. Matysite ekraną **Darbo eiga įrašyta** su informacija apie darbo eigą.    
   Jei sukonfigūravote "Azure" mašininis mokymas vamzdyno darbo eigą, "Customer Insights" prideda prie darbo srities, kurioje yra vamzdynas. "Customer Insights" gaus **bendraautoriaus** vaidmenį "Azure" darbo srityje.

1. Pasirinkite **Atlikta**.

1. Dabar galite vykdyti darbo eigą iš **Tinkintų modelių** puslapio.

## <a name="edit-a-workflow"></a>Darbo eigos redagavimas

1. Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos ir pasirinkite **Redaguoti**.

1. Galite naujinti jūsų darbo eigos atpažįstamą pavadinimą **Rodomo pavadinimo** laukelyje, bet jūs negalite keisti konfigūruoto žiniatinklio paslaugų ar vamzdyno. Pasirinkite **Toliau**.

1. Kiekvienai **žiniatinklio tarnybos įvesčiai** galite atnaujinti atitinkamą **objektą** iš "Customer Insights". Tada pasirinkite **Toliau**.

1. **Modelio išvesties parametrų** žingsnyje nustatykite tolesnes ypatybes:
      1. Įveskite išvesties **Objekto pavadinimą**, į kurį norite įlieti vamzdyno išvestį.
      1. Pasirinkite **Išvesties duomenų talpinimo parametro pavadinimą** jūsų bandymo vamzdynui.
      1. Pasirinkite **Išvesties kelio parametro pavadinimą** jūsų bandymo vamzdynui.

1. Pasirinkite gretinimo atributą iš **Kliento ID rezultatuose** išplečiamojo sąrašo, kuris nustato klientus ir rinkitės **Įrašyti**.
   Pasirinkite atributą iš išvadų išvesties, kurios reikšmės panašios į kliento objekto stulpelį Kliento ID. Jei neturite tokio stulpelio savo duomenų rinkinyje, pasirinkite atributą, kuris atskirai atpažįsta eilutę.

## <a name="run-a-workflow"></a>Darbo eigos vykdymas

1. Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos.

1. Pasirinkite **Vykdyti**.

Jūsų darbo eiga taip pat vykdoma automatiškai kartu su visais suplanuotais atnaujinimais. Sužinokite daugiau apie [suplanuotų atnaujinimų nustatymą](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Darbo eigos naikinimas

1. Puslapyje **Pasirinktiniai modeliai** pasirinkite vertikalią elipsę stulpelyje **Veiksmai** prie jūsų anksčiau sukurtos darbo eigos.

1. Pasirinkite **Naikinti** ir patvirtinkite naikinimo veiksmą.

Jūsų darbo eiga bus panaikinta. [Objektas](entities.md), sukurtas kuriant darbo eigą, išliks ir gali būti peržiūrimas puslapyje **Objektai**.

## <a name="results"></a>Rezultatai

Darbo eigos rezultatai saugomi objekte, sukonfigūruotame modelio išvesties parametro etapo metu. Galite pasiekti šiuos duomenis iš [objektų puslapio](entities.md) arba su [API prieiga](apis.md).

### <a name="api-access"></a>API Prieiga

Konkrečiai „OData” užklausai, skirtai gauti duomenims iš pasirinktinio modelio objekto, naudokite šį formatą:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Pakeiskite `<your instance id>` į savo „Customer Insights” aplinkos ID, kurį rasite jūsų naršyklės adreso juostoje, kai pasiekiate „Customer Insights”.

1. Pakeiskite `<custom model output entity>` į objekto pavadinimą, kurį pateikėte pasirinktinio modelio konfigūracijos modelio išvesties parametrų veiksmo metu.

1. Pakeiskite `<guid value>` į kliento, kurio įrašą norite pasiekti, ID. Paprastai šį ID galite rasti [klientų profilių puslapyje](customer-profiles.md), esančiame Kliento ID lauke.

## <a name="frequently-asked-questions"></a>Dažnai užduodami klausimai

- Kodėl negaliu matyti savo srauto, kai nustatau pasirinktinę modelio darbo eigą?    
  Šią problemą dažnai sukelia srauto konfigūravimo problema. Užtikrinkite, kad [įvesties parametras yra sukonfigūruotas](azure-machine-learning-experiments.md#dataset-configuration) ir [išvesties duomenų saugyklos ir kelio parametrai](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) taip pat sukonfigūruoti.

- Ką reiškia klaida „Nepavyko įrašyti intelekto darbo eigos”?    
  Paprastai vartotojai mato šį klaidos pranešimą, jei jie neturi savininko arba vartotojo prieigos administratoriaus teisių darbo sričiai. Vartotojui reikalingos aukštesnio lygio teisės įgalinti „Customer Insights” apdoroti darbo eigą kaip paslaugą, o ne naudoti vartotojo kredencialus tolesniems darbo eigos vykdymams.

[!INCLUDE [footer-include](includes/footer-banner.md)]
