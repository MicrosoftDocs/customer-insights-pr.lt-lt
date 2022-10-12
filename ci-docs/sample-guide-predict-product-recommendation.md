---
title: Produkto rekomendacijų prognozės pavyzdžio gairės
description: Šiame pavyzdyje pateiktame vadove išbandykite iš anksto pateiktą produkto prognozė modelį.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610154"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Produkto rekomendacijų prognozės pavyzdžio gairės

Šiame vadove apžvelgiamas visapusiškas produkto rekomendacijų pavyzdys prognozė naudojant duomenų pavyzdžius. Rekomenduojame išbandyti šį prognozė [naujoje aplinkoje](manage-environments.md).

## <a name="scenario"></a>Scenarijus

Contoso yra įmonė, gaminanti aukštos kokybės kavos ir kavos aparatus. Jie parduoda produktus per savo Contoso Coffee" svetainę. Jų tikslas yra suprasti, kuriuos produktus jie turėtų rekomenduoja savo pasikartojantiems klientams. Žinojimas, ką klientai labiau **linkę pirkti**, gali padėti jiems sutaupyti rinkodaros pastangų, sutelkiant dėmesį į konkrečias prekes.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėkite straipsnius [apie duomenų įsisavinimą](data-sources.md) ir [prisijungimą Power Query prie duomenų šaltinis](connect-power-query.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinę su duomenų nurijimu apskritai.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite "Power Query" duomenų šaltinis, pavadintą **el**. prekyba, ir pasirinkite **teksto / CSV** jungtį.

1. Įveskite el. prekybos kontaktų URL:https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **el. prekyboskontaktai**.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite pirkimo internetu duomenų URL https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta

1. Šoninės **srities lauke Pavadinimas** pervardykite duomenų šaltinis į **El. prekybos** pirkimas.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinis pavadinimu **LoyaltyScheme** ir pasirinkite teksto / CSV **jungtį**.

1. Įveskite lojalių klientų URL https://aka.ms/ciadclasscustomerloyalty.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **loyCustomers**.

1. **Įrašykite** duomenų šaltinį.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

Peržiūrėkite straipsnį [apie duomenų suvienijimą](data-unification.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinę su duomenų suvienijimu apskritai.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>3 užduotis – sukurkite operacijų istorijos veiklą

Peržiūrėkite straipsnį [apie klientų veiklą](activities.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinęs su veiklos kūrimu apskritai.

1. Sukurkite veiklą, vadinamą **el. prekybaPirchases**, naudodami *el. prekybos objektąPirchases:eCommerce* ir jo pagrindinį raktą **PurchaseId**.

1. Sukurkite ryšį tarp *el. prekybosPirchases:eCommerce* ir *eCommerceContacts:eCommerce* su **ContactID** kaip išoriniu raktu, jungiančiu du subjektus.

1. Pasirinkite **TotalPrice**, skirtą **"EventActivity", ir**"PurchasedOn **"**, kad gautumėte laiko **žymą**.

1. Pasirinkite **"SalesOrderLine"**, skirtą **veiklos tipui**, ir semantiškai susiekite veiklos duomenis.

1. Vykdykite veiklą.

## <a name="task-4---configure-product-recommendation-prediction"></a>4 užduotis – produktų rekomendacijų konfigūravimas prognozė

Įdiegę vieningus klientų profilius ir sukūrę veiklą, paleiskite produkto rekomendaciją prognozė.

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį** plytelėje **Produkto rekomendacijos (peržiūra).**

1. Pasirinkite **Pradėti**.

1. Pavadinkite modelio **OOB produkto rekomendacijų modelį prognozė** ir išvesties objektą **OOBProductRecommendationModelPrediction**.

1. Pasirinkite **Toliau**.

1. Apibrėžkite modelio nuostatas:
   - **Produktų** skaičius: **5**, kad apibrėžtumėte, kiek produktų norite rekomenduoti savo klientams.
   - **Tikėtini** pakartotiniai pirkimai: **taip**, kad į rekomendaciją būtų įtraukti anksčiau įsigyti produktai.
   - **Pažvelkite atgal:** **365 dienos**, kad nustatytumėte, kaip toli modelis pažvelgs atgal, prieš vėl rekomenduodamas produktą.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelio pirmenybės produkto rekomendacijų modeliui.":::

1. Pasirinkite **Toliau**.

1. Atlikdami veiksmą **Įtraukti pirkimo istoriją** pasirinkite **Įtraukti duomenis**.

1. Pasirinkite **SalesOrderLine** ir el. prekybos objektasPirchases ir pasirinkite **Pirmyn**. Reikalingi duomenys automatiškai užpildomi iš veiklos. Pasirinkite **Įrašyti**, tada **Pirmyn**.

1. Praleiskite **veiksmus Produkto informacijos** įtraukimas ir **Produkto filtrai**, nes neturime produkto informacijos duomenų.

1. Atlikdami duomenų atnaujinimo veiksmą **, modelio grafike pasirinkite** Kas mėnesį **.**

1. Pasirinkite **Toliau**.

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-5---review-model-results-and-explanations"></a>5 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Peržiūrėkite [produkto rekomendacijų modelio paaiškinimus](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>6 užduotis – aukštų įsigytų produktų segmento kūrimas

Paleidus modelį sukuriamas naujas objektas, kuris pateikiamas skiltyje **Duomenys** > **Objektai**. Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1. Rezultatų puslapyje pasirinkite **Kurti segmentą**.

1. Sukurkite taisyklę naudodami objektą **OOBProductRecommendationModelPrediction** ir apibrėžkite segmentą:
   - **Laukas**: ProductID
   - **Reikšmė**: pasirinkite tris populiariausius produkto ID

1. Pasirinkite **Įrašyti** ir **paleisti** segmentą.

Dabar turite dinamiškai atnaujinamą segmentą, kuris identifikuoja klientus, kurie gali būti suinteresuoti įsigyti penkis dažniausiai rekomenduojamus produktus. Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

> [!TIP]
> Taip pat galite sukurti prognozė modelio **segmentą puslapyje Segmentai**, pasirinkdami Naujas **ir pasirinkdami** **Kurti iš** > **"Intelligence"**. Norėdami gauti daugiau informacijos, žiūrėkite [Naujo segmento su greitais segmentais](segment-quick.md) kūrimas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
