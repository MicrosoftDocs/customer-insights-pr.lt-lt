---
title: Semantinė klientų atsiliepimų analizė
description: Sužinokite, kaip naudoti sentimentų analizės modelį klientų atsiliepimams Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951113"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Klientų atsiliepimų sentimentų analizė (Peržiūra)

Klientai tikisi aukštos kokybės produktų, paslaugų ir patirties šių dienų. Ypač klientai, kurie dalijasi savo atsiliepimais. Organizacijoms labai sunku analizuoti didėjantį duomenų kiekį, nesumažinant tikslumo ir didesnių darbo sąnaudų. Dynamics 365 Customer Insights siūlo klientų atsiliepimų sentimentų analizės modelį, kuris leidžia organizacijoms tiksliau ir mažesnėmis sąnaudomis analizuoti savo duomenis.

Sentimentų analizė leidžia sintezuoti klientų nuotaikas ir nustatyti verslo aspektus kaip tobulėjimo galimybes. Ši "Customer Insights" funkcija padeda suprasti, kas veikia gerai ir ką reikia spręsti. Sutelkite dėmesį į svarbiausias ir svarbiausias verslo sritis, kad pagerintumėte savo klientų patirtį. Galų gale tai gali padėti jums vairuoti verslo veiksmus, kurie leidžia patirti, dėl kurių atsiranda didelis klientų pasitenkinimas ir lojalumas.

## <a name="overview"></a>Apžvalga

Sentimentų analizės funkcija generuoja dvi išvestines įžvalgas vienam kliento ID. Sentimentų balas (nuo -5 iki 5) ir taikomų verslo aspektų (verslo sričių) sąrašas kartu padeda geriau suprasti klientų atsiliepimus. 

Ši informacija gali padėti pasiekti šiuos rezultatus: 
- Gaukite klientų jausmų prekės ženklui ar organizacijai apžvalgą
- Nustatykite neigiamus klientus, kad sutelktumėte kampanijas ir įsipareigojimus ir optimizuotumėte didesnę grąžą  
- Nustatykite verslo aspektus su klientų nurodytais klausimais  
- Segmento klientai pagal jų norą vykdyti suasmenintas kampanijas su tikslinėmis pardavimo, rinkodaros ir palaikymo pastangomis
- Optimizuoti verslo operacijas sprendžiant klientų paminėtas susirūpinimą keliančias ar galimybes
- Pripažinkite verslo aspektus, kurie daro gerai, ir apdovanokite laimingus klientus lojalumo ir reklamos programomis

Norėdami užtikrinti, kad galėtumėte pasitikėti modelių rezultatais, pateikiame skaidrią informaciją apie tai, kaip modeliai priima sprendimus. Gausite žodžių, kurie turėjo įtakos modelių sprendimui priskirti tam tikrą sentimentų balą ar verslo aspektą atsiliepimų komentarams, sąrašą.  

Mes naudojame du **natūralios kalbos apdorojimo (NLP)** modelius: Pirmasis priskiria kiekvieną atsiliepimų komentarą sentimento balą. Antrasis modelis susieja kiekvieną grįžtamąjį ryšį su visais taikomais verslo aspektais. Modeliai mokomi remiantis viešais duomenimis iš šaltinių socialinėje žiniasklaidoje, mažmeninėje prekyboje, restoranuose, vartojimo produktuose ir automobilių pramonėje.    
  
- Iš anksto apibrėžti modelio verslo aspektai, kuriuos galima susieti su grįžtamojo ryšio duomenimis, yra šie:
-   Klientų valdymas
-   Pirkimo užbaigimas ir apmokėjimas
-   Klientų aptarnavimas
-   Paėmimas parduotuvėje
-   Pakavimas, siuntimas ir gavimas
-   Išankstinis užsakymas
-   Kainos
-   Privatumas ir sauga
-   Akcijos ir apdovanojimai
-   Kvitas ir garantijos
-   Grąžinimas, keitimas ir atšaukimas
-   Įvykdymo tikslumas
-   Svetainės / programos kokybė

> [!NOTE]
> Šiuo metu mes palaikome tik sentimentų analizę dėl anglų klientų atsiliepimų. Ateityje bus palaikoma daugiau kalbų. Jei grįžtamasis ryšys kitomis kalbomis bus nusiųstas, modelis vis tiek grąžins rezultatus. Tačiau šie rezultatai nebus tikslūs. 

## <a name="prerequisites"></a>Būtinosios sąlygos

Sentimentų analizė grindžiama teksto grįžtamojo ryšio duomenimis, kurie praėjo [duomenų suvienijimo procesą](data-unification.md). Labai rekomenduojame [iš anksto sukonfigūruoti grįžtamojo ryšio duomenų objektus kaip semantinio tipo veiklos objektus](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (grįžtamojo ryšio tipą). 

Norėdami konfigūruoti sentimentų analizės modelį, turite bent [autorių teisių](permissions.md).

"Customer Insights" gali apdoroti iki 10 milijonų vieno modelio vykdymo atsiliepimų įrašų. Modelis gali analizuoti atsiliepimų komentarus iki 128 žodžių. Jei atsiliepimų komentaras yra ilgesnis, analizėje atsižvelgiama tik į pirmuosius 128 žodžius.

### <a name="data-requirements"></a>Duomenų reikalavimai
  
Reikalingi šie duomenų atributai:
- Suvienodintas kliento ID (UCID), kad tekstas būtų suderintas su atskiru klientu. Šis ID yra [duomenų suvienijimo proceso rezultatas](data-unification.md).
- Atsiliepimo ID
- Grįžtamojo ryšio laiko žyma
- Atsiliepimo tekstas   

> [!TIP]
> Sentimentų analizė reikalauja jūsų klientų teksto atsiliepimų. Šiuo metu galima konfigūruoti tik vieną atsiliepimų objektą. Jei yra keli grįžtamojo ryšio objektai, galite juos sujungti Power Query prieš pradedant duomenų nurijimas.

## <a name="configure-a-sentiment-analysis"></a>Sentimentų analizės konfigūravimas 

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. **Plytelėje Kliento nuotaikos analizė** pasirinkite **Naudoti modelį**.

1. Srityje **Klientų vertinimų analizė (peržiūra)** pasirinkite **Pradėti**.

1. Modelio **pavadinimo** žingsnyje pateikite **analizės** pavadinimą. 

1. Pateikite **verslo aspekto išvesties objekto pavadinimą** ir **sentimento balo išvesties objekto pavadinimą**, tada pasirinkite **Pirmyn**.

1. **Žingsnyje Būtini duomenys** pasirinkite **Įtraukti duomenis**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Į sentimentų analizės modelį įtraukti duomenų srautą.":::

1. Srityje **Įtraukti duomenis** sąraše pasirinkite semantinį **tipą** Atsiliepimai.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigūravimo veiksmas, skirtas pasirinkti atsiliepimų veiklas sentimentų analizei.":::

1. Pasirinkite veiklas, naudojamas šiai sentimentų analizei, tada pasirinkite **Pirmyn**.
 
1. Susiekite duomenų atributus su modelio atributais. Pasirinkite **Įrašyti**, kad pritaikytumėte pasirinkimus. 

1. Matote duomenų susiejimo būseną. Norėdami tęsti, spustelėkite **Pirmyn**. 

1. Atliekant **veiksmą Peržiūrėti modelio išsamią** informaciją, patikrinkite sentimentų analizės konfigūraciją. Galite grįžti į bet kurią prognozė konfigūracijos dalį. Norėdami pradėti analizę, pasirinkite **Įrašyti ir** paleisti. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Sentimento modelio peržiūros veiksmas, rodantis visus sukonfigūruotus elementus.":::

1. Pasirinkite **Atlikta**, kad paliktumėte konfigūravimo patirtį. Procesas gali užtrukti kelias valandas, priklausomai nuo naudojamų duomenų kiekio. 

## <a name="review-analysis-status"></a>Peržiūrėti analizės būseną

1.  Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.
2.  Pasirinkite prognozę, kurią norite peržiūrėti.
- **Prognozės pavadinimas**: Įvardykite prognozę jos kūrimo metu.
- **prognozė tipas** : prognozė naudojamo modelio tipas.
- **Išvesties objektas**: objekto, kuriame saugoma prognozės išvestis, pavadinimas. Eikite į **Duomenys** > **Objektai** norėdami rasti objektą su šiuo pavadinimu.
- **Prognozuojamas laukas**: šis laukas užpildomas tik kai kurių tipų prognozėms ir nėra naudojamas klientų pasitenkinimo reikšmėje prognozė.
- **Būsena:**: Prognozės vykdymo būsena.
  - **Eilė**: prognozė laukia, kol bus užbaigti kiti procesai.
  - **Atnaujinimas**: prognozė vykdomas, kad būtų kuriami rezultatai, kurie bus įtraukti į išvesties objektą.
  - **Nepavyko** : Prognozės vykdymas nepavyko. Peržiūrėkite įrašus dėl išsamesnės informacijos.
  - **Pavyko**: Prognozė pavyko. Pasirinkite Peržiūrėti po vertikaliomis elipsėmis prognozavimo rezultatų peržiūrai.
- **Redaguota**: data, kai buvo pakeista prognozės konfigūracija.
- **Paskutinį kartą atnaujinta** : data, kai prognozė atnaujino išvesties objekto rezultatus.

## <a name="manage-sentiment-analysis"></a>Valdyti sentimentų analizę

Galite optimizuoti, šalinti triktis, atnaujinti arba panaikinti prognozes. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).

## <a name="review-analysis-results"></a>Peržiūrėti analizės rezultatus
 
1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką. 
1. Pasirinkite prognozė, kurio rezultatus norite peržiūrėti, pavadinimą. Tokiu atveju pasirinkite sentimentų analizę, kurią norite peržiūrėti. 

### <a name="summary-tab"></a>Skirtukas Suvestinė

Rezultatų puslapyje yra keturios pagrindinės duomenų dalys. 

- **Vidutinis sentimentų** balas : padeda suprasti bendrą visų klientų požiūrį. Sentimentų balai sugrupuoti į tris kategorijas: 
  1.    Neigiamas (-5 > 2)
  2.    Neutralus (-1 > 1)
  3.    Teigiamas (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualus bendro kliento jausmo atstovavimas.":::

- **Klientų pasiskirstymas pagal sentimentų balą** : Klientai skirstomi į neigiamas, neutralias ir teigiamas grupes pagal jų nuotaikos balus. Užveskite pelės žymiklį virš histogramos juostų, kad pamatytumėte klientų skaičių ir vidutinį sentimentų balą kiekvienoje grupėje. Šie duomenys gali padėti [kurti klientų segmentus](segments.md) pagal jų sentimentų balus.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Juostinė diagrama, rodanti klientų nuotaikas trijose sentimentų grupėse.":::

- **Vidutinis sentimentų balas laikui bėgant** : klientų nuotaikos laikui bėgant gali keistis. Pateikiame jūsų klientų jausmų tendencijas jūsų duomenų laiko intervale. Šis rodinys gali padėti įvertinti sezoninių akcijų, produktų paleidimo ar kitų terminų intervencijų poveikį klientų nuotaikoms. Peržiūrėkite grafiką išplečiamajame meniu pasirinkdami dominančius metus. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Istorijos diagrama su sentimentų balu laikui bėgant vaizduojama kaip eilutė.":::
 
- **Sentimentai verslo aspektuose** : Šioje lentelėje išvardijami vidutiniai verslo aspektai. Tai gali padėti jums įvertinti, kurie jūsų verslo aspektai jau tenkina klientus ar aspektus, kuriems reikia daugiau dėmesio. Atsiliepimų įrašai, kurie nesutampa su jokiais palaikomo verslo aspektais, skirstomi į **Kitą**. Pagal numatytuosius nustatymus lentelė rūšiuojami abėcėlės tvarka. Rūšiavimą galite modifikuoti pasirinkdami lentelės antraštę.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Verslo aspektų sąrašas su susijusia sentimento verte ir ją mininčių klientų skaičiumi.":::
 
  Pasirinkite verslo aspekto pavadinimą, kad pamatytumėte papildomą informaciją, kaip modelis identifikuoja verslo aspektą. Šioje srityje yra dvi dalys: 

  - **Įtakingi žodžiai** : rodo populiariausius žodžius, kurie turėjo įtakos DI modelio verslo aspekto identifikavimui klientų atsiliepimuose. 
    **Rodyti įžeidžiančius žodžius** : į sąrašą įtraukiate įžeidžiančius žodžius iš originalių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas DI modeliu ir gali neaptikti visų įžeidžiančių žodžių. Mes ir toliau iteruojame ir mokome klasifikatorių optimaliam našumui. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruojamas taip, kaip tikėtasi, praneškite mums. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Įtakingų žodžių sąrašas su perjungimu, kad būtų rodomi arba paslėpti įžeidžiantys žodžiai.":::
 
  - **Atsiliepimų pavyzdžiai** : rodo faktinius atsiliepimų įrašus jūsų duomenyse. Žodžiai yra užkoduoti pagal jų įtaką verslo aspekto identifikavimui. 


### <a name="influential-words-analysis-tab"></a>Skirtukas Įtakingi žodžiai analizė

Yra trys papildomos informacijos dalys, paaiškinančios, kaip veikia sentimentų modelis.
  
1. **Populiariausi žodžiai, prisidedantys prie teigiamų** jausmų: rodo geriausius žodžius, kurie turėjo įtakos DI modelio teigiamų jausmų identifikavimui klientų atsiliepimuose.  
2. **Populiariausi žodžiai, prisidedantys prie neigiamų** jausmų: rodo viršutinius žodžius, kurie turėjo įtakos DI modelio neigiamų jausmų identifikavimui klientų atsiliepimuose.  
3. **Grįžtamojo ryšio pavyzdžiai** : rodomi faktiniai grįžtamojo ryšio įrašai, vienas su neigiamu jausmu ir vienas su teigiamu jausmu. Grįžtamojo ryšio įrašų žodžiai paryškinami pagal jų indėlį į priskirtą sentimento balą. Žodžiai, prisidedantys prie teigiamo jausmo balo, paryškinami žalia spalva. Žodžiai, prisidedantys prie neigiamo rezultato, paryškinami raudonai.
   Pasirinkite **Daugiau**, kad įkeltumėte daugiau atsiliepimų pavyzdžių, kurie suteiktų daugiau informacijos ir konteksto, kaip veikia sentimentų modelis.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Klientų atsiliepimų sentimentų analizės pavyzdžiai.":::
 
**Rodyti įžeidžiančius žodžius** : į sąrašą įtraukiate įžeidžiančius žodžius iš originalių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas DI modeliu ir gali neaptikti visų įžeidžiančių žodžių. Mes ir toliau iteruojame ir mokome klasifikatorių optimaliam našumui. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruojamas taip, kaip tikėtasi, praneškite mums. 

## <a name="act-on-analysis-results"></a>Aktas dėl analizės rezultatų

Galite lengvai pradėti kurti naujus klientų segmentus iš sentimentų analizės rezultatų puslapio pasirinkdami **Kurti segmentus** modelio rezultatų puslapio viršuje.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandų juosta su prognozė modelių parinktimis.":::
 
## <a name="potential-bias"></a>Galimas šališkumas

Kaip ir bet kuri funkcija, kuri naudoja nuspėjantį dirbtinį intelektą, turėtumėte žinoti apie galimą duomenų, kuriuos naudojate klientų nuotaikoms prognozuoti, šališkumą. Pavyzdžiui, jei atsiliepimus renkate tik skaitmeniniu būdu, galite praleisti klientų, kurie pirmiausia vykdo verslą su jumis asmeniškai, atsiliepimus, o tai gali turėti įtakos funkcijos išeigai.

Kadangi ši funkcija naudoja automatizuotas priemones duomenims įvertinti ir prognozėms remiantis remiantis šiais duomenimis daryti, ji gali būti naudojama kaip profiliavimo metodas, nes šis terminas apibrėžiamas Bendrajame duomenų apsaugos reglamente (toliau – BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingi už tai, kad jūsų naudojimas Dynamics 365 Customer Insights, įskaitant sentimentų analizę, atitiktų visus galiojančius įstatymus ir kitus teisės aktus, įskaitant įstatymus, susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir ryšių konfidencialumu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

