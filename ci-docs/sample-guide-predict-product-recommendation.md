---
title: Produkto rekomendacijų prognozės pavyzdžio gairės
description: Šiame pavyzdyje pateiktame vadove išbandykite iš anksto pateiktą produkto prognozė modelį.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762696"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Produkto rekomendacijų prognozės pavyzdžio gairės

Paaiškinsime, kad galutinis produkto rekomendacijų pavyzdys pateiktas prognozė toliau pateiktą duomenų pavyzdį.

## <a name="scenario"></a>Scenarijus

„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę. Jų tikslas yra suprasti, kuriuos produktus jie turėtų rekomenduoja savo pasikartojantiems klientams. Žinodami, kokie klientai **labiau tikėtina,** kad juos įsigys, jie galės sutaupyti rinkodaros pastangų susitelkdami į konkrečius elementus.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėkite straipsnius [apie duomenų nurijimą](data-sources.md) ir [duomenų šaltinių Power Query importavimą naudojant specialiai jungtis](connect-power-query.md). Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite el. prekybos kontaktų URL: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite pirkimo **internetu duomenų URL**[https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta

1. Laukelyje **Pavadinimas** šoninėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite el. prekybos kontaktų URL [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.

1. **Įrašykite** duomenų šaltinį.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>3 užduotis – produktų rekomendacijų konfigūravimas prognozė

Turėdami vieningus klientų profilius, dabar galime paleisti produkto rekomendaciją prognozė.

1. Eikite į **Žvalgyba** > **Prognozėje** rinkitės **Produkto rekomendacijos**.

1. Pasirinkite **Pradėti**.

1. Pavadinkite modelio **OOB produkto rekomendacijų modelį prognozė** ir išvesties objektą **OOBProductRecommendationModelPrediction**.

1. Apibrėžkite tris modelio sąlygas:

   - **Produktų skaičius**: nustatykite šią reikšmę į **5**. Šis parametras apibrėžia, kiek produktų norite rekomenduojama klientams.

   - **Pakartokite tikėtinus pirkinius**: Pasirinkite **Taip**, jei į rekomendaciją norite įtraukti produktus, kuriuos jūsų klientai nusipirko anksčiau.

   - **Atsidarę langą:** pažymėkite bent **365 dienas**. Šie nustatymai nurodo, kiek toli modelis žiūrės į praeitį kliento veikloje, kuri buvo naudojama kaip įvestis rekomendacijoms.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelio pirmenybės produkto rekomendacijų modeliui.":::

1. Žingsnyje **Įtraukti reikiamus duomenis** pasirinkite **Įtraukti duomenis**.

1. **Srityje Įtraukti duomenis** kaip pirkimo retrospektyvos objektą **pasirinkite SalesOrderLine**. Šiuo metu jis greičiausiai dar nesukonfigūruotas. Norėdami sukurti veiklą atlikdami šiuos veiksmus, srityje atidarykite saitą:
   1. **Įveskite veiklos pavadinimą** ir pasirinkite *el. prekybospurchases:e-commerce* kaip **veiklos objektą**. Pirminis raktas **yra** *PurchaseId*.
   1. Apibrėžkite ir pavadinkite ryšį su *el. prekybos objektuContacts* :eCommerce ir pasirinkite **ContactId** kaip išorinį raktą.
   1. Veiklos suvienijimui nustatykite **įvykio veiklą** kaip *TotalPrice* ir Timestamp į *PurchasedOn*. Galite nurodyti daugiau laukų, kaip nurodyta [kliento veikloje](activities.md).
   1. Veiklos tipui **pasirinkite** *SalesOrderLine*. Susiekite šiuos veiklos laukus:
      - Užsakymo eilutės ID: PurchaseId
      - Užsakymo ID: PurchaseId
      - Užsakymo duomenys: PurchasedOn
      - Produkto ID: ProductId
      - Suma: TotalPrice
   1. Peržiūrėkite ir užbaikite veiklą prieš grįždami prie modelio konfigūracijos.

1. Žingsnyje **Pasirinkti veiklas** skyriuje Veikla **pasirinkite** naujai sukurtą veiklą. Pasirinkite **Pirmyn** ir atributų susiejimas jau užpildytas. Pasirinkite **Įrašyti**.

1. Šiame pavyzdiniame vadove praleidžiame **rinkinį Įtraukti produkto informaciją** ir **produktų filtrus**, nes neturime informacijos apie produktą duomenų.

1. Žingsnyje **Duomenų naujinimai** nustatykite modelio tvarkaraštį.

   Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų. Šiam pavyzdžiui, rinkitės **Kas mėnesį**.

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**. Tai užtruks keletą minučių, kad modelis būtų paleistas pirmą kartą.

## <a name="task-4---review-model-results-and-explanations"></a>4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Dabar galite peržiūrėti produkto rekomendacijų modelio paaiškinimus. Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>5 užduotis – aukštų įsigytų produktų segmento kūrimas

Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.

Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1. Eikite į **Segmentai**. Pasirinkite **Naujas** ir pasirinkite **Kurti iš žvalgybos informacijos**.

   ![Sukurkite segmentą su modelio išvestimi.](media/segment-intelligence.png)

1. Pažymėkite **OOBProductRecommendationModelPrediction** galinį punktą ir apibrėžkite segmentą:

   - Laukelis: Produkto ID
   - Reikšmė: pažymėkite tris geriausius produkto ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Kurkite segmentą iš modelio rezultatų.":::

Dabar turite dinamiškai atnaujinamą segmentą, kuris identifikuoja klientus, kurie gali būti suinteresuoti įsigyti tris labiausiai rekomenduojamus produktus.

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
