---
title: Suderinkite objektus duomenų suvienodinimui
description: Suderinkite objektus tam, kad sukurtumėte suvienytus kliento profilius.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406418"
---
# <a name="match-entities"></a>Susiekite objektus

Užbaigę susiejimo etapą, būsite pasirengę susieti savo objektus. Atitikimo etapas nurodo, kaip sujungti jūsų duomenų rinkinius į vieningą kliento profilio duomenų rinkinį. Atitikties etapui reikia bent [dviejų susietų objektų](map-entities.md).

## <a name="specify-the-match-order"></a>Nurodykite atitikties eiliškumą

Eikite į **suvienodinti** > **atitikti** ir norėdami pradėti atitikties etapą, pasirinkite **nustatyti eiliškumą**.

Kiekvienas atitikmuo sujungia du ar daugiau objektų į vieną objektą išlaikant kiekvieną unikalų kliento įrašą. Toliau pateiktame pavyzdyje, išrinkome tris objektus: **ContactCSV: Testdata** kaip **pirminį** objektą, **WebAccountCSV: TestData** kaip **2 objektą** ir **CallRecordSmall: TestData** kaip **3 objektą**. Diagrama, esanti virš parinkčių pavaizduoja, kaip bus vykdomas atitikties eiliškumas.

> [!div class="mx-imgBorder"]
> ![Redaguoti duomenų atitikties eiliškumą](media/configure-data-match-order-edit-page.png "Redaguoti duomenų atitikties eiliškumą")
  
**Pirminis** objektas yra suderintas su **2 objektu**. Duomenų rinkinys, kuris atsiranda iš pirmojo atitikimo, atitinka **3 objektą**.
Šiame pavyzdyje mes pasirinkome tik du atitikmenis, bet sistema gali palaikyti daugiau.

> [!IMPORTANT]
> Objektas, kurį pasirinkote kaip savo **pirminį** objektą, bus naudojamas kaip suvienyto pagrindinio duomenų rinkinio pagrindas. Papildomi objektai, kurie yra pasirenkami per atitikties etapą, bus pridėti prie šio objekto. Tuo pat metu tai nereiškia, kad suvienytas objektas apims *visus* į šį objektą įtrauktus duomenis.
>
> Yra dvi aplinkybės, kurios gali padėti pasirinkti jūsų objektų hierarciją:
>
> - Kuris objektas turi labiausiai užbaigtus ir patikimus duomenis apie jūsų klientus?
> - Ar ką tik nustatytas objektas turi atributus, kuriiuos taip pat naudoja kiti objektai (pavyzdžiui, vardas, telefono numeris arba el. pašto adresas)? Jei ne, pasirinkite antrą patikimiausią objektą.

Jei norite išsaugoti atitikties eiliškumą, pasirinkite **atlikta**.

## <a name="define-rules-for-your-first-match-pair"></a>Nustatykite taisyklės savo pirmajai atitikties porai

Nurodę atitikties eiliškumą, **atitikties** puslapyje matysite apibrėžtus atitikmenis. Ekrano viršuje esančios plytelės bus tuščios kol vykdysite savo atitikties eiliškumą.

> [!div class="mx-imgBorder"]
> ![Apibrėžti taisykles](media/configure-data-match-need-rules.png "Apibrėžti taisykles")

**Reikalingos taisyklės** pranešimas įspėja, kad atitikties taisyklei nėra nurodytos atitikties poros. Atitikties taisyklėse nurodoma logika, pagal kurią bus derinama konkreti objektų pora.

1. Norėdami apibrėžti savo pirmąją taisyklę, pažymėkite atitinkamą atitikties eilutę atitikties lentelėje (1) ir atidarykite **taisyklės aprašo** sritį, tada pasirinkite **sukurti naują taisyklę** (2).

   > [!div class="mx-imgBorder"]
   > ![Sukurti naują taisyklę](media/configure-data-match-new-rule2.png "Sukurti naują taisyklę")

2. **Redaguoti taisyklę** srityje, konfigūruokite šios taisyklės sąlygas. Kiekviena sąlyga yra rodoma dviejose eilutėse, kurios turi privalomus pasirinkimus.

   > [!div class="mx-imgBorder"]
   > ![Naujos taisyklės sritis](media/configure-data-match-new-rule-condition.png "Naujos taisyklės sritis")

   Objektas/laukas (pirmasis) – atributas, kuris bus naudojamas atitikimui su pirmuoju atitikties poros objektu. Pavyzdžiuose gali būti telefono numeris arba el. pašto adresas. Pasirinkite atributą, kuris gali būti unikalus klientui.

   > [!TIP]
   > Venkite atitikimo pagal veiklos tipo atributus. Kitaip tariant, jei atributas yra veikla, tai galli būti prastas atitikmens kriterijus.  

   Objektas/laukas (antrasis) – atributas, kuris bus naudojamas atitikimui su antruoju atitikties poros objektu.

   Normalizuoti – **normalizavimo metodas**: įvairios normalizavimo parinktys pasiekiamos pasirinktiems objektams. Pavyzdžiui, skyrybos arba tarpų pašalinimas

   Organizacijos pavadinimo normalizavimui (peržiūrai) taip pat galite pasirinkti **tipą (telefonas, pavadinimas, organizacija)**

   > [!div class="mx-imgBorder"]
   > ![Normalizacija – B2B](media/match-normalization-b2b.png "Normalizacija – B2B")

   Tikslumo lygis – tikslumo lygis, kuris bus naudojamas šiai sąlygai. Atitikimo sąlygos tikslumo lygio nustatymas gali būti dviejų tipų: **pagrindinis** ir **pasirinktinis**.  
   - Pagrindinis: leidžia rinktis iš keturių parinkčių: žemos, vidutinės, aukštos ir tikslios. Pasirinkite **tikslus**, kai norite suderinti įrašus, kurie atitinka 100 procentų. Pasirinkite bet kurį kitą lygį, kai norite suderinti įrašus, kurie nėra vienodi 100 procentų.
   - Pasirinktinis: norėdami apibrėžti pasirinktinę procentinę dalį, kurią turi atitikti įrašai arba įvesti vertę **pasirinktiniame** lauke, naudokite slankiklį. Sistema atitiks tik tuos įrašus, kurie pereis sujungiamų atitikties porų ribą. Slankiklio reikšmės yra nuo 0 iki 1. Taigi 0,64 atitinka 64 procentus.

3. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

### <a name="add-multiple-conditions"></a>Įtraukti kelias sąlygas

Norėdami, kad jūsų objektai atitiktų tik kelias sąlygas, įtraukite daugiau sąlygų, susietų per AND operatorių.

1. Srityje **redaguoti taisyklę** pasirinkite **įtraukti sąlygą**. Taip pat pažymėdami pašalinimo mygtuką, esantį šalia esamos sąlygos, galite panaikinti sąlygas.

2. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

## <a name="add-multiple-rules"></a>Įtraukti kelias taisykles

Kiekviena sąlyga taikoma vienai porai atributų, o taisyklės apima sąlygų grupes. Norėdami, kad jūsų objektai atitiktų skirtingas atributų grupes, galite įtraukti daugiau taisyklių.

1. Publikos įžvalgose, eikite į **Duomenys** > **Sujungti** > **Suderinti**.

2. Pasirinkite objektą, kurį norite atnaujinti ir pažymėkite **pridėti taisykles**.

3. Vadovaukitės procedūra kaip nurodyta [apibrėžti taisykles jūsų pirmai atitikties porai](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Taisyklės eiliškumas yra svarbus. Atitikties algoritmas bando atitikti pagal pirmąją taisyklę ir pagal antrą taisyklę tik jei atitiktys nebuvo nustatytos pirmojoje taisyklėje.

## <a name="define-deduplication-on-a-match-entity"></a>Nustatykite papildomą dublikavimą suderintame objekte

Kartu nurodant kryžmines objektų atitikties taisykles kaip aprašyta ankstesniuose skyriuose, taip pat galite nurodyti papildomo dublikavimo taisykles. *Papildomas dublikavimas* yra procesas. Jis nustato dublikuotus įrašus, sulieja juos į vieną įrašą ir susieja visus šaltinio įrašus į šį sulietą įrašą su kitais ID su suderintu įrašu.

Po to, kai nustatomas papildomo dublikavimo įrašas, jis bus naudojamas kryžminio objekto atitikties procese. Papildomas dublikavimas yra įgyvendinamas objekto lygmeniu ir gali būti taikomas visiems objektams naudojamiems atitikties procese.

### <a name="add-deduplication-rules"></a>Įtraukti papildomo dublikavimo taisykles

1. Publikos įžvalgose, eikite į **Duomenys** > **Sujungti** > **Suderinti**.

1. **Suderinti dublikatai** skyriuje pasirinkite **Nustatyti objektus**.

1. **Suderinti ypatybes** skyriuje pasirinkite objektus, kuriuso norite taikyti papildomam dublikavimui.

1. Nustatykite, kaip sulieti dublikuotus įrašus ir pasirinkite vieną iš trijų suderinimo parinkčių:
   - *Daugiausiai užpildyti*: Nustato įrašus su daugiausiai užpildytų atributų kaip laimėtojo įrašą. Tai yra nustatytoji suderinimo parinktis.
   - *Naujausi*: Nustato įrašą laimėtoją pagal naujausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
   - *Seniausi*: Nustato įrašą laimėtoją pagal seniausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
 
   > [!div class="mx-imgBorder"]
   > ![Papildomo dublikavimo taisyklių 1 žingsnis](media/match-selfconflation.png "Papildomo dublikavimo taisyklių 1 žingsnis")
 
1. Kai objektai yra pasirinkti ir jų suderinimo ypatybė yra nustatyta, pasirinkite **Sukurti naują taisyklę** tam, kad nustatytumėte papildomo dublikavimo taisykles objekto lygmeniu.
   - **Pasirinkite laukelį** rodo visus esamus laukelius iš objekto, kuriam norite papildomai dublikuoti duomenų šaltinį.
   - Nurodykite normalizavimo ir tikslinimo nustatymus panašiu būdu kaip parodyta kryžminio objekto suderinime.
   - Galite nustatyti papildomas sąlygas pasirinkę **Įtraukti sąlygą**.
 
   > [!div class="mx-imgBorder"]
   > ![Papildomo dublikavimo taisyklių 2 žingsnis](media/match-selfconflation-rules.png "Papildomo dublikavimo taisyklių 2 žingsnis")

  Galite sukurti keletą papildomo dublikavimo taisyklių objektui. 

1. Suderinimo proceso vykdymas dabar grupuoja įrašus pagal sąlygas nustatytas papildomo dublikavimo taisyklėse. Po įrašų grupavimo, suliejimo politika yra taikoma siekiant nustatyti laimėjusį įrašą.

1. Laimėjęs įrašas tuomet yra praleidžiamas pro kryžminio objekto suderinamumą.

1. Bet kuri tinkinta suderinimo taisyklė visada nustato atitiktį ir niekuomet neatitinka viršijančių papildomo dublikavimo taisyklių. Jei papildomo dublikavimo taisyklė nustato atitikties įrašus ir tinkinta atitikties taisyklė yra nustatyta taip, kad niekada neatitiktų tų įrašų, tuomet šie du įrašai nebebus suderinti.

1. Po suderinamumo proceso vykdymo, matysite papildomo dublikavimo statistiką.
   
> [!NOTE]
> Papildomo dublikavimo taisyklių nurodymas nėra būtinas. Jei nėra nustatytų tokių taisyklių, taikomos sistemos nustatytos taisyklės. Jos sugriauna visus įrašus, kurie bendrina tą patį vertės derinį (tikslią atitiktį) lyginant su pirminiu raktu ir laukelius atitikties taisyklėse į vieną įrašą prieš praleisdami pro objekto duomenis į kryžminio objekto suderinimą pagerintam vykdymui ir sistemos švarai.

## <a name="run-your-match-order"></a>Vykdyti savo atitikties eiliškumą

Nustatę suderinimo taisykles, įskaitant kryžminio objekto suderinimo ir papildomo dublikavimo taisykles, galite vykdyti suderinimo užsakymą. Norėdami pradėti procesą, puslapyje **atitikti** pasirinkite **vykdyti**. Atitikties algoritmo vykdymas gali užtrukti. Kol atitikties procesas nesibaigia, **atitikties** puslapyje keisti ypatybių negalite. Rasite suvienodintą kliento profilio objektą, sukurtą **objektų** puslapyje. Jūsų suvienyto kliento objektas vadinamas **Conflationmatchpairs: CustomerInsights**.

Norėdami atlikti papildomų pakeitimų ir iš naujo paleisti veiksmą, vykdomą gretinimą galite atšaukti. Spustelėkite tekstą **Atnaujinama...** ir pasirodžiusio šoninio skydo apačioje pasirinkite **Atšaukti užduotį**.

Baigus atitikties procesą tekstas **Atnaujinama...** bus pakeistas į **Sėkmingai atlikta** ir vėl galėsite naudoti visas puslapio funkcijas.

Pirmasis atitikties procesas sukuria vieningą pagrindinį objektą. Visi tolesni atitikimai išplečia šį objektą.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="review-and-validate-your-matches"></a>Peržiūrėkite ir patvirtinkite savo atitiktis

Įvertinkite atitikusių porų kokybę ir ją patobulinkite:

- **Atitikties** puslapyje rasite dvi plyteles su pradinėmis jūsų duomenų įžvalgomis.

  - **Unikalūs klientai**: rodo unikalių profilių, kuriuos nustatė sistema, skaičių.
  - **Sutampantys įrašai**: rodo visų jūsų atitikties porų atitikimų skaičių.

- **Atitikties eiliškumo** lentelėje, palygindami įrašų skaičių, kurie buvo gauti iš šio atitikties poros objekto ir sėkmingai atitikusių įrašų procentą, galite įvertinti kiekvienos atitikties poros rezultatus.

- Objekto **taisyklių** skyriuje, **atitikties eiliškumo** lentelėje rasite sėkmingai atitikusių įrašų pagal taisyklę procentą. Pažymėję šalia taisyklės esantį lentelės simbolį, galite peržiūrėti visus taisyklės įrašus. Rekomenduojame peržiūrėti įrašų pogrupį ir patvirtinti, kad atitikimas įvykdytas teisingai.

- Išbandykite skirtingas jūsų sąlygų tikslumo ribas ir nustatykite optimalią reikšmę.

  1. Pasirinkite atitikties poros taisyklės elipsę (...), kurią norite išbandyti ir pažymėkite **redaguoti**.

  2. Pasirinkite sąlygą, kurią norite išbandyti. Kiekvienas kriterijus vaizduojamas atskiroje eilutėje **atitikties taisyklės** srityje.

  3. Tai, ką matysite **kriterijų peržiūros** puslapyje, priklauso nuo sąlygai pasirinkto lygio tikslumo. Rasti pasirinktos sąlygos suderintų ir nesuderintų duomenų skaičių.

     Gerai supraskite skirtingų ribinės vertės lygių poveikius. Galite palyginti, kiek įrašų bus suderinta po kiekvienu ribinės vertės lygiu ir peržiūrėti kiekvienos parinkties įrašus. Pažymėkite kiekvieną plytelę ir peržiūrėkite duomenis lentelės sekcijoje.

## <a name="optimize-your-matches"></a>Optimizuoti savo atitiktis

Pagerinkite kokybę iš naujo konfigūruodami kelis atitikties parametrus:

- **Pakeisti atitikties eiliškumą** pasirenkant **redaguoti** ir keisti atitikties eiliškumo laukus.

  > [!div class="mx-imgBorder"]
  > ![Redaguoti duomenų atitikties eiliškumą](media/configure-data-match-order-edit.png "Redaguoti duomenų atitikties eiliškumą")

- Jei apibrėžėte kelias taisykles, **pakeiskite taisyklių eiliškumą**. Galite pertvarkyti atitikties taisykles pasirinkdami **judėti aukštyn** ir **judėti žemyn** parinktis atitikties taisyklių tinklelyje.

  > [!div class="mx-imgBorder"]
  > ![Pakeisti taisyklės eiliškumą](media/configure-data-change-rule-order.png "Pakeisti taisyklės eiliškumą")

- Jei apibrėžėte atitikties taisyklę ir norėtumėte sukurti panašią taisyklę su pakeitimais, **kopijuokite savo taisykles**. Tai darykite pasirinkdami **kopijuoti**.

  > [!div class="mx-imgBorder"]
  > ![Kopijuoti taisyklę](media/configure-data-duplicate-rule.png "Kopijuoti taisyklę")

- **Redaguokite savo taisykles** pažymėdami **redagavimo** simbolį. Galite taikyti šiuos pakeitimus:

  - Keisti sąlygos atributus: pažymėkite naujus atributus konkrečioje būsenos eilutėje.
  - Pakeiskite sąlygos ribinę vertę: koreguokite tikslumo slankiklį.
  - Pakeiskite sąlygos normalizavimo metodą: atnaujinkite normalizavimo metodą.

## <a name="specify-your-custom-match-records"></a>Nurodykite pasirinktinius atitikties įrašus

Galite nurodyti sąlygas, pagal kurias tam tikri įrašai turi visada atitikti arba neatitikti. Šios taisyklės gali būti įkeltos į atitikties procesą vienu metu.

1. Pažymėkite **pasirinktinės atitikties** parinktį **atitikties eiliškumo** ekrane.

   > [!div class="mx-imgBorder"]
   > ![Sukurti pasirinktinę atitiktį](media/custom-match-create.png "Sukurti pasirinktinę atitiktį")

2. Jei nėra įkeltų objektų, matysite naują **pasirinktinės atitikties** dialogo langą, kuriame reikia užpildyti tam tikrą informaciją. Jei anksčiau pateikėte šią informaciją, pereikite prie 8 veiksmo.

   > [!div class="mx-imgBorder"]
   > ![Naujas pasirinktinės atitikties dialogo langas](media/custom-match-new-dialog-box.png "Naujas pasirinktinės atitikties dialogo langas")

3. Pasirinkite **užpildyti šabloną**, jei norite gauti šabloną, nurodantį, kurie įrašai iš kurių objektų turi visada atitikti arba neatitikti. Dviejuose skirtinguose failuose turėsite atskirai užpildyti „visada atitinka“ ir „niekada neatitinka“ įrašus.

4. Šablone yra laukų, nurodančių objektą ir objekto pirminių raktų reikšmes, kurias reikia naudoti pasirinktinio atitikimo srityje. Pavyzdžiui, jei norite, kad pirminis raktas 12345 iš pardavimo objekto visada atitiktų pirminį raktą 34567 iš kontakto objekto, turėsite nurodyti kaip pateikta žemiau:
    - Objektas1: pardavimai
    - Objekto1kodas: 12345
    - Objektas2: kontaktas
    - Objekto2kodas: 34567

   Tas pats šablono failas gali nurodyti pasirinktinius atitikties įrašus iš kelių objektų.

5. Įtraukę visus pageidaujamus perrašymus, išsaugokite šablono failą.

6.Eikite į **Duomenys** > **Duomenų šaltiniai** ir vartokite šablono failus kaip naujus objektus. Kai failai paversti, galite juos naudoti atitikties konfigūracijai.

7. Kai galite įkelti failus ir objektus, pasirinkite **pasirinktinės atitikties** parinktį dar kartą, Matysite parametrus, nurodančius objektus, kuriuos norite įtraukti. Iš išskleidžiamojo meniu pasirinkite būtinus objektus.

   > [!div class="mx-imgBorder"]
   > ![Pasirinktiniai atitikties perrašymai](media/custom-match-overrides.png "Pasirinktiniai atitikties perrašymai")

8. Pasirinkite objektus, kuriuos norite naudoti **visada atitinka** ir **niekada neatitinka**, tada pažymėkite **atlikta**.

9. Pasirinkite **įrašyti** **atitikties** puslapyje, jei norite pasirinktinės nustatytos atitikties konfigūracijos.

10. Pasirinkite **vykdyti** **atitikties** puslapyje, jei norite pradėti atitikties procesą ir pasirinktinė atitikties konfigūracija įsigalios. Konfigūracijos nustatymai perrašys visas suderintas sistemos taisykles.

11. Kai atitiktis bus baigta, galite patikrinti „**ConflationMatchPair**“ objektą ir patvirtinti, kad perrašymai konfliacijos atitikimuose įvyko.

## <a name="next-step"></a>Kitas veiksmas

Kai užbaigsite bent vienos atitinkančios poros atitikties procesą, galėsite išspręsti galimus duomenų prieštaravimus [**suliejimo**](merge-entities.md) temoje.
