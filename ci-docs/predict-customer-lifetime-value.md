---
title: Kliento gyvavimo ciklo (CLV) vertės prognozė
description: Prognozuojamas aktyvių klientų pajamų potencialas ateityje.
ms.date: 07/21/2022
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
ms.openlocfilehash: b6f6665d906cc96688efe84035336f64d2a39303
ms.sourcegitcommit: 80d8436d8c940f1267e6f26b221b8d7ce02ed26b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186450"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Kliento gyvavimo ciklo (CLV) vertės prognozė

Prognozuojama potenciali reikšmė (pajamos), kurią atskiri aktyvūs klientai įves į jūsų verslą per apibrėžtą būsimą laikotarpį. Ši funkcija gali padėti pasiekti įvairius tikslus:

- Nustatykite didelės vertės klientus ir apdorokite šią įžvalgą
- Kurti strategines klientų segmentus, atsižvelgiant į jų potencialią vertę, kad suasmenintas kampanijas būtų galima vykdyti naudojant tikslinius pardavimo, rinkodaros ir palaikymo veiksmus
- Vadovo produktų kūrimas susitelkus į funkcijas, kurios padidinti klientų vertę
- Pardavimo arba rinkodaros strategijos optimizavimas ir biudžeto skirstymas tiksliau klientų kampanijai
- Vertingų klientų atpažinimas ir apdovanokite juos pasitelkdami apdovanodami arba pristatę apdovanojimų programas

## <a name="prerequisites"></a>Būtinosios sąlygos

Prieš pradėdami nurodykite, ką jūsų verslui reiškia CLV. Šiuo metu palaikome transakcija paremtą CLV prognozę. Prognozuojama kliento reikšmė pagrįsta verslo operacijų retrospektyva. Kad sukurtumėte prognozę, jums reikia bent [Prisidėjusio asmens](permissions.md) teisių.

Konfigūruodami ir paleisdami CLV modelį, galite sukurti kelis modelius su skirtingomis įvesties nuostatas ir palyginti modelio rezultatus, kad pamatytumėte, kuris modelio scenarijus geriausiai atitinka jūsų verslo reikmes.

### <a name="data-requirements"></a>Duomenų reikalavimai

Toliau nurodyti duomenys yra būtini ir, jei pažymėti pasirinktiniai, rekomenduojama norint padidinti modelio efektyvumą. Kuo daugiau duomenų gali apdoroti modelis, tuo tikslesnė prognozė bus. Todėl raginame, jei įmanoma, suvartoti daugiau klientų veiklos duomenų.

- Kliento identifikatorius: unikalusis identifikatorius, kuris gretina operacijas su individualiu klientu

- Operacijų retrospektyva: istoriniai operacijų žurnalai su šia semantinių duomenų schema
    - **Operacijos ID**: kiekvienos operacijos unikalusis identifikatorius
    - **Operacijos data**: kiekvienos operacijos data, pageidautina laiko žyma
    - **Operacijos suma** kiekvienos operacijos piniginė vertė (pavyzdžiui, pajamos arba pelno marža)
    - **Prie grąžinimų priskirta žyma** (pasirinktinis): Bulio logikos reikšmė, nurodanti, ar operacija yra grąžinimas 
    - **Produkto ID** (pasirinktinis): su operacija susijusio produkto ID

- Papildomi duomenys (pasirinktinai), pavyzdžiui
    - Žiniatinklio veiklos: svetainės lankytojų retrospektyva, el. laiškų retrospektyva
    - Lojalumo veiksmai: lojalumo atsilyginimo taškų apskaičiavimas ir panaudojimo istorija
    - Klientų aptarnavimas žurnalas, aptarnavimo skambutis, skundai ar grąžinimo istorija
    - Kliento profilio informacija
- Duomenys apie klientų veiklas (pasirinktiniai):
    - Veiklos identifikatoriai, padedantys atskirti to paties tipo veiklas
    - Klientų identifikatoriai, siejantys veiklas su klientais
    - Veiklos informacija, apimanti veiklos pavadinimą ir datą
    - Semantinė veiklų duomenų schema yra:
        - **Pirminis raktas**: unikalusis veiklos identifikatorius
        - **Laiko žyma**: pirminio rakto identifikuoto įvykio data ir laikas
        - **Įvykis (veiklos pavadinimas)**: norimo naudoti įvykio pavadinimas
        - **Išsami informacija (suma arba reikšmė)**: išsami informacija apie kliento veiklą

- Siūlomos duomenų charakteristikos:
    - Pakankami istoriniai duomenys: mažiausiai vieneri operacijų duomenų metai. Pageidautina nuo dvejų iki trijų metų senumo operacijų duomenų, kad būtų galima prognozuoti CLV vieneriems metams.
    - Keli pirkiniai vienam klientui: idealiu atveju, bent dvi ar trys operacijos vienam klientui, pageidautina atliktos per skirtingas datas.
    - Klientų skaičius: bent 100 unikalių klientų, geriausia daugiau nei 10 000 klientų. Modelis neveiks su mažiau nei 100 klientų ir nepakankamais istoriniais duomenimis
    - Duomenų išbaigtumas: mažiau nei 20 % trūkstamų reikšmių privalomuose įvesties duomenų laukuose

> [!NOTE]
> - Modeliui reikia jūsų klientų sandorių istorijos. Vienu metu galima sukonfigūruoti tik vieną sandorio istorijos objektą. Jei yra keli pirkimo / operacijų objektai, galite juos sujungti prieš pradėdami Power Query naudoti duomenis.
> - Tačiau papildomiems kliento duomenims (pasirinktiniems) galite įtraukti tiek kliento veiklos objektų, kiek norite, atsižvelgdami į modelį.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kurti kliento gyvavimo ciklo vertės prognozę

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Rinkitės **Kliento gyvavimo ciklo vertės** plytelę ir rinkitės **Naudoti modelį**. 

1. **Srityje Kliento gyvenimo trukmės reikšmė** pasirinkite **Darbo pradžia**.

1. **Pavadinkite šį modelį** ir **išvesties objekto pavadinimą** tam, kad kad atskirtumėte juos nuo kitų modelių ar objektų.

1. Pasirinkite **Toliau**.

### <a name="define-model-preferences"></a>Nustatyti modelio nuostatas

1. Nustatykite **Prognozė laikotarpį** norėdami apibrėžti, kiek ateityje norėsite numatyti CLV.    
   Pagal numatytuosius nustatymus vienetas nustatomas kaip mėnesiai. Galite pakeisti jį į metus ir ieškoti toliau ateityje.

   > [!TIP]
   > Norint tiksliai prognozuoti jūsų nustatytą laikotarpį CLV, reikalingas palyginamasis istorinių duomenų laikotarpis. Pavyzdžiui, jei norite prognozuoti CLV kitiems 12 mėnesių, rekomenduojama turėti mažiausiai 18-24 mėnesių senumo istorinius duomenis.

1. Nurodykite, ką **Aktyvūs klientai** reiškia jūsų įmonei. Nustatykite laiką, per kurį klientas turi turėti bent vieną operaciją, kuri bus laikoma aktyvia. Modelis nuspės tik aktyvių klientų CLV. 
   - **Leiskite modeliui apskaičiuoti pirkimo intervalą (rekomenduojama)**: modelis analizuoja jūsų duomenis ir nustato laikotarpį, pagrįstą istoriniais pirkiniais.
   - **Intervalą nustatykite rankiniu būdu**: jei turite konkretų aktyvaus kliento verslo aprašą, pasirinkite šią parinktį ir atitinkamai nustatykite laikotarpį.

1. Apibrėžkite didelės **vertės kliento procentus,** kad modelis pateiktų jūsų verslo aprašą atitinkantį rezultatą.
    - **Modelio skaičiavimas (rekomenduojama)**: modelis analizuoja jūsų duomenis ir nustato, koks gali būti jūsų įmonės didelės vertės klientas pagal klientų operacijų retrospektyvą. Kad būtų galima rasti itin vertingų klientų dalį, modelis naudoja heur vienareikšmę taisyklę (o tai yra 80/20 taisyklė arba pareto principai). Klientų, kurie per istorinį laikotarpį sudaro 80 % sukauptų pajamų, procentinė dalis laikoma didelės vertės klientais. Paprastai mažiau nei 30–40 % klientų sudaro 80 % sukauptų pajamų. Tačiau šis skaičius gali skirtis atsižvelgiant į jūsų verslą ir pramonės šaką.    
    - **Geriausių aktyvių klientų procentinė dalis**: apibrėžkite savo įmonės didelės vertės klientus kaip aktyvių klientų procentą. Pavyzdžiui, šią parinktį galite naudoti didelės vertės klientams apibrėžti kaip geriausius 20 % būsimų klientų.

    Jei jūsų verslas apibrėžia didelės vertės klientus skirtingu būdu, [praneškite mums, kaip norėtume prasčiau naudoti](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Pasirinkdami **Toliau** eikite prie kito veiksmo.

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Veiksme **Būtini duomenys** rinkitės **Įtraukti duomenis** į **Kliento operacijų istoriją** ir pasirinkite objektą, kuris pateikia operacijų istorijos informaciją kaip aprašyta [būtinose sąlygose](#prerequisites).

1. Sudarykite semantinių laukelių žemėlapį į atributus per jūsų įsigijimo istorijos objektą ir pasirinkite **Kitas**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Konfigūravimo žingsnio, per kuriuos galima susieti reikalingų duomenų atributus, vaizdas.":::
 
1. Jei toliau laukų neįrašote, konfigūruokite ryšį iš pirkimo retrospektyvos objekto į *Kliento* objektą ir pasirinkite **Įrašyti**.
    1. Pasirinkite transakcijos istorijos objektą.
    1. Pažymėkite lauką, kuris pirkimo retrospektyvos objektu nustato klientą. Ji turi būti susijęs su kliento objekto pirminiu kliento ID.
    1. Pasirinkite darbo eigos objektą, kuris sutampa su pagrindiniu kliento objektu.
    1. Įveskite pavadinimą, apibūdinantį ryšį.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Konfigūravimo žingsnio vaizdas, nurodantis ryšį su kliento objektu.":::

1. Pasirinkite **Toliau**.

### <a name="add-optional-activity-data"></a>Pasirinktinių veiklos duomenų įtraukimas

Pagrindiniai duomenų sąveikos su klientais veiksmai (pvz., žiniatinklis, klientų aptarnavimas ir įvykių žurnalai) įtraukia kontekstą į operacijų įrašus. Daugiau klientų veiklos duomenų modelių gali padidinti prognozių tikslumą.

1. Atlikdami veiksmą **Papildomi duomenys (pasirinktinai)** pasirinkite **Pridėti duomenų** dalyje **Padidinti modelio įžvalgas su papildomais veiklos duomenimis**. Pasirinkite kliento veiklos objektą, kuris pateikia kliento veiklos informaciją, kaip nurodyta [būtinose sąlygose](#prerequisites).

1. Sudarykite semantinių laukelių žemėlapį į atributus per jūsų kliento veiklos objektą ir pasirinkite **Kitas**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Konfigūravimo žingsnio, per kuriuos galima susieti laukelius papildomiems duomenims.":::

1. Pažymėkite veiklos tipą, atitinkantį kliento veiklos, kurią pridedate, tipą. Pasirinkite iš esamų veiklos tipų arba įtraukite naują veiklos tipą.

1. Sukonfigūruokite ryšį iš savo kliento veiklos objekto *Kliento* objektą.

    1. Pasirinkite laukelį, kuris nustato klientą kliento veiklos lentelėje. Jis gali būti tiesiogiai susietas su pagrindiniu jūsų kliento objekto ID jūsų *Kliento* objekte.
    1. Pasirinkite *kliento* atitinkantį pirminį *kliento* objektą.
    1. Įveskite pavadinimą, apibūdinantį ryšį.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Konfigūracijos srauto žingsnio vaizdas, norint įtraukti papildomų duomenų ir sukonfigūruoti veiklą su užpildomais pavyzdžiais.":::

1. Pasirinkite **Įrašyti**.
    Jei norite įtraukti kitas klientų veiklas, įtraukite daugiau duomenų.

1. Įtraukite pasirinktinius kliento duomenis arba pasirinkite **Pirmyn**.

### <a name="add-optional-customer-data"></a>Pasirinktinių kliento duomenų įtraukimas

Pasirinkite iš 18 dažniausiai naudojamų kliento profilio atributų, kuriuos norite įtraukti kaip modelio įvestį. Šie atributai gali lemti labiau suasmenintus, aktualius ir veiksmingesnius modelio rezultatus jūsų verslo naudojimo atvejais.

Pavyzdžiui: "Contoso Coffee" nori numatyti kliento viso gyvenimo vertę, kad nukreiptų į didelės vertės klientus su individualizuotu pasiūlymu, susijusiu su jų naujo espreso aparato pristatymu. Contoso naudoja CLV modelį ir prideda visus 18 klientų profilio atributų, kad sužinotų, kurie veiksniai daro įtaką jų didžiausios vertės klientams. Jie mano, kad kliento vieta yra įtakingiausias veiksnys šiems klientams.
Turėdami šią informaciją, jie organizuoja vietinį renginį espreso aparato paleidimui ir bendradarbiauja su vietiniais pardavėjais dėl suasmenintų pasiūlymų ir ypatingos patirties renginyje. Neturėdami šios informacijos, Contoso galėjo siųsti tik bendruosius rinkodaros el. laiškus ir praleido galimybę suasmeninti šį vietinį savo didelės vertės klientų segmentą.

1. Atlikdami veiksmą **Papildomi duomenys (pasirinktinai)** pasirinkite **Pridėti duomenų** dalyje **Dar labiau padidinti modelio įžvalgas su papildomais klientų duomenimis**.

1. Objekte **pasirinkite** **Klientas: CustomerInsights**, kad pasirinktumėte vieningą kliento profilio lentelę, susiejančią su kliento atributų duomenimis. Norėdami gauti **kliento ID**, pasirinkite **System.Customer.CustomerId**.

1. Susiekite daugiau laukų, jei duomenys pasiekiami jūsų vieninguose klientų profiliuose.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Kliento profilio duomenų susietų laukų pavyzdys.":::

1. Pasirinkite **Įrašyti** susieję atributus, kuriuos modelis turėtų naudoti, kad padėtų numatyti kliento gyvavimo ciklo vertę.

1. Pasirinkite **Toliau**.

### <a name="set-update-schedule"></a>Nustatyti grafiko naujinimą

1. **Duomenų naujinimo grafiko** žingsnyje pasirinkite dažnumą, kurį pagal naujausius duomenis norite perkvalifikuoti. Šis parametras yra svarbus norint atnaujinti prognozių tikslumą, kai programoje "Customer Insights" praryjami nauji duomenys. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

### <a name="review-and-run-the-model-configuration"></a>Modelio konfigūracijos peržiūra ir paleidimas

1. Atlikdami savo **modelio išsamios informacijos peržiūros** veiksmą, patikrinkite jų prognozę. Prie bet kurios prognozės konfigūracijos dalies galite sugrįžti pažymėdami **Redaguoti** po rodoma reikšme. Taip pat galite pasirinkti konfigūracijos žingsnį iš eigos indikatoriaus.

1. Jei visos reikšmės yra teisingai sukonfigūruotos, pasirinkite **Įrašyti ir vykdyti** , kad būtų paleistas modelis. Skirtuke **Mano prognozės** galite matyti proceso prognozė būseną. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

## <a name="review-prediction-status-and-results"></a>Peržiūrėti prognozė būseną ir rezultatus

### <a name="review-prediction-status"></a>Peržiūrėti prognozė būseną

1.  Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.
2.  Pasirinkite prognozę, kurią norite peržiūrėti.

- **Prognozės pavadinimas**: Įvardykite prognozę jos kūrimo metu.
- **Prognozės tipas**: Prognozei naudojamo modelio tipas
- **Išvesties objektas**: objekto, kuriame saugoma prognozės išvestis, pavadinimas. Eikite į **Duomenys** > **Objektai** norėdami rasti objektą su šiuo pavadinimu.
- **Prognozuojamas laukas**: šis laukas užpildomas tik kai kurių tipų prognozėms ir nėra naudojamas klientų pasitenkinimo reikšmėje prognozė.
- **Būsena:**: Prognozės vykdymo būsena.
    - **Eilė**: prognozė laukia, kol bus užbaigti kiti procesai.
    - **Atnaujinimas**: prognozė vykdomas, kad būtų kuriami rezultatai, kurie bus įtraukti į išvesties objektą.
    - **Nepavyko** : Prognozės vykdymas nepavyko. [Peržiūrėkite įrašus](manage-predictions.md#troubleshoot-a-failed-prediction) dėl išsamesnės informacijos.
    - **Pavyko**: Prognozė pavyko. Pasirinkite **Peržiūrėti** po vertikaliomis elipsėmis prognozavimo rezultatų peržiūrai.
- **Redaguota**: data, kai buvo pakeista prognozės konfigūracija.
- **Paskutinį kartą atnaujinta** : data, kai prognozė atnaujino rezultatus išvesties objekte.

### <a name="review-prediction-results"></a>Peržiūrėti prognozės rezultatus

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pažymėkite prognozė, kurio rezultatus norite peržiūrėti.

Rezultatų puslapyje yra trys pagrindinės duomenų dalys.

- **Mokymo modelio** efektyvumas: A, B ar C yra galimos kategorijos. Šis įvertinimas nurodo objekto prognozė ir gali padėti jums priimti sprendimą naudoti rezultatus, saugomus išvesties objektu. Pasirinkite **Sužinokite apie šį įvertinimą** , kad geriau suprastumėte pagrindines modelio efektyvumo metrikas ir kaip buvo išvesta galutinė modelio efektyvumo klasė.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Modelio balo informacijos lauko vaizdas su A laipsniu":::

  Naudojant didelės vertės klientų apibrėžimą, pateiktą konfigūruojant prognozė, sistema nustato, kaip AI modelis atliktas prognozuojamų didelės vertės klientų lyginant su pradiniu modeliu.    

  Laipsniai nustatomi pagal šias taisykles:
  - **„A”**, kai modelis tiksliai prognozavo bent 5 % daugiau labai svarbių klientų, palyginus su pradiniu modeliu.
  - **„B”**, kai modelis tiksliai prognozavo nuo 0 iki 5 % labai svarbių vertės klientų, palyginus su pradiniu modeliu.
  - **„C”**, kai modelis tiksliai prognozavo mažiau labai svarbių klientų, palyginus su pradiniu modeliu.

  Modelio **įvertinimo** srityje rodoma daugiau informacijos apie AI modelio efektyvumą ir pradinį modelį. Pagal pradinį modelį ne AI pagrįstas metodas klientų pasverti vertei apskaičiuoti, visų pirma remiantis klientų įsigytais istoriniais tikslais.     
  Standartinė formulė, naudojama CLV apskaičiuoti pagal pradinį modelį:    

  _**Kiekvieno kliento CLV** = vidutinis mėnesinis kliento pirkimas aktyviame kliento lange *CLV prognozės laikotarpio mėnesių skaičius* Bendra visų klientų saugojimo sparta*_

  AI modelis lyginamas su pradiniu modeliu pagal dvi modelio efektyvumo metrikas.
  
  - **Sėkmės koeficientas prognozuojant labai vertingus klientus**

    Žr. skirtumą tarp prognozuojamų didelės vertės klientų, kurie naudoja AI modelį, palyginti su pradiniu modeliu. Pavyzdžiui, 84 % sėkmingų klientų skaičius reiškia, kad iš visų vertingų klientų mokymo duomenyse AI modelis galėjo tiksliai užfiksuoti 84 %. Tada palyginsime šį sėkmės koeficientą su pradinio modelio sėkmingų duomenų koeficientu ir pranešame apie santykinį pakeitimą. Ši reikšmė naudojama modeliui priskirti.

  - **Klaidų metrika**
    
    Naudodami kitą metriką galite peržiūrėti bendrą modelio našumą, atsižvelgiant į klaidas ir prognozuoti būsimas reikšmes. Šią klaidą įvertinti naudojame bendrą šakninio vidurkio kvadratinės klaidos (RMSE) metriką. RMSE yra standartinis būdas įvertinti modelio klaidą prognozuojant kiekybinius duomenis. AI modelio RMSE lyginamas su pradinės linijos modelio RMSE ir pranešama apie santykinį skirtumą.

  AI modelis pagal prioritetus suteikia tikslaus klientų rango pagal vertę, kuri juos suteikia jūsų verslui. Todėl galutinis modelio įvertinimas susekimas naudojamas tik prognozuojamų didelės vertės klientų sėkmės koeficientui. RMSE metrika yra opi prie išorinių objektų. Scenarijų, kai klientų, kurių pirkimo vertės yra itin didelės, procentinė dalis, bendra RMSE metrika gali ne visiškai pavaizduoti modelio efektyvumą.   

- **Klientų reikšmė pagal procentus**: naudojant jūsų didelės vertės klientų apibrėžimą klientai grupuojami į žemos ir didelės vertės klientus pagal CLV prognozes ir rodomi diagramoje. Užvesdami pelės žymiklį virš histogramos juostų, galite matyti kiekvienos grupės klientų skaičių ir tos grupės vidutinę CLV. Šie duomenys gali padėti, jei [norite kurti klientų segmentus pagal jų](segments.md) CLV prognozes.

- **Daugelis ne vienu metu lemiamų veiksnių**: kuriant CLV prognozė remiantis AI modeliui pateikiamais įvesties duomenimis. Kiekvienas iš veiksnių turi savo svarbą, apskaičiuojamą bendroms modelio prognozėms. Šiuos veiksnius galite naudoti prognozės rezultatams patvirtinti. Šie faktoriai taip pat suteikia daugiau įžvalgų apie svarbiausius faktorius, kurie labiausiai pranašesni visiems jūsų klientams prognozuojant CLV.

## <a name="manage-predictions"></a>Prognozių valdymas

Prognozes galima optimizuoti, šalinti jų triktis, atnaujinti arba panaikinti. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
