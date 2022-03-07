---
title: Klientų atsiliepimų sentimentų analizė
description: Sužinokite, kaip naudoti sentimentų analizės modelį klientų atsiliepimuose Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: b06613b00a512a31479f9d30d539a010e17d33ba
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231475"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Klientų atsiliepimų sentimentų analizė (Peržiūra)

Klientai tikisi aukštos kokybės produktų, paslaugų ir patirties šiomis dienomis. Ypač klientai, kurie dalijasi savo atsiliepimais. Organizacijoms labai sunku analizuoti didėjantį duomenų kiekį, nesumažinant tikslumo ir didesnių darbo sąnaudų. Dynamics 365 Customer Insights siūlo klientų atsiliepimų sentimentų analizės modelį, kuris leidžia organizacijoms tiksliau ir mažesnėmis sąnaudomis analizuoti savo duomenis.

Jausmų analizė leidžia sintezuoti klientų nuotaikas ir nustatyti verslo aspektus kaip tobulėjimo galimybes. Ši "Customer Insights" funkcija padeda suprasti, kas veikia gerai ir į ką reikia atkreipti dėmesį. Sutelkite dėmesį į aktualiausias ir įtakingiausias verslo sritis, kad pagerintumėte savo klientų patirtį. Galų gale, tai gali padėti jums vairuoti verslo veiksmus, kurie įgalina patirtį, kuri lemia didelį klientų pasitenkinimą ir lojalumą.

## <a name="overview"></a>Apžvalga

Sentimentų analizės funkcija generuoja dvi išvestines įžvalgas pagal kliento ID. Nuotaikos balas (nuo -5 iki 5) ir taikomų verslo aspektų sąrašas (verslo sritys) kartu padeda geriau suprasti klientų atsiliepimus. 

Ši informacija gali padėti pasiekti šiuos rezultatus: 
- Gaukite klientų jausmų prekės ženklui ar organizacijai apžvalgą
- Nustatykite klientus, turinčius neigiamą požiūrį, kad sutelktumėte kampanijas ir įsipareigojimus ir optimizuotumėte didesnę grąžą  
- Nustatyti verslo aspektus su klientų nurodytais klausimais  
- Segmentuokite klientus pagal jų požiūrį vykdyti suasmenintas kampanijas su tikslinėmis pardavimo, rinkodaros ir palaikymo pastangomis
- Optimizuoti verslo operacijas sprendžiant klientų minėtas susirūpinimą keliančias sritis ar galimybes
- Pripažinkite verslo aspektus, kurie gerai veikia, ir apdovanokite laimingus klientus per lojalumo ir skatinimo programas

Siekiant užtikrinti, kad galite pasitikėti modelių rezultatais, pateikiame skaidrią informaciją apie tai, kaip modeliai priima sprendimus. Gausite žodžių, kurie turėjo įtakos modelių sprendimui priskirti tam tikrą sentimento balą ar verslo aspektą atsiliepimų komentarams, sąrašą.  

Mes naudojame du **natūralios kalbos apdorojimo (NLP) modelius**: pirmasis kiekvienam atsiliepimų komentarui priskiria sentimento balą. Antrasis modelis susieja kiekvieną grįžtamąjį ryšį su visais taikomais verslo aspektais. Modeliai yra mokomi iš viešųjų duomenų iš socialinės žiniasklaidos, mažmeninės prekybos, restoranų, vartojimo produktų ir automobilių pramonės šaltinių.    
  
Iš anksto nustatyti modelio verslo aspektai, susieti su grįžtamojo ryšio duomenimis, yra šie:
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
> Šiuo metu mes palaikome tik anglų klientų atsiliepimų sentimentų analizę. Ateityje bus remiama daugiau kalbų. Jei atsiliepimai kitomis kalbomis bus įkelti, modelis vis tiek pateiks rezultatus. Tačiau šie rezultatai nebus tikslūs. 

## <a name="prerequisites"></a>Būtinosios sąlygos

Sentimentų analizė pagrįsta teksto grįžtamojo ryšio duomenimis, kurie praėjo [duomenų suvienijimo procesą](data-unification.md). Labai rekomenduojame [iš anksto sukonfigūruoti grįžtamojo ryšio duomenų objektus kaip semantinio tipo veiklos objektus](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (grįžtamojo ryšio tipą). 

Norėdami konfigūruoti sentimentų analizės modelį, turite bent jau [bendraautoriaus teises](permissions.md).

"Customer Insights" gali apdoroti iki 10 milijonų atsiliepimų įrašų vienam modeliui paleisti. Modelis gali analizuoti grįžtamojo ryšio komentarus iki 128 žodžių. Jei atsiliepimų komentaras yra ilgesnis, analizėje atsižvelgiama tik į pirmuosius 128 žodžius.

### <a name="data-requirements"></a>Duomenų reikalavimai
  
Reikalingi šie duomenų atributai:
- Vieningas kliento ID (UCID), kad teksto grįžtamojo ryšio duomenų įrašai atitiktų atskirą klientą. Šis ID yra duomenų suvienodinimo [proceso](data-unification.md) rezultatas.
- Atsiliepimo ID
- Grįžtamojo ryšio laiko žyma
- Atsiliepimo tekstas   

> [!TIP]
> Sentimentų analizė reikalauja jūsų klientų teksto atsiliepimų. Šiuo metu galima konfigūruoti tik vieną grįžtamojo ryšio objektą. Jei yra keli grįžtamojo ryšio objektai, galite juos sujungti Power Query prieš pradedant duomenų nurijimas.

## <a name="configure-a-sentiment-analysis"></a>Sentimentų analizės konfigūravimas 

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Plytelėje **Klientų jausmų analizė** pasirinkite **Naudoti modelį**.

1. **Srityje Klientų nuotaikų analizė (peržiūra)** pasirinkite **Pradėti**.

1. **Atlikdami modelio pavadinimo** veiksmą pateikite **analizės pavadinimą**. 

1. Pateikite verslo aspekto **išvesties objekto pavadinimą** ir sentimento balo **išvesties objekto pavadinimą**, tada pasirinkite **Pirmyn**.

1. **Atlikdami veiksmą Reikiami duomenys** pasirinkite **Įtraukti duomenis**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Įtraukite duomenų srautą į sentimentų analizės modelį.":::

1. **Srityje Duomenų įtraukimas** iš sąrašo pasirinkite semantinį tipą **Grįžtamasis ryšys**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigūracijos veiksmas norint pasirinkti sentimentų analizės grįžtamojo ryšio veiklas.":::

1. Pasirinkite veiklas, kurios bus naudojamos šiai sentimentų analizei, tada pasirinkite **Pirmyn**.
 
1. Susiekite duomenų atributus su modelio atributais. Pasirinkite **Įrašyti**, kad pritaikytumėte pasirinkimus. 

1. Matote duomenų susiejimo būseną. Norėdami tęsti, spustelėkite **Pirmyn**. 

1. **Atlikdami modelio išsamios informacijos** peržiūra, patikrinkite savo jausmų analizės konfigūraciją. Galite grįžti į bet kurią prognozė konfigūracijos dalį. Pasirinkite **Įrašyti ir paleiskite**, kad pradėtumėte analizę. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Peržiūrėti sentimentų modelio, kuriame rodomi visi sukonfigūruoti elementai, veiksmą.":::

1. Pasirinkite **Atlikta**, kad paliktumėte konfigūravimo patirtį. Procesas gali užtrukti kelias valandas, priklausomai nuo naudojamų duomenų kiekio. 

## <a name="review-analysis-status"></a>Peržiūrėti analizės būseną

1.  Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.
2.  Pasirinkite prognozę, kurią norite peržiūrėti.
- **Prognozės pavadinimas**: Įvardykite prognozę jos kūrimo metu.
- **prognozė tipas**: prognozė naudojamo modelio tipas.
- **Išvesties objektas**: objekto, kuriame saugoma prognozės išvestis, pavadinimas. Eikite į **Duomenys** > **Objektai** norėdami rasti objektą su šiuo pavadinimu.
- **Prognozuojamas laukas**: šis laukas užpildomas tik kai kurių tipų prognozėms ir nėra naudojamas klientų pasitenkinimo reikšmėje prognozė.
- **Būsena:**: Prognozės vykdymo būsena.
  - **Eilė**: prognozė laukia, kol bus užbaigti kiti procesai.
  - **Atnaujinimas**: prognozė vykdomas, kad būtų kuriami rezultatai, kurie bus įtraukti į išvesties objektą.
  - **Nepavyko** : Prognozės vykdymas nepavyko. Peržiūrėkite įrašus dėl išsamesnės informacijos.
  - **Pavyko**: Prognozė pavyko. Pasirinkite Peržiūrėti po vertikaliomis elipsėmis prognozavimo rezultatų peržiūrai.
- **Redaguota**: data, kai buvo pakeista prognozės konfigūracija.
- **Paskutinį kartą atnaujinta**: data, kai prognozė atnaujino rezultatus išvesties objekte.

## <a name="manage-sentiment-analysis"></a>Valdyti sentimentų analizę

Galite optimizuoti, šalinti triktis, atnaujinti arba naikinti prognozes. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).

## <a name="review-analysis-results"></a>Peržiūrėti analizės rezultatus
 
1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką. 
1. Pasirinkite prognozė, kurio rezultatus norite peržiūrėti, pavadinimą. Tokiu atveju pasirinkite sentimentų analizę, kurią norite peržiūrėti. 

### <a name="summary-tab"></a>Skirtukas Suvestinė

Rezultatų puslapyje yra keturios pagrindinės duomenų sekcijos. 

- **Vidutinis nuotaikos balas**: padeda suprasti bendrą visų klientų nuotaiką. Sentimentų balai sugrupuoti į tris kategorijas: 
  1.    Neigiamas (-5 > 2)
  2.    Neutralus (-1 > 1)
  3.    Teigiamas (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualinis bendro kliento jausmo atspindys.":::

- **Klientų pasiskirstymas pagal sentimentų balus**: klientai skirstomi į neigiamas, neutralias ir teigiamas grupes pagal jų nuotaikos balus. Palaikykite pelės žymiklį virš histogramos juostų, kad pamatytumėte klientų skaičių ir vidutinį nuotaikos balą kiekvienoje grupėje. Šie duomenys gali padėti sukurti [klientų](segments.md) segmentus pagal jų sentimentų balus.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Juostinė diagrama, rodanti klientų jausmus trijose sentimentų grupėse.":::

- **Vidutinis sentimentų balas laikui bėgant**: klientų nuotaikos laikui bėgant gali keistis. Pateikiame jūsų klientų nuotaikų tendencijas jūsų duomenų diapazone. Šis rodinys gali padėti įvertinti sezoninių akcijų, produktų paleidimo ar kitų laiko ribojamų intervencijų poveikį klientų nuotaikoms. Peržiūrėkite grafiką pasirinkdami dominančių metų iš išplečiamojo meniu. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Istorijos diagrama su sentimento balu laikui bėgant pateikiama kaip eilutė.":::
 
- **Nuotaikos visais verslo aspektais**: Šioje lentelėje išvardijamos vidutinės nuotaikos įvairiuose verslo aspektuose. Tai gali padėti jums įvertinti, kurie jūsų verslo aspektai jau patenkina klientus ar aspektus, kuriems reikia daugiau dėmesio. Grįžtamojo ryšio įrašai, kurie nesutampa su jokiais palaikomais verslo aspektais, klasifikuojami dalyje **Kita**. Lentelė rūšiuojamas abėcėlės tvarka pagal numatytuosius nustatymus. Rūšiavimą galite modifikuoti pasirinkdami lentelės antraštę.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Verslo aspektų sąrašas su susijusia sentimento verte ir ją mininčių klientų skaičiumi.":::
 
  Pasirinkite verslo aspekto pavadinimą, kad pamatytumėte papildomą informaciją, kaip modelis identifikuoja verslo aspektą. Šioje srityje yra dvi dalys: 

  - **Įtakingi žodžiai**: rodo viršutinius žodžius, kurie turėjo įtakos DI modelio verslo aspekto identifikavimui klientų atsiliepimuose. 
    **Rodyti įžeidžiančius žodžius**: leidžia įtraukti įžeidžiančius žodžius į sąrašą iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas DI modeliu ir gali aptikti ne visus įžeidžiančius žodžius. Mes ir toliau iteruojame ir mokome klasifikatorių optimaliam veikimui. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruojamas taip, kaip tikėtasi, praneškite mums. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Įtakingų žodžių sąrašas su perjungimu, kad būtų rodomi ar paslėpti įžeidžiantys žodžiai.":::
 
  - **Atsiliepimų** pavyzdžiai: duomenyse rodomi faktiniai grįžtamojo ryšio įrašai. Žodžiai yra užkoduoti pagal jų įtaką verslo aspekto identifikavimui. 


### <a name="influential-words-analysis-tab"></a>Įtakingų žodžių analizės skirtukas

Yra trys papildomos informacijos skyriai, paaiškinantys, kaip veikia sentimento modelis.
  
1. **Populiariausi žodžiai, prisidedantys prie teigiamų nuotaikų**: rodo geriausius žodžius, kurie turėjo įtakos AI modelio teigiamų nuotaikų identifikavimui klientų atsiliepimuose.  
2. **Populiariausi žodžiai, prisidedantys prie neigiamo jausmo**: rodo geriausius žodžius, kurie turėjo įtakos DI modelio neigiamų nuotaikų identifikavimui klientų atsiliepimuose.  
3. **Atsiliepimų pavyzdžiai: rodomi faktiniai** grįžtamojo ryšio įrašai, vienas su neigiamu jausmu ir vienas su teigiamu jausmu. Grįžtamojo ryšio įrašų žodžiai paryškinami pagal jų indėlį į priskirtą sentimento balą. Žodžiai, kurie prisideda prie teigiamo nuotaikos balo, paryškinami žaliai. Žodžiai, prisidedantys prie neigiamo rezultato, paryškinami raudonai.
   Pasirinkite **Peržiūrėti daugiau**, jei norite įkelti daugiau atsiliepimų pavyzdžių, kuriuose pateikiama daugiau informacijos ir konteksto, kaip veikia sentimento modelis.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Klientų atsiliepimų sentimentų analizės pavyzdžiai.":::
 
**Rodyti įžeidžiančius žodžius**: leidžia įtraukti įžeidžiančius žodžius į sąrašą iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas DI modeliu ir gali aptikti ne visus įžeidžiančius žodžius. Mes ir toliau iteruojame ir mokome klasifikatorių optimaliam veikimui. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruojamas taip, kaip tikėtasi, praneškite mums. 

## <a name="act-on-analysis-results"></a>Analizės rezultatų aktas

Galite lengvai pradėti kurti naujus klientų segmentus iš sentimentų analizės rezultatų puslapio modelio rezultatų puslapio viršuje pasirinkdami **Segmentų** kūrimas.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandų juosta su prognozė modelių parinktimis.":::
 
## <a name="potential-bias"></a>Galimas šališkumas

Kaip ir bet kuri funkcija, naudojanti nuspėjamą dirbtinį intelektą, turėtumėte žinoti apie galimą duomenų, kuriuos naudojate klientų nuotaikoms prognozuoti, šališkumą. Pavyzdžiui, jei atsiliepimus renkate tik skaitmeniniu būdu, galite praleisti klientų, kurie pirmiausia vykdo verslą su jumis asmeniškai, atsiliepimus, o tai gali turėti įtakos funkcijos produkcijai.

Kadangi ši funkcija naudoja automatizuotas priemones duomenims įvertinti ir prognozėms, pagrįstoms šiais duomenimis, atlikti, ji gali būti naudojama kaip profiliavimo metodas, nes šis terminas apibrėžtas Bendrajame duomenų apsaugos reglamente (BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingi už tai, kad jūsų naudojimas Dynamics 365 Customer Insights, įskaitant jausmų analizę, atitiktų visus galiojančius įstatymus ir kitus teisės aktus, įskaitant įstatymus, susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir pranešimų konfidencialumu.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

