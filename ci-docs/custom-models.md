---
title: Pasirinktiniai mašininio mokymo modeliai | „Microsoft Docs“
description: Darbas su pasirinktiniais modeliais iš „Azure“ mašininio mokymosi „Dynamics 365 Customer Insights“.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609756"
---
# <a name="custom-machine-learning-models"></a>Pasirinktiniai mašininio mokymo modeliai

> [!NOTE]
> "mašininis mokymas Studio" (klasika) palaikymas baigsis 2024 m. rugpjūčio 31 d. Rekomenduojame pereiti prie ["Azure mašininis mokymas](/azure/machine-learning/overview-what-is-azure-machine-learning) iki tos datos.
>
> Nuo 2021 m. gruodžio 1 d. negalėsite kurti naujų mašininis mokymas studijos (klasikinių) išteklių. Iki 2024 m. rugpjūčio 31 d. galite toliau naudoti esamus "mašininis mokymas Studio" (klasikinius) išteklius. Daugiau informacijos ieškokite [Perkėlimas į "Azure" mašininis mokymas](/azure/machine-learning/migrate-overview).

Pasirinktiniai modeliai leidžia valdyti darbo eigas pagal "Azure" mašininis mokymas modelius. Darbo eigos padeda jums pasirinkti duomenis, iš kurių norite sukurti įžvalgas ir padaryti žemėlapių rezultatus į jūsų suvienodinto kliento duomenis. Dėl išsamesnės informacijos apie tinkintų ML modelių kūrimą, žr. [Naudoti „Azure“ mašininiu mokymusi pagrįstus modelius](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Žiniatinklio paslaugos, paskelbtos per ["Azure" mašininis mokymas paketinius vamzdynus](/azure/machine-learning/concept-ml-pipelines).
- Dujotiekis turi būti skelbiamas pagal dujotiekio galinį [punktą](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- " [Azure Data Lake Gen2" saugyklos paskyra,](/azure/storage/blobs/data-lake-storage-quickstart-create-account) susieta su jūsų "Azure Studio" egzemplioriumi.
- Jei naudojate "Azure" mašininis mokymas darbo sritis su vamzdynais, savininko arba vartotojo prieigos administratoriaus teises į "Azure mašininis mokymas Workspace".

  > [!NOTE]
  > Duomenys perduodami tarp jūsų „Customer Insights” egzempliorių ir pasirinktų „Azure” žiniatinklio paslaugų arba srautų darbo eigoje. Kai perduodate duomenis į „Azure“ tarnybą, įsitikinkite, kad tarnyba sukonfigūruota taip, kad duomenų apdorojimas ir vieta atitiktų visus tokiems jūsų organizacijos duomenims taikomus teisinius arba norminius reikalavimus.

## <a name="add-a-new-workflow"></a>Naujos darbo eigos įtraukimas

1. Eikite į **Įžvalgą** > **Tinkinti modeliai** ir pasirinkite **Naują darbo eigą**.

1. Pateikite atpažįstamą **vardą**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Naujos darbo eigos srities ekrano kopija.":::

1. Pasirinkite organizaciją, kurioje **Nuomininkas, kuriame yra jūsų žiniatinklio tarnyba** yra žiniatinklio tarnyba.

1. Jei jūsų „Azure Machine Learning“ prenumerata yra kitame nuomininke nei „Customer Insights“, pasirinktai organizacijai pasirinkite **Prisijungti** naudodami savo kredencialus.

1. Pasirinkite **Darbo aplinkas** susietas su jūsų žiniatinklio paslaugomis.

1. Pasirinkite "Azure mašininis mokymas" srautą žiniatinklio **tarnyboje, kurioje yra jūsų modelio** išskleidžiamasis meniu. Tada pasirinkite **Toliau**.
   Sužinokite apie [„Azure“ mašininio mokymosi vamzdyno publikavimą naudojant kūrimo įrankį](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ar [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Kiekvienai **Žiniatinklio tarnybos įvesčiai** pasirinkite atitinkamą **Objektą** iš „Customer Insights“. Tada pasirinkite **Toliau**.
   > [!NOTE]
   > Pasirinktinio modelio darbo eiga taisys atributus, kuriuos naudojant žiniatinklio tarnybos įvesties laukai bus susieti su objekto atributais pagal lauko pavadinimą ir duomenų tipą. Matysite klaidą, jei žiniatinklio tarnybos lauko negalima susieti su objektu.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Darbo eigos konfigūravimas.":::

1. Modelio **išvesties parametrams** nustatykite šias ypatybes:
   - **Vamzdyno išvesties rezultatų objekto pavadinimas**
   - **Išvesties duomenų saugykla paketinio vamzdyno parametro pavadinimas**
   - **Išvesties kelio parametro pavadinimas** jūsų paketiniame vamzdyne

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Modelio išvesties parametro juosta.":::

1. Rezultatuose **pasirinkite atitikimo atributą iš** kliento ID, kuris identifikuoja klientus, ir pasirinkite **Įrašyti**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Susiekite rezultatus su kliento duomenų juosta.":::

   Ekrane **Darbo eigos įrašymas** rodoma išsami informacija apie darbo eigą. Jei sukonfigūravote "Azure mašininis mokymas" srauto darbo eigą, "Customer Insights" prideda prie darbo srities, kurioje yra srautas. "Customer Insights" gaus **bendraautorio** vaidmenį "Azure" darbo srityje.

1. Pasirinkite **Atlikta**. Rodomas **puslapis Pasirinktiniai modeliai**.

1. Pasirinkite vertikalią darbo eigos daugtaškį (&vellip;) ir pasirinkite **Vykdyti**. Jūsų darbo eiga taip pat vykdoma automatiškai su kiekvienu [suplanuotu atnaujinimu](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Esamos darbo eigos valdymas

Eikite į **"Intelligence** > **Custom" modelius** ir peržiūrėkite sukurtas darbo eigas.

Pasirinkite darbo eigą, kad peržiūrėtumėte galimus veiksmus.

- **Darbo eigos redagavimas**
- **Darbo eigos vykdymas**
- [**Darbo eigos naikinimas**](#delete-a-workflow)

### <a name="edit-a-workflow"></a>Darbo eigos redagavimas

1. Eikite į **"Intelligence** > **Custom" modelius**.

1. Šalia darbo eigos, kurią norite atnaujinti, pasirinkite vertikalią daugtaškį (&vellip;) ir pasirinkite **Redaguoti**.

1. Jei reikia, pakeiskite **rodomą pavadinimą** ir pasirinkite **Pirmyn**.

1. Jei reikia, atnaujinkite kiekvienos **žiniatinklio tarnybos įvesties** objektą **iš** "Customer Insights". Tada pasirinkite **Toliau**.

1. Modelio **išvesties parametrų** dalyje pakeiskite bet kurį iš šių parinkčių:
   - **Vamzdyno išvesties rezultatų objekto pavadinimas**
   - **Išvesties duomenų saugykla paketinio vamzdyno parametro pavadinimas**
   - **Išvesties kelio parametro pavadinimas** jūsų paketiniame vamzdyne

1. Pakeiskite atitikimo atributą iš **Kliento ID rezultatuose**, kad identifikuotumėte klientus. Pasirinkite atributą iš išvadų išvesties, kurios reikšmės panašios į kliento objekto stulpelį Kliento ID. Jei duomenų rinkinyje tokio stulpelio neturite, pasirinkite atributą, kuris unikaliai identifikuoja eilutę.

1. Pasirinkite **Įrašyti**

### <a name="delete-a-workflow"></a>Darbo eigos naikinimas

1. Eikite į **"Intelligence** > **Custom" modelius**.

1. Šalia darbo eigos, kurią norite ištrinti, pasirinkite vertikalią daugtaškį (&vellip;) ir pasirinkite **Naikinti**.

1. Patvirtinkite šį naikinimą.

Jūsų darbo eiga bus panaikinta. Objektas [...](entities.md), kuris buvo sukurtas kuriant darbo eigą, išlieka ir gali būti peržiūrėtas puslapyje **Duomenų** > **objektai**.

## <a name="view-the-results"></a>Rezultatų peržiūra

Darbo eigos rezultatai saugomi objekto pavadinime, apibrėžtame modelio išvesties **parametruose**. Pasiekite šiuos duomenis iš [**·** > **duomenų subjektų** puslapio](entities.md) arba su [API prieiga](apis.md).

### <a name="api-access"></a>API Prieiga

Konkrečiai „OData” užklausai, skirtai gauti duomenims iš pasirinktinio modelio objekto, naudokite šį formatą:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Pakeiskite `<your instance id>` savo "Customer Insights" aplinkos ID, kuris rodomas naršyklės adreso juostoje, kai pasiekiate "Customer Insights".

1. Pakeiskite `<custom model output entity>` objekto pavadinimu, kurį pateikėte modelio **išvesties parametrams**.

1. Pakeiskite `<guid value>` kliento, kurį norite pasiekti, kliento ID. Šis ID rodomas [puslapyje klientų profiliai](customer-profiles.md), esančiame lauke CustomerID.

## <a name="frequently-asked-questions"></a>Dažnai užduodami klausimai

- Kodėl negaliu matyti savo srauto, kai nustatau pasirinktinę modelio darbo eigą?
  Šią problemą dažnai sukelia srauto konfigūravimo problema. Užtikrinkite, kad [įvesties parametras yra sukonfigūruotas](azure-machine-learning-experiments.md#dataset-configuration) ir [išvesties duomenų saugyklos ir kelio parametrai](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) taip pat sukonfigūruoti.

- Ką reiškia klaida „Nepavyko įrašyti intelekto darbo eigos”? 
  Paprastai vartotojai mato šį klaidos pranešimą, jei jie neturi savininko arba vartotojo prieigos administratoriaus teisių darbo sričiai. Vartotojui reikalingos aukštesnio lygio teisės įgalinti „Customer Insights” apdoroti darbo eigą kaip paslaugą, o ne naudoti vartotojo kredencialus tolesniems darbo eigos vykdymams.

- Ar palaikomas privatus mano pasirinktinio modelio darbo eigos galinio punkto / privatus saitas?
  "Customer Insights" šiuo metu nepalaiko pasirinktinių modelių privataus galinio punkto, tačiau yra neautomatinis sprendimas. Dėl išsamesnės informacijos kreipkitės į palaikymo tarnybą.

## <a name="responsible-ai"></a>Atsakingas AI

Prognozės siūlo galimybes kurti geresnes kliento patirtis, pagerinti verslo galimybes ir pelno srautus. Primygtinai rekomenduojame jums subalansuoti jūsų prognozės vertę lyginant su poveikiu, kurį ji turi ir tendencijas, kurios gali būti pristatytos etiniu požiūriu. Sužinokite daugiau apie tai, kaip „Microsoft“ [rekomenduoja atsakingą AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Galite taip pat sužinoti apie [mašininio mokymosi procesų atsakomybę ir technikas](/azure/machine-learning/concept-responsible-ml) būdingas „Azure“ mašininiam mokymuisi.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
