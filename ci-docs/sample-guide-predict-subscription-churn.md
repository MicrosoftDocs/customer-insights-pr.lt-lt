---
title: Prenumeratos atsisakymo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad bandytumėte nestandartinį prenumeravimo atsisakymo prognozės modelį.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610016"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Prenumeratos atsisakymo prognozės pavyzdžio vedlys

Šiame vadove jums bus paaiškintas nuo galo iki galo pateiktas prenumeratos atsisakymo prognozė naudojant duomenų pavyzdžius pavyzdys. Rekomenduojame išbandyti šį prognozė [naujoje aplinkoje](manage-environments.md).

## <a name="scenario"></a>Scenarijus

Contoso yra įmonė, gaminanti aukštos kokybės kavos ir kavos aparatus. Jie parduoda produktus per savo Contoso Coffee" svetainę. Jie neseniai pradėjo prenumeravimo verslą savo klientams tam, kad jie reguliariai gautų kavos. Jų tikslas yra suprasti, kurie užsiprenumeravę klientai gali atšaukti savo prenumeratą per ateinančius kelis mėnesius. Žinojimas, kuris iš jų klientų **gali nukentėti**, gali padėti jiems sutaupyti rinkodaros pastangų, sutelkiant dėmesį į jų išlaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėkite straipsnius [apie duomenų įsisavinimą](data-sources.md) ir [prisijungimą Power Query prie duomenų šaltinis](connect-power-query.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinę su duomenų nurijimu apskritai.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite "Power Query" duomenų šaltinis, pavadintą **el**. prekyba, ir pasirinkite **teksto / CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **El. prekyboskontaktai**

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinis pavadinimu **LoyaltyScheme** ir pasirinkite teksto / CSV **jungtį**.

1. Įveskite lojalumo klientų https://aka.ms/ciadclasscustomerloyalty URL.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **loyCustomers**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-subscription-information"></a>Suvartojama prenumeratos informacija

1. Sukurkite duomenų šaltinis pavadinimu **"SubscriptionHistory"** ir pasirinkite **teksto / CSV** jungtį.

1. Įveskite prenumeratų URL https://aka.ms/ciadchurnsubscriptionhistory.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Prenumeravimo ID**: Visas numeris
   - **Prenumeravimo suma**: Valiuta
   - **Prenumeravimo galutinė data**: Data/Laikas
   - **Prenumeravimo pradžios data**: Data/Laikas
   - **Perlaidos data**: Data/Laikas
   - **Pasikartoja**: Tiesa/Netiesa
   - **Yra_automatiškai_atnaujinama**: Tiesa/Netiesa
   - **Atnaujinimo dažnis mėnesiai**: Visas numeris

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **SubscriptionHistory**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-website-reviews"></a>Suvartokite kliento duomenis iš svetainės peržiūrų

1. Sukurkite duomenų šaltinis pavadinimu **Svetainė ir pasirinkite** teksto / CSV **jungtį**.

1. Įveskite svetainių apžvalgų https://aka.ms/ciadclasswebsite URL.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Peržiūros reitingas**: Visas numeris
   - **Apžvalgos data**: Data

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **webReviews**.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

Peržiūrėkite straipsnį [apie duomenų suvienijimą](data-unification.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinę su duomenų suvienijimu apskritai.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>3 užduotis – sukurkite operacijų istorijos veiklą

Peržiūrėkite straipsnį [apie klientų veiklą](activities.md). Toliau pateiktoje informacijoje daroma prielaida, kad esate susipažinęs su veiklos kūrimu apskritai.

1. Sukurkite veiklą, vadinamą SubscriptionHistory **, naudodami prenumeratos objektą** *ir jo pirminį raktą* CustomerId **.**

1. Sukurkite ryšį tarp *SubscriptionHistory:Subscription* ir *eCommerceContacts:eCommerce* su **CustomerID** kaip išoriniu raktu, kad sujungtumėte du objektus.

1. Pasirinkite **"EventActivity" ir**"SubscriptionEndDate **", skirtą**"TimeStamp **"**, "SubscriptionType"**·**.

1. Pasirinkite **Veiklos tipo** prenumerata **ir** semantiškai susiekite veiklos duomenis.

1. Vykdykite veiklą.

1. Įtraukite kitą veiklą ir susiekite jos laukų pavadinimus su atitinkamais laukais:
   - Kliento veiklos objektas: Atsiliepimai:Žiniatinklio svetainė
   - Pirminis raktas: Žiniatinklis.Apžvalgos.ApžvalgosId
   - Laiko žyma: Svetainė.Apžvalgos.ApžvalgosData
   - Įvykis (veiklos pavadinimas): Svetainė.Apžvalgos.RodomasVeiklosTipas
   - Išsami informacija (suma arba reikšmė): Svetainė.Apžvalgos.ApžvalgųĮvertinimas

1. Vykdykite veiklą.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Užduotis 4 - Konfigūruoti prenumeravimo nutraukimo prognozę

Įdiegę vieningus klientų profilius ir sukūrę veiklą, paleiskite prenumeratos praradimo prognozė. Išsamių veiksmų ieškokite [prenumeratos atsisakymo prognozė](predict-subscription-churn.md).

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį** plytelėje Kliento klientų pasitraukimo **modelis**.

1. Pasirinkite **Prenumeratos** pagal praradimo tipą, tada **Pradėkite**.

1. Pavadinkite modelį **OOB prenumeravimo nutraukimo prognozė** ir išvesties objektą **OOBprenumeravimonutraukimoprognozė**.

1. Apibrėžkite modelio nuostatas:
   - **Dienos nuo prenumeratos pasibaigimo**: **60** dienų, nurodančių, kad klientas laikomas prarastu, jei jis neatnaujina prenumeratos per šį laikotarpį pasibaigus prenumeratai.
   - **Dienos, kurias reikia ištirti ateityje, kad būtų galima prognozuoti praradimą**: **93** dienos, kuri yra trukmė, kurią modelis prognozuoja, kurie klientai gali prarasti. Kuo toliau žvelgiate į ateitį, tuo rezultatai bus netikslesni.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pasirinkite modelio nuostatas ir praradimo apibrėžimą.":::

1. Pasirinkite **Toliau**.

1. Atlikdami veiksmą **Privalomieji duomenys** pasirinkite **Įtraukti duomenis**, kad pateiktumėte prenumeratų istoriją.

1. Pasirinkite **Prenumeratą** ir objektą SubscriptionHistory ir pasirinkite **Pirmyn**. Reikalingi duomenys automatiškai užpildomi iš veiklos. Pasirinkite **Įrašyti**.

1. Dalyje Kliento veikla pasirinkite **Įtraukti duomenis**.

1. Šiame pavyzdyje pridėkite žiniatinklio peržiūros veiklą.

1. Pasirinkite **Toliau**.

1. Atlikdami duomenų atnaujinimo veiksmą **, modelio grafike pasirinkite** Kas mėnesį **.**

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-5---review-model-results-and-explanations"></a>5 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Peržiūrėkite prenumeratos praradimo modelio paaiškinimus. Daugiau informacijos ieškokite [prognozė rezultatų](predict-subscription-churn.md#view-prediction-results) peržiūra.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Užduotis 6 - Sukurti didelės atsisakymo rizikos klientų segmentą

Paleidus modelį sukuriamas naujas objektas, kuris pateikiamas skiltyje **Duomenys** > **Objektai**. Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1. Rezultatų puslapyje pasirinkite **Kurti segmentą**.

1. Sukurkite taisyklę naudodami objektą **OOBSubscriptionChurnPrediction** ir apibrėžkite segmentą:
   - **Laukas**: ChurnScore
   - **Operatorius**: didesnis nei
   - **Vertė**: 0,6

1. Pasirinkite **Įrašyti** ir **paleisti** segmentą.

Dabar turite segmentą, kuris dinamiškai naujinamas ir nustato didelės rizikos klientų atsisakymą šiam prenumeratos verslui. Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

> [!TIP]
> Taip pat galite sukurti prognozė modelio **segmentą puslapyje Segmentai**, pasirinkdami Naujas **ir pasirinkdami** **Kurti iš** > **"Intelligence"**. Norėdami gauti daugiau informacijos, žiūrėkite [Naujo segmento su greitais segmentais](segment-quick.md) kūrimas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
