---
title: Klientų ciklo reikšmės prognozės pavyzdinis vadovas
description: Naudokite šį pavyzdinį vadovą, kad išbandytumėte klientų ciklo reikšmės prognozės modelį.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: c130e5f699f7eb921b69a20bc6d4ba9eab5b2779
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354841"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Klientų ciklo reikšmės (CLV) prognozės pavyzdinis vadovas

Šiame vadove pateiktas visapusiškas Klientų ciklo reikšmės (CLV) pavyzdys „Customer Insights” naudojant pavyzdinius duomenis.

## <a name="scenario"></a>Scenarijus

Contoso yra įmonė, gaminanti aukštos kokybės kavos ir kavos aparatus. Jie parduoda produktus per savo Contoso Kavos" svetainę. Įmonė nori suprasti vertę (pajamas), kurią jų klientai gali sugeneruoti per artimiausius 12 mėnesių. Žinodama numatomą klientų vertę per artimiausius 12 mėnesių, įmonė galės nukreipti savo rinkodaros pastangas vertingiausiems klientams.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [Bendraautoriaus teisės](permissions.md) auditorijos įžvalgose.
- Rekomenduojame jums atlikti šiuos žingsnius [naujoje aplinkoje](manage-environments.md).

## <a name="task-1---ingest-data"></a>Užduotis 1 - Duomenų vartojimas

Peržiūrėkite straipsnius [apie duomenų nurijimas](data-sources.md) ir [duomenų šaltinių importavimą naudojant Power Query jungtis](connect-power-query.md). Tolesnė informacija pateikiama su sąlyga, kad susipažinote su naudojamais duomenimis iš esmės.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Kliento duomenų naudojimas iš e-komercijos platformos

1. Sukurkite duomenų šaltinį pavadinimu **e-komercija**, pasirinkite importavimo parinktį ir **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Redaguodami duomenis pasirinkite **Transformuoti** ir **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Sukurta**: Data/Laikas/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformuoti gimimo datą į datą.":::

1. „Pavadinimas“ laukelyje dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos kontaktai**

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-online-purchase-data"></a>Vartokite internete įsigytus duomenis

1. Įtraukite kitą duomenų rinkinį į **e-komercijos** duomenų šaltinį. Pasirinkite **Tekstas/CSV** jungtis dar kartą.

1. Įveskite URL **Interneto įsigijimų** duomenis https://aka.ms/ciadclassonline.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Įsigyta**: Data/Laikas
   - **Bendra kaina**: Valiuta

1. Laukelyje **Pavadinimas** šoninėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **e-komercijos įsigijimai**.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliento duomenų naudojimas iš lojalumo schemos

1. Sukurkite duomenų šaltinį pavadinimu **Lojalumo schema**, pasirinkite importavimo parinktį ir pasirinkite **Tekstas/CSV** jungtį.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/ciadclasscustomerloyalty.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:
   - **Gimimo data**: Data
   - **Uždirbtitaškai**: Visas skaičius
   - **Sukurta**: Data/Laikas

1. Laukelyje **Pavadinimas** dešinėje juostoje pervardykite savo duomenų šaltinį iš **Laukimas** į **lojalūs klientai**.

1. **Įrašykite** duomenų šaltinį.

### <a name="ingest-customer-data-from-website-reviews"></a>Suvartokite kliento duomenis iš svetainės peržiūrų

1. Norėdami sukurti duomenų šaltinį pavadinimu **Interneto svetainė**, pasirinkite importavimo parinktį ir pasirinkite **Teksto/CSV** jungtis.

1. Įveskite URL e-komercijos kontaktams https://aka.ms/CI-ILT/WebReviews.

1. Redaguodami duomenis pasirinkite **Transformuoti** ir tuomet **Naudoti pirmą eilutę kaip antraštes**.

1. Naujinti duomenų tipą toliau išvardytiems stulpeliams:

   - **ApžvalgosĮvertinimas**: Dešimtainis skaičius
   - **Apžvalgos data**: Data

1. Dešinės juostos lauke „Pavadinimas” pervadinkite jūsų duomenų šaltinį iš **Užklausa** į **Apžvalgos**.

1. **Įrašykite** duomenų šaltinį.

## <a name="task-2---data-unification"></a>Užduotis 2 - Duomenų suvienodinimas

Įtraukę duomenis mes pradedame duomenų suvienodinimo procesą, kad sukurtumėte vieningąjį kliento profilį. Dėl daugiau informacijos, žr. [Duomenų suvienodinimas](data-unification.md).

### <a name="map"></a>Schema

1. Suvartojus duomenis, sudarykite kontaktų žemėlapį iš e-komercijos ir lojalumo duomenų į bendrus duomenų tipus. Eikite į **Duomenys** > **Suvienodinti** > **Žemėlapis**.

1. Pasirinkite objektus, kurie rodo kliento profilį – **e-komercijoskontaktai** ir **lojalumoklientai**. Tada pasirinkite **Taikyti**.

   ![suvienodinti e-komercijos ir lojalumo duomenų šaltinius.](media/unify-ecommerce-loyalty.png)

1. Pasirinkite **Kontakto ID** kaip pagrindinį raktą **e-komercijos kontaktus** ir **Lojalumo ID** kaip pirminį raktą **lojalumo klientams**.

   ![Suvienodinkite lojalumo ID kaip pagrindinį raktą.](media/unify-loyaltyid.png)

1. Pasirinkite **Įrašyti**.

### <a name="match"></a>Sugretinti

1. Eikite į **Atitikties** skirtuką ir pasirinkite **Nustatyti užsakymą**.

1. Pirminiame **išplečiamajame** sąraše pasirinkite **eCommerceContacts: el. prekyba** pirminis šaltinis ir įtraukite visus įrašus.

1. Išplečiamajame sąraše **Objektas 2** pasirinkite **loyCustomers: LoyaltyScheme** įtraukite visus įrašus.

   ![Suvienodinti e-komercijos atitiktį ir lojalumą.](media/unify-match-order.png)

1. Pasirinkite **Įtraukti taisyklę**

1. Įtraukite savo pirmąją sąlygą naudodami visą pavadinimą.

   - El. prekyboscontacts išplečiamajame sąraše pažymėkite **Visas vardas**.
   - loyCustomers išplečiamajame sąraše pažymėkite **Visas vardas**.
   - Pažymėkite **normalizuoti** išplečiamąjį sąrašą ir pasirinkite **Tipas (Telefonas, Vardas, Adresas, ...)**.
   - Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

1. Įveskite pavadinimą **Visas pavadinimas, El. paštas** naujai taisyklei.

   - Įtraukite antrąją sąlygą el. pašto adresui pasirinkdami **Įtraukite sąlygą**
   - Objekto "eCommerceContacts" **išplečiamajame sąraše** pasirinkite "El. paštas".
   - Objekto loyCustomers **išplečiamajame sąraše** pasirinkite "El. paštas".
   - Palikite normalizavimą tuščią.
   - Nustatykite **Preciziškumo lygis**: **Pagrindinis** ir **Vertė**: **Aukštas**.

   ![Suvienodinkite atitikties taisyklę pavadinimui ir el. paštui.](media/unify-match-rule.png)

1. Pasirinkite **Atlikta**.

1. Pasirinkite **Įrašyti** ir **Vykdyti**.

### <a name="merge"></a>Sulieti

1. Eikite į **Sulieti** skirtuką.

1. **Kontakto ID** skirtą **lojalių klientų** objekte, keiskite rodomą pavadinimą į **KontaktoIDlojalumas** tam, kad jis skirtųsi nuo kitų vartotų ID.

   ![pervardykite kontakto ID iš lojalumo ID.](media/unify-merge-contactid.png)

1. Pasirinkite **Įrašyti** ir **Vykdyti suliejimo ir užbaigimo procesus**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>3 užduotis – Klientų ciklo reikšmės prognozės konfigūravimas

Sutvarkę vieninguosius klientų profilius, galime vykdyti klientų ciklo reikšmės prognozę. Išsamius veiksmus ieškokite [Customer Lifetime Value prognozė](predict-customer-lifetime-value.md).

1. Eikite į **Įžvalgos**  > **Prognozės** ir pasirinkite **Klientų ciklo reikšmės modelį**.

1. Pereikite per informaciją šoninėje srityje ir pasirinkite **Pradėti**.

1. Pavadinkite modelį **„OOB” e-prekybos CLV Prognozė**, o išvesties objektą – **„OOBeCommerceCLVPrediction”**.

1. Apibrėžkite CLV modelio nuostatas:
   - **Prognozės laikotarpis**: **12 mėnesių arba 1 metai**. Šis parametras apibrėžia, kaip toli į ateitį galima prognozuoti klientų ciklo reikšmę.
   - **Aktyvūs klientai**: Nurodykite, ką jūsų įmonei reiškia aktyvūs klientai. Nustatykite istorinį skirtąjį laiką, per kurį klientas turi atlikti bent vieną operaciją, kad būtų laikomas aktyviu. Modelis nuspės tik aktyvių klientų CLV. Pasirinkite, ar leisti modeliui apskaičiuoti laiką pagal istorinius operacijų duomenis, arba pateikite konkretų skirtąjį laiką. Šiame pavyzdiniame vadove mes **leidžiame modeliui apskaičiuoti pirkimo intervalą**, kuris yra numatytoji parinktis.
   - **Didelės vertės klientai**: Apibrėžkite didelės vertės klientus kaip geriausiai mokančių klientų procentilį. Modelis naudoja šią įvestį, kad pateiktų rezultatus, atitinkančius jūsų verslo didelės vertės klientų apibrėžimą. Galite pasirinkti, jog leidžiate modeliui apibrėžti didelės vertės klientus. Jis naudoja euristinę taisyklę, iš kurios išvedamas procentilis. Taip pat galite apibrėžti didelės vertės klientus kaip ateityje geriausiai mokėsiančių klientų procentilį. Šiame pavyzdiniame vadove rankiniu būdu nustatome didelės vertės klientus kaip **geriausius 30 % aktyvių mokių klientų** ir pažymime **Toliau**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Nuostatų veiksmas CLV modelio vadovo patirtyje.":::

1. Veiksme **Būtini duomenys** pasirinkite **Įtraukti duomenis**, kad pateiktumėte operacijų retrospektyvos duomenys.

1. Įtraukite **e-prekybosPirkiniai : e-prekyba** objektą ir susiekite atributus, kurių reikalauja modelis:
   - Operacijos ID: e-prekyba.e-prekybosPirkiniai.PirkinioId
   - Operacijos data: e-prekyba.e-prekybosPirkiniai.ĮjungtasPirkimas
   - Operacijos suma: e-prekyba.e-prekybosPirkiniai.BendraKaina
   - Produkto ID: e-prekyba.e-prekybosPirkiniai.ProduktoId

1. Pasirinkite **Toliau**.

1. Nustatykite ryšį tarp **e-prekybosPirkiniai : e-prekyba** objekto ir **e-prekybosKontaktai : e-prekyba**.

1. Veiksmas **Papildomi duomenys (pasirinktiniai)** leidžia jums įtraukti daugiau klientų veiklos duomenų. Šie duomenys gali padėti gauti daugiau įžvalgų apie klientų sąveiką su jūsų verslu, o tai gali prisidėti prie CLV. Pagrindinių kliento sąveikų, tokių kaip žiniatinklio žurnalų, klientų aptarnavimo žurnalų arba apdovanojimų programos retrospektyvos, įtraukimas gali pagerinti prognozių tikslumą. Pasirinkite **Įtraukti duomenis**, kad įtrauktumėte daugiau klientų veiklos duomenų.

1. Įtraukite kliento veiklos objektą ir susiekite jo laukų pavadinimus su atitinkamais laukais, kurių reikalauja modelis:
   - Kliento veiklos objektas: Atsiliepimai:Žiniatinklio svetainė
   - Pirminis raktas: Žiniatinklis.Apžvalgos.ApžvalgosId
   - Laiko žyma: Svetainė.Apžvalgos.ApžvalgosData
   - Įvykis (veiklos pavadinimas): Svetainė.Apžvalgos.RodomasVeiklosTipas
   - Išsami informacija (suma arba reikšmė): Svetainė.Apžvalgos.ApžvalgųĮvertinimas

1. Pasirinkite **Kitas** ir sukonfigūruokite veiklą bei ryšį tarp operacijos ir kliento duomenų:  
   - Veiklos tipas: Pasirinkti esamą
   - Veiklos žyma: Apžvalga
   - Atitinkama žyma: Žiniatinklis.Apžvalgos.VartotojoId
   - Kliento objektas: e-prekybosKontaktai:e-prekyba
   - Ryšys: ŽiniatinklioApžvalgos

1. Pasirinkite **Kitas** tam, kad nustatytumėte modelio grafiką.

   Modelį reikia reguliariai mokyti, kad jis galėtų išmokti naujus modelius, įvedant naujus duomenis. Šiam pavyzdžiui pasirinkite **Mėnesinis**.

1. Peržiūrėję visą išsamią informaciją, pasirinkite **Įrašyti ir vykdyti**.

## <a name="task-4---review-model-results-and-explanations"></a>4 užduotis – Peržiūrėti modelio rezultatus ir paaiškinimus

Leisti modeliui užbaigti mokymąsi ir duomenų vertinimą. Tada galėsite peržiūrėti CLV modelio rezultatus ir paaiškinimus. Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5 užduotis – Didelės vertės klientų segmento kūrimas

Paleidus modelį sukuriamas naujas objektas, kuris pateikiamas skiltyje **Duomenys** > **Objektai**. Galite sukurti naują klientų segmentą, pagrįstą modelio sukurtu objektu.

1. Eikite į **Segmentai**. 

1. Pasirinkite **Naujas** ir **Sukurti iš** > **Įžvalgų**.

   ![Sukurkite segmentą su modelio išvestimi.](media/segment-intelligence.png)

1. Pasirinkite **„OOBeCommerceCLVPrediction”** objektą ir apibrėžkite segmentą:
  - Laukas: „CLVScore”
  - Operatorius: didesnis nei
  - Vertė: 1500

1. Pasirinkite **Peržiūrėti** ir **Įrašykite** segmentą.

Dabar turite segmentą, nustatantį klientus, kurie, kaip prognozuojama, sugeneruos daugiau nei $1500 pajamų per artimiausius 12 mėnesių. Įterpus daugiau duomenų, šis segmentas atnaujinamas dinamiškai.

Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).
