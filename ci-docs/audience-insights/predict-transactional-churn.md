---
title: Perdavimo nutraukimo prognozė
description: Prognozuokite, ar klientas yra rizikingas taip, kad daugiau nebepirks jūsų produktų ar paslaugų.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0e587739f9f4d03942d70a72de4f9378822054d
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095612"
---
# <a name="transactional-churn-prediction-preview"></a>Perdavimo nutraukimo prognozė (peržiūra)

Perdavimo nutraukimo prognozė padeda nuprognozuoti, ar klientas daugiau nebepirks jūsų produktų ar paslaugų per tam tikrą laiko langą. Galite sukurti naują nutraukimo prognozę **Įžvalga** > **Prognozės**. Norėdami pamatyti kitas jūsų sukurtas prognozes pasirinkite **Mano prognozės**.

> [!TIP]
> Pabandykite mokymus perdavimo nutraukimo prognozei naudojant pavyzdžio duomenis: [Perdavimo nutraukimo prognozės (peržiūros) pavyzdžio vedlys](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Verslo žinios, kad suprastumėte, ką praradimas reiškia verslui. Palaikome laiku pagrįstas nutraukimo sąvokas reiškiančias, kad klientas nutraukė po tam tikro nepirkimo laikotarpio.
- Duomenys apie jūsų operacijas/pirkimus ir jų istorija:
    - Perlaidos identifikatoriai skirti atskirti įsigijimus/perlaidas.
    - Kliento identifikatoriai atitinka perlaidas jūsų klientams.
    - Perlaidos įvykio datos, kurios nustato perlaidos datą.
    - Semantinei duomenų schemai įsigijimui/perlaidoms būtina tolesnė informacija:
        - **Perlaidos ID:** Unikalusis įsigijimo ar perlaidos identifikatorius.
        - **Perlaidos data:** Perlaidos ir įsigijimo data.
        - **Perlaidos vertė:** Elemento/perlaidos kiekio skaitmeninė vertė/valiuta.
        - (Pasirenkama) **Unikalus gaminio ID:** Gaminio ID ar paslaugos įsigytos, jei jūsų duomenys yra elemento lygmens linijoje.
        - (Pasirenkama) **Ar ši perlaida buvo grįžtamoji:** Tiesos/netiesos laukelis nurodo, ar perlaida buvo grąžinta ar ne. Jei **Perlaidos vertė** yra neigiama, mes taip pat naudosime šią informaciją grįžimo numatymui.
- (Pasirenkamas) Duomenys apie kliento veiklas:
    - Veiklos identifikatoriai, padedantys atskirti to paties tipo veiklas.
    - Klientų identifikatoriai, siejantys veiklas su klientais.
    - Veiklos informacija, apimanti veiklos pavadinimą ir datą.
    - Kliento veiklų semantinė duomenų schema apima:
        - **Pirminis raktas:** unikalusis veiklos identifikatorius. Pavyzdžiui, interneto svetainės lankymas ar įrašo naudojimas rodo, kad klientas išbandė jūsų produkto pavyzdį.
        - **Laiko žymė:** pirminio rakto identifikuoto įvykio data ir laikas.
        - **Įvykis:** įvykio, kurį norite naudoti, pavadinimas. Pavyzdžiui, laukelis pavadintas „Naudotojo veiksmas“ prekių parduotuvėje gali būti kliento naudojamas kuponas.
        - **Informacija:** išsami informacija apie įvykį. Pavyzdžiui, laukelis pavadintas „Kupono vertė“ prekių parduotuvėje gali būti kupono valiutos vertė.
- Siūlomos duomenų charakteristikos:
    - Pakankami istoriniai duomenys: sandorio duomenys bent dvigubam pasirinkto laiko tarpui. Geriausia, nuo dviejų iki trijų duomenų prenumeratos metų. 
    - Keli pirkimai vienam klientui: geriausia bent du sandoriai kiekvienam klientui.
    - Klientų skaičius: bent 10 klientų profilių, geriausia daugiau nei 1 000 klientų. Modelis neveiks su mažiau nei 10 klientų, o istoriniai duomenys bus nepakankami.
    - Duomenų užbaigtumas: mažiau nei 20 % trūkstamų reikšmių pateiktame objekto duomenų laukelyje.

> [!NOTE]
> Įmonėms su didesniu klientų pirkimo dažniu (kas kelias savaites) rekomenduojama rinktis trumpesnį prognozės laikotarpį su perkėlimo apibrėžimu. Esant mažam pirkimo dažniui (kas keletą mėnesių arba kartą per metus) pasirinkite ilgesnį prognozės laikotarpį ir perkėlimo apibrėžimą.

## <a name="create-a-transactional-churn-prediction"></a>Sukurkite perlaidos nutraukimo prognozę

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Pasirinkite **Kliento nutraukimo modelis (peržiūra)** plytą ir pasirinkite **Naudoti šį modelį**.
   
1. **Kliento nutraukimo modelio** juostoje pasirinkite **Perlaidos** ir pasirinkite **Pradėti**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Momentinė ekrano nuotrauka su pasirinkta perlaidos parinktimi kliento nutraukimo modelio juostoje.":::

### <a name="name-model"></a>Pavadinimo modelis

1. Suteikite modeliui pavadinimą, kad atskirtumėte jį nuo kitų modelių.

1. Išvesties objekto pavadinimui nurodyti galite naudoti tik raides ir skaičius be tarpų. Tai pavadinimas, kurį naudos modelio objektas. 

1. Pasirinkite **Toliau**.

### <a name="define-customer-churn"></a>Apibrėžkite kliento praradimą

1. Nustatykite dienų langą siekiant nuprognozuoti nutraukimą **Nustatyti klientus, kurie gali atsisakyti per tolesnį laiką** laukelį. Pavyzdžiui, prognozuoti jūsų klientų nutraukimo riziką kitoms 90 dienų siekiant suderinti su jūsų reklamos laikymo pastangomis. Nutraukimo rizikos prognozavimas ilgesniam ar trumpesniam laikotarpiui gali apsunkinti faktorių nustatymą jūsų atsisakymo rizikos profilyje, bet jis priklauso nuo konkrečių verslo reikalavimų. 
   >[!TIP]
   > **Įrašyti ir uždaryti** galite pasirinkti bet kuriuo metu, kad prognozė būtų išsaugota kaip juodraštis. Norėdami tęsti, prognozės juodraštį galite rasti skirtuke **Mano prognozė**.

1. Įveskite dienų skaičių siekiant nustatyti atsisakymą **Klientas atsisakė, jei jie neatliko jokių pirkimų per:** laukelį. Pavyzdžiui, jei klientas nieko nenupirko per paskutines 30 dienų, jis gali būti laikomas atsisakęs jūsų verslo paslaugų. 

1. Norėdami tęsti, spustelėkite **Pirmyn**

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Pasirinkite **Įtraukti duomenis** skirtus **Įsigijimo istorijai** ir pasirinkite objektą, kuris pateikia perlaidos/įsigijimo istorijos informaciją kaip aprašyta [būtinosiose sąlygose](#prerequisites).

1. Sudarykite semantinių laukelių žemėlapį į atributus per jūsų įsigijimo istorijos objektą ir pasirinkite **Kitas**. Norėdami peržiūrėti laukų aprašymus, peržiūrėkite [būtinąsias sąlygas](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Sudarykite semantinių įsigijimo objekto laukelių žemėlapį.":::

1. Jei laukeliai nėra užpildyti, konfigūruokite ryšius iš jūsų įsigijimo istorijos laukelio į kliento laukelį.
    1. Pasirinkite **Įsigijimo istorijos objektas**.
    1. Pasirinkite **Laukelis**, kuris nustato klientą įsigijimo istorijos objekte. Ji turi būti susijęs su kliento objekto pirminiu kliento ID.
    1. Pasirinkite **kliento objektą**, atitinkantį pirminį kliento objektą.
    1. Įveskite pavadinimą, apibūdinantį ryšį.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Įsigijimo istorijos puslapis rodo ryšių sukūrimą su klientu.":::
   
1. Pasirinkite **Toliau**.

1. Pasirinktinai, pasirinkite **Įtraukti duomenis** skirtus **Kliento veikloms**. Pasirinkite objektą, kuris pateikia kliento veiklos informaciją kaip aprašyta būtinosiose sąlygose.

1. Sudarykite semantinių laukelių žemėlapį į atributus per jūsų kliento veiklos objektą ir pasirinkite **Kitas**. Norėdami peržiūrėti laukų aprašymus, peržiūrėkite [būtinąsias sąlygas](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Susieti klientų operacijų laukelius transakcijų duomenims.":::

1. Pasirinkite veiklos tipą, kuris atitinka konfigūruojamos kliento veiklos tipą. Pasirinkite **Sukurti naują** ir pasirinkite esamą veiklos tipą ar sukurkite naują tipą.

1. Turėsite sukonfigūruoti kliento veiklos objekto ryšį su kliento objektu.
    1. Pasirinkite laukelį, kuris nustato klientą kliento veiklos lentelėje. Jis gali būti tiesiogiai susietas su jūsų kliento objekto pirminiu kliento ID.
    1. Pasirinkite kliento objektą, atitinkantį pirminį kliento objektą
    1. Įveskite pavadinimą, apibūdinantį ryšį.

1. Pasirinkite **Įrašyti**.

1. Jei turite bet kurias kitas kliento veiklas, kurias norite įtraukti, pakartokite ankstesnius žingsnius.

1. Pasirinkite **Toliau**.

### <a name="set-schedule-and-review-configuration"></a>Grafiko ir peržiūros konfigūravimo nustatymas

1. Nustatykite modelio apmokymo iš naujo dažnumą. Šie nustatymai yra svarbūs siekiant atnaujinti prognozių tikslumą, kaip naujų duomenų naudojimą. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

1. Peržiūrėti prognozės konfigūravimą. Galite eiti atgal keletą žingsnių pasirinkę **Redaguoti** po rodoma verte. Arba galite pažymėti konfigūravimo veiksmą eigos indikatoriuje.

1. Jei visos reikšmės sukonfigūruotos teisingai, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte prognozavimo procesą. Skirtuke **Mano prognozės** galite matyti savo prognozių būseną. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

## <a name="review-a-prediction-status-and-results"></a>Prognozės būsenos ir rezultatų peržiūra

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite prognozę, kurią norite peržiūrėti.
   - **Prognozės pavadinimas:** Įvardykite prognozę jos kūrimo metu.
   - **Prognozės tipas:** Prognozei naudojamo modelio tipas
   - **Išvesties objektas:** objekto, kuriame saugoma prognozės išvestis, pavadinimas. Objektą šiuo pavadinimu galite rasti **Duomenys** > **Objektai**.    
     Resultato objekte *„ChurnScore“* yra prognozuojama netekimo tikimybė, o *„IsChurn“* yra dvejetainė žyma, pagrįsta *„ChurnScore“* su 0,5 ribine verte. Numatytoji ribinė vertė jūsų scenarijui gali neveikti. [Sukurkite naują segmentą](segments.md#create-a-new-segment) su jūsų pageidaujama ribine verte.
     Ne visi klientai būtinai yra aktyvūs klientai. Kai kurie ilgą laiką gali būti neturėję jokios veiklos ir jau yra laikomi perkeltais pagal perkėlimo apibrėžimą. Jau perkeltų klientų perkėlimo riziką prognozuoti nėra naudinga, nes jie nėra dominanti auditorija.
   - **Prognozuotas laukelis:** Šis laukelis užpildomas keliems prognozių tipams ir nėra naudojamas nutraukimo prognozėje.
   - **Būsena:** Prognozės vykdymo būsena.
        - **Laukiama:** Prognozė laukia kitų procesų vykdymo.
        - **Paleidimas iš naujo:** Prognozė šiuo metu vykdoma siekiant sukurti rezultatus, kurie susilies į išvesties objektą.
        - **Nepavyko:** Prognozės vykdymas nepavyko. [Peržiūrėkite įrašus](manage-predictions.md#troubleshoot-a-failed-prediction) dėl išsamesnės informacijos.
        - **Pavyko:** Prognozė pavyko. Norėdami peržiūrėti prognozę, po vertikaliu daugtaškiu pasirinkite  **Rodyti**
   - **Redaguota:** data, kai buvo pakeista prognozės konfigūracija.
   - **Paskutinį kartą atnaujinta:** data, kai prognozė atnaujino rezultatus išvesties objekte.

1. Pažymėkite vertikalius daugtaškius šalia prognozės, kurios rezultatus norite peržiūrėti, ir pasirinkite **Rodyti**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Peržiūrėkite valdiklį tam, kad pamatytumėte prognozės rezultatus.":::   

1. Rezultatų puslapyje yra trys pagrindinės duomenų dalys:
    1. **Mokymo modelio efektyvumas:** galimi balai yra A, B arba C. Šis rezultatas nurodo prognozės efektyvumą ir gali padėti apsispręsti naudoti išvesties objekte saugomus rezultatus. Balai nustatomi pagal šias taisykles:
         
         - **A** kai prognozės modelio tikslumas yra mažiausiai 50% visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra didesnis nei slenksčio lygis mažiausiai 10%.
            
         - **B** kai prognozės modelio tikslumas yra mažiausiai 50 % visų prognozių ir kai prognozių tikslumo procentas klientams, kurie nutraukė, yra iki 10% didesnis nei slenksčio lygis.
            
         - **C** kai prognozės modelio tikslumas yra mažesnis 50% visų prognozių ar kai prognozių tikslumo procentas nutraukusiems klientams yra mažesnis nei slenksčio lygis.
               
         - **Slenkstis** užima prognozės laiko lango įvestį modeliui (pavyzdžiui, vieneri metai), o modelis sukuria kitus laiko tarpus dalydamas juos iš 2 iki tol, kol pasiekia vieną mėnesį ar mažiau. Jis naudoja šiuos tarpus, kad sukurtų verslo taisykles klientams, kurie neįsigijo jų šiuo laikotarpiu. Šie klientai laikomi atsisakę. Laiko pagrįsta veiklos taisyklė su didesniu pajėgumu nuspėti, kas greičiausiai atsisakys yra pasirenkamas kaip slenksčio modelis.
            
    1. **Praradimo tikimybė (klientų skaičius):** klientų grupės pagal prognozuojamą praradimo riziką. Šie duomenys gali būti naudingi vėliau, jei norite sukurti klientų segmentą su didele praradimo rizika. Tokie segmentai padeda suprasti, kokios turėtų būti priklausymo segmentui ribinės reikšmės.
       
    1. **Svarbiausi veiksniai:** kuriant prognozę, atsižvelgiama į daugelį veiksnių. Visi faktoriai turi savo apskaičiuotą svarbą sujungtoms prognozėms, kurias sukuria modelis. Šiuos veiksnius galite naudoti prognozės rezultatams patvirtinti. Arba šią informaciją galite naudoti vėliau [kurdami segmentus](segments.md), kurie gali padėti paveikti klientų praradimo riziką.

## <a name="manage-predictions"></a>Prognozių valdymas

Prognozes galima optimizuoti, šalinti jų triktis, atnaujinti arba panaikinti. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
