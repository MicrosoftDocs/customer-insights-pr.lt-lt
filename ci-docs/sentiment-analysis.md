---
title: Klientų atsiliepimų nuotaikų analizavimas (peržiūra)
description: Sužinokite, kaip naudoti nuotaikų analizės modelį klientų atsiliepimuose Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610476"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Klientų atsiliepimų nuotaikų analizavimas (peržiūra)

Nuotaikų analizė leidžia susintetinti klientų nuotaikas ir nustatyti verslo aspektus kaip tobulėjimo galimybes. Ši "Customer Insights" funkcija padeda suprasti, kas veikia gerai ir į ką reikia atkreipti dėmesį. Tai gali padėti jums paskatinti verslo veiksmus, kurie įgalina funkcijas, kurios užtikrina didelį klientų pasitenkinimą ir lojalumą.

## <a name="overview"></a>Apžvalga

Nuotaikų analizės funkcija generuoja dvi išvestines įžvalgas pagal kliento ID. Nuotaikų balas (nuo -5 iki 5) ir taikomų verslo aspektų (verslo sričių), kurie kartu padeda geriau suprasti klientų atsiliepimus, sąrašas.

Ši analizė padeda jums:
- Gaukite klientų nuotaikų prekės ženklui ar organizacijai apžvalgą
- Identifikuokite klientus, turinčius neigiamų nuotaikų, kad sutelktumėte kampanijas ir įtraukimus ir optimizuotumėte, kad gautumėte didesnę grąžą  
- Nustatykite verslo aspektus su klientų nurodytomis problemomis  
- Segmentuokite klientus pagal jų norą vykdyti suasmenintas kampanijas su tiksliniais pardavimais, rinkodara ir palaikymo pastangomis
- Optimizuokite verslo operacijas, spręsdami klientų paminėtas susirūpinimą keliančias ar galimybes
- Pripažinkite verslo aspektus, kuriems sekasi gerai, ir apdovanokite laimingus klientus per lojalumo ir skatinimo programas

Modelis pateikia žodžių, kurie turėjo įtakos modelio sprendimui priskirti tam tikrą nuotaikos balą arba verslo aspektą atsiliepimų komentarams, sąrašas.  

Mes naudojame du **natūralios kalbos apdorojimo (NLP) modelius**: pirmasis kiekvienam grįžtamojo ryšio komentarui priskiria sentimentų balą. Antrasis modelis susieja kiekvieną atsiliepimą su visais taikomais verslo aspektais. Modeliai mokomi pagal viešus duomenis iš šaltinių socialinėje žiniasklaidoje, mažmeninėje prekyboje, restoranuose, vartojimo produktuose ir automobilių pramonėje.
  
Iš anksto apibrėžti verslo aspektai, kuriuos modelis susieja su grįžtamojo ryšio duomenimis, yra šie:
- Klientų valdymas
- Pirkimo užbaigimas ir apmokėjimas
- Klientų aptarnavimas
- Paėmimas parduotuvėje
- Pakavimas, siuntimas ir gavimas
- Išankstinis užsakymas
- Kainos
- Privatumas ir sauga
- Akcijos ir apdovanojimai
- Kvitas ir garantijos
- Grąžinimas, keitimas ir atšaukimas
- Įvykdymo tikslumas
- Svetainės / programos kokybė

> [!NOTE]
> Šiuo metu mes palaikome tik anglų kalbos klientų atsiliepimų nuotaikų analizę. Ateityje bus palaikoma daugiau kalbų. Jei įkeliami atsiliepimai kitomis kalbomis, modelis vis tiek pateiks rezultatus. Tačiau šie rezultatai nebus tikslūs.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent jau [bendraautorių leidimai](permissions.md)
- [Vieningieji](data-unification.md) teksto atsiliepimų duomenys. Labai rekomenduojame [konfigūruoti atsiliepimų duomenų objektus kaip semantinio tipo veiklos objektus](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (atsiliepimų tipas).
- Vieningasis kliento ID (UCID) iš duomenų suvienijimo, siekiant suderinti teksto atsiliepimų duomenų įrašus su atskiru klientu.
- Atsiliepimo ID
- Atsiliepimų laiko žyma
- Atsiliepimo tekstas

"Customer Insights" gali apdoroti iki 10 milijonų atsiliepimų įrašų vienam vykdomam modeliui. Modelis gali analizuoti atsiliepimų komentarus iki 128 žodžių. Jei grįžtamojo ryšio komentaras yra ilgesnis, analizėje atsižvelgiama tik į pirmuosius 128 žodžius.

> [!NOTE]
> Galima sukonfigūruoti tik vieną atsiliepimų objektą. Jei yra keli grįžtamojo ryšio objektai, sujunkite juos Power Query prieš gaudami duomenis.

## <a name="configure-a-sentiment-analysis"></a>Nuotaikų analizės konfigūravimas

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį** plytelėje **Kliento nuotaikų analizė (peržiūra).**

1. Pasirinkite **Pradėti**.

1. **Pavadinkite** analizę ir pateikite verslo aspekto **išvesties objekto pavadinimą** bei nuotaikos balo **išvesties objekto pavadinimą**.

1. Pasirinkite **Toliau**.

1. Pasirinkite **Įtraukti duomenis**, kad gautumėte **klientų atsiliepimus**.

1. Pasirinkite semantinį veiklos tipą **Grįžtamasis ryšys**, kuriame yra atsiliepimų duomenys. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfigūracijos veiksmas, skirtas pasirinkti atsiliepimų veiklą nuotaikų analizei.":::

1. Pasirinkite veiklas, kurias norite naudoti šiai nuotaikų analizei, tada pasirinkite **Pirmyn**.

1. Susiekite atributus savo duomenyse su modelio atributais. 

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Toliau**. Veiksme **Peržiūra ir vykdymas** rodoma konfigūracijos suvestinė ir suteikiama galimybė atlikti keitimus prieš kuriant analizę.

1. Pasirinkite **Redaguoti** atlikdami bet kurį iš veiksmų, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte vykdyti modelį. Pasirinkite **Atlikta**. Skirtukas **Mano numatymai** rodomi, kol kuriamas prognozė. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Peržiūrėti analizės rezultatus

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Mano numatymai** pasirinkite prognozė, kurį norite peržiūrėti.

Yra du rezultatų skirtukai.

### <a name="sumary-tab"></a>Sumary skirtukas

Rezultatų puslapyje yra keturios pagrindinės duomenų dalys.

- **Vidutinis nuotaikų balas**: nuotaikų balai padeda suprasti bendrą visų klientų nuotaiką.
  - **Neigiamas** (-5 > 2)
  - **Neutralus** (-1 > 1)
  - **Teigiamas** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Vizualinis bendrų klientų nuotaikų vaizdavimas.":::

- **Klientų pasiskirstymas pagal nuotaikų balą**: klientai skirstomi į neigiamas, neutralias ir teigiamas grupes pagal jų nuotaikų balus. Užveskite pelės žymeklį virš histogramos juostų, kad pamatytumėte klientų skaičių ir vidutinį nuotaikų balą kiekvienoje grupėje. Šie duomenys gali padėti [kurti klientų](prediction-based-segment.md) segmentus pagal jų nuotaikų balus.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Juostinė diagrama, rodanti klientų nuotaikas trijose nuotaikų grupėse.":::

- **Vidutinis nuotaikų balas laikui** bėgant: klientų nuotaikos laikui bėgant gali keistis. Mes teikiame jūsų klientų nuotaikų tendencijas pagal jūsų duomenų laiko intervalą. Šis rodinys padeda įvertinti sezoninių reklamų, produktų pristatymo ar kitų per nustatytą laiką atliekamų intervencijų poveikį klientų nuotaikoms. Peržiūrėkite diagramą išskleidžiamajame meniu pasirinkdami dominančius metus.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Istorijos diagrama, kurioje nuotaikų balas laikui bėgant pateikiamas kaip eilutė.":::

- **Nuotaikos įvairiais verslo aspektais**: vidutinės nuotaikos visuose verslo aspektuose padeda įvertinti, kurie jūsų verslo aspektai jau tenkina klientus arba reikalauja daugiau dėmesio. Atsiliepimų įrašai, kurie nesutampa su jokiais palaikomais verslo aspektais, priskiriami kategorijai **Kita**. Rūšiuokite duomenis pasirinkdami bet kurį stulpelį.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Verslo aspektų sąrašas su susijusia sentimentų verte ir ją mininčių klientų skaičiumi.":::

  Pasirinkite verslo aspekto pavadinimą, kad pamatytumėte, kaip pagal modelį identifikuojamas verslo aspektas:

  - **Įtakingi žodžiai**: Svarbiausi žodžiai, kurie turėjo įtakos dirbtinio intelekto modelio verslo aspekto identifikavimui klientų atsiliepimuose.
    **Rodyti įžeidžiančius žodžius**: leidžia į sąrašą įtraukti įžeidžiančius žodžius iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas dirbtinio intelekto modeliu ir gali neaptikti visų įžeidžiančių žodžių. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruotas taip, kaip tikėtasi, praneškite mums.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Įtakingų žodžių sąrašas su perjungimu, kad būtų rodomi arba slepiami įžeidžiantys žodžiai.":::

  - **Atsiliepimų pavyzdžiai**: faktiniai atsiliepimų įrašai jūsų duomenyse. Žodžiai koduojami spalvomis pagal jų įtaką verslo aspekto identifikavimui.

### <a name="influential-words-analysis-tab"></a>Įtakingas žodžių analizės skirtukas

Yra trys papildomos informacijos skyriai, paaiškinantys, kaip veikia nuotaikos modelis.
  
- **Svarbiausi žodžiai, prisidedantys prie teigiamų nuotaikų**: svarbiausi žodžiai, kurie turėjo įtakos dirbtinio intelekto modelio teigiamų nuotaikų identifikavimui klientų atsiliepimuose.  

- **Svarbiausi žodžiai, prisidedantys prie neigiamų nuotaikų**: svarbiausi žodžiai, kurie turėjo įtakos dirbtinio intelekto modelio neigiamų nuotaikų identifikavimui klientų atsiliepimuose.

- **Atsiliepimų pavyzdžiai**: faktiniai atsiliepimų įrašai, vienas su neigiamomis nuotaikomis ir teigiamas nuotaikas. Žodžiai atsiliepimų įrašuose paryškinami pagal jų indėlį į priskirtą nuotaikų balą. Žodžiai, prisidedantys prie teigiamo sentimentų balo, paryškinami žaliai. Žodžiai, prisidedantys prie neigiamo balo, paryškinami raudonai.
   Pasirinkite **Žiūrėti daugiau**, kad įkeltumėte daugiau atsiliepimų pavyzdžių.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Klientų atsiliepimų nuotaikos analizės pavyzdžiai.":::

**Rodyti įžeidžiančius žodžius**: leidžia į sąrašą įtraukti įžeidžiančius žodžius iš pradinių klientų atsiliepimų duomenų. Pagal numatytuosius nustatymus jis išjungtas.  Įžeidžiantis žodžių maskavimas yra varomas dirbtinio intelekto modeliu ir gali neaptikti visų įžeidžiančių žodžių. Jei aptinkate įžeidžiantį žodį, kuris nebuvo filtruotas taip, kaip tikėtasi, praneškite mums.

## <a name="act-on-analysis-results"></a>Analizės rezultatų aktas

Norėdami kurti naujus klientų segmentus iš nuotaikų analizės rezultatų rezultatų rezultatų, modelio rezultatų puslapio viršuje pasirinkite **Kurti segmentus**.

## <a name="potential-bias"></a>Galimas šališkumas

Kaip ir naudojant bet kurią funkciją, kuri naudoja nuspėjamąjį dirbtinį intelektą, duomenys, kuriuos naudojate klientų nuotaikoms prognozuoti, gali būti šališki. Pavyzdžiui, jei atsiliepimus renkate tik skaitmeniniu būdu, galite praleisti klientų, kurie pirmiausia asmeniškai vykdo verslą su jumis, atsiliepimų, kurie turi įtakos funkcijos išvestims.

Kadangi ši funkcija naudoja automatizuotas priemones duomenims įvertinti ir prognozėms, pagrįstoms tais duomenimis, daryti, ji gali būti naudojama kaip profiliavimo metodas, nes šis terminas apibrėžtas Bendrajame duomenų apsaugos reglamente (toliau – BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingi už tai, kad užtikrintumėte, jog jūsų naudojimas, įskaitant nuotaikų Dynamics 365 Customer Insights analizę, atitiktų visus galiojančius įstatymus ir kitus teisės aktus, įskaitant įstatymus, susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir pranešimų konfidencialumu.

[!INCLUDE [footer-include](includes/footer-banner.md)]

