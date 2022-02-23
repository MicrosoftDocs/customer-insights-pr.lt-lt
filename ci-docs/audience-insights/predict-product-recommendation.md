---
title: Produkto rekomendacijos prognozė
description: Prognozuojami produktai, kuriuos klientas gali įsigyti arba su jais bendrauti.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 62b829b6ca3074e0ca52fb52584b74572bb05f05
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967849"
---
# <a name="product-recommendation-prediction-preview"></a>Produkto rekomendacijos prognozė (apžvalga)

Produktų rekomendacijų modelis sukuria prognozuojamų produktų rekomendacijų rinkinius. Rekomendacijos pagrįstos ankstesniu pirkimo elgsena ir klientais, kurie turi panašius pirkimo modelius. Puslapyje prognozės galite kurti naujas prognozes **Įžvalgos** > **Prognozių** puslapyje. Norėdami pamatyti kitas jūsų sukurtas prognozes pasirinkite **Mano prognozės**.

Produkto rekomendacijos gali būti taikomos pagal vietinius įstatymus ir reglamentus bei klientų lūkesčius, į kuriuos modelis nėra sukurtas atsižvelgti.  Kaip šios prognozuojančios galimybės naudotojas, **turite peržiūrėti rekomendacijas prieš pristatydamas jas savo klientams**, kad užtikrintumėte, jog vadovaujatės galiojančiais įstatymais ar reglamentais bei klientų lūkesčiais dėl galimų jūsų rekomendacijų. 

Be to, iš šio modelio rezultatų gausite rekomendacijų, pagrįstų produkto ID. Jūsų pateikimo mechanizmas turės pažymėti prognozuojamus produkto ID su tinkamu turiniu, kad jūsų klientai galėtų atsižvelgti į lokalizavimą, vaizdų turinį ir kitą įmonei būdingą turinį arba elgseną.

## <a name="sample-guide"></a>Pavyzdžio vadovas

Jei norėtumėte išbandyti šią funkciją, tačiau neturite duomenų toliau pateiktiems reikalavimams įvykdyti, galite [sukurti diegimo pavyzdį](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.

- Verslo žinių, kad būtų galima suprasti įvairius jūsų įmonės produktų tipus ir klientų bendravimą su jais. Palaikome produktų, kuriuos anksčiau įsigijo jūsų klientai, rekomendavimas arba naujų produktų rekomendacijos.

- Duomenys apie operacijas, pirkinius ir jų retrospektyvą:
    - Operacijų identifikatoriai, skirti pirkimams arba operacijoms.
    - Klientų identifikatoriai, siejantys operacijas su klientais.
    - Operacijos įvykio datos, nurodančios operacijos atlikimo datas.
    - Operacijos produkto ID informacija.
    - (Pasirinktinai) Produktų katalogo duomenų objektas produktų filtrui naudoti.
    - (Pasirinktinis) Jei operacija yra grįžtamoji, ar ne.
    - Semantinė duomenų schema reikalauja šios informacijos:
        - **Perlaidos ID:** Unikalusis įsigijimo ar perlaidos identifikatorius.
        - **Sandorio data:** sandorio arba įsigijimo data.
        - **Operacijos reikšmė:** pirkimo arba operacijos skaitinė reikšmė.
        - **Unikalus produkto ID:** įsigyto produkto arba aptarnavimo ID, jei duomenys yra eilutės elemento lygyje.
        - (Pasirinktinai) **Pirkimas arba grąžinimas:** bulio logikos laukelis, kuriame reikšmė *teisinga* nustato, kad sandoris buvo grąžinimas. Jei pirkimo arba grąžinimo data nenurodytą, modelis ir **sandorio vertė** yra neigiama, mes taip pat naudosime šią informaciją grąžinimui numatyti.
- Siūlomos duomenų charakteristikos:
    - Pakankami istoriniai duomenys: bent vieneri metai operacijos duomenų, geriausiai dveji ar treji metai, įskaitant sezoniškumą.
    - Keli pirkimai vienam klientui: trys ar daugiau sandorių kiekvienam kliento ID
    - Klientų skaičius: bent 100 klientų, geriausia daugiau nei 10 000 klientų. Modelio nepavyks naudoti turint mažiau nei 100 klientų.

> [!NOTE]
> - Modeliui reikia jūsų klientų sandorių istorijos. Sandorio apibrėžtis yra gana lanksti. Bet kokie duomenys, apibūdinays naudotojo ir produkto sąveiką, gali veikti kaip įvestis. Pavyzdžiui, produkto įsigijimas, dalyvavimas pamokoje ar renginyje.
> - Vienu metu galima sukonfigūruoti tik vieną sandorio istorijos objektą. Jei yra keli pirkimo objektai, sujunk juos Power Query prieš nurijus duomenis.
> - Jei užsakymas ir užsakymo duomenys yra skirtingi objektai, prieš naudodami modelį juos sujunkite. Modelis objekte neveikia tik su užsakymo ID ar gavimo ID.


## <a name="create-a-product-recommendation-prediction"></a>Kurkite produkto rekomendacijos prognozę

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Rinkitės **Produkto rekomendacijų modelis (peržiūra)** plytelę ir rinkitės **Naudoti šį** modelį.
   > [!div class="mx-imgBorder"]
   > ![Produkto rekomendacijų modelio plytelė su mygtuku Naudoti šį modelį.](media/product-recommendation-usethismodel.PNG "Produkto rekomendacijų modelio plytelė su mygtuku Naudoti šį modelį")

1. Peržiūrėkite informaciją apie modelio reikalavimus. Jei turite reikiamus duomenis, pažymėkite **Darbo pradžia**.

### <a name="name-model"></a>Pavadinimo modelis

1. Suteikite modeliui pavadinimą, kad atskirtumėte jį nuo kitų modelių.

1. Įveskite išvesties objekto pavadinimą tik raidėmis ir skaičiais be tarpų. Tai pavadinimas, kurį naudos modelio objektas. Tada pasirinkite **Toliau**.

### <a name="define-product-recommendation-configuration"></a>Produkto rekomendacijų konfigūracijos apibrėžimas

1. Nustatykite **Produktų skaičių,** kurį norite rekomenduoti klientui. Ši reikšmė priklauso nuo to, kaip pristatymo metodas užpildo duomenis. Jei galite rekomenduojate tris produktus, atitinkamai nustatykite šią reikšmę.
   
   >[!TIP]
   > Norėdami **įrašyti** prognozė juodraštį kaip juodraštį, galite bet kada pasirinkti Įrašyti juodraštį. Straipsnio juodraštį rasite prognozėje **Mano prognozės** skirtuke.

1. Pasirinkite, ar norite įtraukti produktus, kuriuos pirkėjai neseniai įsigijo **lauke Numatoma pakartoti** pirkimus.

1. Nustatykite **langą Žiūrėti atgal**. Šis parametras nurodo laikotarpį, kurį modelis atsižvelgia prieš rekomenduodamas produktą vartotojui dar kartą. Pavyzdžiui, nurodykite, kad klientas perka nešiojamąjį kompiuterį kas dvejus metus. Šiame lange peržiūrėkite paskutinių dviejų metų pirkimo istoriją, o radus prekę ji bus filtruojama iš rekomendacijų.

1. Pasirinkti **Toliau**

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Pasirinkite **Įtraukti duomenis** ir pasirinkite veiklos tipą šoninėje srityje, kurioje yra reikiama operacijos arba pirkimo retrospektyvos informacija.

1. Dalyje **Pasirinkti veiklas** pasirinkite konkrečias veiklas iš pažymėtos veiklos, į kurios norite susitelkti skaičiuojant.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Šoninė sritis, vaizduojanti semantikos tipo konkrečių veiklų pasirinkimą.":::

1. Jeigu dar nesusiejote veiklos su semantiniu tipu, pasirinkite **Redaguoti**, kad tai atliktumėte. Atidaroma interaktyvioji semantinių veiklų susiejimo parinktis. Susiekite savo duomenis su atitinkamais pasirinkto veiklos tipo laukais.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Puslapio parametro veiklos tipas.":::

1. Susieję veiklą su atitinkamu semantiniu tipu, pažymėkite **Toliau**, kad tęstumėte 
 
1. Susiekite semantinius atributus su laukais, kurių reikia modeliui paleisti.

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**.


### <a name="configure-product-filters"></a>Produkto filtrų konfigūravimas

Kartais tik tam tikri produktai yra naudingi arba tinkami jūsų sukurtos prognozės tipui. Produktų filtrai leidžia identifikuoti produktų pogrupį su konkrečiomis charakteristikomis jūsų klientams rekomenduoti. Modelis naudos visus produktus, kuriuos galima naudoti modeliams sužinoti, tačiau naudos tik tuos produktus, kurie atitinka produkto filtrą jo rezultate.

1. Atlikdami veiksmą **Pridėti produkto informaciją** pridėkite produkto katalogą su kiekvienu produktu. Reikiamą informaciją pažymėkite ir pasirinkite **Toliau**.

3. Atlikdami veiksmą **Produktų filtrai** rinkitės iš toliau nurodytų parinkčių.

   * **Jokių filtrų**: naudokite visus produktus iš rekomenduojamų produktų prognozės.

   * **Konkrečių produktų filtrų apibrėžimas**: naudokite konkrečius produktus produktų rekomendacijų prognozėje.

1. Pasirinkite **Toliau**.

1. Jei renkatės apibrėžti produktų filtrą, turite jį apibrėžti dabar. Srityje **Produktų katalogo atributai** pasirinkite atributus iš savo *Produktų katalogo objekto*, kurį norite įtraukti į filtrą.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Šoninė sritis, kurioje rodomi produktų katalogo objekto atributai produktų filtrams pasirinkti.":::

1. Pasirinkite, ar norite, kad produktų filtre būtų naudojamos jungtys **ir** ar **arba**, kad logiškai derintumėte atributų pasirinkimą iš produktų katalogo.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Produktų filtrų su loginėmis AND jungtimis konfigūravimo pavyzdys.":::

1. Pasirinkite **Toliau**.

### <a name="set-update-schedule-and-review-configuration"></a>Naujinimo grafiko ir peržiūros konfigūravimo nustatymas

1. Nustatykite modelio apmokymo iš naujo dažnumą. Šis parametras svarbus norint atnaujinti prognozių tikslumą, kai į „Customer Insights“ importuojami nauji duomenys. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

1. Peržiūrėkite konfigūraciją. Prie bet kurios prognozės konfigūracijos dalies galite sugrįžti pažymėdami **Redaguoti** po rodoma reikšme. Arba galite pažymėti konfigūravimo veiksmą eigos indikatoriuje.

1. Jei visos reikšmės sukonfigūruotos teisingai, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte prognozavimo procesą. Skirtuke **Mano prognozės** galite matyti savo prognozių būseną. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

## <a name="review-a-prediction-status-and-results"></a>Prognozės būsenos ir rezultatų peržiūra

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.
   > [!div class="mx-imgBorder"]
   > ![Mano prognozių puslapio rodinys.](media/product-recommendation-mypredictions.PNG "Mano prognozių puslapio rodinys")

1. Pasirinkite prognozę, kurią norite peržiūrėti.
   - **Prognozės pavadinimas:** kūrimo metu nurodytas prognozės pavadinimas.
   - **Prognozės tipas:** prognozei naudojamo modelio tipas
   - **Išvesties objektas:** objekto, kuriame saugoma prognozės išvestis, pavadinimas. Objektą šiuo pavadinimu galite rasti **Duomenys** > **Objektai**.    
      *Balai* išvesties objekte yra kiekybinė rekomendacijos priemonė. Modelis rekomenduoja produktus, kurių rezultatai geresni, o ne produktus, kurių rezultatai prastesni.
   - **Prognozavimo laukelis:** šis laukelis pildomas tik tam tikro tipo prognozėms ir nėra naudojamas produktų rekomendavimo prognozei.
   - **Būsena:** dabartinė prognozės vykdymo būsena.
        - **Eilėje:** prognozė šiuo metu laukia kitų vykdomų procesų.
        - **Atnaujinama:** šiuo metu vykdomas prognozės „rezultato“ apdorojimo etapas, kurio metu gauti rezultatai bus perduoti į išvesties objektą.
        - **Nepavyko:** prognozė nepavyko. Norėdami gauti daugiau informacijos, pasirinkite **Žurnalai**.
        - **Pavyko:** prognozė sėkminga. Norėdami peržiūrėti prognozę, po vertikaliu daugtaškiu pasirinkite  **Rodyti**
   - **Redaguota:** data, kai buvo pakeista prognozės konfigūracija.
   - **Paskutinį kartą atnaujinta:** data, kai prognozė atnaujino rezultatus išvesties objekte.

1. Pažymėkite vertikalius daugtaškius šalia prognozės, kurios rezultatus norite peržiūrėti, ir pasirinkite **Rodyti**.
   > [!div class="mx-imgBorder"]
   > ![Prognozės parinkčių peržiūra vertikalių daugtaškių meniu, įskaitant redagavimą, atnaujinimą, peržiūrą, žurnalus ir šalinimą.](media/product-recommendation-verticalellipses.PNG "Prognozės parinkčių peržiūra vertikalių daugtaškių meniu, įskaitant redagavimą, atnaujinimą, peržiūrą, žurnalus ir šalinimą")

1. Rezultatų puslapyje yra penkios pagrindinės duomenų skiltys:
    1. **Mokymo modelio efektyvumas:** galimi balai yra A, B arba C. Šis rezultatas nurodo prognozės efektyvumą ir gali padėti apsispręsti naudoti išvesties objekte saugomus rezultatus.
        - Balai nustatomi pagal šias taisykles:
            - **Modelis** bus laikomas **kokybišku, jei** „Sėkmės @ K” metrika bus bent 10 % daugiau nei pradinė. 
            - **B** Modelis laikomas **B** kokybės, jei „Success @ K“ metrika yra nuo 0 % iki 10 % didesnė nei pradinė vertė.
            - **C** Modelis laikomas **C** kokybės, jei „Success @ K“ metrika yra mažesnė nei pradinė vertė.
               
               > [!div class="mx-imgBorder"]
               > ![Modelio efektyvumo rezultato rodinys.](media/product-recommendation-modelperformance.PNG "Modelio efektyvumo rezultato rodinys")
            - **Pradinis**: modelis atsižvelgia į svarbiausius rekomenduojamus produktus, kai perkant naudojami visi klientai ir, naudojant modelio nustatytas išmokintas taisykles, klientams nustatomas rekomendacijų rinkinys. Tada prognozės lyginamos su geriausiais produktais ir apskaičiuojamos pagal klientų, kurie įsigijo produktą, skaičių. Jei klientas savo rekomenduojamuose produktuose turi bent vieną produktą, kuris taip pat buvo matomas geriausiai įsigytuose produktuose, jis laikomas pradinės linijos dalimi. Jei 10 iš šių klientų būtų įsigiję rekomenduojamą produktą iš 100 bendro klientų, pradinis atskaitos skaičius būtų 10%.
            - **Sėkmė @ K**: naudojant operacijų laikotarpio tikrinimo rinkinį, visiems klientams kuriamos rekomendacijos ir jos lyginamos su operacijų tikrinimo rinkinys. Pavyzdžiui, 12 mėnesių laikotarpiu 12 mėnesį galima atidėti kaip duomenų tikrinimo rinkinį. Jei modelis numato bent vieną dalyką, kurį galėtumėte įsigyti 12 mėnesį pagal tai, ką jis išmoko iš ankstesnių 11 mėnesių, klientas padidins metriką „Sėkmė @ K”.
    
    1. **Daugelis siūlomų produktų (su rezultatu):** penki pagrindiniai produktai, kurie buvo prognozuojami klientams.
       > [!div class="mx-imgBorder"]
       > ![Grafikas, kuriame rodomi 5 populiariausi produktai.](media/product-recommendation-topproducts.PNG "Grafikas, kuriame rodomi 5 populiariausi produktai")
    
    1. **Pagrindiniai rekomendacijų veiksniai:** produktų rekomendacijoms teikti modelis naudoja klientų sandorių istoriją. Jis išmoksta modelius pagal paskutinius pirkimus ir rand panašumų tarp klientų ir produktų. Tada šie panašumai naudojami produktų rekomendacijoms generuoti.
    Toliau nurodyti veiksniai, galintys turėti įtakos pagal modelį sugeneruotai produkto rekomendacijai. 
        - **Ankstesni sandoriai**: praeityje pirkimo šablonus modelis naudojo produkto rekomendacijoms generuoti. Pavyzdžiui, modelis gali rekomenduoti _„Surface Arc Mouse“_, jei kas nors neseniai įsigijo _„Surface Book 3“_ ir _„Surface Pen“_. Atsižvelgdamas į istoriją modelis išmoko, kad daug klientų įsigijo _„Surface Arc Mouse“_ po to, kai įsigijo _„Surface Book 3“_ ir _„Surface Pen“_.
        - **Kliento panašumas**: rekomenduojamą produktą istoriškai įsigijo kiti klientai, kurių pirkimo modeliai yra panašūs. Pavyzdžiui, Jonui buvo rekomenduojama įsigyti _„Surface Headphones 2“_, nes Joana ir Brunas neseniai įsigijo _„Surface Headphones 2“_. Modelis mano, kad Jonas yra panašus į Joaną ir Bruną, nes istoriškai jų pirkimo modeliai buvo panašūs.
        - **Produktų panašumas**: rekomenduojamas produktas yra panašus į kitus produktus, kuriuos anksčiau pirko klientas. Modelis abu produktus laiko panašiais, jei jie buvo perkami kartu arba juos pirko panašūs klientai. Pavyzdžiui, žmogus gauna rekomendaciją įsigyti _USB talpyklą_, nes anksčiau jis įsigijo _USB-C ir USB adapterį_, todėl modelis mano, kad _USB talpykla_ yra panaši į _USB-C ir USB adapterį_, atsižvelgiant į istorinius pirkimo modelius.

        Kiekvienai produkto rekomendacijosi įtakos turi vienas ar keli iš šių veiksnių. Rekomendacijų, kai kiekvienas įtakojantis veiksnys atliko tam tikrą vaidmenį, dalis procentais vaizduojama diagramoje. Toliau pateikiamme pavyzdyje 100 % rekomendacijų įtakos turėjo ankstesni sandoriai. Iš jų 60 % pagal klientų panašumą, o 22 % pagal produktų panašumą. Pelės žymeklį palaikykite virš diagramos juostų, kad peržiūrėtumėte procentinę įtaką darančių veiksnių dalį.

        > [!div class="mx-imgBorder"]
        > ![Pagrindiniai rekomendacijų veiksniai.](media/product-recommendation-keyrecommendationfactors.png "Pagrindiniai rekomendacijų veiksniai, kuriuos išmoksta modelis produktų rekomendacijoms generuoti")
       
     
   1. **Duomenų statistika**: apžvelgiamas operacijų, klientų ir produktų, į kuriuos atsižvelgė modelis, skaičius. Jis pagrįstas įvesties duomenimis, kurie buvo naudojami modeliams išmokti ir produkto rekomendacijoms generuoti.

      > [!div class="mx-imgBorder"]
      > ![Duomenų statistika.](media/product-recommendation-datastatistics.png "Duomenų statistika apie modelio naudojamus įvesties ir išvesties duomenis šablonams išmokti")

      Šiame skyriuje rodoma duomenų taškų, kuriuos modelis naudojo modelyje, statistika, siekiant išmokti modelius ir generuoti produkto rekomendacijas. Filtravimas, sukonfigūruotas modelio konfigūracijoje, bus taikomas modelio sugeneruotam rezultatui. Tačiau modelis naudoja visus turimus duomenis modeliams išmokti. Todėl, jei modelio konfigūracijoje naudosite produktų filtravimą, šiame skyriuje bus rodomas bendras produktų, kuriuos išanalizavo modelis, kad išmoktų šablonus, skaičius, kuris gali skirtis nuo apibrėžtus filtravimo kriterijus atitinkančių produktų skaičiaus.

   1. **Didelio pasitikėjimo produktų rekomendacijos:** jūsų klientams pateiktų rekomendacijų, kuris modelis tikėtinai bus nupirktas kliento, pavyzdys.    
      Jei pridedamas produktų katalogas, produkto ID pakeičiamas produktų pavadinimais. Produktų pavadinimuose pateikiama daugiau veiksmų ir intuityvios informacijos apie prognozes.
       > [!div class="mx-imgBorder"]
       > ![Sąrašas, kuriame rodomi aukšti pavienių klientų rinkinio pasiūlymai.](media/product-recommendation-highconfidence.PNG "Sąrašas, kuriame rodomi aukšti pavienių klientų rinkinio pasiūlymai")

## <a name="manage-predictions"></a>Prognozių valdymas

Prognozes galima optimizuoti, šalinti jų triktis, atnaujinti arba panaikinti. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
