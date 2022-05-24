---
title: Perlaidos nutraukimo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad pabandytumėte nestandartinį perlaidos nutraukimo prognozės modelį.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741329"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Perlaidos nutraukimo prognozės pavyzdžio vedlys

Šis vedlys jus supažindins nuo pradžios iki galo su perlaidos nutraukimo prognozės pavyzdžiu tinkintose „Customer Insights“ naudojant toliau pateiktus duomenis. Visi šiame vedlyje naudojami duomenys nėra realūs kliento duomenys ir yra „Contoso“ duomenų rinkinio, esančio *Demonstracinėje* aplinkoje jūsų „Customer Insights“ prenumeratoje, dalis.

## <a name="scenario"></a>Scenarijus

„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę. Jų tikslas yra sužinoti, kurie klientai dažniausiai įsigiję produktus reguliariai ir nustos būti aktyviais klientais per artimiausias 60 dienų. Žinojimas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėkite straipsnius [apie duomenų nurijimą](data-sources.md) ir [duomenų šaltinių Power Query importavimą naudojant specialiai jungtis](connect-power-query.md). Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Keisti gimimo dieną į datą.":::

1. Lauke **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

1. Įrašykite duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta
   
1. Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.

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

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Užduotis 3 - Konfigūruoti perlaidos nutraukimo prognozę

Turėdami vieningus klientų profilius, dabar galime paleisti operacijų prognozė. Išsamių veiksmų ieškokite [straipsnyje Transaction churn prognozė](predict-transactional-churn.md)." 

1. Eikite į **Įžvalga** > **Atrasti** ir pasirinkite norėdami naudoti **Kliento nutraukimo modelį**.

1. Pasirinkite **Perlaidos** parinktį ir rinkitės **Pradėti**.

1. Įvardykite modelį **OOB e-komercijos perlaidos nutraukimo prognozė** ir išvesties objektą **„OOBeCommerceChurnPrediction“**.

1. Nustatykite dvi sąlygas nutraukimo modeliui:

   * **Prognozės langas**: **mažiausiai 60** dienų. Šis nustatymas nustato, kaip toli į ateitį norime prognozuoti kliento nutraukimą.

   * **Nutraukimo sąvoka**: **mažiausiai 60** dienų. Trukmė be įsigijimo, po kurio klientas laikomas nutraukusiu paslaugas.

     :::image type="content" source="media/model-levers.PNG" alt-text="Pasirinkite modelio išlyginimo prognozės langą ir nutraukimo sąvoką.":::

1. Pasirinkite **Pirkimo retrospektyva (būtina)** ir pasirinkite **Įtraukti duomenis** pirkimo retrospektyvai.

1. Įtraukite **e-komercijos įsigijimai : e-komerciją** objektą ir nustatykite laukelių žemėlapį iš e-komercijos į atitinkamus laukelius būtinus modeliui.

1. Prisijunkite prie **e-komercijos įsigijimų : e-komercijos** objekto su **e-komercijos kontaktais : e-komercija**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Prijunkite e-komercijos objektus.":::

1. Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.

   Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų. Šiam pavyzdžiui, rinkitės **Kas mėnesį**.

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-4---review-model-results-and-explanations"></a>4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Dabar galite peržiūrėti "Churn" modelio paaiškinimus. Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Užduotis 5 - Sukurti didelės atsisakymo rizikos klientų segmentą

Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.   

Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1.  Eikite į **Segmentai**. Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Sukurkite segmentą su modelio išvestimi.":::

1. **Pasirinkite OOBeCommerceChurnPrediction** galinį punktą ir apibrėžkite segmentą: 
   - Laukelis: Nutraukimo balas
   - Operatorius: didesnis nei
   - Vertė: 0,6

Dabar turite dinamiškai atnaujinamą segmentą, kuris identifikuoja didelės rizikos klientus.

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
