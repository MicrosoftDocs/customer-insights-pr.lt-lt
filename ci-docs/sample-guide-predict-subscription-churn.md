---
title: Prenumeratos atsisakymo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad bandytumėte nestandartinį prenumeravimo atsisakymo prognozės modelį.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741421"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Prenumeratos atsisakymo prognozės pavyzdžio vedlys

Praeisime kartu pro prenumeravimo nutraukimo prognozės pavyzdį nuo pradžios iki galo naudodami toliau pateiktus pavyzdžio duomenis. 

## <a name="scenario"></a>Scenarijus

„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę. Jie neseniai pradėjo prenumeravimo verslą savo klientams tam, kad jie reguliariai gautų kavos. Jų tikslas yra suprasti, kurie prenumeruojantys klientai gali atšaukti savo prenumeratą per kelis ateinančius mėnesius. Žinojimas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. Lauke **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

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

### <a name="ingest-subscription-information"></a>Suvartojama prenumeratos informacija

1. Sukurti duomenų šaltinį pavadinimus **Prenumeravimo istorija**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadchurnsubscriptionhistory.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Prenumeravimo ID**: Visas numeris
   - **Prenumeravimo suma**: Valiuta
   - **Prenumeravimo galutinė data**: Data/Laikas
   - **Prenumeravimo pradžios data**: Data/Laikas
   - **Perlaidos data**: Data/Laikas
   - **Pasikartoja**: Tiesa/Netiesa
   - **Yra_automatiškai_atnaujinama**: Tiesa/Netiesa
   - **Atnaujinimo dažnis mėnesiai**: Visas numeris

1. Laukelyje **Pavadinimas** dešinėje juostoje, pervardykite savo duomenų šaltinį iš **Laukiama** į **Prenumeravimo istorija**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-website-reviews"></a>Suvartokite kliento duomenis iš svetainės peržiūrų

1. Norėdami sukurti duomenų šaltinį pavadinimu **Interneto svetainė**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasswebsite.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Peržiūros reitingas**: Visas numeris
   - **Peržiūros data**: Data

1. „Pavadinimas“ laukelyje dešinėje juostoje, pervardykite savo duomenų šaltinį iš **Laukiama** į **Žiniatinklio peržiūros**.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Užduotis 3 - Konfigūruoti prenumeravimo nutraukimo prognozę

Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę. Išsamių veiksmų ieškokite [straipsnyje Prenumerata prognozė](predict-subscription-churn.md). 

1. Eikite į **Įžvalga** > **Atrasti** ir pasirinkite norėdami naudoti **Kliento nutraukimo modelį**.

1. Pasirinkite **Pernumeravimo** parinktį ir pasirinkite **Pradėti**.

1. Pavadinkite modelį **OOB prenumeravimo nutraukimo prognozė** ir išvesties objektą **OOBprenumeravimonutraukimoprognozė**.

1. Nustatykite dvi sąlygas nutraukimo modeliui:

   * **Dienos iki pasibaigs prenumerata**: **mažiausiai 60** dienų. Jei klientas neatnaujina prenumeratos per šį laikotarpį po to, kai baigsis prenumerata, laikoma, kad jis atsisakė paslaugų. 

   * **Atsisakymo sąvoka**: **mažiausiai 93** dienų. Modelio nuspėjama trukmė, per kurį klientai gali atsisakyti. Kuo toliau žvelgiate į ateitį, tuo rezultatai bus netikslesni.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pasirinkite modelio išlyginimo prognozės langą ir nutraukimo sąvoką.":::

1. Pasirinkite **Įtraukti būtinus duomenis** ir pasirinkite **Įtraukite duomenis** prenumeratos istorijai.

1. Įtraukite **Prenumeratą : prenumeravimo istorija** objektą ir sudarykite laukelių žemėlapį iš e-komercijos pagal atitinkamus modeliui būtinus laukelius.

1. Prisijunkite prie **Prenumerata : Prenumeravimo istorija** objekto su **E-komercijos kontaktų : e-komercija**, pavadinkite ryšius **e-komercijos prenumerata**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Sujunkite e-komercijos objektus.":::

1. Kliento veiklos skyriuje įtraukite **Žiniatinklio peržiūros: interneto svetainės** objektą ir sudarykite laukelių žemėlapį iš žiniatinklio peržiūros pagal atitinkamus modeliui būtinus laukelius. 
   - Pirminis raktas: Peržiūros ID
   - Laiko juostos antspaudas: Peržiūros data
   - Įvykis: Peržiūros reitingavimas

1. Konfigūruokite veiklą interneto svetainės peržiūroms. Pasirinkite veiklą **Peržiūrėti** ir prisijungti prie **Žiniatinklio peržiūrų : interneto svetainės** objektą su **e-komercijos kontaktų : e-komercija**.

1. Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.

   Modelis turi būti reguliariai bandomas siekiant išmokti naujas iškarpas, kai esama naujų vartojamų duomenų. Šiam pavyzdžiui, rinkitės **Kas mėnesį**.

1. Peržiūrėję visą išsamią informaciją pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-4---review-model-results-and-explanations"></a>4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Galite dabar peržiūrėti prenumeravimo atsisakymo modelio paaiškinimus. Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Užduotis 5 - Sukurti didelės atsisakymo rizikos klientų segmentą

Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.   

Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1.  Eikite į **Segmentai**. Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Sukurkite segmentą su modelio išvestimi.":::

1. Pasirinkite **„OOBSubscriptionChurnPrediction“** galutinį tašką ir nustatykite segmentą: 
   - Laukelis: Nutraukimo balas
   - Operatorius: didesnis nei
   - Vertė: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nustatykite prenumeravimo atsisakymo segmentą.":::

Dabar turite segmentą, kuris dinamiškai naujinamas ir nustato didelės rizikos klientų atsisakymą šiam prenumeratos verslui.

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]