---
title: Kliento gyvavimo ciklo (CLV) vertės prognozė
description: Prognozuojamas aktyvių klientų pajamų potencialas ateityje.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 04c4252aae374cf25c16b71415ee4a89b51b0040
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954589"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Kliento gyvavimo ciklo vertės (CLV) prognozė (Apžvalga)

Prognozuojama potenciali reikšmė (pajamos), kurią atskiri aktyvūs klientai įves į jūsų verslą per apibrėžtą būsimą laikotarpį. Ši funkcija gali padėti pasiekti įvairius tikslus: 
- Nustatykite didelės vertės klientus ir apdorokite šią įžvalgą
- Kurti strategines klientų segmentus, atsižvelgiant į jų potencialią vertę, kad suasmenintas kampanijas būtų galima vykdyti naudojant tikslinius pardavimo, rinkodaros ir palaikymo veiksmus
- Vadovo produktų kūrimas susitelkus į funkcijas, kurios padidinti klientų vertę
- Pardavimo arba rinkodaros strategijos optimizavimas ir biudžeto skirstymas tiksliau klientų kampanijai
- Vertingų klientų atpažinimas ir apdovanokite juos pasitelkdami apdovanodami arba pristatę apdovanojimų programas 

## <a name="prerequisites"></a>Būtinosios sąlygos

Prieš pradėdami nurodykite, ką jūsų verslui reiškia CLV. Šiuo metu palaikome transakcija paremtą CLV prognozę. Prognozuojama kliento reikšmė pagrįsta verslo operacijų retrospektyva. Kad sukurtumėte prognozę, jums reikia bent [Prisidėjusio asmens](permissions.md) teisių.

Konfigūruodami ir paleisdami CLV modelį, galite sukurti kelis modelius su skirtingomis įvesties nuostatas ir palyginti modelio rezultatus, kad pamatytumėte, kuris modelio scenarijus geriausiai atitinka jūsų verslo reikmes.

###  <a name="data-requirements"></a>Duomenų reikalavimai

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
> - Modeliui reikia jūsų klientų sandorių istorijos. Vienu metu galima sukonfigūruoti tik vieną sandorio istorijos objektą. Jei yra keli pirkimo/operacijos objektai, galite sujungti juos „Power Query“ modulyje prieš įtraukdami duomenis.
> - Tačiau papildomiems kliento duomenims (pasirinktiniems) galite įtraukti tiek kliento veiklos objektų, kiek norite, atsižvelgdami į modelį.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kurti kliento gyvavimo ciklo vertės prognozę

1. Publikos įžvalgose, eikite į **Intelektas** > **Prognozės**.

1. Rinkitės **Kliento gyvavimo ciklo vertės** plytelę ir rinkitės **Naudoti modelį**. 

1. Juostoje **Kliento gyvavimo ciklo vertės (peržiūra)** rinkitės **Pradėti**.

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

### <a name="add-optional-data"></a>Įtraukti pasirinktinius duomenis

Pagrindiniai duomenų sąveikos su klientais veiksmai (pvz., žiniatinklis, klientų aptarnavimas ir įvykių žurnalai) įtraukia kontekstą į operacijų įrašus. Daugiau klientų veiklos duomenų modelių gali padidinti prognozių tikslumą. 

1. Žingsnyje **Papildomi duomenys (pasirinktiniai)** rinkitės **Įtraukti duomenis**. Pasirinkite kliento veiklos objektą, kuris pateikia kliento veiklos informaciją, kaip nurodyta [būtinose sąlygose](#prerequisites).

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

1. Pasirinkite **Toliau**.

### <a name="set-update-schedule"></a>Nustatyti grafiko naujinimą

1. **Duomenų naujinimo grafiko** žingsnyje pasirinkite dažnumą, kurį pagal naujausius duomenis norite perkvalifikuoti. Šie nustatymai yra svarbūs prognozių tikslumo naujinimui, nes nauji duomenys yra vartojami publikos įžvalgose. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

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
    - **Nepavyko** : Prognozės vykdymas nepavyko. [Peržiūrėkite įrašus](#troubleshoot-a-failed-prediction) dėl išsamesnės informacijos.
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

## <a name="refresh-a-prediction"></a>Prognozės atnaujinimas

Prognozės automatiškai atnaujinamos pagal tą patį [grafiką, kai duomenys](system.md#schedule-tab) atnaujinami, kaip sukonfigūruoti parametruose. Galite juos paleisti iš naujo ir rankiniu būdu.

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.
2. Pasirinkite vertikalius daugtaškius šalia norimos atnaujinti prognozės.
3. Pasirinkite **Atnaujinti**.

## <a name="delete-a-prediction"></a>Prognozės šalinimas

Prognozės panaikinimas taip pat pašalina jos išvesties objektą.

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.
2. Pasirinkite vertikalius daugtaškius šalia norimos pašalinti prognozės.
3. Pasirinkite **Naikinti**.

## <a name="troubleshoot-a-failed-prediction"></a>Nepavykusios prognozės trikčių šalinimas

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.
2. Pasirinkite vertikalias elipses šalia prognozės, kuriose norite peržiūrėti klaidų žurnalus.
3. Pasirinkite **Žurnalai**.
4. Peržiūrėkite visas klaidas. Galimos kelių tipų klaidos, kurios aprašo, kokia būsena sukėlė klaidą. Pavyzdžiui, klaida, kurios duomenų nepakanka, kad būtų galima tiksliai prognozuoti, paprastai išsprendžiama į auditorijos įžvalgas įkeliant daugiau duomenų.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
