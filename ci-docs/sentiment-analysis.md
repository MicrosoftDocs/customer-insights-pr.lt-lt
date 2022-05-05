---
title: Klientų atsiliepimų nuotaikų analizė
description: Sužinokite, kaip naudoti jausmų analizės modelį klientų atsiliepimams programoje Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e51225bbfcd445180b12661cba12256c3f042045
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643528"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Klientų atsiliepimų nuotaikų analizė (Peržiūra)

Šiais laikais klientai tikisi aukštos kokybės produktų, paslaugų ir patirties. Ypač klientams, kurie dalijasi savo atsiliepimais. Organizacijoms labai sunku analizuoti didėjantį duomenų kiekį, nesumažinant tikslumo ir didesnių darbo sąnaudų. Dynamics 365 Customer Insights siūlo klientų atsiliepimų sentimentų analizės modelį, kuris leidžia organizacijoms tiksliau ir mažesnėmis sąnaudomis analizuoti savo duomenis.

Sentimentų analizė leidžia sintetinti klientų nuotaikas ir nustatyti verslo aspektus kaip tobulėjimo galimybes. Ši "Customer Insights" funkcija padeda suprasti, kas gerai veikia ir ką reikia spręsti. Sutelkite dėmesį į svarbiausias ir įtakingiausias verslo sritis, kad pagerintumėte savo klientų patirtį. Galų gale, tai gali padėti jums vairuoti verslo veiksmus, kurie leidžia patirtį, kuri lemia didelį klientų pasitenkinimą ir lojalumą.

## <a name="overview"></a>Apžvalga

Sentimentų analizės funkcija generuoja dvi išvestines įžvalgas pagal kliento ID. Sentimentų balas (nuo -5 iki 5) ir taikomų verslo aspektų (verslo sričių) sąrašas kartu padeda geriau suprasti klientų atsiliepimus. 

Ši informacija gali padėti pasiekti šiuos rezultatus: 
- Gaukite klientų nuotaikų apie prekės ženklą ar organizaciją apžvalgą
- Nustatykite klientus, turinčius neigiamų nuotaikų, kad sutelktumėte kampanijas ir užduotis bei optimizuotumėte didesnę grąžą  
- Nustatykite verslo aspektus su klientų nurodytomis problemomis  
- Segmentuoti klientus pagal jų nuotaikas vykdyti suasmenintas kampanijas su tiksliniais pardavimais, rinkodara ir palaikymo pastangomis
- Optimizuoti verslo operacijas sprendžiant klientų paminėtas susirūpinimą keliančias sritis ar galimybes
- Pripažinkite verslo aspektus, kuriems sekasi gerai, ir apdovanokite laimingus klientus per lojalumo ir reklamos programas

Siekdami užtikrinti, kad galėtumėte pasitikėti modelių rezultatais, teikiame skaidrią informaciją apie tai, kaip modeliai priima sprendimus. Gausite žodžių, kurie turėjo įtakos modelių sprendimui priskirti tam tikrą sentimentų balą ar verslo aspektą atsiliepimų komentarams, sąrašą.  

Mes naudojame du **natūralios kalbos apdorojimo (NLP) modelius**: pirmasis priskiria kiekvienam atsiliepimų komentarui sentimento balą. Antrasis modelis susieja kiekvieną grįžtamąjį ryšį su visais taikomais verslo aspektais. Modeliai yra mokomi apie viešuosius duomenis iš šaltinių socialinėje žiniasklaidoje, mažmeninėje prekyboje, restoranuose, vartojimo produktuose ir automobilių pramonėje.    
  
Iš anksto nustatyti modelio verslo aspektai, susieti su grįžtamojo ryšio duomenimis, apima:
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
> Šiuo metu mes palaikome tik Anglijos klientų atsiliepimų nuotaikų analizę. Ateityje bus palaikoma daugiau kalbų. Jei grįžtamasis ryšys kitomis kalbomis bus įkeltas, modelis vis tiek grąžins rezultatus. Tačiau šie rezultatai nebus tikslūs. 

## <a name="prerequisites"></a>Būtinosios sąlygos

Sentimentų analizė grindžiama tekstinio grįžtamojo ryšio duomenimis, kurie praėjo duomenų [suvienijimo procesą](data-unification.md). Labai rekomenduojame [iš anksto sukonfigūruoti atsiliepimų duomenų objektus kaip semantinio tipo veiklos objektus](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsiliepimo tipas). 

Norėdami konfigūruoti jausmų analizės modelį, turite bent jau [bendraautoriaus teises](permissions.md).

"Customer Insights" gali apdoroti iki 10 milijonų atsiliepimų įrašų vienam modeliui paleisti. Modelis gali analizuoti atsiliepimų komentarus iki 128 žodžių. Jei atsiliepimų komentaras yra ilgesnis, analizėje atsižvelgiama tik į pirmuosius 128 žodžius.

### <a name="data-requirements"></a>Duomenų reikalavimai
  
Reikalingi šie duomenų atributai:
- Vieningas kliento ID (UCID), kad tekstinio grįžtamojo ryšio duomenų įrašai atitiktų atskirą klientą. Šis ID yra duomenų suvienijimo [proceso](data-unification.md) rezultatas.
- Atsiliepimo ID
- Grįžtamojo ryšio laiko žyma
- Atsiliepimo tekstas   

> [!TIP]
> Sentimentų analizė reikalauja jūsų klientų teksto atsiliepimų. Šiuo metu galima konfigūruoti tik vieną grįžtamojo ryšio objektą. Jei yra keli grįžtamojo ryšio objektai, galite juos Power Query susieti prieš pradedant duomenų nurijimą.

## <a name="configure-a-sentiment-analysis"></a>Jausmų analizės konfigūravimas 

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Plytelėje **Kliento jausmų analizė** pasirinkite **Naudoti modelį**.

1. **Srityje Klientų sentimentų analizė (peržiūra)** pasirinkite **Pradėti**.

1. Žingsnyje **Modelio pavadinimas** pateikite **analizės pavadinimą**. 

1. Pateikite verslo aspekto **išvesties objekto pavadinimą** ir sentimentų balo **išvesties objekto pavadinimą**, tada pasirinkite **Pirmyn**.

1. Žingsnyje **Būtini duomenys** pasirinkite **Įtraukti duomenis**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Įtraukite duomenų srautą į sentimentų analizės modelį.":::

1. **Srityje Įtraukti duomenis** iš sąrašo pasirinkite semantinį tipą **Atsiliepimai**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigūravimo veiksmas, skirtas pasirinkti grįžtamojo ryšio veiklas jausmų analizei.":::

1. Pasirinkite veiklas, kurios bus naudojamos šiai jausmų analizei, tada pasirinkite **Pirmyn**.
 
1. Susiekite duomenų atributus su modelio atributais. Pasirinkite **Įrašyti**, kad pritaikytumėte pasirinkimus. 

1. Matote duomenų susiejimo būseną. Norėdami tęsti, spustelėkite **Pirmyn**. 

1. Žingsnyje **Peržiūrėti išsamią modelio informaciją** patvirtinkite sentimentų analizės konfigūraciją. Galite grįžti į bet kurią prognozė konfigūracijos dalį. Pasirinkite Įrašyti ir **paleiskite**, kad pradėtumėte analizę. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Sentimentų modelio, kuriame rodomi visi sukonfigūruoti elementai, peržiūros veiksmas.":::

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

## <a name="manage-sentiment-analysis"></a>Valdyti jausmų analizę

Galite optimizuoti, šalinti triktis, atnaujinti arba naikinti prognozes. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).

## <a name="review-analysis-results"></a>Peržiūrėti analizės rezultatus
 
1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką. 
1. Pasirinkite prognozė, kurio rezultatus norite peržiūrėti, pavadinimą. Tokiu atveju pasirinkite jausmų analizę, kurią norite peržiūrėti. 

### <a name="summary-tab"></a>Skirtukas Suvestinė

Rezultatų puslapyje yra keturi pagrindiniai duomenų skyriai. 

- **Vidutinis sentimentų balas**: padeda suprasti bendrą visų klientų nuotaiką. Sentimentų balai skirstomi į tris kategorijas: 
  1.    Neigiamas (-5 > 2)
  2.    Neutralus (-1 > 1)
  3.    Teigiamas (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualus bendro klientų jausmo vaizdas.":::

- **Klientų pasiskirstymas pagal sentimentų balus**: Klientai skirstomi į neigiamas, neutralias ir teigiamas grupes pagal jų sentimentų balus. Užveskite pelės žymeklį virš histogramos juostų, kad pamatytumėte klientų skaičių ir vidutinį sentimentų balą kiekvienoje grupėje. Šie duomenys gali padėti jums [sukurti klientų](segments.md) segmentus pagal jų sentimentų balus.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Juostinė diagrama, rodanti klientų nuotaikas visose trijose jausmų grupėse.":::

- **Vidutinis sentimentų balas laikui bėgant**: klientų nuotaikos laikui bėgant gali pasikeisti. Mes pateikiame jūsų klientų nuotaikų tendencijas pagal jūsų duomenų laiko intervalą. Šis rodinys gali padėti įvertinti sezoninių akcijų, produktų pristatymo ar kitų laiko intervencijų poveikį klientų nuotaikoms. Peržiūrėkite grafiką pasirinkdami dominančius metus iš išplečiamojo meniu. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Istorijos diagrama, kurios sentimentų balas laikui bėgant vaizduojamas kaip eilutė.":::
 
- **Nuotaikos visuose verslo aspektuose**: šioje lentelėje išvardijamos vidutinės nuotaikos visais verslo aspektais. Tai gali padėti jums įvertinti, kurie jūsų verslo aspektai jau tenkina klientus ar aspektus, kuriems reikia daugiau dėmesio. Grįžtamojo ryšio įrašai, kurie nesutampa su jokiais palaikomais verslo aspektais, skirstomi į kategorijas dalyje **Kita**. Lentelė pagal numatytuosius nustatymus rūšiuojama abėcėlės tvarka. Rūšiavimą galite modifikuoti pasirinkdami lentelės antraštę.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Verslo aspektų sąrašas su susijusia sentimentų verte ir ją paminėjusių klientų skaičiumi.":::
 
  Pasirinkite verslo aspekto pavadinimą, kad pamatytumėte papildomos informacijos, kaip modelis identifikuoja verslo aspektą. Šioje srityje yra dvi dalys: 

  - **Įtakingi žodžiai**: rodo geriausius žodžius, kurie turėjo įtakos AI modelio verslo aspekto nustatymui klientų atsiliepimuose. 
    **Rodyti įžeidžiančius žodžius**: leidžia į sąrašą įtraukti įžeidžiančius žodžius iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra maitinamas AI modeliu ir gali neaptikti visų įžeidžiančių žodžių. Mes ir toliau iteruojame ir mokome klasifikatorių optimaliam našumui. Jei aptiksite įžeidžiantį žodį, kuris nebuvo filtruojamas taip, kaip tikėtasi, praneškite mums. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Įtakingų žodžių sąrašas su perjungimu, kad būtų rodomi arba paslėpti įžeidžiantys žodžiai.":::
 
  - **Atsiliepimų pavyzdžiai**: rodo faktinius atsiliepimų įrašus jūsų duomenyse. Žodžiai koduojami spalvomis pagal jų įtaką verslo aspekto identifikavimui. 


### <a name="influential-words-analysis-tab"></a>Įtakingas žodžių analizės skirtukas

Yra trys papildomos informacijos skyriai, paaiškinantys, kaip veikia jausmų modelis.
  
1. **Geriausi žodžiai, prisidedantys prie teigiamų nuotaikų**: rodo geriausius žodžius, kurie turėjo įtakos AI modelio teigiamų nuotaikų nustatymui klientų atsiliepimuose.  
2. **Populiariausi žodžiai, prisidedantys prie neigiamų nuotaikų**: rodo geriausius žodžius, kurie turėjo įtakos AI modelio neigiamų nuotaikų nustatymui klientų atsiliepimuose.  
3. **Grįžtamojo ryšio pavyzdžiai**: rodo faktinius grįžtamojo ryšio įrašus, vieną su neigiamu jausmu ir vieną su teigiamu jausmu. Žodžiai atsiliepimų įrašuose paryškinami pagal jų indėlį į priskirtą sentimentų balą. Žodžiai, kurie prisideda prie teigiamo sentimentų balo, yra paryškinti žalia spalva. Žodžiai, prisidedantys prie neigiamo balo, paryškinami raudonai.
   Pasirinkite **Peržiūrėti daugiau**, kad įkeltumėte daugiau atsiliepimų pavyzdžių, kuriuose pateikiama daugiau informacijos ir konteksto, kaip veikia sentimentų modelis.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Klientų atsiliepimų nuotaikų analizės pavyzdžiai.":::
 
**Rodyti įžeidžiančius žodžius**: leidžia į sąrašą įtraukti įžeidžiančius žodžius iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra maitinamas AI modeliu ir gali neaptikti visų įžeidžiančių žodžių. Mes ir toliau iteruojame ir mokome klasifikatorių optimaliam našumui. Jei aptiksite įžeidžiantį žodį, kuris nebuvo filtruojamas taip, kaip tikėtasi, praneškite mums. 

## <a name="act-on-analysis-results"></a>Analizės rezultatų aktas

Galite lengvai pradėti kurti naujus klientų segmentus iš sentimentų analizės rezultatų puslapio, modelio rezultatų puslapio viršuje pasirinkdami **Kurti segmentus**.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandų juosta su prognozė modelių parinktimis.":::
 
## <a name="potential-bias"></a>Galimas šališkumas

Kaip ir bet kuriai funkcijai, kuri naudoja nuspėjamąjį dirbtinį intelektą, turėtumėte žinoti apie galimą šališkumą duomenyse, kuriuos naudojate klientų nuotaikoms prognozuoti. Pavyzdžiui, jei atsiliepimus renkate tik skaitmeniniu būdu, galite praleisti atsiliepimus iš klientų, kurie pirmiausia vykdo verslą su jumis asmeniškai, o tai gali turėti įtakos funkcijos išvestimi.

Kadangi ši funkcija naudoja automatizuotas priemones duomenims įvertinti ir prognozėms, pagrįstoms tais duomenimis, daryti, ji gali būti naudojama kaip profiliavimo metodas, kaip šis terminas apibrėžtas Bendrajame duomenų apsaugos reglamente (BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingas už tai, kad jūsų naudojimasis, įskaitant jausmų Dynamics 365 Customer Insights analizę, atitiktų visus taikomus įstatymus ir kitus teisės aktus, įskaitant įstatymus, susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir pranešimų konfidencialumu.

[!INCLUDE [footer-include](includes/footer-banner.md)]

