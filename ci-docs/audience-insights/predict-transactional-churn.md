---
title: Sandorių prognozė (yra vaizdo įrašas)
description: Prognozuokite, ar klientas yra rizikingas taip, kad daugiau nebepirks jūsų produktų ar paslaugų.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 602a86a67006925faac00add8e089d28f7071c14
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967757"
---
# <a name="transaction-churn-prediction-preview"></a>Prenumeratų praradimo nuspėjimas (peržiūra)

Perdavimo nutraukimo prognozė padeda nuprognozuoti, ar klientas daugiau nebepirks jūsų produktų ar paslaugų per tam tikrą laiko langą. Galite sukurti naują nutraukimo prognozę **Įžvalga** > **Prognozės**. Norėdami pamatyti kitas jūsų sukurtas prognozes pasirinkite **Mano prognozės**. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Aplinkose, pagrįstose verslo klientais, galime prognozuoti kliento transakcijos chroną ir kliento derinį bei kitą informaciją, pvz., produktų kategoriją. Įtraukus sudėčių galima išsiaiškinti, kokia tikimybė, kad klientas „Contoso" nebesipirks produktų kategorijos „stacionarus biuras." Be to, verslo klientams galime naudoti AI ir sugeneruoti galimų priežasčių, kodėl klientas tikriausiai bus antrinės informacijos kategorijos klientas, sąrašą.

> [!TIP]
> Naudodami duomenų pavyzdį prognozė prognozė (peržiūra) vadovo duomenis: [Perlaido praradimo nuspėjimas (peržiūra) pavyzdys](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Verslo žinios, kad suprastumėte, ką praradimas reiškia verslui. Palaikome laiku pagrįstas nutraukimo sąvokas reiškiančias, kad klientas nutraukė po tam tikro nepirkimo laikotarpio.
- Duomenys apie jūsų operacijas/pirkimus ir jų istorija:
    - Perlaidos identifikatoriai skirti atskirti įsigijimus/perlaidas.
    - Kliento identifikatoriai atitinka perlaidas jūsų klientams.
    - Perlaidos įvykio datos, kurios nustato perlaidos datą.
    - Semantinei duomenų schemai įsigijimui/perlaidoms būtina tolesnė informacija:
        - **Perlaidos ID**: Unikalusis įsigijimo ar perlaidos identifikatorius.
        - **Sandorio data**: sandorio arba įsigijimo data.
        - **Perlaidos vertė**: Elemento/perlaidos kiekio skaitmeninė vertė/valiuta.
        - (Pasirenkama) **Unikalus gaminio ID**: Gaminio ID ar paslaugos įsigytos, jei jūsų duomenys yra elemento lygmens linijoje.
        - (Pasirenkama) **Ar ši perlaida buvo grįžtamoji**: Tiesos/netiesos laukelis nurodo, ar perlaida buvo grąžinta ar ne. Jei **Perlaidos vertė** yra neigiama, mes taip pat naudosime šią informaciją grįžimo numatymui.
- (Pasirenkamas) Duomenys apie kliento veiklas:
    - Veiklos identifikatoriai, padedantys atskirti to paties tipo veiklas.
    - Klientų identifikatoriai, siejantys veiklas su klientais.
    - Veiklos informacija, apimanti veiklos pavadinimą ir datą.
    - Kliento veiklų semantinė duomenų schema apima:
        - **Pirminis raktas:** unikalusis veiklos identifikatorius. Pavyzdžiui, interneto svetainės lankymas ar įrašo naudojimas rodo, kad klientas išbandė jūsų produkto pavyzdį.
        - **Laiko žymė:** pirminio rakto identifikuoto įvykio data ir laikas.
        - **Įvykis:** įvykio, kurį norite naudoti, pavadinimas. Pavyzdžiui, laukelis pavadintas „Naudotojo veiksmas“ prekių parduotuvėje gali būti kliento naudojamas kuponas.
        - **Informacija:** išsami informacija apie įvykį. Pavyzdžiui, laukelis pavadintas „Kupono vertė“ prekių parduotuvėje gali būti kupono valiutos vertė.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Verslo žinios, kad suprastumėte, ką praradimas reiškia verslui. Palaikome laiku pagrįstas nutraukimo sąvokas reiškiančias, kad klientas nutraukė po tam tikro nepirkimo laikotarpio.
- Duomenys apie jūsų operacijas/pirkimus ir jų istorija:
    - Perlaidos identifikatoriai skirti atskirti įsigijimus/perlaidas.
    - Kliento identifikatoriai atitinka perlaidas jūsų klientams.
    - Perlaidos įvykio datos, kurios nustato perlaidos datą.
    - Semantinei duomenų schemai įsigijimui/perlaidoms būtina tolesnė informacija:
        - **Perlaidos ID**: Unikalusis įsigijimo ar perlaidos identifikatorius.
        - **Sandorio data**: sandorio arba įsigijimo data.
        - **Perlaidos vertė**: Elemento/perlaidos kiekio skaitmeninė vertė/valiuta.
        - (Pasirenkama) **Unikalus gaminio ID**: Gaminio ID ar paslaugos įsigytos, jei jūsų duomenys yra elemento lygmens linijoje.
        - (Pasirenkama) **Ar ši perlaida buvo grįžtamoji**: Tiesos/netiesos laukelis nurodo, ar perlaida buvo grąžinta ar ne. Jei **Perlaidos vertė** yra neigiama, mes taip pat naudosime šią informaciją grįžimo numatymui.
- (Pasirenkamas) Duomenys apie kliento veiklas:
    - Veiklos identifikatoriai, padedantys atskirti to paties tipo veiklas.
    - Klientų identifikatoriai, siejantys veiklas su klientais.
    - Veiklos informacija, apimanti veiklos pavadinimą ir datą.
    - Kliento veiklų semantinė duomenų schema apima:
        - **Pirminis raktas:** unikalusis veiklos identifikatorius. Pavyzdžiui, interneto svetainės lankymas ar įrašo naudojimas rodo, kad klientas išbandė jūsų produkto pavyzdį.
        - **Laiko žymė:** pirminio rakto identifikuoto įvykio data ir laikas.
        - **Įvykis:** įvykio, kurį norite naudoti, pavadinimas. Pavyzdžiui, laukelis pavadintas „Naudotojo veiksmas“ prekių parduotuvėje gali būti kliento naudojamas kuponas.
        - **Informacija:** išsami informacija apie įvykį. Pavyzdžiui, laukelis pavadintas „Kupono vertė“ prekių parduotuvėje gali būti kupono valiutos vertė.
- (pasirinktinis) Duomenys apie klientus:
    - Šie duomenys turėtų būti sutapti su daugiau statinių atributų tam, kad modelis būtų geriausias.
    - Kliento duomenų semantinė duomenų schema apima:
        - **CustomerID:** Unikalus kliento identifikatorius.
        - **Sukurta data:** data, kai klientas buvo įtrauktas iš pradžių.
        - **Valstija arba provincija:** kliento valstija arba provincija.
        - **Šalis:** kliento šalis.
        - **Pramonės šaka:** kliento pramonės šakos tipas. Pavyzdžiui, laukas pramonės šaka, esančio pramonės šakoje, gali nurodyti, ar klientas buvo mažmeninis.
        - **Kvalifikavimas:** jūsų verslo kliento skirstymas į kategorijas. Pvz., laukas pavadinimu „ValueSegment", esantis medyje, gali būti kliento pakopa pagal kliento dydį.

---

- Siūlomos duomenų charakteristikos:
    - Pakankami istoriniai duomenys: sandorio duomenys bent dvigubam pasirinkto laiko tarpui. Pageidautina nuo dviejų iki trijų operacijų retrospektyvos metų. 
    - Keli pirkimai vienam klientui: geriausia bent du sandoriai kiekvienam klientui.
    - Klientų skaičius: bent 10 klientų profilių, geriausia daugiau nei 1 000 klientų. Modelis neveiks su mažiau nei 10 klientų, o istoriniai duomenys bus nepakankami.
    - Duomenų užbaigtumas: mažiau nei 20 % trūkstamų reikšmių pateiktame objekto duomenų laukelyje.

> [!NOTE]
> Įmonėms su didesniu klientų pirkimo dažniu (kas kelias savaites) rekomenduojama rinktis trumpesnį prognozės laikotarpį su perkėlimo apibrėžimu. Esant mažam pirkimo dažniui (kas keletą mėnesių arba kartą per metus) pasirinkite ilgesnį prognozės laikotarpį ir perkėlimo apibrėžimą.

## <a name="create-a-transaction-churn-prediction"></a>Kurti perdavimo praradimo nuspėjimą

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Pasirinkite **Kliento nutraukimo modelis (peržiūra)** plytą ir pasirinkite **Naudoti šį modelį**.

1. Srityje **Kliento apysavimo modelis (peržiūra)** pasirinkite **Operacija ir** pasirinkite **Pradėti**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Momentinė ekrano nuotrauka su pasirinkta transakcijos parinktimi, esančioje srityje Kliento modelis juosta.":::
 
### <a name="name-model"></a>Pavadinimo modelis

1. Suteikite modeliui pavadinimą, kad atskirtumėte jį nuo kitų modelių.

1. Išvesties objekto pavadinimui nurodyti galite naudoti tik raides ir skaičius be tarpų. Tai pavadinimas, kurį naudos modelio objektas. 

1. Pasirinkite **Toliau**.

### <a name="define-customer-churn"></a>Apibrėžkite kliento praradimą

1. Nustatykite **langą prognozė**. Pavyzdžiui, prognozuoti jūsų klientų nutraukimo riziką kitoms 90 dienų siekiant suderinti su jūsų reklamos laikymo pastangomis. Nutraukimo rizikos prognozavimas ilgesniam ar trumpesniam laikotarpiui gali apsunkinti faktorių nustatymą jūsų atsisakymo rizikos profilyje, bet jis priklauso nuo konkrečių verslo reikalavimų.
   >[!TIP]
   > Norėdami **įrašyti** prognozė juodraštį kaip juodraštį, galite bet kada pasirinkti Įrašyti juodraštį. Norėdami tęsti, prognozės juodraštį galite rasti skirtuke **Mano prognozė**.

1. Lauke Churn apibrėžimas įveskite dienų **skaičių**. Pavyzdžiui, jei klientas nieko nenupirko per paskutines 30 dienų, jis gali būti laikomas atsisakęs jūsų verslo paslaugų. 

1. Norėdami tęsti, spustelėkite **Pirmyn**.

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Pasirinkite **Įtraukti duomenis** ir pasirinkite veiklos tipą šoninėje srityje, kurioje yra reikiama operacijos arba pirkimo retrospektyvos informacija.

1. Dalyje **Pasirinkti** veiklas pasirinkite konkrečią veiklą iš pasirinkto veiklos tipo, į kurį norite sutelkti dėmesį.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Šoninė sritis, vaizduojanti semantikos tipo konkrečių veiklų pasirinkimą.":::

   Jeigu dar nesusiejote veiklos su semantiniu tipu, pasirinkite **Redaguoti**, kad tai atliktumėte. Atidaroma interaktyvioji semantinių veiklų susiejimo parinktis. Susiekite savo duomenis su atitinkamais pasirinkto veiklos tipo laukais.

1. Susiekite semantinius atributus su laukais, kurių reikia modeliui paleisti. Jei laukeliai nėra užpildyti, konfigūruokite ryšius iš jūsų įsigijimo istorijos laukelio į *kliento* laukelį. Pasirinkite **Įrašyti**.

1. **Veiksmą Įtraukti reikiamus duomenis** pasirinkite **Pirmyn,** jei nenorite įtraukti daugiau veiklų.


# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Įtraukti papildomus duomenis (pasirinktinai)

Sukonfigūruokite ryšį iš savo kliento veiklos objekto *Kliento* objektą.

1. Pasirinkite laukelį, kuris nustato klientą kliento veiklos lentelėje. Jis gali būti tiesiogiai susietas su pagrindiniu jūsų kliento objekto ID jūsų *Kliento* objekte.

1. Pažymėkite objektą, kuris yra jūsų pagrindinis *kliento* objektas.

1. Įveskite pavadinimą, apibūdinantį ryšį.

#### <a name="customer-activities"></a>Kliento veiklos

1. Pasirinktinai, pasirinkite **Įtraukti duomenis** skirtus **Kliento veikloms**.

1. Pažymėkite semantinio veiklos tipą, kuriame yra norimi naudoti duomenys, tada skyriuje Veiklos pažymėkite vieną ar daugiau **veiklų**.

1. Pasirinkite veiklos tipą, kuris atitinka konfigūruojamos kliento veiklos tipą. Pasirinkite **Sukurti naują** ir pasirinkite esamą veiklos tipą ar sukurkite naują tipą.

1. Pasirinkite **Kitas**, tada **Įrašyti**.

1. Jei turite bet kurias kitas kliento veiklas, kurias norite įtraukti, pakartokite ankstesnius žingsnius.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Rinkitės nuspėjimo lygį

Dauguma prognozių kuriami kliento lygiu. Kai kuriose situacijose, kurios gali būti nepakankami, kad būtų patenkinti jūsų verslo poreikiai. Šią funkciją galite naudoti, jei norite numatyti, pvz., kliento šaką, o ne visą klientą.

1. Norėdami sukurti prognozė lygį, o ne klientą, pažymėkite **Pažymėti antrinio lygio objektą**. Jei parinkties nėra, patikrinkite, ar baigėte ankstesnį skyrių.

1. Išplėskite objektus, iš kurių norite pasirinkti antrinį lygį, arba naudokite ieškos filtro lauką pasirinktoms parinktims filtruoti.

1. Pasirinkite atributą, kurį norite naudoti kaip antrinį lygį, tada pažymėkite **Įtraukti**.

1. Pasirinkite **Toliau**.

> [!NOTE]
> Šiame skyriuje galimi objektai rodomi, nes jie turi ryšį su objektu, kurį pasirinkote ankstesniame skyriuje. Jei nematote objekto, kurį norite įtraukti, patikrinkite, ar jis turi galiojantį ryšį, kuris yra **ryšių** srityje. Tik vienas su vienu ir daugelis su vienu ryšiai galioja šiai konfigūracijai.

### <a name="add-additional-data-optional"></a>Įtraukti papildomus duomenis (pasirinktinai)

Sukonfigūruokite ryšį iš savo kliento veiklos objekto *Kliento* objektą.

1. Pasirinkite laukelį, kuris nustato klientą kliento veiklos lentelėje. Jis gali būti tiesiogiai susietas su pagrindiniu jūsų kliento objekto ID jūsų *Kliento* objekte.

1. Pažymėkite objektą, kuris yra jūsų pagrindinis *kliento* objektas.

1. Įveskite pavadinimą, apibūdinantį ryšį.

#### <a name="customer-activities"></a>Kliento veiklos

1. Pasirinktinai, pasirinkite **Įtraukti duomenis** skirtus **Kliento veikloms**.

1. Pažymėkite semantinio veiklos tipą, kuriame yra norimi naudoti duomenys, tada skyriuje Veiklos pažymėkite vieną ar daugiau **veiklų**.

1. Pasirinkite veiklos tipą, kuris atitinka konfigūruojamos kliento veiklos tipą. Pasirinkite **Sukurti naują** ir pasirinkite esamą veiklos tipą ar sukurkite naują tipą.

1. Pasirinkite **Kitas**, tada **Įrašyti**.

1. Jei turite bet kurias kitas kliento veiklas, kurias norite įtraukti, pakartokite ankstesnius žingsnius.

#### <a name="customers-data"></a>Klientų duomenys

1. Galite pažymėti **Įtraukti duomenis** skirtus **Klientų duomenims**.

1. Susiekite semaninius atributus su laukais savo kliento duomenyse, kaip nurodyta. Siekiant užtikrinti geriausią modelio efektyvumą, naudojamų laukų duomenys dažnai neturi keistis. Pavyzdžiui, pasirinkus lauką „Klasifikuoti", kuris pakeitė kiekvieną mėnesį, bus naudojama tik paskutinė prognozė reikšmė, net jei kuriant prognozė modelius ta pati reikšmė retrospektyviškai gali būti taikoma klientui.

1. Pasirinkite **Toliau**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Teikia pasirinktinį abonementų su lyginamaisiais indeksais sąrašą

Įtraukite verslo klientų ir klientų, kuriuos norite naudoti kaip kaitvardį, sąrašą. Gausite išsamią informaciją apie šiuos santykinius abonementus, įskaitant jų kologloginį įvertinimą ir [daugelį neloginių funkcijų](#review-a-prediction-status-and-results) darančių įtaką jų "prognozė."

1. Pasirinkite **+ Įtraukti klientą**.

1. Pasirinkite klientus, kurie veikia kaip palyginami.

1. Norėdami tęsti, spustelėkite **Pirmyn**.

---

### <a name="set-schedule-and-review-configuration"></a>Grafiko ir peržiūros konfigūravimo nustatymas

1. Nustatykite modelio apmokymo iš naujo dažnumą. Šie nustatymai yra svarbūs siekiant atnaujinti prognozių tikslumą, kaip naujų duomenų naudojimą. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

1. Peržiūrėti prognozės konfigūravimą. Galite eiti atgal keletą žingsnių pasirinkę **Redaguoti** po rodoma verte. Arba galite pažymėti konfigūravimo veiksmą eigos indikatoriuje.

1. Jei visos reikšmės sukonfigūruotos teisingai, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte prognozavimo procesą. Skirtuke **Mano prognozės** galite matyti savo prognozių būseną. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

## <a name="review-a-prediction-status-and-results"></a>Prognozės būsenos ir rezultatų peržiūra

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite prognozę, kurią norite peržiūrėti.
   - **Prognozės pavadinimas**: Įvardykite prognozę jos kūrimo metu.
   - **Prognozės tipas**: Prognozei naudojamo modelio tipas
   - **Išvesties objektas**: objekto, kuriame saugoma prognozės išvestis, pavadinimas. Objektą šiuo pavadinimu galite rasti **Duomenys** > **Objektai**.
     Resultato objekte *„ChurnScore“* yra prognozuojama netekimo tikimybė, o *„IsChurn“* yra dvejetainė žyma, pagrįsta *„ChurnScore“* su 0,5 ribine verte. Numatytoji ribinė vertė jūsų scenarijui gali neveikti. [Sukurkite naują segmentą](segments.md#create-a-new-segment) su jūsų pageidaujama ribine verte.
     Ne visi klientai būtinai yra aktyvūs klientai. Kai kurie ilgą laiką gali būti neturėję jokios veiklos ir jau yra laikomi perkeltais pagal perkėlimo apibrėžimą. Klientams, kurie jau yra susidomę, nėra naudinga prognozuoti riziką, nes jie nėra dominančios auditorijos.
   - **Prognozuotas laukelis**: Šis laukelis užpildomas keliems prognozių tipams ir nėra naudojamas nutraukimo prognozėje.
   - **Būsena:**: Prognozės vykdymo būsena.
        - **Laukiama**: Prognozė laukia kitų procesų vykdymo.
        - **Paleidimas iš naujo**: Prognozė šiuo metu vykdoma siekiant sukurti rezultatus, kurie susilies į išvesties objektą.
        - **Nepavyko** : Prognozės vykdymas nepavyko. [Peržiūrėkite įrašus](manage-predictions.md#troubleshoot-a-failed-prediction) dėl išsamesnės informacijos.
        - **Pavyko**: Prognozė pavyko. Norėdami peržiūrėti prognozę, po vertikaliu daugtaškiu pasirinkite  **Rodyti**
   - **Redaguota**: data, kai buvo pakeista prognozės konfigūracija.
   - **Paskutinį kartą atnaujinta** : data, kai prognozė atnaujino rezultatus išvesties objekte.

1. Pažymėkite vertikalius daugtaškius šalia prognozės, kurios rezultatus norite peržiūrėti, ir pasirinkite **Rodyti**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Peržiūrėkite valdiklį tam, kad pamatytumėte prognozės rezultatus.":::

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

1. Rezultatų puslapyje yra trys pagrindinės duomenų dalys:
   - **Mokymo modelio efektyvumas**: galimi balai yra A, B arba C. Šis rezultatas nurodo prognozės efektyvumą ir gali padėti apsispręsti naudoti išvesties objekte saugomus rezultatus. Balai nustatomi pagal šias taisykles: 
        - **A** kai prognozės modelio tikslumas yra mažiausiai 50% visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra didesnis nei slenksčio lygis mažiausiai 10%.
            
        - **B** kai prognozės modelio tikslumas yra mažiausiai 50 % visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra iki 10% didesnis nei slenksčio lygis.
            
        - **C** kai prognozės modelio tikslumas yra mažesnis 50% visų prognozių ar kai prognozių tikslumo procentas nutraukusiems klientams yra mažesnis nei slenksčio lygis.
               
        - **Slenkstis** užima prognozės laiko lango įvestį modeliui (pavyzdžiui, vieneri metai), o modelis sukuria kitus laiko tarpus dalydamas juos iš 2 iki tol, kol pasiekia vieną mėnesį ar mažiau. Jis naudoja šiuos tarpus, kad sukurtų verslo taisykles klientams, kurie neįsigijo jų šiuo laikotarpiu. Šie klientai laikomi atsisakę. Laiko pagrįsta veiklos taisyklė su didesniu pajėgumu nuspėti, kas greičiausiai atsisakys yra pasirenkamas kaip slenksčio modelis.
            
    - **Praradimo tikimybė (klientų skaičius)**: Klientų grupės pagal prognozuojamą praradimo riziką. Šie duomenys gali būti naudingi vėliau, jei norite sukurti klientų segmentą su didele praradimo rizika. Tokie segmentai padeda suprasti, kokios turėtų būti priklausymo segmentui ribinės reikšmės.
       
    - **Svarbiausi veiksniai**: Kuriant prognozę, atsižvelgiama į daugelį veiksnių. Visi faktoriai turi savo apskaičiuotą svarbą sujungtoms prognozėms, kurias sukuria modelis. Naudodami šiuos faktorius galite patikrinti savo prognozė rezultatus, arba naudodami šią informaciją vėliau kurkite segmentus, kurie galėtų [turėti įtakos](segments.md) kliento riziką.


# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

1. Rezultatų puslapyje yra trys pagrindinės duomenų dalys:
   - **Mokymo modelio efektyvumas**: galimi balai yra A, B arba C. Šis rezultatas nurodo prognozės efektyvumą ir gali padėti apsispręsti naudoti išvesties objekte saugomus rezultatus. Balai nustatomi pagal šias taisykles: 
        - **A** kai prognozės modelio tikslumas yra mažiausiai 50% visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra didesnis nei slenksčio lygis mažiausiai 10%.
            
        - **B** kai prognozės modelio tikslumas yra mažiausiai 50 % visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra iki 10% didesnis nei slenksčio lygis.
            
        - **C** kai prognozės modelio tikslumas yra mažesnis 50% visų prognozių ar kai prognozių tikslumo procentas nutraukusiems klientams yra mažesnis nei slenksčio lygis.
               
        - **Slenkstis** užima prognozės laiko lango įvestį modeliui (pavyzdžiui, vieneri metai), o modelis sukuria kitus laiko tarpus dalydamas juos iš 2 iki tol, kol pasiekia vieną mėnesį ar mažiau. Jis naudoja šiuos tarpus, kad sukurtų verslo taisykles klientams, kurie neįsigijo jų šiuo laikotarpiu. Šie klientai laikomi atsisakę. Laiko pagrįsta veiklos taisyklė su didesniu pajėgumu nuspėti, kas greičiausiai atsisakys yra pasirenkamas kaip slenksčio modelis.
            
    - **Praradimo tikimybė (klientų skaičius)**: Klientų grupės pagal prognozuojamą praradimo riziką. Šie duomenys gali būti naudingi vėliau, jei norite sukurti klientų segmentą su didele praradimo rizika. Tokie segmentai padeda suprasti, kokios turėtų būti priklausymo segmentui ribinės reikšmės.
       
    - **Svarbiausi veiksniai**: Kuriant prognozę, atsižvelgiama į daugelį veiksnių. Visi faktoriai turi savo apskaičiuotą svarbą sujungtoms prognozėms, kurias sukuria modelis. Naudodami šiuos faktorius galite patikrinti savo prognozė rezultatus, arba naudodami šią informaciją vėliau kurkite segmentus, kurie galėtų [turėti įtakos](segments.md) kliento riziką.


1. Verslo klientams rasite papildomos **funkcijų analizės informacijos** puslapį. Joje yra keturios duomenų sekcijos:

    - Dešinioje srityje pažymėtas elementas apibrėžia šio puslapio turinį. Pažymėkite elementą iš **geriausių klientų** arba **Slenksties klientų**. Abu sąrašus užsakyti pagal mažėjanti jo reikšmė, neatsižvelgiant į tai, ar balas yra tik klientas, ar bendras klientų balas, ir antrinis lygis, pvz., produktų kategorija.
        
        - **Populiariausi klientai**: 10 klientų, kuriems pagal savo balus kyla didžiausia auksčiausios ir mažiausios aukščiausios auksinės grėsmės, sąrašas. 
        - **Klientų vertinimas**: konfigūruojant modelį pasirinktų iki 10 klientų sąrašas.
 
    - **Praradimo balas:** Dešinioje srityje rodomas pasirinkto elemento duotuvas.
    
    - **Praradimo rizikos paskirstymas:** rodomas chroniškų riziką skirstinį klientams ir procentu, kuriame yra parinktas klientas. 
    
    - **Viršutinės funkcijos, didėjančios ir mažėjančios chronkų grėsmės:** pažymėtam elementui dešinioje srityje išvardytos penkios viršutinės funkcijos, dėl kurių didėjo ir sumažino riziką. Galite rasti kiekvienos inu viena nuo kitos funkcijos elemento reikšmę ir jo įtaką praradimo balui. Taip pat rodoma vidutinė kiekvienos funkcijos reikšmė įvairiuose žemuose, vidutinio ir aukšto verslo klientų segmentuose. Ji padeda geriau kontekstizuoti pažymėto elemento viršutinių funkcijų reikšmes ir palyginti jas su mažais, vidutiniu ir aukštu praradimo klientų segmentais.

       - Žemas: klientai arba kliento ir antrinio lygio kombinacijos su 0–0,33 balo praradimo balu
       - Vidutinis: klientai arba kliento ir antrinio lygio paskyros su 0,33–0,66 lygio praradimo balu
       - Aukštas: klientai arba kliento ir antrinio lygio paskyros su didesniu nei 0,66 lygio praradimo balu
    
       Kai jūs prognozuojame, kad jis yra kliento lygyje, visi klientai atsižvelgia į tai, kad susietus vidutinius hiteronų segmentų funkcijų reikšmes. Jei numatoma, kad pirmame kiekvieno kliento lygyje bus prognozės segmentų suvedimas priklauso nuo antrinės pusės srityje pasirinkto elemento lygio. Pavyzdžiui, jei elementas turi antrinį produktų kategorijos lygį = biuro uždėjimo funkcija, tuomet šalutiniais elementais, kurių rašymo funkcija yra viena iš produktų kategorijos, atsižvelgiama tik tada, kai išskaidymo metu išskaidymo vidutinė elemento reikšmėje yra šie segmentai. Ši logika taikoma tam, kad būtų galima užtikrinti sąžiningą elemento funkcijų reikšmių palyginimą su vidutinėmis reikšmėmis žemuose, vidutinio ir aukštoje stulpelių segmentuose.

       Kai kuriais atvejais vidutinė žemos, vidutinio arba aukšto dangoraižų segmentų reikšmės yra tuščios arba negalima, nes nėra elementų, kurie pagal aukščiau pateiktą apibrėžimą priklausytų atitinkamims segmentams.
       
       > [!NOTE]
       > Reikšmių pagal vidutinius žemus, vidutinius ir didelius stulpelius skirstymas į kategorijas, pvz., šalį ar pramonės šaką, skiriasi. Kadangi „vidurkio" funkcijos reikšmės reikšmė nėra taikoma klasifikuotiems elementams, šių stulpelių reikšmės yra klientų dalis, esanti žemuose, vidutinio ir aukšto turinio segmentuose, kurių reikšminė reikšmė tokia pat kaip ir šoniniame skyde pažymėto elemento.

---

## <a name="manage-predictions"></a>Prognozių valdymas

Prognozes galima optimizuoti, šalinti jų triktis, atnaujinti arba panaikinti. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Norėdami gauti daugiau informacijos, eikite į [Valdyti prognozes](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
