---
title: Klientų atsiliepimų nuotaikų analizavimas (peržiūra)
description: Sužinokite, kaip naudoti nuotaikų analizės modelį klientų atsiliepimuose Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055546"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Klientų atsiliepimų nuotaikų analizavimas (peržiūra)

Šiais laikais klientai tikisi aukštos kokybės produktų, paslaugų ir potyrių. Ypač klientai, kurie dalijasi savo atsiliepimais. Organizacijoms labai sudėtinga analizuoti didėjantį duomenų kiekį nesumažinant tikslumo ir didesnių darbo sąnaudų. Dynamics 365 Customer Insights siūlo klientų atsiliepimų nuotaikų analizės modelį, leidžiantį organizacijoms tiksliau ir mažesnėmis sąnaudomis analizuoti savo duomenis.

Nuotaikų analizė leidžia susintetinti klientų nuotaikas ir nustatyti verslo aspektus kaip tobulėjimo galimybes. Ši "Customer Insights" funkcija padeda suprasti, kas veikia gerai ir į ką reikia atkreipti dėmesį. Sutelkite dėmesį į aktualiausias ir paveikiausias verslo sritis, kad pagerintumėte savo klientų patirtį. Galų gale tai gali padėti jums paskatinti verslo veiksmus, kurie įgalina patirtį, užtikrinančią didelį klientų pasitenkinimą ir lojalumą.

## <a name="overview"></a>Apžvalga

Nuotaikų analizės funkcija generuoja dvi išvestines įžvalgas pagal kliento ID. Nuotaikų balas (nuo -5 iki 5) ir taikomų verslo aspektų (verslo sričių) sąrašas kartu padeda geriau suprasti klientų atsiliepimus. 

Ši informacija gali padėti pasiekti šiuos rezultatus: 
- Gaukite klientų nuotaikų prekės ženklui ar organizacijai apžvalgą
- Identifikuokite klientus, turinčius neigiamų nuotaikų, kad sutelktumėte kampanijas ir įtraukimus ir optimizuotumėte, kad gautumėte didesnę grąžą  
- Nustatykite verslo aspektus su klientų nurodytomis problemomis  
- Segmentuokite klientus pagal jų norą vykdyti suasmenintas kampanijas su tiksliniais pardavimais, rinkodara ir palaikymo pastangomis
- Optimizuokite verslo operacijas, spręsdami klientų paminėtas susirūpinimą keliančias ar galimybes
- Pripažinkite verslo aspektus, kuriems sekasi gerai, ir apdovanokite laimingus klientus per lojalumo ir skatinimo programas

Siekdami užtikrinti, kad galėtumėte pasitikėti modelių rezultatais, teikiame skaidrią informaciją apie tai, kaip modeliai priima sprendimus. Gausite sąrašą žodžių, kurie turėjo įtakos modelių sprendimui priskirti tam tikrą nuotaikos balą arba verslo aspektą atsiliepimų komentarams.  

Mes naudojame du **natūralios kalbos apdorojimo (NLP) modelius**: pirmasis kiekvienam grįžtamojo ryšio komentarui priskiria sentimentų balą. Antrasis modelis susieja kiekvieną atsiliepimą su visais taikomais verslo aspektais. Modeliai mokomi pagal viešus duomenis iš šaltinių socialinėje žiniasklaidoje, mažmeninėje prekyboje, restoranuose, vartojimo produktuose ir automobilių pramonėje.    
  
Iš anksto apibrėžti verslo aspektai, kuriuos modelis susieja su grįžtamojo ryšio duomenimis, yra šie:
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
> Šiuo metu mes palaikome tik anglų kalbos klientų atsiliepimų nuotaikų analizę. Ateityje bus palaikoma daugiau kalbų. Jei įkeliami atsiliepimai kitomis kalbomis, modelis vis tiek pateiks rezultatus. Tačiau šie rezultatai nebus tikslūs. 

## <a name="prerequisites"></a>Būtinosios sąlygos

Nuotaikų analizė pagrįsta teksto grįžtamojo ryšio duomenimis, kurie išgyveno [duomenų suvienijimo procesą](data-unification.md). Labai rekomenduojame [iš anksto sukonfigūruoti atsiliepimų duomenų objektus kaip semantinio tipo veiklos objektus](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsiliepimų tipą). 

Norint sukonfigūruoti nuotaikų analizės modelį, jums reikia bent bendraautorio [teisių](permissions.md).

"Customer Insights" gali apdoroti iki 10 milijonų atsiliepimų įrašų vienam vykdomam modeliui. Modelis gali analizuoti atsiliepimų komentarus iki 128 žodžių. Jei grįžtamojo ryšio komentaras yra ilgesnis, analizėje atsižvelgiama tik į pirmuosius 128 žodžius.

### <a name="data-requirements"></a>Duomenų reikalavimai
  
Reikalingi šie duomenų atributai:
- Vieningasis kliento ID (UCID), skirtas susieti tekstinių atsiliepimų duomenų įrašus su atskiru klientu. Šis ID yra duomenų suvienijimo [proceso](data-unification.md) rezultatas.
- Atsiliepimo ID
- Atsiliepimų laiko žyma
- Atsiliepimo tekstas   

> [!TIP]
> Nuotaikų analizei reikia jūsų klientų teksto atsiliepimų. Šiuo metu galima konfigūruoti tik vieną atsiliepimų objektą. Jei yra keli grįžtamojo ryšio objektai, galite juos sujungti prieš pradėdami Power Query duomenų įsisavinimą.

## <a name="configure-a-sentiment-analysis"></a>Nuotaikų analizės konfigūravimas 

1. Programoje „Customer Insights” eikite į **Įžvalga** > **Prognozės**.

1. Plytelėje **Kliento nuotaikų analizė** pasirinkite **Naudoti modelį**.

1. **Srityje Klientų nuotaikų analizė (peržiūra)** pasirinkite **Darbo pradžia**.

1. Atlikdami veiksmą Modelio pavadinimas pateikite **analizės pavadinimą**.**·** 

1. Pateikite verslo aspekto **išvesties objekto pavadinimą** ir nuotaikos balo išvesties objekto **pavadinimą**, tada pasirinkite **Pirmyn**.

1. Atlikdami veiksmą **Privalomieji duomenys** pasirinkite **Įtraukti duomenis**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Įtraukite duomenų srautą į nuotaikų analizės modelį.":::

1. **Srityje Įtraukti duomenis** iš sąrašo pasirinkite semantinį tipą **Atsiliepimai**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigūracijos veiksmas, skirtas pasirinkti atsiliepimų veiklą nuotaikų analizei.":::

1. Pasirinkite veiklas, kurias norite naudoti šiai nuotaikų analizei, tada pasirinkite **Pirmyn**.
 
1. Susiekite atributus savo duomenyse su modelio atributais. Pasirinkite **Išsaugoti**, kad pritaikytumėte savo pasirinkimus. 

1. Matote duomenų susiejimo būseną. Norėdami tęsti, spustelėkite **Pirmyn**. 

1. Atlikdami veiksmą **Peržiūrėti išsamią modelio informaciją**, patvirtinkite nuotaikų analizės konfigūraciją. Galite grįžti į bet kurią prognozė konfigūracijos dalį. Pasirinkite **Įrašyti ir paleiskite**, kad pradėtumėte analizę. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Nuotaikų modelio, kuriame rodomi visi sukonfigūruoti elementai, peržiūros veiksmas.":::

1. Pasirinkite **Atlikta**, kad paliktumėte konfigūravimo patirtį. Procesas gali užtrukti kelias valandas, atsižvelgiant į naudojamų duomenų kiekį. 

## <a name="review-analysis-status"></a>Peržiūros analizės būsena

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
- **Paskutinį kartą atnaujinta**: data, kada prognozė atnaujino rezultatus išvesties objekte.

## <a name="manage-sentiment-analysis"></a>Nuotaikų analizės valdymas

Galite optimizuoti, šalinti triktis, atnaujinti arba naikinti numatymus. Peržiūrėkite įvesties duomenų naudojimo ataskaitą ir sužinokite, kaip greičiau sukurti patikimesnę prognozę. Daugiau informacijos rasite [Prognozių valdymas](manage-predictions.md).

## <a name="review-analysis-results"></a>Peržiūrėkite analizės rezultatus
 
1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką. 
1. Pasirinkite prognozė, kurio rezultatus norite peržiūrėti, pavadinimą. Tokiu atveju pasirinkite nuotaikų analizę, kurią norite peržiūrėti. 

### <a name="summary-tab"></a>Skirtukas Suvestinė

Rezultatų puslapyje yra keturios pagrindinės duomenų dalys. 

- **Vidutinis nuotaikų balas**: padeda suprasti bendrą visų klientų nuotaiką. Nuotaikų balai sugrupuoti į tris kategorijas: 
  1.    Neigiamas (-5 > 2)
  2.    Neutralus (-1 > 1)
  3.    Teigiamas (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualinis bendrų klientų nuotaikų vaizdavimas.":::

- **Klientų pasiskirstymas pagal nuotaikų balą**: klientai skirstomi į neigiamas, neutralias ir teigiamas grupes pagal jų nuotaikų balus. Užveskite pelės žymeklį virš histogramos juostų, kad pamatytumėte klientų skaičių ir vidutinį nuotaikų balą kiekvienoje grupėje. Šie duomenys gali padėti [kurti klientų](segments.md) segmentus pagal jų nuotaikų balus.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Juostinė diagrama, rodanti klientų nuotaikas trijose nuotaikų grupėse.":::

- **Vidutinis nuotaikų balas laikui** bėgant: klientų nuotaikos laikui bėgant gali keistis. Mes teikiame jūsų klientų nuotaikų tendencijas pagal jūsų duomenų laiko intervalą. Šis rodinys gali padėti įvertinti sezoninių reklamų, produktų pristatymų ar kitų per nustatytą laiką atliekamų intervencijų poveikį klientų nuotaikoms. Peržiūrėkite diagramą išskleidžiamajame meniu pasirinkdami dominančius metus. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Istorijos diagrama, kurioje nuotaikų balas laikui bėgant pateikiamas kaip eilutė.":::
 
- **Nuotaikos tarp verslo aspektų**: šioje lentelėje pateikiamos vidutinės nuotaikos visuose verslo aspektuose. Tai gali padėti įvertinti, kurie jūsų verslo aspektai jau tenkina klientus ar aspektus, kuriems reikia daugiau dėmesio. Atsiliepimų įrašai, kurie nesutampa su jokiais palaikomais verslo aspektais, priskiriami kategorijai **Kita**. Pagal numatytuosius nustatymus lentelė yra surūšiuota abėcėlės tvarka. Rūšiavimą galite modifikuoti pasirinkdami lentelės antraštę.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Verslo aspektų sąrašas su susijusia sentimentų verte ir ją mininčių klientų skaičiumi.":::
 
  Pasirinkite verslo aspekto pavadinimą, kad pamatytumėte papildomą informaciją, kaip pagal modelį identifikuojamas verslo aspektas. Šioje srityje yra dvi dalys: 

  - **Įtakingi žodžiai**: rodo svarbiausius žodžius, kurie turėjo įtakos dirbtinio intelekto modelio verslo aspekto nustatymui klientų atsiliepimuose. 
    **Rodyti įžeidžiančius žodžius**: leidžia į sąrašą įtraukti įžeidžiančius žodžius iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas dirbtinio intelekto modeliu ir gali neaptikti visų įžeidžiančių žodžių. Mes tęsiame kartojimą ir treniruojame klasifikatorių, kad jis veiktų optimaliai. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruotas taip, kaip tikėtasi, praneškite mums. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Įtakingų žodžių sąrašas su perjungimu, kad būtų rodomi arba slepiami įžeidžiantys žodžiai.":::
 
  - **Atsiliepimų pavyzdžiai**: jūsų duomenyse rodomi faktiniai atsiliepimų įrašai. Žodžiai koduojami spalvomis pagal jų įtaką verslo aspekto identifikavimui. 


### <a name="influential-words-analysis-tab"></a>Įtakingas žodžių analizės skirtukas

Yra trys papildomos informacijos skyriai, paaiškinantys, kaip veikia nuotaikos modelis.
  
1. **Populiariausi žodžiai, prisidedantys prie teigiamų nuotaikų**: rodo svarbiausius žodžius, kurie turėjo įtakos dirbtinio intelekto modelio teigiamų nuotaikų nustatymui klientų atsiliepimuose.  
2. **Populiariausi žodžiai, prisidedantys prie neigiamų nuotaikų**: rodo svarbiausius žodžius, kurie turėjo įtakos dirbtinio intelekto modelio neigiamų nuotaikų nustatymui klientų atsiliepimuose.  
3. **Atsiliepimų pavyzdžiai**: rodomi faktiniai atsiliepimų įrašai, vienas su neigiamomis nuotaikomis ir teigiamas. Žodžiai atsiliepimų įrašuose paryškinami pagal jų indėlį į priskirtą nuotaikų balą. Žodžiai, prisidedantys prie teigiamo sentimentų balo, paryškinami žaliai. Žodžiai, prisidedantys prie neigiamo balo, paryškinami raudonai.
   Pasirinkite **Žiūrėti daugiau**, kad įkeltumėte daugiau atsiliepimų pavyzdžių, kuriuose pateikiama daugiau informacijos ir konteksto, kaip veikia nuotaikų modelis.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Klientų atsiliepimų nuotaikos analizės pavyzdžiai.":::
 
**Rodyti įžeidžiančius žodžius**: leidžia į sąrašą įtraukti įžeidžiančius žodžius iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas dirbtinio intelekto modeliu ir gali neaptikti visų įžeidžiančių žodžių. Mes tęsiame kartojimą ir treniruojame klasifikatorių, kad jis veiktų optimaliai. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruotas taip, kaip tikėtasi, praneškite mums. 

## <a name="act-on-analysis-results"></a>Analizės rezultatų aktas

Galite lengvai pradėti kurti naujus klientų segmentus nuotaikų analizės rezultatų puslapyje modelio **rezultatų puslapio viršuje pasirinkę Kurti segmentus**.

:::image type="content" source="media/create-segment-model.png" alt-text="Komandų juosta su parinktimis prognozė modeliuose.":::
 
## <a name="potential-bias"></a>Galimas šališkumas

Kaip ir naudojant bet kurią funkciją, kuri naudoja nuspėjamąjį dirbtinį intelektą, turėtumėte žinoti apie galimą duomenų, kuriuos naudojate klientų nuotaikoms prognozuoti, šališkumą. Pavyzdžiui, jei atsiliepimus renkate tik skaitmeniniu būdu, galite praleisti klientų, kurie pirmiausia vykdo verslą su jumis asmeniškai, atsiliepimų, o tai gali turėti įtakos funkcijos išvestims.

Kadangi ši funkcija naudoja automatizuotas priemones duomenims įvertinti ir prognozėms, pagrįstoms tais duomenimis, daryti, ji gali būti naudojama kaip profiliavimo metodas, nes šis terminas apibrėžtas Bendrajame duomenų apsaugos reglamente (toliau – BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingi už tai, kad užtikrintumėte, jog jūsų naudojimas, įskaitant nuotaikų Dynamics 365 Customer Insights analizę, atitiktų visus galiojančius įstatymus ir kitus teisės aktus, įskaitant įstatymus, susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir pranešimų konfidencialumu.

[!INCLUDE [footer-include](includes/footer-banner.md)]

