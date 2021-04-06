---
title: Produkto rekomendacijų prognozės pavyzdžio gairės
description: Šiame pavyzdyje pateiktame vadove išbandykite iš anksto pateiktą produkto prognozė modelį.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595283"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Produkto rekomendacijų prognozės (peržiūros) pavyzdžio gairės

Paaiškinsime, kad galutinis produkto rekomendacijų pavyzdys pateiktas prognozė toliau pateiktą duomenų pavyzdį.

## <a name="scenario"></a>Scenarijus

„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę. Jų tikslas yra suprasti, kuriuos produktus jie turėtų rekomenduoja savo pasikartojantiems klientams. Žinodami, kokie klientai **labiau tikėtina,** kad juos įsigys, jie galės sutaupyti rinkodaros pastangų susitelkdami į konkrečius elementus.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėti straipsnius [apie duomenų vartojimą](data-sources.md) ir [importuoti duomenų šaltinius naudojant „Power Query“ jungtis](connect-power-query.md) konkrečiai. Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

5. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

6. **Įrašykite** duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta

1. Laukelyje **Pavadinimas** šoninėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.

1. Įrašykite duomenų šaltinį.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.

1. Įrašykite duomenų šaltinį.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

Po duomenų suvartojimo dabar pradėsime **Žemėlapis, Atitiktis, Sulieti** procesą siekiant sukurti suvienodintą kliento profilį. Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).

### <a name="map"></a>Schema

1. Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus. Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.

2. Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**.

   ![suvienodinti e-komercijos ir lojalumo duomenų šaltinius.](media/unify-ecommerce-loyalty.png)

3. Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.

   ![Suvienodinkite lojalumo ID kaip pagrindinį raktą.](media/unify-loyaltyid.png)

### <a name="match"></a>Sugretinti

1. Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.

2. **Pagrindiniame** iškrentančiame meniu sąraše pasirinkite **e-komercijos kontaktai : e-komercija** kaip pagrindinį šaltinį ir įtraukite visus įrašus.

3. **Objektas 2** iškrentančiame sąraše pasirinkite **lojalūs klientai : lojalumo schemą** ir įtraukite visus įrašus.

   ![Suvienodinti e-komercijos atitiktį ir lojalumą.](media/unify-match-order.png)

4. Pasirinkite **Sukurkite naują taisyklę**

5. Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.

   - E-komercijos kontaktams pasirinkite **Visas pavadinimas** iškrentančiame meniu.
   - Lojalumo klientams pasirinkite **Visas pavadinimas** iškrentančiame meniu.
   - Pasirinkite **Normalizuoti** iškrentantį meniu ir pasirinkite **Tipas (Telefonas, Pavadinimas, Adresas, ...)**.
   - Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

6. Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.

   - Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**
   - Objekto e-komercijos kontaktams, pasirinkite **El. paštas** iškrentančiame meniu.
   - Lojalių klientų objektui pasirinkite **El. paštas** iškrentančiame meniu.
   - Palikite normalizavimą tuščią.
   - Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

   ![Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.](media/unify-match-rule.png)

7. Pasirinkite **Įrašyti** ir **Vykdyti**.

### <a name="merge"></a>Sulieti

1. Eikite į **Sulieti** skirtuką.

1. **Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.

   ![pervardykite kontakto ID iš lojalumo ID.](media/unify-merge-contactid.png)

1. Pasirinkite **Įrašyti** ir **Vykdyti** tam, kad pradėtumėte suliejimo procesą.

## <a name="task-3---configure-product-recommendation-prediction"></a>3 užduotis – produktų rekomendacijų konfigūravimas prognozė

Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę.

1. Eikite į **Žvalgyba** > **Prognozėje** rinkitės **Produkto rekomendacijos**.

1. Pasirinkite **Pradėti**.

1. Pavadinkite modelio **OOB produkto rekomendacijų modelį prognozė** ir išvesties objektą **OOBProductRecommendationModelPrediction**.

1. Apibrėžkite tris modelio sąlygas:

   - **Produktų skaičius**: nustatykite šią reikšmę į **5**. Šis parametras apibrėžia, kiek produktų norite rekomenduojama klientams.

   - **Siūlyti produktus, kuriuos klientai neseniai įsigijo?** : Pasirinkite **Taip** ir nurodykite, kad į klientų anksčiau įsigytą rekomendaciją norite įtraukti produktų.

   - **Atsidarę langą:** pažymėkite bent **365 dienas**. Šie nustatymai nurodo, kiek toli modelis žiūrės į praeitį kliento veikloje, kuri buvo naudojama kaip įvestis rekomendacijoms.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Modelio pirmenybės produkto rekomendacijų modeliui.":::

1. Pasirinkite **Būtini duomenys** ir pasirinkite **Įtraukti duomenis** pirkimo retrospektyvai.

1. Įtraukite **e-komercijos įsigijimai : e-komerciją** objektą ir nustatykite laukelių žemėlapį iš e-komercijos į atitinkamus laukelius būtinus modeliui.

1. Prisijunkite prie **e-komercijos įsigijimų : e-komercijos** objekto su **e-komercijos kontaktais : e-komercija**.

   ![Prijunkite e-komercijos objektus.](media/model-purchase-join.png)

1. Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.

   Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų. Šiam pavyzdžiui, rinkitės **Kas mėnesį**.

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.


## <a name="task-4---review-model-results-and-explanations"></a>Užduotis 4 - Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Dabar galite peržiūrėti produkto rekomendacijų modelio paaiškinimus. Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>5 užduotis – aukštų įsigytų produktų segmento kūrimas

Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.

Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1. Eikite į **Segmentai**. Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**.

   ![Sukurkite segmentą su modelio išvestimi.](media/segment-intelligence.png)

1. Pažymėkite **OOBProductRecommendationModelPrediction** galinį punktą ir apibrėžkite segmentą:

   - Laukelis: Produkto ID
   - Operatorius: reikšmė
   - Reikšmė: pažymėkite tris geriausius produkto ID

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Kurkite segmentą iš modelio rezultatų.":::

Dabar turite dinamiškai atnaujintą segmentą, kuris nustato klientus, labiau norinčius įsigyti tris labiausiai rekomenduojamus produktus 

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]