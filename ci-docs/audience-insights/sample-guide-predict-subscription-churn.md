---
title: Prenumeratos atsisakymo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad bandytumėte nestandartinį prenumeravimo atsisakymo prognozės modelį.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653990"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Prenumeravimo atsisakymo prognozės (peržiūros) pavyzdžio vedlys

Praieisime kartu pro prenumeravimo nutraukimo prognozės pavyzdį nuo pradžios iki galo naudodami toliau pateiktus pavyzdžio duomenis. 

## <a name="scenario"></a>Scenarijus

„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę. Jie neseniai pradėjo prenumeravimo verslą savo klientams tam, kad jie reguliariai gautų kavos. Jų tiklsas yra suprasti, kurie prenumeruojantys klientai gali atšaukti savo prenumeratą per kelis ateinančius mėnesius. Žinomijas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Rekomenduojame jums atlikti šiuos žingsnius [naujojoe aplinkoje](manage-environments.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų suvartojimas

Peržiūrėti straipsnius [apie duomenų vartojimą](data-sources.md) ir [importuoti duomenų šaltinius naudojant „Power Query“ jungtis](connect-power-query.md) konkrečiai. Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   [!div class="mx-imgBorder"]
   ![Keisti gimimo dieną į datą](media/ecommerce-dob-date.PNG "transformuoti gimimo datą į datą")

1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Query** į **loyKlientai**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-subscription-information"></a>Suuvartojama prenumeratos informacija

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

1. „Pavadinimas“ laukelyje dešinėje juostoje, pervardyktie savo duomenų šaltinį iš **Laukiama** į **Prenumeravimo istorija**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-website-reviews"></a>Suvartokite kliento duomenis iš svetainės peržiūrų

1. Norėdami sukurti duomenų šaltinį pavadinimu **Interneto svetainė**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasswebsite.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Peržiūros reitingas**: Visas numeris
   - **Peržiūros data**: Data

1. „Pavadinimas“ laukelyje dešinėje juostoje, pervardyktie savo duomenų šaltinį iš **Laukiama** į **Žiniatinklio peržiūros**.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

Po duomenų suvartojimo dabar pradėsime **Žemėlapis, Atitiktis, Sulieti** procesą siekiant sukurti suvienodintą kliento profilį. Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).

### <a name="map"></a>Schema

1. Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus. Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.

1. Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="suvienodinti e-komercijos ir lojalumo duomenų šaltinius.":::

1. Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Suvienodinkite lojalumo ID kaip pagrindinį raktą.":::

### <a name="match"></a>Sugretinti

1. Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.

1. **Pagrindiniame** iškrentančiame meniu sąraše pasirinkite **e-komercijos kontaktai : e-komercija** kaip pagrindinį šaltinį ir įtraukite visus įrašus.

1. **Objektas 2** iškrentančiame sąraše pasirinkite **lojalūs klientai : lojalumo schemą** ir įtraukite visus įrašus.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Suvienodinti e-komercijos atitiktį ir lojalumą.":::

1. Pasirinkite **Sukurkite naują taisyklę**

1. Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.

   * E-komercijos kontaktams pasirinkite **Visas pavadinimas** iškrentančiame meniu.
   * Lojalumo klientams pasirinkite **Visas pavadinimas** iškrentančiame meniu.
   * Pasirinkite **Normalizuoti** iškrentantį meniu ir pasirinkite **Tipas (Telefonas, Pavadinimas, Adresas, ...)**.
   * Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

1. Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.

   * Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**
   * Objekto e-komercijos kontaktams, pasirinkite **El. paštas** iškrentančiame meniu.
   * Lojalių klientų objektui pasirinkite **El. paštas** iškrentančiame meniu. 
   * Palikite normalizavimą tuščią. 
   * Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.":::

7. Pasirinkite **Įrašyti** ir **Vykdyti**.

### <a name="merge"></a>Sulieti

1. Eikite į **Sulieti** skirtuką.

1. **Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="pervardykite kontakto ID iš lojalumo ID.":::

1. Pasirinkite **Įrašyti** ir **Vykdyti** tam, kad pradėtumėte suliejimo procesą.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Užduotis 3 - Konfigūruoti prenumeravimo nutraukimo prognozę

Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę. Išsamiems žingsniams, žr. [Prenumeravimo nutraukimo prognozė (peržiūra)](predict-subscription-churn.md) straipsnį. 

1. Eikite į **Įžvalga** > **Atrasti** ir pasirinkite norėdami naudoti **Kliento nutraukimo modelį**.

1. Pasirinkite **Pernumeravimo** parinktį ir pasirinkite **Pradėti**.

1. Pavadinkite modelį **OOB prenumeravimo nutraukimo prognozė** ir išvesties objektą **OOBprenumeravimonutraukimoprognozė**.

1. Nustatykite dvi sąlygas nutraukimo modeliui:

   * **Dienos iki pasibaigs prenumerata**: **mažiausiai 60** dienų. Jei klientas neatnaujina prenumeratos per šį laikotarpį po to, kai baigsis prenumerata, laikoma, kad jis atsisakė paslaugų. 

   * **Atsisakymo sąvoka**: **mažiausiai 93** dienų. Modelio nuspėjama trukmė, per kurį klientai gali atsisakyti. Kuo toliau žvelgiate į ateitį, tuo rezultatai bus netikslesni.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pasirinkite modelio išlyginimo prognozės langą ir nutraukimo sąvoką.":::

1. Pasirinkite **Įtrarukti būtinus duomenis** ir pasirinkite **Įtraukite duomenis** prenumeratos istorijai.

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

1. Peržiūrėją visą išsamią informaciją, rinkitės **Įrašyti ir vykdyti**.

## <a name="task-4---review-model-results-and-explanations"></a>Užduotis 4 - Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Galite dabar peržiūrėti prenumeravimo atsisakymo modelio paaiškinimus. Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Užduotis 5 - Sukurti didelės atsisakymo rizikos klientų segmentą

Gamybos modelio vykdymas sukurią naują objektą, kurį galite matyti **Duomenys** > **Objektai**.   

Galite sukurti naują segmentą pagal modelio sukurtą objektą.

1.  Eikite į **Segmentai**. Pasirinkite **Naujas** ir rinkitės **Sukurtas iš** > **Įžvalgos**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Sukurkite segmentą su modelio išvestimi.":::

1. Pasirinkite **„OOBSubscriptionChurnPrediction“** galutinį tašką ir nustatykite segmentą: 
   - Laukelis: Nutraukimos balas
   - Operatorius: didesnis nei
   - Vertė: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nustatykite prenumeravimo atsisakymo segmentą.":::

Gala turite segmentą, kuris dinamiškai naujinamas ir nustato didelės rizikos klientų atsisakymą šiam prenumeratos verslui.

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).
