---
title: Produkto rekomendacijos prognozė
description: Prognozuojami produktai, kuriuos klientas gali įsigyti arba su jais bendrauti.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270515"
---
# <a name="product-recommendation-prediction-preview"></a>Produkto rekomendacijos prognozė (apžvalga)

Produktų rekomendacijų modelis sukuria prognozuojamų produktų rekomendacijų rinkinius. Rekomendacijos pagrįstos ankstesniu pirkimo elgsena ir klientais, kurie turi panašius pirkimo modelius. Puslapyje prognozės galite kurti naujas prognozes **Įžvalgos** > **Prognozių** puslapyje. Norėdami pamatyti, ką sukūrėte, pasirinkite **Nano prognozės**.

Produkto rekomendacijos gali būti taikomos pagal vietinius įstatymus ir sprendimus bei klientų lūkesčius, į kuriuos modelis nėra sukurtas tam, kad būtų galima specialiai atsižvelgti.  Kaip šios prognozuojamos galimybės, **vartotojas, prieš pristatant jas klientams, turite peržiūrėti rekomendacijas,** kad užtikrintumėte, jog laikote visų taikytinų įstatymų ir nuostatų dėl klientų lūkesčius, kurių galite tikėtis. 

Be to, iš šio modelio rezultatų gausite rekomendacijų, pagrįstų produkto ID. Jūsų pateikimo mechanizmas turės atsižvelgti į prognozuojamus produkto ID ir susieti juos su tinkamu klientų turiniu, kad jis būtų lokalizuotas, vaizdas ir kitas su verslu susietas turinys arba elgsena.

## <a name="sample-guide"></a>Pavyzdžio vadovas

Jei norėtumėte išbandyti šią funkciją, tačiau neturite duomenų toliau pateiktiems reikalavimams įvykdyti, galite [sukurti diegimo pavyzdį](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.
- Verslo žinių, kad būtų galima suprasti įvairius jūsų įmonės produktų tipus ir klientų bendravimą su jais. Palaikome produktų, kuriuos anksčiau įsigijo jūsų klientai, rekomendavimas arba naujų produktų rekomendacijos.
- Duomenys apie operacijas, pirkinius ir jų retrospektyvą:
    - Transakcijos identifikatoriai, skirti pirkti ar transakkcijos.
    - Klientų identifikatoriai, siejantys transakcijas su klientais.
    - Transakcijos įvykio datos, nurodanti datas, kada įvyko operacija.
    - (Pasirinktinis) Operacijos produkto ID informacija.
    - (Pasirinktinis) Jei operacija yra grąža, ar ne.
    - Semantinė duomenų schema reikalauja šios informacijos:
        - **Perlaidos ID:** Unikalus įsigijmo ar perlaidos identifikatorius.
        - Lauke **Transakcijos data** nurodoma operacijos ar įsigijimo data.
        - **Operacijos reikšmė:** pirkimo arba transakcijos skaitinė reikšmė.
        - **Unikalus produkto ID:** įsigyto produkto arba aptarnavimo ID, jei duomenys yra eilutės elemento lygyje.
        - (pasirinktinis) **Pirkimas arba grąžinimas:** teisingas / klaidingas laukas, nurodantis, ar operacija buvo grąža, ar ne. Jei **Perlaidos vertė** yra neigiama, mes taip pat naudosime šią informaciją grįžimo numatymui.


## <a name="create-a-product-recommendation-prediction"></a>Kurkite produkto rekomendacijos prognozę

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Rinkitės **Produkto rekomendacijų modelis (peržiūra)** plytelę ir rinkitės **Naudoti šį** modelį.
   > [!div class="mx-imgBorder"]
   > ![Produkto rekomendacijų modelio plytelė su mygtuku Naudoti šį modelį](media/product-recommendation-usethismodel.PNG "Produkto rekomendacijų modelio plytelė su mygtuku Naudoti šį modelį")

1. Peržiūrėkite informaciją apie modelio reikalavimus. Jei turite reikiamus duomenis, pažymėkite **Darbo pradžia**.

### <a name="name-model"></a>Pavadinimo modelis

1. Suteikite modeliui pavadinimą, kad atskirtumėte jį nuo kitų modelių.

1. Įveskite išvesties objekto pavadinimą tik raidėmis ir skaičiais be tarpų. Tai pavadinimas, kurį naudos modelio objektas. Tada pasirinkite **Toliau**.

### <a name="define-product-recommendation-configuration"></a>Produkto rekomendacijų konfigūracijos apibrėžimas

1. Nustatykite **Produktų skaičių,** kurį norite rekomenduoti klientui. Ši reikšmė priklauso nuo to, kaip pristatymo metodas užpildo duomenis. Jei galite rekomenduojate tris produktus, atitinkamai nustatykite šią reikšmę.
   
   >[!TIP]
   > **Įrašyti ir uždaryti** galite pasirinkti bet kuriuo metu, kad prognozė būtų išsaugota kaip juodraštis. Straipsnio juodraštį rasite prognozėje **Mano prognozės** skirtuke.

1. Pasirinkite, jei norite **Siūlyti klientų neseniai įsigytus produktus**.

1. Jei pasirinkote *nerekomenduoti* neseniai įsigytų produktų, nustatykite langą **Peržiūrėti atgal**. Šis parametras nurodo laikotarpį, kurį modelis atsižvelgia prieš rekomenduodamas produktą vartotojui dar kartą. Pavyzdžiui, nurodyti, kad klientas nusipirks nešiojamą kompiuterį kas 2 metus. Šiame lange bus peržiūrėkite paskutinių 2 metų pirkimo retrospektyvą ir, jei elementas bus randamas, jis bus filtruojamas pagal rekomendacijas.

1. Pasirinkti **Toliau**

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Rinkitės **Įtraukti duomenis** skirtus **Kliento operacijų istorijai** ir pasirinkite objektą, kuris pateikia operacijų istorijos informaciją kaip aprašyta [būtinose sąlygose](#prerequisites).

1. Sudarykite semantinių laukelių žemėlapį į atributus per jūsų įsigijimo istorijos objektą ir pasirinkite **Kitas**. Norėdami peržiūrėti laukų aprašymus, peržiūrėkite [būtinąsias sąlygas](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Objekto ryšio apibrėžimas](media/product-recommendation-purchasehistorymapping.PNG "Pirkimo retrospektyvos puslapis, kuriame rodomi semantiniai atributai, susieti su pasirinkto pirkimo retrospektyvos objekto laukais")

1. Jei toliau laukų neužpildote, konfigūruokite ryšį iš pirkimo retrospektyvos objekto į *Kliento* įrašą.
    1. Pasirinkite **Įsigijimo istorijos objektas**.
    1. Pasirinkite **Laukelis**, kuris nustato klientą įsigijimo istorijos objekte. Ji turi būti susijęs su kliento objekto pirminiu kliento ID *Kliento* įraše.
    1. Pasirinkite **kliento objektą**, atitinkantį pirminį kliento objektą.
    1. Įveskite pavadinimą, apibūdinantį ryšį.
       > [!div class="mx-imgBorder"]
       > ![Įsigijimo istorijos puslapis rodo ryšių sukūrimą su klientu](media/model-purchase-join.png "Įsigijimo istorijos puslapis rodo ryšių sukūrimą su klientu")

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**.

### <a name="set-schedule-and-review-configuration"></a>Grafiko ir peržiūros konfigūravimo nustatymas

1. Nustatykite modelio apmokymo iš naujo dažnumą. Šis parametras svarbus norint atnaujinti prognozių tikslumą, kai į „Customer Insights“ importuojami nauji duomenys. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

1. Peržiūrėkite konfigūraciją. Prie bet kurios prognozės konfigūracijos dalies galite sugrįžti pažymėdami **Redaguoti** po rodoma reikšme. Arba galite pažymėti konfigūravimo veiksmą eigos indikatoriuje.

1. Jei visos reikšmės sukonfigūruotos teisingai, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte prognozavimo procesą. Skirtuke **Mano prognozės** galite matyti savo prognozių būseną. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

## <a name="review-a-prediction-status-and-results"></a>Prognozės būsenos ir rezultatų peržiūra

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.
   > [!div class="mx-imgBorder"]
   > ![Mano prognozių puslapio rodinys](media/product-recommendation-mypredictions.PNG "Mano prognozių puslapio rodinys")

1. Pasirinkite prognozę, kurią norite peržiūrėti.
   - **Prognozės pavadinimas:** kūrimo metu nurodytas prognozės pavadinimas.
   - **Prognozės tipas:** prognozei naudojamo modelio tipas
   - **Išvesties objektas:** objekto, kuriame saugoma prognozės išvestis, pavadinimas. Objektą šiuo pavadinimu galite rasti **Duomenys** > **Objektai**.
   - **Prognozuotas laukelis:** Šis laukelis užpildomas keliems prognozių tipams ir nėra naudojamas nutraukimo prognozėje.
   - **Būsena:** dabartinė prognozės vykdymo būsena.
        - **Eilėje:** prognozė šiuo metu laukia kitų vykdomų procesų.
        - **Atnaujinama:** šiuo metu vykdomas prognozės „rezultato“ apdorojimo etapas, kurio metu gauti rezultatai bus perduoti į išvesties objektą.
        - **Nepavyko:** prognozė nepavyko. Norėdami gauti daugiau informacijos, pasirinkite **Žurnalai**.
        - **Pavyko:** prognozė sėkminga. Norėdami peržiūrėti prognozę, po vertikaliu daugtaškiu pasirinkite  **Rodyti**
   - **Redaguota:** data, kai buvo pakeista prognozės konfigūracija.
   - **Paskutinį kartą atnaujinta:** data, kai prognozė atnaujino rezultatus išvesties objekte.

1. Pažymėkite vertikalius daugtaškius šalia prognozės, kurios rezultatus norite peržiūrėti, ir pasirinkite **Rodyti**.
   > [!div class="mx-imgBorder"]
   > ![Prognozės parinkčių peržiūra vertikalių daugtaškių meniu, įskaitant redagavimą, atnaujinimą, peržiūrą, žurnalus ir šalinimą](media/product-recommendation-verticalellipses.PNG "Prognozės parinkčių peržiūra vertikalių daugtaškių meniu, įskaitant redagavimą, atnaujinimą, peržiūrą, žurnalus ir šalinimą")

1. Rezultatų puslapyje yra trys pagrindinės duomenų dalys:
    1. **Mokymo modelio efektyvumas:** galimi balai yra A, B arba C. Šis rezultatas nurodo prognozės efektyvumą ir gali padėti apsispręsti naudoti išvesties objekte saugomus rezultatus.
        - Balai nustatomi pagal šias taisykles:
            - **Modelis** bus laikomas **kokybišku, jei** „Sėkmės @ K" metrika bus bent 10 % daugiau nei pradinė. 
            - **B** bus laikomas kokybišku, jei **B** „Sėkmės @ K" metrika bus nuo 0 iki 10 % didesnė nei pradinė.
            - **C** bus laikomas kokybišku, jei **C** „Sėkmės @ K" metrika bus mažesnė nei pradinė.
               
               > [!div class="mx-imgBorder"]
               > ![Modelio efektyvumo rezultato rodinys](media/product-recommendation-modelperformance.PNG "Modelio efektyvumo rezultato rodinys")
            - **Pradinis**: modelis atsižvelgia į svarbiausius rekomenduojamus produktus, kai perkant naudojami visi klientai ir, naudojant modelio nustatytas išmokintas taisykles, klientams nustatomas rekomendacijų rinkinys. Tada prognozės lyginamos su geriausiais produktais ir apskaičiuojamos pagal klientų, kurie įsigijo produktą, skaičių. Jei klientas savo rekomenduojamuose produktuose turi bent vieną produktą, kuris taip pat buvo matomas geriausiai įsigytuose produktuose, jis laikomas pradinės linijos dalimi. Jei 10 iš šių klientų būtų įsigę rekomenduojamą produktą iš 100 bendro klientų, pradinis atskaitos skaičius būtų 10%.
            - **Sėkmė @ K**: naudojant operacijų laikotarpio tikrinimo rinkinį, visiems klientams kuriamos rekomendacijos ir jos lyginamos su operacijų tikrinimo rinkinys. Pavyzdžiui, 12 mėnesių laikotarpiu 12 mėnesį galima atidėti kaip duomenų tikrinimo rinkinį. Jei modelis numato bent vieną dalyką, kurį galėtumėte įsigyti 12 mėnesį pagal tai, ką jis išmoko iš ankstesnių 11 mėnesių, klientas padidins metriką „Sėkmė @ K".
    
    1. **Daugelis siūlomų produktų (su sutampa):** 5 populiariausi produktai, kurie buvo prognozuojami klientams.
       > [!div class="mx-imgBorder"]
       > ![Grafikas, kuriame rodomi 5 populiariausi produktai](media/product-recommendation-topproducts.PNG "Grafikas, kuriame rodomi 5 populiariausi produktai")
    
    1. **Labai susaikdančių produktų rekomendacijos:** jūsų klientams pateiktų rekomendacijų, pagal kurias klientas tikriausiai įsigys modelio išgąsdą, pavyzdys.
       > [!div class="mx-imgBorder"]
       > ![Sąrašas, kuriame rodomi aukšti pavienių klientų rinkinio pasiūlymai](media/product-recommendation-highconfidence.PNG "Sąrašas, kuriame rodomi aukšti pavienių klientų rinkinio pasiūlymai")

## <a name="fix-a-failed-prediction"></a>Nesėkmingos prognozės koregavimas

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.

1. Pasirinkite prognozę, kurios klaidų žurnalus norite peržiūrėti, ir pasirinkite **Žurnalai**.

1. Peržiūrėkite visas klaidas. Galimos kelių tipų klaidos, kurios aprašo, kokia būsena sukėlė klaidą. Pavyzdžiui, klaida, kuri įvyko, nes nepakanka duomenų tiksliai prognozei, įprastai yra išsprendžiama įkeliant papildomų duomenų į „Customer Insights“.

## <a name="refresh-a-prediction"></a>Prognozės atnaujinimas

Prognozės automatiškai atnaujinamos pagal tą patį [grafiką, kai duomenys](system.md#schedule-tab) atnaujinami, kaip sukonfigūruoti parametruose.

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.

1. Pasirinkite vertikalius daugtaškius šalia norimos atnaujinti prognozės.

1. Pasirinkite **Atnaujinti**.

## <a name="delete-a-prediction"></a>Prognozės šalinimas

Panaikinus objektą prognozė taip pat bus pašalinti jo išvesties objektas.

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.

1. Pasirinkite vertikalius daugtaškius šalia norimos pašalinti prognozės.

1. Pasirinkite **Naikinti**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]