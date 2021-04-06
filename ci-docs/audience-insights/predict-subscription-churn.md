---
title: Prenumeratos praradimo prognozė
description: Prognozuokite, ar yra rizika, kad klientas nebenaudoti prenumeruojamų jūsų įmonės produktų ar paslaugų.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 75f5f9f8f56a33b2a43a605595a463ca2e937c6b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595666"
---
# <a name="subscription-churn-prediction-preview"></a>Prenumeratos praradimo prognozė (peržiūra)

Prenumeratos praradimo prognozavimo funkcija padeda prognozuoti, ar yra rizika, kad klientas nebenaudoti prenumeruojamų jūsų įmonės produktų ar paslaugų. Puslapyje **Duomenų rinkimas** > **Prognozės** galite kurti naują prenumeratos praradimo prognozę. Norėdami pamatyti kitas jūsų sukurtas prognozes pasirinkite **Mano prognozės**.

> [!TIP]
> Pabandykite mokymus prenumeravimo nutraukimo prognozei naudojant pavyzdžio duomenis: [Prenumeravimo nutraukimo prognozės pavyzdžio gairės](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Mažiausiai [Prisidėjusiojo leidimai](permissions.md).
- Verslo žinios, kad suprastumėte, ką praradimas reiškia verslui. Mes palaikome praradimo apibrėžimus pagal laikotarpius, o tai reiškia, kad klientas yra prarastas tam tikrą laikotarpį nuo jo prenumeratos pabaigos.
- Duomenys apie prenumeratas ir jų istoriją:
    - Prenumeratos identifikatoriai, naudojami atskirti prenumeratoms.
    - Klientų identifikatoriai, siejantys prenumeratas su klientais.
    - Prenumeratos įvykių datos, apimančios pradžios datas, pabaigos datas ir datas, kada įvyko prenumeratos įvykiai.
    - Prenumeratos informacija, skirta nustatyti, ar tai pasikartojanti prenumerata ir kaip dažnai ji atnaujinama.
    - Prenumeratų semantinei duomenų schemai reikalinga ši informacija:
        - **Prenumeratos ID:** unikalus prenumeratos identifikatorius.
        - **Prenumeratos pabaigos data:** kliento prenumeratos galiojimo pabaigos data.
        - **Prenumeratos pradžios data:** kliento prenumeratos pradžios data.
        - **Operacijos data:** prenumeratos pakeitimo data. Pavyzdžiui, klientas, įsigijo arba atšaukė prenumeratą.
        - **Ar tai pasikartojanti prenumerata:** loginis TRUE/FALSE laukas, nustatantis, ar prenumerata bus atnaujinama su tuo pačiu prenumeratos ID be kliento įsikišimo
        - **Pasikartojimo dažnis (mėnesiais):** pasikartojančioms prenumeratoms tai yra atnaujinimo laikotarpis. Jis nurodomas mėnesiais. Pavyzdžiui, metinės prenumeratos, kuri kiekvienais metais automatiškai pratęsiama klientui dar metams, reikšmė yra 12.
        - (Pasirinktinai) **Prenumeratos suma:** suma, kurią klientas moka už prenumeratos atnaujinimą. Tai gali būti naudinga apžvelgiant skirtingų prenumeratos lygių tendencijas.
- Duomenys apie kliento veiklą:
    - Veiklos identifikatoriai, padedantys atskirti to paties tipo veiklas.
    - Klientų identifikatoriai, siejantys veiklas su klientais.
    - Veiklos informacija, apimanti veiklos pavadinimą ir datą.
    - Kliento veiklų semantinė duomenų schema apima:
        - **Pirminis raktas:** unikalusis veiklos identifikatorius. Pavyzdžiui, apsilankymas svetainėje arba naudojimo įrašas, rodantis, kad klientas peržiūrėjo televizinio šou epizodą.
        - **Laiko žymė:** pirminio rakto identifikuoto įvykio data ir laikas.
        - **Įvykis:** įvykio, kurį norite naudoti, pavadinimas. Pavyzdžiui, vaizdo transliavimo paslaugos lauke „UserAction“ galėtų būti reikšmė „Peržiūrėta“.
        - **Informacija:** išsami informacija apie įvykį. Pavyzdžiui, vaizdo transliavimo paslaugos lauke „ShowTitle“ galėtų būti kliento peržiūrėto vaizdo įrašo reikšmė.
   > [!NOTE]
   > Reikia turėti bent du veiklos įrašus 50 % klientų, kad galėtumėte apskaičiuoti klientų praradimą.

## <a name="create-a-subscription-churn-prediction"></a>Prenumeratos praradimo prognozės kūrimas

1. Publikos įžvalgose, eikite į **Intelektas** > **Prognozės**.
1. Pasirinkite plytelę **Prenumeratos praradimo prognozė (peržiūra)**, o tada pasirinkite **Naudoti šį modelį**.
   > [!div class="mx-imgBorder"]
   > ![Prenumeratos praradimo modelio plytelė su mygtuku „Naudoti šį modelį“](media/subscription-churn-usethismodel.PNG "Prenumeratos praradimo modelio plytelė su mygtuku „Naudoti šį modelį“")

### <a name="name-model"></a>Pavadinimo modelis

1. Suteikite modeliui pavadinimą, kad atskirtumėte jį nuo kitų modelių.
1. Išvesties objekto pavadinimui nurodyti galite naudoti tik raides ir skaičius be tarpų. Tai pavadinimas, kurį naudos modelio objektas. Tada pasirinkite **Toliau**.

### <a name="define-customer-churn"></a>Apibrėžkite kliento praradimą

1. Įveskite **Dienų skaičių nuo prenumeratos pabaigos**, kurį jūsų įmonė taikys prarastam klientui. Šis laikotarpis įprastai skirtas verslo veikloms, pvz., pasiūlymams ar kitoms rinkodaros pastangoms, siekiant išvengti kliento praradimo.
1. Įveskite **dienų, kiek toli reikia prognozuoti klientų praradimą,** skaičių, kad nustatytumėte laikotarpį, kuriam reikia prognozuoti klientų praradimą. Pavyzdžiui, jei norite prognozuoti klientų praradimo riziką per 90 dienų laikotarpį tam, kad galėtumėte stengtis pritaikyti savo klientų išlaikymo rinkodaros priemones. Prognozuojant klientų praradimo riziką ilgesniems ar trumpesniems laikotarpiams gali būti sunkiau atsižvelgti į klientų praradimo rizikos profilio veiksnius, tačiau tai labai priklauso nuo konkrečių jūsų verslui taikomų reikalavimų. Norėdami tęsti, spustelėkite **Pirmyn**
   >[!TIP]
   > **Įrašyti ir uždaryti** galite pasirinkti bet kuriuo metu, kad prognozė būtų išsaugota kaip juodraštis. Norėdami tęsti, prognozės juodraštį galite rasti skirtuke **Mano prognozė**.

### <a name="add-required-data"></a>Įtraukite būtinus duomenis

1. Pažymėkite lauką **Įtraukti duomenis** iš **Prenumeratos istorija** ir pasirinkite objektą, kuris teikia prenumeratos istorijos informaciją, kaip aprašyta [būtinosiose sąlygose](#prerequisites).
1. Jei toliau pateikti laukai neužpildyti, sukonfigūruokite ryšį perkeldami informaciją iš savo prenumeratos istorijos objekto į kliento objektą.
    1. Pasirinkite **Prenumeratos istorijos objektas**.
    1. Pasirinkite **lauką**, kuris identifikuoja klientą prenumeratos istorijos objekte. Ji turi būti susijęs su kliento objekto pirminiu kliento ID.
    1. Pasirinkite **kliento objektą**, atitinkantį pirminį kliento objektą.
    1. Įveskite pavadinimą, apibūdinantį ryšį.
       > [!div class="mx-imgBorder"]
       > ![Prenumeratos istorijos puslapis, kuriame pavaizduotas ryšio su klientu kūrimas](media/subscription-churn-subscriptionhistoryrelationship.PNG "Prenumeratos istorijos puslapis, kuriame pavaizduotas ryšio su klientu kūrimas")
1. Pasirinkite **Toliau**.
1. Susiekite semantinius laukus su savo prenumeratos istorijos objekto atributais ir pasirinkite **Įrašyti**. Norėdami peržiūrėti laukų aprašymus, peržiūrėkite [būtinąsias sąlygas](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Prenumeratos istorijos puslapis, kuriame pavaizduoti semantiniai atributai, susieti su pasirinkto prenumeratos istorijos objekto laukais](media/subscription-churn-subscriptionhistorymapping.PNG "Prenumeratos istorijos puslapis, kuriame pavaizduoti semantiniai atributai, susieti su pasirinkto prenumeratos istorijos objekto laukais")
1. Pažymėkite lauką **Įtraukti duomenis** iš **Kliento veiklos** ir pasirinkite objektą, kuris teikia kliento veiklos informaciją, kaip aprašyta būtinosiose sąlygose.
1. Pasirinkite veiklos tipą, kuris atitinka konfigūruojamos kliento veiklos tipą.  Pasirinkite **Kurti naują** ir nurodykite pavadinimą, jei nematote parinkties, atitinkančios reikiamą veiklos tipą.
1. Turėsite sukonfigūruoti kliento veiklos objekto ryšį su kliento objektu.
    1. Pažymėkite lauką, kuris identifikuoja klientą kliento veiklos lentelėje ir kuris gali būti tiesiogiai susijęs su kliento objekto pirminiu kliento ID.
    1. Pasirinkite kliento objektą, atitinkantį pirminį kliento objektą
    1. Įveskite pavadinimą, apibūdinantį ryšį.
1. Pasirinkite **Toliau**.
1. Susiekite semantinius laukus su savo kliento veiklos objekto atributais ir pasirinkite **Įrašyti**. Norėdami peržiūrėti laukų aprašymus, peržiūrėkite [būtinąsias sąlygas](#prerequisites).
1. (Pasirinktinai) Jei turite kitų kliento veiklų, kurias norite įtraukti, pakartokite aukščiau aprašytus veiksmus.
   > [!div class="mx-imgBorder"]
   > ![Objekto ryšio apibrėžimas](media/subscription-churn-customeractivitiesmapping.PNG "Kliento veiklų puslapis, kuriame pavaizduoti semantiniai atributai, susieti su pasirinkto kliento veiklos objekto laukais")
1. Pasirinkite **Toliau**.

### <a name="set-schedule-and-review-configuration"></a>Grafiko ir peržiūros konfigūravimo nustatymas

1. Nustatykite modelio apmokymo iš naujo dažnumą. Šie nustatymai yra svarbūs prognozių tikslumo naujinimui, nes nauji duomenys yra vartojami publikos įžvalgose. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.
1. Pasirinkite **Toliau**.
1. Peržiūrėkite konfigūraciją. Prie bet kurios prognozės konfigūracijos dalies galite sugrįžti pažymėdami **Redaguoti** po rodoma reikšme. Arba galite pažymėti konfigūravimo veiksmą eigos indikatoriuje.
1. Jei visos reikšmės sukonfigūruotos teisingai, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte prognozavimo procesą. Skirtuke **Mano prognozės** galite matyti savo prognozių būseną. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

## <a name="review-a-prediction-status-and-results"></a>Prognozės būsenos ir rezultatų peržiūra

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.
   > [!div class="mx-imgBorder"]
   > ![Mano prognozių puslapio rodinys](media/subscription-churn-mypredictions.PNG "Mano prognozių puslapio rodinys")
1. Pasirinkite prognozę, kurią norite peržiūrėti.
   - **Prognozės pavadinimas:** kūrimo metu nurodytas prognozės pavadinimas.
   - **Prognozės tipas:** prognozei naudojamo modelio tipas
   - **Išvesties objektas:** objekto, kuriame saugoma prognozės išvestis, pavadinimas. Objektą šiuo pavadinimu galite rasti **Duomenys** > **Objektai**.
   - **Nuspėjamas laukas:** šis laukas užpildomas tik kai kurių tipų prognozėms ir nėra naudojamas prenumeratos praradimo prognozei.
   - **Būsena:** dabartinė prognozės vykdymo būsena.
        - **Eilėje:** prognozė šiuo metu laukia kitų vykdomų procesų.
        - **Atnaujinama:** šiuo metu vykdomas prognozės „rezultato“ apdorojimo etapas, kurio metu gauti rezultatai bus perduoti į išvesties objektą.
        - **Nepavyko:** prognozė nepavyko. Norėdami gauti daugiau informacijos, pasirinkite **Žurnalai**.
        - **Pavyko:** prognozė sėkminga. Norėdami peržiūrėti prognozę, po vertikaliu daugtaškiu pasirinkite  **Rodyti**
   - **Redaguota:** data, kai buvo pakeista prognozės konfigūracija.
   - **Paskutinį kartą atnaujinta:** data, kai prognozė atnaujino rezultatus išvesties objekte.
1. Pažymėkite vertikalius daugtaškius šalia prognozės, kurios rezultatus norite peržiūrėti, ir pasirinkite **Rodyti**.
   > [!div class="mx-imgBorder"]
   > ![Prognozės parinkčių peržiūra vertikalių daugtaškių meniu, įskaitant redagavimą, atnaujinimą, peržiūrą, žurnalus ir šalinimą](media/subscription-churn-verticalellipses.PNG "Prognozės parinkčių peržiūra vertikalių daugtaškių meniu, įskaitant redagavimą, atnaujinimą, peržiūrą, žurnalus ir šalinimą")
1. Rezultatų puslapyje yra trys pagrindinės duomenų dalys:
    1. **Mokymo modelio efektyvumas:** galimi balai yra A, B arba C. Šis rezultatas nurodo prognozės efektyvumą ir gali padėti apsispręsti naudoti išvesties objekte saugomus rezultatus.
        - Balai nustatomi pagal šias taisykles:
            - **A**: kai modelis tiksliai numatė bent 50 % visų prognozių ir kai prarastų klientų tikslių prognozių procentas yra didesnis nei istorinis vidutinis praradimo rodiklis bent 10 % istorinio vidutinio praradimo rodiklio.
            - **B**: kai modelis tiksliai numatė bent 50 % visų prognozių ir kai prarastų klientų tikslių prognozių procentas yra iki 10 % istorinio vidutinio praradimo rodiklio didesnis nei istorinis vidutinis praradimo rodiklis.
            - **C**: kai modelis tiksliai numatė mažiau kaip 50 % visų prognozių arba kai prarastų klientų tikslių prognozių procentas yra mažesnis nei istorinis vidutinis praradimo rodiklis.
               > [!div class="mx-imgBorder"]
               > ![Modelio efektyvumo rezultato rodinys](media/subscription-churn-modelperformance.PNG "Modelio efektyvumo rezultato rodinys")
    1. **Praradimo tikimybė (klientų skaičius):** klientų grupės pagal prognozuojamą praradimo riziką. Šie duomenys gali būti naudingi vėliau, jei norite sukurti klientų segmentą su didele praradimo rizika. Tokie segmentai padeda suprasti, kokios turėtų būti priklausymo segmentui ribinės reikšmės.
       > [!div class="mx-imgBorder"]
       > ![Diagrama, vaizduojanti praradimo rezultatų paskirstymą, suskirstyta į intervalus nuo 0 proc. iki 100 proc.](media/subscription-churn-resultdistribution.PNG "Diagrama, vaizduojanti praradimo rezultatų paskirstymą, suskirstyta į intervalus nuo 0 proc. iki 100 proc.")
    1. **Svarbiausi veiksniai:** kuriant prognozę, atsižvelgiama į daugelį veiksnių. Kiekvienas iš veiksnių turi savo svarbą, apskaičiuojamą bendroms modelio prognozėms. Šiuos veiksnius galite naudoti prognozės rezultatams patvirtinti. Arba šią informaciją galite naudoti vėliau [kurdami segmentus](segments.md), kurie gali padėti paveikti klientų praradimo riziką.
       > [!div class="mx-imgBorder"]
       > ![Sąrašas, kuriame matomi svarbiausi veiksniai ir jų svarba prognozuojant praradimo rezultatą](media/subscription-churn-influentialfactors.PNG "Sąrašas, kuriame matomi svarbiausi veiksniai ir jų svarba prognozuojant praradimo rezultatą")

## <a name="fix-a-failed-prediction"></a>Nesėkmingos prognozės koregavimas

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.
1. Pasirinkite prognozę, kurios klaidų žurnalus norite peržiūrėti, ir pasirinkite **Žurnalai**.
   > [!div class="mx-imgBorder"]
   > ![Rezultatų meniu juostos, įskaitant uždarymo, modelio redagavimo ir žurnalų mygtukus, rodinys](media/subscription-churn-logsbutton.PNG "Rezultatų meniu juostos, įskaitant uždarymo, modelio redagavimo ir žurnalų mygtukus, rodinys")
1. Peržiūrėkite visas klaidas. Galimos kelių tipų klaidos, kurios aprašo, kokia būsena sukėlė klaidą. Pavyzdžiui, klaida pranešanti, kad nėra pakankamai duomenų tinkamai prognozei dažniausiai išsprendžiama įkeliant papildomus duomenis.

## <a name="refresh-a-prediction"></a>Prognozės atnaujinimas

Prognozės automatiškai atsinaujins tuo pačiu parametruose sukonfigūruotu [grafiku, kuriuo atnaujinami jūsų duomenys](system.md#schedule-tab).

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.
1. Pasirinkite vertikalius daugtaškius šalia norimos atnaujinti prognozės.
1. Pasirinkite **Atnaujinti**.

## <a name="delete-a-prediction"></a>Prognozės šalinimas

1. Eikite į skirtuką **Mano prognozės** iš **Duomenų rinkimas** > **Prognozės**.
1. Pasirinkite vertikalius daugtaškius šalia norimos pašalinti prognozės.
1. Pasirinkite **Naikinti**.

> [!NOTE]
> Panaikinus prognozę, pašalinamas jo išvesties objektas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]