---
title: Nuspėkite kliento gyvavimo ciklo reikšmę (CLV)
description: Prognozuojamas aktyvių klientų pajamų potencialas ateityje.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610384"
---
# <a name="predict-customer-lifetime-value-clv"></a>Nuspėkite kliento gyvavimo ciklo reikšmę (CLV)

Prognozuojama potenciali reikšmė (pajamos), kurią atskiri aktyvūs klientai įves į jūsų verslą per apibrėžtą būsimą laikotarpį. Šis prognozė padeda:

- Nustatykite didelės vertės klientus ir apdorokite šią įžvalgą.
- Kurkite strateginius klientų segmentus pagal jų galimą vertę, kad galėtumėte vykdyti suasmenintas kampanijas su tiksliniais pardavimais, rinkodara ir palaikymo pastangomis.
- Vadovaukite produktų kūrimui sutelkdami dėmesį į funkcijas, kurios padidina kliento vertę.
- Optimizuokite pardavimų ar rinkodaros strategiją ir tiksliau paskirstykite biudžetą klientų informavimui.
- Atpažinkite ir apdovanokite didelės vertės klientus per lojalumo ar atlygio programas.

Nustatykite, ką CLV reiškia jūsų verslui. Mes palaikome sandoriais pagrįstus CLV prognozė. Numatoma kliento vertė grindžiama verslo sandorių istorija. Apsvarstykite galimybę sukurti kelis modelius su skirtingomis įvesties nuostatomis ir palyginkite modelio rezultatus, kad sužinotumėte, kuris modelio scenarijus geriausiai atitinka jūsų verslo poreikius.

> [!TIP]
> Išbandykite CLV prognozė naudodami duomenų pavyzdžius: [kliento gyvavimo ciklo vertė (CLV) prognozė pavyzdinis vadovas](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent jau [bendraautorių](permissions.md) leidimai
- Mažiausiai 100 unikalių klientų, pageidautina daugiau nei 10 000 klientų
- Kliento identifikatorius – unikalus identifikatorius, skirtas suderinti operacijas su atskiru klientu
- Bent vienerių metų sandorių istorija, pageidautina nuo dvejų iki trejų metų. Idealiu atveju bent nuo dviejų iki trijų operacijų vienam kliento ID, pageidautina per kelias datas. Operacijų istorijoje turi būti:
  - **Operacijos ID**: kiekvienos operacijos unikalusis identifikatorius
  - **Operacijos data**: kiekvienos operacijos data arba laiko žyma
  - **Operacijos suma** kiekvienos operacijos piniginė vertė (pavyzdžiui, pajamos arba pelno marža)
  - **Grąžinimams** priskirta etiketė: Bulio loginė tikroji / klaidinga reikšmė, nurodanti, ar operacija yra grąža
  - **Produkto ID**: operacijoje dalyvaujančio produkto ID
- Duomenys apie kliento veiklą:
  - **Pirminis raktas**: unikalus veiklos identifikatorius
  - **Laiko žyma**: įvykio, identifikuojamo pagal pirminį raktą, data ir laikas
  - **Įvykis (veiklos pavadinimas)**: įvykio, kurį norite naudoti, pavadinimas
  - **Išsami informacija (suma arba reikšmė)**: išsami informacija apie kliento veiklą
- Papildomi duomenys, tokie kaip:
  - Veikla žiniatinklyje: apsilankymų svetainėje istorija arba el. pašto istorija
  - Lojalumo veikla: lojalumo atlygio taškų kaupimo ir išpirkimo istorija
  - Klientų aptarnavimas žurnalas: slaptų skambučių, skundų ar grąžinimo istorija
  - Kliento profilio informacija
- Mažiau nei 20 % trūkstamų reikšmių privalomuose laukuose

> [!NOTE]
> Galima konfigūruoti tik vieną operacijų istorijos objektą. Jei yra keli pirkimo ar operacijų objektai, sujunkite juos Power Query prieš gaudami duomenis.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kurti kliento gyvavimo ciklo vertės prognozę

Pasirinkite **Įrašyti juodraštį** bet kuriuo metu, kad išsaugotumėte prognozė kaip juodraštį. Juodraštis prognozė rodomas skirtuke **Mano numatymai**.

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį**, esantį plytelėje **Kliento gyvenimo trukmės reikšmė**.

1. Pasirinkite **Pradėti**.

1. **Pavadinkite šį modelį** ir **išvesties objekto pavadinimą** tam, kad kad atskirtumėte juos nuo kitų modelių ar objektų.

1. Pasirinkite **Toliau**.

### <a name="define-model-preferences"></a>Nustatyti modelio nuostatas

1. Nustatykite **Prognozė laikotarpį** norėdami apibrėžti, kiek ateityje norėsite numatyti CLV. Pagal numatytuosius nustatymus vienetas nustatomas kaip mėnesiai.

   > [!TIP]
   > Norint tiksliai numatyti CLV nustatytam laikotarpiui, reikalingas palyginamas istorinių duomenų laikotarpis. Pavyzdžiui, jei norite prognozuoti CLV ateinantiems 12 mėnesių, turėkite bent 18–24 mėnesių istorinius duomenis.

1. Nustatykite laiką, per kurį klientas turi turėti bent vieną operaciją, kuri bus laikoma aktyvia. Modelis prognozuoja CLV tik aktyviems **klientams**.
   - **Leisti modeliui apskaičiuoti pirkimo intervalą (rekomenduojama)**: modelis analizuoja jūsų duomenis ir nustato laikotarpį pagal istorinius pirkinius.
   - **Nustatyti intervalą rankiniu būdu**: aktyvaus kliento apibrėžimo laikotarpis.

1. Apibrėžkite didelės vertės kliento **procentilį**.
    - **Modelio skaičiavimas (rekomenduojama)**: modelis naudoja taisyklę 80/20. Klientų, kurie per istorinį laikotarpį sudaro 80 % sukauptų pajamų, procentinė dalis laikoma didelės vertės klientais. Paprastai mažiau nei 30–40 % klientų sudaro 80 % sukauptų pajamų. Tačiau šis skaičius gali skirtis atsižvelgiant į jūsų verslą ir pramonės šaką.
    - **Didžiausių aktyvių klientų** procentas: specifinis procentilis didelės vertės klientui. Pavyzdžiui, įveskite **25**, kad apibrėžtumėte didelės vertės klientus kaip 25% geriausių būsimų mokėjimų klientų.

    Jei jūsų verslas apibrėžia didelės vertės klientus skirtingu būdu, [praneškite mums, kaip norėtume prasčiau naudoti](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Pasirinkite **Toliau**.

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Pasirinkite **Įtraukti duomenis** į **Kliento operacijų istoriją**.

1. Pasirinkite semantinį veiklos tipą **SalesOrder** arba **SalesOrderLine**, kuriame yra operacijų istorija. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Pridėkite privalomus CLV modelio duomenis":::

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Įtraukite daugiau veiklų arba pasirinkite **Pirmyn**.

### <a name="add-optional-activity-data"></a>Pasirinktinių veiklos duomenų įtraukimas

Pagrindiniai duomenų sąveikos su klientais veiksmai (pvz., žiniatinklis, klientų aptarnavimas ir įvykių žurnalai) įtraukia kontekstą į operacijų įrašus. Daugiau klientų veiklos duomenų modelių gali padidinti prognozių tikslumą.

1. Pasirinkite **Pridėti duomenų** dalyje **Padidinti modelio įžvalgas su papildomais veiklos duomenimis**.

1. Pažymėkite veiklos tipą, atitinkantį kliento veiklos, kurią pridedate, tipą. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**.

1. [Pridėkite pasirinktinių klientų duomenų](#add-optional-customer-data) arba pasirinkite **Pirmyn** ir eikite į [Nustatyti naujinimo tvarkaraštį](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Pasirinktinių kliento duomenų įtraukimas

Pasirinkite iš 18 dažniausiai naudojamų kliento profilio atributų, kuriuos norite įtraukti kaip modelio įvestį. Šie atributai gali lemti labiau suasmenintus, aktualius ir veiksmingesnius modelio rezultatus jūsų verslo naudojimo atvejais.

Pavyzdžiui: "Contoso Coffee" nori numatyti kliento viso gyvenimo vertę, kad nukreiptų į didelės vertės klientus su individualizuotu pasiūlymu, susijusiu su jų naujo espreso aparato pristatymu. Contoso naudoja CLV modelį ir prideda visus 18 klientų profilio atributų, kad sužinotų, kurie veiksniai daro įtaką jų didžiausios vertės klientams. Jie mano, kad kliento vieta yra įtakingiausias veiksnys šiems klientams.
Turėdami šią informaciją, jie organizuoja vietinį renginį espreso aparato paleidimui ir bendradarbiauja su vietiniais pardavėjais dėl suasmenintų pasiūlymų ir ypatingos patirties renginyje. Neturėdami šios informacijos, Contoso galėjo siųsti tik bendruosius rinkodaros el. laiškus ir praleido galimybę suasmeninti šį vietinį savo didelės vertės klientų segmentą.

1. Pasirinkite **Pridėti duomenų** dalyje **Padidinti modelio įžvalgas dar labiau su papildomais klientų duomenimis**.

1. Objekte **pasirinkite** **Klientas: Kliento tyrimai,** kad pasirinktumėte vieningą kliento profilį, susiejantį su kliento atributų duomenimis. Norėdami gauti **kliento ID**, pasirinkite **System.Customer.CustomerId**.

1. Susiekite daugiau laukų, jei duomenys pasiekiami jūsų vieninguose klientų profiliuose.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Kliento profilio duomenų susietų laukų pavyzdys.":::

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**.

### <a name="set-update-schedule"></a>Nustatyti grafiko naujinimą

1. Pasirinkite dažnį, kad perkvalifikuotumėte modelį, remdamiesi naujausiais duomenimis. Šis parametras yra svarbus norint atnaujinti prognozių tikslumą, kai nauji duomenys patenka į "Customer Insights". Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

### <a name="review-and-run-the-model-configuration"></a>Modelio konfigūracijos peržiūra ir paleidimas

Peržiūros **ir vykdymo** veiksme rodoma konfigūracijos suvestinė ir suteikiama galimybė atlikti keitimus prieš kuriant prognozė.

1. Pasirinkite **Redaguoti** atlikdami bet kurį iš veiksmų, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte vykdyti modelį. Pasirinkite **Atlikta**. Skirtukas **Mano numatymai** rodomi, kol kuriamas prognozė. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognozė rezultatų peržiūra

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Mano numatymai** pasirinkite norimą peržiūrėti prognozė.

Rezultatų puslapyje yra trys pagrindinės duomenų dalys.

- **Mokymo modelio našumas**: A, B arba C klasės nurodo prognozė našumą ir gali padėti priimti sprendimą naudoti išvesties objekte saugomus rezultatus.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Modelio balo informacijos lauko vaizdas su A laipsniu":::

  "Customer Insights" įvertina, kaip di modeliui sekėsi prognozuoti didelės vertės klientus, palyginti su baziniu modeliu.

  Laipsniai nustatomi pagal šias taisykles:
  - **„A”**, kai modelis tiksliai prognozavo bent 5 % daugiau labai svarbių klientų, palyginus su pradiniu modeliu.
  - **„B”**, kai modelis tiksliai prognozavo nuo 0 iki 5 % labai svarbių vertės klientų, palyginus su pradiniu modeliu.
  - **„C”**, kai modelis tiksliai prognozavo mažiau labai svarbių klientų, palyginus su pradiniu modeliu.
  
  Pasirinkite [**Sužinoti apie šį balą**](#learn-about-the-score), kad atidarytumėte **modelio įvertinimo** sritį, kurioje rodoma daugiau informacijos apie AI modelio našumą ir bazinį modelį. Tai padės geriau suprasti pagrindinę modelio našumo metriką ir tai, kaip buvo išvestas galutinis modelio našumo įvertinimas. Pagal pradinį modelį ne AI pagrįstas metodas klientų pasverti vertei apskaičiuoti, visų pirma remiantis klientų įsigytais istoriniais tikslais.

- **Klientų vertė pagal procentilį**: mažos vertės ir didelės vertės klientai rodomi diagramoje. Užveskite pelės žymeklį virš histogramos juostų, kad pamatytumėte klientų skaičių kiekvienoje grupėje ir tos grupės vidutinį CLV. Pasirinktinai kurkite [klientų](prediction-based-segment.md) segmentus pagal jų CLV prognozes.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Klientų vertė pagal procentilį CLV modeliui":::

- **Daugelis ne vienu metu lemiamų veiksnių**: kuriant CLV prognozė remiantis AI modeliui pateikiamais įvesties duomenimis. Kiekvienas iš veiksnių turi savo svarbą, apskaičiuojamą bendroms modelio prognozėms. Naudokite šiuos veiksnius, kad patikrintumėte prognozė rezultatus. Šie faktoriai taip pat suteikia daugiau įžvalgų apie svarbiausius faktorius, kurie labiausiai pranašesni visiems jūsų klientams prognozuojant CLV.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Įtakingiausi CLV modelio veiksniai":::

### <a name="learn-about-the-score"></a>Sužinokite apie balą

Standartinė formulė, naudojama CLV apskaičiuoti pagal pradinį modelį:

 _**CLV kiekvienam klientui** = vidutinis kliento mėnesio pirkimas aktyviame kliento lange * CLV prognozė laikotarpio mėnesių skaičius * Bendras visų klientų išlaikymo lygis_

AI modelis lyginamas su pradiniu modeliu pagal dvi modelio efektyvumo metrikas.
  
- **Sėkmės koeficientas prognozuojant labai vertingus klientus**

  Žr. skirtumą tarp prognozuojamų didelės vertės klientų, kurie naudoja AI modelį, palyginti su pradiniu modeliu. Pavyzdžiui, 84 % sėkmingų klientų skaičius reiškia, kad iš visų vertingų klientų mokymo duomenyse AI modelis galėjo tiksliai užfiksuoti 84 %. Tada palyginsime šį sėkmės koeficientą su pradinio modelio sėkmingų duomenų koeficientu ir pranešame apie santykinį pakeitimą. Ši reikšmė naudojama modeliui priskirti.

- **Klaidų metrika**

  Peržiūrėkite bendrą modelio našumą pagal klaidas prognozuojant būsimas reikšmes. Šią klaidą įvertinti naudojame bendrą šakninio vidurkio kvadratinės klaidos (RMSE) metriką. RMSE yra standartinis būdas įvertinti modelio klaidą prognozuojant kiekybinius duomenis. AI modelio RMSE lyginamas su pradinės linijos modelio RMSE ir pranešama apie santykinį skirtumą.

AI modelis pagal prioritetus suteikia tikslaus klientų rango pagal vertę, kuri juos suteikia jūsų verslui. Todėl galutinis modelio įvertinimas susekimas naudojamas tik prognozuojamų didelės vertės klientų sėkmės koeficientui. RMSE metrika yra opi prie išorinių objektų. Scenarijų, kai klientų, kurių pirkimo vertės yra itin didelės, procentinė dalis, bendra RMSE metrika gali ne visiškai pavaizduoti modelio efektyvumą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
