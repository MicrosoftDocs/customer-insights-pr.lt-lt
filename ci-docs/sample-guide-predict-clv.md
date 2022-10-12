---
title: Klientų ciklo reikšmės (CLV) prognozės pavyzdinis vadovas
description: Naudokite šį pavyzdinį vadovą, kad išbandytumėte klientų ciklo reikšmės prognozės modelį.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609648"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Klientų ciklo reikšmės (CLV) prognozės pavyzdinis vadovas

Šiame vadove apžvelgiamas kliento viso gyvenimo trukmės vertės (CLV) pavyzdys, prognozė "Customer Insights", naudojant duomenų pavyzdžius. Rekomenduojame išbandyti šį prognozė [naujoje aplinkoje](manage-environments.md).

## <a name="scenario"></a>Scenarijus

Contoso yra įmonė, gaminanti aukštos kokybės kavos ir kavos aparatus. Jie parduoda produktus per savo Contoso Coffee" svetainę. Įmonė nori suprasti vertę (pajamas), kurią jų klientai gali sugeneruoti per artimiausius 12 mėnesių. Žinodama numatomą klientų vertę per artimiausius 12 mėnesių, įmonė galės nukreipti savo rinkodaros pastangas vertingiausiems klientams.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Mažiausiai [Prisidėjusiojo leidimai](permissions.md).

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

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta

1. Šoninės **srities lauke Pavadinimas** pervardykite duomenų šaltinis į **El. prekybos** pirkimas.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinis pavadinimu **LoyaltyScheme** ir pasirinkite teksto / CSV **jungtį**.

1. Įveskite lojalumo klientų https://aka.ms/ciadclasscustomerloyalty URL.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **loyCustomers**.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-customer-data-from-website-reviews"></a>Suvartokite kliento duomenis iš svetainės peržiūrų

1. Sukurkite duomenų šaltinis pavadinimu **Svetainė ir pasirinkite** teksto / CSV **jungtį**.

1. Įveskite svetainių apžvalgų https://aka.ms/CI-ILT/WebReviews URL.

1. Redaguodami duomenis pasirinkite Transformuoti **, tada** Naudokite pirmąją eilutę kaip antraštes **.**

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **ApžvalgosĮvertinimas**: Dešimtainis skaičius
   - **Apžvalgos data**: Data

1. Dešinėje **srityje esančiame lauke Pavadinimas** pervardykite duomenų šaltinis į **Apžvalgos**.

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

1. Įtraukite kitą veiklą ir susiekite jos laukų pavadinimus su atitinkamais laukais:
   - **Veiklos objektas**: apžvalgos:Svetainė
   - **Pirminis raktas**: ReviewId
   - **Laiko žyma**: ReviewDate
   - **Renginio veikla**: ActivityTypeDisplay
   - **Papildoma informacija**: ReviewRating
   - **Veiklos tipas**: Peržiūra

1. Vykdykite veiklą.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>4 užduotis – Klientų ciklo reikšmės prognozės konfigūravimas

Įdiegę vieningus klientų profilius ir sukūrę veiklą, paleiskite kliento viso gyvenimo vertę (CLV) prognozė. Išsamių veiksmų ieškokite [kliento viso gyvenimo vertės prognozė](predict-customer-lifetime-value.md).

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį**, esantį plytelėje **Kliento gyvenimo trukmės reikšmė**.

1. Pasirinkite **Pradėti**.

1. Pavadinkite modelį **„OOB” e-prekybos CLV Prognozė**, o išvesties objektą – **„OOBeCommerceCLVPrediction”**.

1. Apibrėžkite modelio nuostatas:
   - **prognozė laikotarpis**: **12 mėnesių arba 1 metai**, siekiant apibrėžti, kaip toli į ateitį prognozuoti CLV.
   - **Aktyvūs klientai**: **leiskite modeliui apskaičiuoti pirkimo intervalą**, kuris yra laikotarpis, per kurį klientas turi būti turėjęs turėti bent vieną operaciją, kad būtų laikomas aktyviu.
   - **Didelės vertės klientas**: rankiniu būdu apibrėžkite didelės vertės klientus kaip **30% geriausių aktyvių klientų**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Nuostatų veiksmas CLV modelio vadovo patirtyje.":::

1. Pasirinkite **Toliau**.

1. Veiksme **Būtini duomenys** pasirinkite **Įtraukti duomenis**, kad pateiktumėte operacijų retrospektyvos duomenys.

    :::image type="content" source="media/clv-model-required.png" alt-text="Pridėkite reikiamą duomenų žingsnį į CLV modelio valdomą patirtį.":::

1. Pasirinkite **SalesOrderLine** ir el. prekybos objektasPirchases ir pasirinkite **Pirmyn**. Reikalingi duomenys automatiškai užpildomi iš veiklos. Pasirinkite **Įrašyti**, tada **Pirmyn**.

1. Veiksmas **Papildomi duomenys (pasirinktiniai)** leidžia įtraukti daugiau klientų veiklos duomenų, kad gautumėte daugiau įžvalgų apie klientų sąveiką. Šiame pavyzdyje pasirinkite **Įtraukti duomenų** ir įtraukite žiniatinklio peržiūros veiklą.

1. Pasirinkite **Toliau**.

1. Atlikdami duomenų atnaujinimo veiksmą **, modelio grafike pasirinkite** Kas mėnesį **.**

1. Pasirinkite **Toliau**.

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-5---review-model-results-and-explanations"></a>5 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Peržiūrėkite [CLV modelio rezultatus ir paaiškinimus](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>6 užduotis – Didelės vertės klientų segmento kūrimas

Paleidus modelį sukuriamas naujas objektas, kuris pateikiamas skiltyje **Duomenys** > **Objektai**. Galite sukurti naują klientų segmentą, pagrįstą modelio sukurtu objektu.

1. Rezultatų puslapyje pasirinkite **Kurti segmentą**.

1. Sukurkite taisyklę naudodami objektą **OOBeCommerceCLVPrediktion** ir apibrėžkite segmentą:
   - **Laukas**: CLVScore
   - **Operatorius**: didesnis nei
   - **Vertė**: 1500

1. Pasirinkite **Įrašyti** ir **paleisti** segmentą.

Dabar turite segmentą, nustatantį klientus, kurie, kaip prognozuojama, sugeneruos daugiau nei $1500 pajamų per artimiausius 12 mėnesių. Įterpus daugiau duomenų, šis segmentas atnaujinamas dinamiškai. Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

> [!TIP]
> Taip pat galite sukurti prognozė modelio **segmentą puslapyje Segmentai**, pasirinkdami Naujas **ir pasirinkdami** **Kurti iš** > **"Intelligence"**. Norėdami gauti daugiau informacijos, žiūrėkite [Naujo segmento su greitais segmentais](segment-quick.md) kūrimas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
