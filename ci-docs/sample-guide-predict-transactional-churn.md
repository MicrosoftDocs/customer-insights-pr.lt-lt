---
title: Perlaidos nutraukimo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad pabandytumėte nestandartinį perlaidos nutraukimo prognozės modelį.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609694"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Perlaidos nutraukimo prognozės pavyzdžio vedlys

Šiame vadove jums bus paaiškintas nuo galo iki galo pavyzdys, kaip operacijos metu prognozė naudojant duomenų pavyzdžius. Rekomenduojame išbandyti šį prognozė [naujoje aplinkoje](manage-environments.md).

## <a name="scenario"></a>Scenarijus

Contoso yra įmonė, gaminanti aukštos kokybės kavos ir kavos aparatus. Jie parduoda produktus per savo Contoso Coffee" svetainę. Jų tikslas yra sužinoti, kurie klientai dažniausiai įsigiję produktus reguliariai ir nustos būti aktyviais klientais per artimiausias 60 dienų. Žinojimas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Mažiausiai [Prisidėjusiojo leidimai](permissions.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėkite straipsnius [apie duomenų įsisavinimą](data-sources.md) ir [prisijungimą Power Query prie duomenų šaltinis](connect-power-query.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinę su duomenų nurijimu apskritai.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinis pavadinimu **El. prekyba** ir pasirinkite teksto / CSV **jungtį**.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Keisti gimimo dieną į datą.":::

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **El. prekyboskontaktai**

1. Įrašykite duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite pirkimo internetu duomenų URL https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **El. prekybaPirkos**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinis pavadinimu **LoyaltyScheme** ir pasirinkite teksto / CSV **jungtį**.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **loyCustomers**.

1. Įrašykite duomenų šaltinį.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Užduotis 4 - Konfigūruoti perlaidos nutraukimo prognozę

Turėdami suvienodintus klientų profilius ir vykdydami veiklą, paleiskite operacijos nutraukimo prognozė.

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį**, esantį kliento praradimo **modelyje**.

1. Pasirinkite **Operacija**, skirtą praradimo tipui, tada **– Pradėti**.

1. Įvardykite modelį **OOB e-komercijos perlaidos nutraukimo prognozė** ir išvesties objektą **„OOBeCommerceChurnPrediction“**.

1. Pasirinkite **Toliau**.

1. Apibrėžkite modelio nuostatas:

   - **prognozė langas**: **60** dienų, kad apibrėžtume, kaip toli į ateitį norime prognozuoti klientų praradimą.

   - **Praradimo apibrėžimas**: **60** dienų, kad būtų galima nurodyti trukmę be pirkimo, po kurios klientas laikomas nušalintu.

     :::image type="content" source="media/model-levers.PNG" alt-text="Pasirinkite modelio nuostatas prognozė Langas ir Praradimo apibrėžimas.":::

1. Pasirinkite **Toliau**.

1. Pasirinkite **Pirkimo retrospektyva (būtina)** ir pasirinkite **Įtraukti duomenis** pirkimo retrospektyvai.

1. Pasirinkite **SalesOrderLine** ir el. prekybos objektasPirchases ir pasirinkite **Pirmyn**. Reikalingi duomenys automatiškai užpildomi iš veiklos. Pasirinkite **Įrašyti**, tada **Pirmyn**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Prijunkite e-komercijos objektus.":::

1. Praleiskite veiksmą **Papildomi duomenys (pasirinktinai).**

1. Atlikdami duomenų atnaujinimo veiksmą **, modelio grafike pasirinkite** Kas mėnesį **.**

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-5---review-model-results-and-explanations"></a>5 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Peržiūrėkite praradimo modelio paaiškinimus. Daugiau informacijos ieškokite [prognozė rezultatų](predict-transactional-churn.md#view-prediction-results) peržiūra.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Užduotis 6 - Sukurti didelės atsisakymo rizikos klientų segmentą

Vykdant gamybos modelį sukuriamas naujas objektas, kuris pateikiamas duomenų **objektų** > **sąraše**. Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1. Rezultatų puslapyje pasirinkite **Kurti segmentą**.

1. Sukurkite taisyklę naudodami objektą **OOBeCommerceChurnPrediction** ir apibrėžkite segmentą:
   - **Laukas**: ChurnScore
   - **Operatorius**: didesnis nei
   - **Vertė**: 0,6

1. Pasirinkite **Įrašyti** ir **paleisti** segmentą.

Dabar turite dinamiškai atnaujinamą segmentą, kuris identifikuoja didelės praradimo rizikos klientus. Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

> [!TIP]
> Taip pat galite sukurti prognozė modelio **segmentą puslapyje Segmentai**, pasirinkdami Naujas **ir pasirinkdami** **Kurti iš** > **"Intelligence"**. Norėdami gauti daugiau informacijos, žiūrėkite [Naujo segmento su greitais segmentais](segment-quick.md) kūrimas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
