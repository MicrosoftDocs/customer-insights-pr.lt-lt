---
title: Nuspėkite produkto rekomendacijas
description: Prognozuojami produktai, kuriuos klientas gali įsigyti arba su jais bendrauti.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610292"
---
# <a name="predict-product-recommendations"></a>Nuspėkite produkto rekomendacijas

Produktų rekomendacijų modelis sukuria prognozuojamų produktų rekomendacijų rinkinius. Rekomendacijos pagrįstos ankstesniu pirkimo elgsena ir klientais, kurie turi panašius pirkimo modelius. Šis modelis skirtas individualiems vartotojams (nuo B iki C).

Turite turėti verslo žinių apie skirtingus savo verslo produktų tipus ir apie tai, kaip jūsų klientai su jais sąveikauja. Palaikome produktų, kuriuos anksčiau įsigijo jūsų klientai, rekomendavimas arba naujų produktų rekomendacijos.

Produkto rekomendacijos gali būti taikomos pagal vietinius įstatymus ir reglamentus bei klientų lūkesčius, į kuriuos modelis nėra sukurtas atsižvelgti. Todėl prieš pristatydami rekomendacijas savo klientams **turite peržiūrėti jas,** kad įsitikintumėte, jog laikotės visų galiojančių įstatymų ar kitų teisės aktų ir klientų lūkesčių dėl to, ką galite rekomenduoti.

Šio modelio išvestyje pateikiamos rekomendacijos, pagrįstos produkto ID. Jūsų pristatymo mechanizmas turi susieti numatomus produkto ID su tinkamu turiniu, kad klientai galėtų atsižvelgti į lokalizavimą, vaizdo turinį ir kitą konkretaus verslo turinį ar elgseną.

> [!TIP]
> Išbandykite produkto rekomendaciją prognozė naudodami duomenų pavyzdžius: [produkto rekomendacija prognozė pavyzdinis vadovas](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent jau [bendraautorių leidimai](permissions.md)
- Mažiausiai 100 klientų, pageidautina daugiau nei 10 000 klientų.
- Kliento identifikatorius – unikalus identifikatorius, skirtas suderinti operacijas su atskiru klientu
- Bent vienerių metų sandorių duomenys, pageidautina nuo dvejų iki trejų metų, kad būtų įtrauktas tam tikras sezoniškumas. Idealiu atveju bent trys ar daugiau operacijų vienam kliento ID. Operacijų istorijoje turi būti:
  - **Operacijos ID** : unikalus pirkimo arba operacijos identifikatorius.
  - **Operacijos data**: pirkimo arba sandorio data.
  - **Sandorio** vertė: pirkimo arba sandorio skaitinė vertė.
  - **Unikalus produkto ID**: įsigyto produkto ar paslaugos ID, jei jūsų duomenys yra eilutės prekės lygio.
  - **Pirkimas arba grąžinimas**: loginė tikroji / klaidinga reikšmė, kai *tiesa* nurodo, kad operacija buvo grąža. Jei pirkimo arba grąžinimo duomenys nepateikiami modelyje, o **operacijos** vertė yra neigiama, darome išvadą, kad bus gauta grąža.
- Produktų katalogo duomenų objektas, naudojamas kaip produkto filtras.

> [!NOTE]
> - Modeliui reikalinga klientų operacijų istorija, kai operacija yra bet kokie duomenys, apibūdinantys vartotojo ir produkto sąveiką. Pavyzdžiui, produkto įsigijimas, dalyvavimas pamokoje ar renginyje.
> - Galima konfigūruoti tik vieną operacijų istorijos objektą. Jei yra keli pirkimo objektai, sujunkite juos Power Query prieš gaudami duomenis.
> - Jei užsakymas ir užsakymo duomenys yra skirtingi objektai, prieš naudodami modelį juos sujunkite. Modelis objekte neveikia tik su užsakymo ID ar gavimo ID.

## <a name="create-a-product-recommendation-prediction"></a>Kurkite produkto rekomendacijos prognozę

Pasirinkite **Įrašyti juodraštį** bet kuriuo metu, kad išsaugotumėte prognozė kaip juodraštį. Juodraštis prognozė rodomas skirtuke **Mano numatymai**.

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį** plytelėje **Produkto rekomendacijos (peržiūra).**

1. Pasirinkite **Pradėti**.

1. **Pavadinkite šį modelį** ir **išvesties objekto pavadinimą** tam, kad kad atskirtumėte juos nuo kitų modelių ar objektų.

1. Pasirinkite **Toliau**.

### <a name="define-product-recommendation-preferences"></a>Produkto rekomendacijų nuostatų apibrėžimas

1. Nustatykite **produktų**, kuriuos norite rekomenduoti klientui, skaičių. Ši reikšmė priklauso nuo to, kaip pristatymo metodas užpildo duomenis.

1. Pasirinkite, ar norite įtraukti produktus, kuriuos klientai anksčiau įsigijo lauke **Kartoti numatomus** pirkinius.

1. Nustatykite **langą** "Pažvelkite atgal" su laiko rėmu, į kurį atsižvelgia modelis, prieš rekomenduodami gaminį vartotojui dar kartą. Pavyzdžiui, nurodykite, kad klientas perka nešiojamąjį kompiuterį kas dvejus metus. Modelis peržiūri pastarųjų dvejų metų pirkimo istoriją, o jei randa elementą, prekė filtruojama iš rekomendacijų.

1. Pasirinkti **Toliau**

### <a name="add-purchase-history"></a>Įtraukti pirkimų retrospektyvą

1. Pasirinkite **Įtraukti duomenis** į **Kliento operacijų istoriją**.

1. Pasirinkite semantinį veiklos tipą **SalesOrderLine**, kuriame yra reikiama operacijų arba pirkimo retrospektyvos informacija. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Šoninė sritis, vaizduojanti semantikos tipo konkrečių veiklų pasirinkimą.":::

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**.

### <a name="add-product-information-and-filters"></a>Produkto informacijos ir filtrų įtraukimas

Kartais tik tam tikri produktai yra naudingi arba tinkami jūsų sukurtos prognozės tipui. Naudokite produktų filtrus, kad nustatytumėte produktų, turinčių konkrečių savybių, pogrupį, kurį rekomenduosite savo klientams. Modelis naudos visus produktus, kuriuos galima naudoti modeliams sužinoti, tačiau naudos tik tuos produktus, kurie atitinka produkto filtrą jo rezultate.

1. Įtraukite produktų katalogo objektą, kuriame yra informacija apie kiekvieną produktą. Susiekite reikiamą informaciją ir pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**.

1. Pasirinkite **Produkto filtrai**:

   - **Jokių filtrų**: naudokite visus produktus iš rekomenduojamų produktų prognozės.

   - **Konkrečių produktų filtrų apibrėžimas**: naudokite konkrečius produktus produktų rekomendacijų prognozėje. Srityje Produktų katalogo **atributai** pasirinkite atributus iš produktų katalogo objekto, kurį norite įtraukti į filtrą.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Šoninė sritis, kurioje rodomi produktų katalogo objekto atributai produktų filtrams pasirinkti.":::

1. Pasirinkite, ar norite naudoti **produkto filtrą ir** (arba **)** logiškai sujungti pasirinktus atributus iš produktų katalogo.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Produktų filtrų su loginėmis AND jungtimis konfigūravimo pavyzdys.":::

1. Pasirinkite **Toliau**.

### <a name="set-update-schedule"></a>Nustatyti grafiko naujinimą

1. Pasirinkite dažnį, kad perkvalifikuotumėte savo modelį. Šis parametras yra svarbus norint atnaujinti prognozių tikslumą, kai nauji duomenys patenka į "Customer Insights". Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

### <a name="review-and-run-the-model-configuration"></a>Modelio konfigūracijos peržiūra ir paleidimas

Peržiūros **ir vykdymo** veiksme rodoma konfigūracijos suvestinė ir suteikiama galimybė atlikti keitimus prieš kuriant prognozė.

1. Pasirinkite **Redaguoti** atlikdami bet kurį iš veiksmų, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte vykdyti modelį. Pasirinkite **Atlikta**. Skirtukas **Mano numatymai** rodomi, kol kuriamas prognozė. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognozė rezultatų peržiūra

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Mano numatymai** pasirinkite norimą peržiūrėti prognozė.

Rezultatų puslapyje yra penkios pagrindinės duomenų dalys.

- **Modelio našumas:** A, B arba C klasės nurodo prognozė našumą ir gali padėti priimti sprendimą naudoti išvesties objekte saugomus rezultatus.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Modelio našumo rezultato vaizdas su A klase.":::

  Laipsniai nustatomi pagal šias taisykles:
  - **A**, kai metrika "Sėkmė @ K" yra bent 10% didesnė už bazinę liniją.
  - **B**, kai metrika "Sėkmė @ K" yra nuo 0% iki 10% didesnė nei pradinė.
  - **C**, kai metrika "Sėkmė @ K" yra mažesnė už bazinę liniją.
  - **Bazinis lygis**: dažniausiai rekomenduojami produktai pagal pirkimo skaičių visiems klientams + išmoktos taisyklės, nustatytos pagal modelį, = rekomendacijų rinkinys klientams. Tada prognozės lyginamos su geriausiais produktais ir apskaičiuojamos pagal klientų, kurie įsigijo produktą, skaičių. Jei klientas savo rekomenduojamuose produktuose turi bent vieną produktą, kuris taip pat buvo matomas geriausiai įsigytuose produktuose, jis laikomas pradinės linijos dalimi. Pavyzdžiui, jei 10 iš šių klientų turėjo rekomenduojamą produktą, įsigytą iš 100 visų klientų, bazinis lygis yra 10%.
  - **Sėkmė @ K**: Rekomendacijos sukuriamos visiems klientams ir lyginamos su operacijų laikotarpio patvirtinimo rinkiniu. Pavyzdžiui, per 12 mėnesių laikotarpį 12 mėnuo atidedamas kaip patvirtinimo duomenų rinkinys. Jei modelis numato bent vieną dalyką, kurį galėtumėte įsigyti 12 mėnesį pagal tai, ką jis išmoko iš ankstesnių 11 mėnesių, klientas padidins metriką „Sėkmė @ K”.

- **Daugelis siūlomų produktų (su rezultatu):** penki pagrindiniai produktai, kurie buvo prognozuojami klientams.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafikas, kuriame rodomi 5 populiariausi produktai.":::

- **Pagrindiniai rekomendacijų veiksniai:** produktų rekomendacijoms teikti modelis naudoja klientų sandorių istoriją. Jis išmoksta modelius pagal paskutinius pirkimus ir rand panašumų tarp klientų ir produktų. Tada šie panašumai naudojami produktų rekomendacijoms generuoti.
  Toliau nurodyti veiksniai gali turėti įtakos modelio sugeneruotai produkto rekomendacijai.
  - **Ankstesnės operacijos**: rekomenduojamas produktas buvo pagrįstas ankstesniais pirkimo modeliais. Pavyzdžiui, modelis gali rekomenduoti *„Surface Arc Mouse“*, jei kas nors neseniai įsigijo *„Surface Book 3“* ir *„Surface Pen“*. Atsižvelgdamas į istoriją modelis išmoko, kad daug klientų įsigijo *„Surface Arc Mouse“* po to, kai įsigijo *„Surface Book 3“* ir *„Surface Pen“*.
  - **Kliento panašumas**: rekomenduojamą produktą istoriškai įsigijo kiti klientai, kurių pirkimo modeliai yra panašūs. Pavyzdžiui, Jonui buvo rekomenduojama įsigyti *„Surface Headphones 2“*, nes Joana ir Brunas neseniai įsigijo *„Surface Headphones 2“*. Modelis mano, kad Jonas yra panašus į Joaną ir Bruną, nes istoriškai jų pirkimo modeliai buvo panašūs.
  - **Produktų panašumas**: rekomenduojamas produktas yra panašus į kitus produktus, kuriuos anksčiau pirko klientas. Modelis abu produktus laiko panašiais, jei jie buvo perkami kartu arba juos pirko panašūs klientai. Pavyzdžiui, žmogus gauna rekomendaciją įsigyti *USB talpyklą*, nes anksčiau jis įsigijo *USB-C ir USB adapterį*, todėl modelis mano, kad *USB talpykla* yra panaši į *USB-C ir USB adapterį*, atsižvelgiant į istorinius pirkimo modelius.

  Kiekvienai produkto rekomendacijosi įtakos turi vienas ar keli iš šių veiksnių. Rekomendacijų, kai kiekvienas įtakojantis veiksnys atliko tam tikrą vaidmenį, dalis procentais vaizduojama diagramoje. Toliau pateikiamme pavyzdyje 100 % rekomendacijų įtakos turėjo ankstesni sandoriai. Iš jų 60 % pagal klientų panašumą, o 22 % pagal produktų panašumą. Pelės žymeklį palaikykite virš diagramos juostų, kad peržiūrėtumėte procentinę įtaką darančių veiksnių dalį.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Pagrindiniai rekomendaciniai veiksniai, kuriuos modelis išmoko generuoti produktų rekomendacijas.":::

- **Duomenų statistika**: operacijų, klientų ir produktų, kuriuos svarstytas modelis, skaičiaus apžvalga. Jis pagrįstas įvesties duomenimis, kurie buvo naudojami modeliams išmokti ir produkto rekomendacijoms generuoti.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Duomenų statistika apie įvesties duomenis, kuriuos modelis naudoja modelio modeliams išmokti.":::
  
  Modelis naudoja visus turimus duomenis, kad sužinotų modelius. Todėl, jei modelio konfigūracijoje naudojate produkto filtravimą, šiame skyriuje rodomas bendras produktų, kuriuos modelis analizavo, kad sužinotų modelius, skaičius, kuris gali skirtis nuo produktų, atitinkančių apibrėžtus filtravimo kriterijus, skaičiaus. Filtravimas taikomas modelio sugeneruotai išvestims.

- **Produktų rekomendacijų pavyzdys:** rekomendacijų, kurias, modelio manymu, greičiausiai pirks klientas, pavyzdys. Jei įtraukiamas produktų katalogas, produktų ID pakeičiami produktų pavadinimais.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Sąrašas, kuriame rodomi aukšti pavienių klientų rinkinio pasiūlymai.":::

> [!NOTE]
> Šio modelio išvesties objekte Balas *rodo* kiekybinį rekomendacijos matą. Modelis rekomenduoja produktus, kurių rezultatai geresni, o ne produktus, kurių rezultatai prastesni. Norėdami peržiūrėti įvertinimą, eikite į **Duomenų** > **objektai** ir peržiūrėkite išvesties objekto, kurį nustatėte šiam modeliui, duomenų skirtuką.

[!INCLUDE [footer-include](includes/footer-banner.md)]
