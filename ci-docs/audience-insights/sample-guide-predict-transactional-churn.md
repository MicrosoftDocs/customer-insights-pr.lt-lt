---
title: Perlaidos nutraukimo prognozės pavyzdžio vedlys
description: Naudokite šį pavyzdžio vedlį tam, kad pabandytumėte nestandartinį perlaidos nutraukimo prognozės modelį.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 055708ed3f9f468cad83ecf976a460814bf05199
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643603"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Perlaidos nutraukimo prognozės (peržiūra) pavyzdžio vedlys

Šis vedlys jus supažindins nuo pradžios iki galo su perlaidos nutraukimo prognozės pavyzdžiu tinkintose „Customer Insights“ naudojant toliau pateiktus duomenis. Visi šiame vedlyje naudojiami duomenys nėra realūs kliento duomenys ir yra „Contoso“ duomenų rinkinio, esančio *Demonstracinėje* aplinkoje jūsų „Customer Insights“ prenumeratoje, dalis.

## <a name="scenario"></a>Scenarijus

„Contoso“ yra bendrovė gaminanti aukštos kokybės kavą ir kavos aparatus, kuriuos parduoda per „Contoso Coffee“ interneto svetainę. Jų tikslas yra sužinoti, kurie klientai dažniausiai įsigija produktus reguliariai ir nustos būti aktyviais klientais per artimiausias 60 dienų. Žinomijas, kurie jų klientai **greičiausiai nutrauks paslaugas** gali padėti įmonei sutaupyti reklamos pastangas susikoncentruojant į klientų išlaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Rekomenduojame jums atlikti šiuos žingsnius [naujojoe aplinkoje](manage-environments.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėti straipsnius [apie duomenų vartojimą](data-sources.md) ir [importuoti duomenų šaltinius naudojant „Power Query“ jungtis](connect-power-query.md) konkrečiai. Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscontacts.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Sukurta dieną**: Data/Laikas/Zona

   [!div class="mx-imgBorder"]
   ![Keisti gimimo dieną į datą](media/ecommerce-dob-date.PNG "transformuoti gimimo datą į datą")

1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

1. Įrašykite duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta
   
1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.

1. Įrašykite duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta dieną**: Data/Laikas

1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Query** į **loyKlientai**.

1. Įrašykite duomenų šaltinį.


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



## <a name="task-3---configure-transaction-churn-prediction"></a>Užduotis 3 - Konfigūruoti perlaidos nutraukimo prognozę

Su suvienodinto kliento profiliais savo vietoje galite dabar vykdyti prenumeravimo nutraukimo prognozę. Išsamiems žingsniams, žr. [Prenumeravimo nutraukimo prognozė (peržiūra)](predict-subscription-churn.md) straipsnį. 

1. Eikite į **Įžvalga** > **Atrasti** ir pasirinkite norėdami naudoti **Kliento nutraukimo modelį**.

1. Pasirinkite **Perlaidos** parinktį ir rinkitės **Pradėti**.

1. Įvardykite modelį **OOB e-komercijos perlaidos nutraukimo prognozė** ir išvesties objektą **„OOBeCommerceChurnPrediction“**.

1. Nustatykite dvi sąlygas nutraukimo modeliui:

   * **Prognozės langas**: **mažiausiai 60** dienų. Šis nustatymas nustato, kaip toli į ateitį norime prognozuoti kliento nutraukimą.

   * **Nutraukimo sąvoka**: **mažiausiai 60** dienų. Trukmė be įsigijimo, po kuriso klientas laikomas nutraukusiu paslaugas.

     :::image type="content" source="media/model-levers.PNG" alt-text="Pasirinkite modelio išlyginimo prognozės langą ir nutraukimo sąvoką.":::

1. Pasirinkite **Įsigijimo istorija (būtinas)** ir rinkitės  **Įtraukti duomenis** prenumeravimo istorijai.

1. Įtraukite **e-komercijos įsigijimai : e-komerciją** objektą ir nustatykite laukelių žemėlapį iš e-komercijos į atitinkamus laukelius būtinus modeliui.

1. Prisijunkite prie **e-komercijos įsigijimų : e-komercijos** objekto su **e-komercijos kontaktais : e-komercija**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Prijunkite e-komercijos objektus.":::

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
   - Laukelis: atsisakymo balas
   - Operatorius: didesnis nei
   - Vertė: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Nustatykite prenumeravimo atsisakymo segmentą.":::

Gala turite segmentą, kuris dinamiškai naujinamas ir nustato didelės rizikos klientų atsisakymą šiam prenumeratos verslui.

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).