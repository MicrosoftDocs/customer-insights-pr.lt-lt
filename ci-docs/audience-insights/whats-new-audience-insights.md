---
title: Naujos ir būsimos funkcijos
description: Informacija apie naujas funkcijas, pagerinimus ir klaidų ištaisymus.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 2159481f9355de738a7b457dcf0849a45c3e08db
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896245"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kas naujo publikos įžvalgų „Dynamics 365 Customer Insights“ pajėgumuose

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Džiaugiamės galėdami pranešti apie mūsų naujausius atnaujinimus! Šiame straipsnyje apibendrinamos viešos peržiūros versijos funkcijos, bendro pasiekiamumo patobulinimai ir funkcijų atnaujinimai. Norėdami peržiūrėti ilgalaikius funkcijų planus, peržiūrėkite [„Dynamics 365“ ir „Power Platform“ išleidimo planai](/dynamics365/release-plans/).

Naujinimus atliekame pagal regionus. Taigi tam tikri regionai gali matyti funkcijas prieš kitus. Jei nenurodyta kitaip, jums nereikia imtis jokių veiksmų ir mes automatiškai atnaujinsime programą be prastovų.

> [!TIP]
> Norėdami teikti ir balsuoti už funkcijų užklausas bei produktų pasiūlymus, eikite į [„Dynamics 365“ programos idėjų portalą](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="march-2021-updates"></a>2021 m. kovo mėn. atnaujinimai

2021 m. kovo mėnesio atnaujinimai apima kelias funkcijas, efektyvumo atnaujinimus bei klaidų taisymus.

### <a name="activities"></a>Veiklos

- **Veiklos vedlys ir semantiniai tipai** Patobulinome ir atnaujinome savo veiklos žymėjimo patirtį, kad padėtume kurti veiklos žymėjimą ir jį supaprastintume. Šiame naujame procese naudotojai gauna interaktyviąją galimybę, kad galėtų atlikti kiekvieną proceso veiksmą. Atliekant veiklos žymėjimo veiksmą, be kelių veiklos tipų pasirinkimo naudotojas gali pasirinkti semantiškai žymėti duomenis *prenumeratai* ir (arba) *„SalesOrderLine“* pagal pramonės standarto schemas, kurias galima naudoti tolesniam vartojimui.    
  Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).

### <a name="data-ingestion"></a>Duomenų įsisavinimas

- **Prisijunkite prie vietinių duomenų šaltinių, naudodami Power Platform duomenų srautus ir tinklų sietuvus** Su malonumu pranešame apie Power Platform duomenų srautų ir vietinio jungiamumo naudojant tinklų sietuvus su „Customer Insights“ peržiūrą su siejama Power Platform arba Dataverse aplinka. Visi nauji duomenų šaltiniai, sukurti „Customer Insights“ su susieta Dataverse aplinka bus numatytieji Power Platform duomenų srautai, užtikrinantys vietinį duomenų ryšį ir išsamų jungčių bei transformavimo galimybių rinkinį.

### <a name="extensibility"></a>Išplėtimas

- **Eksportavimai, tvarkomi ryšiuose ir eksportavimuose** Pakeitėme puslapio **Eksportavimo paskirties vietos** pavadinimą į **Ryšiai** ir pridėjome atskirą puslapį **Eksportavimai**. Kaip šio naujinimo dalį pekelsime esamus eksportavimus į ryšio poras bei į eksportavimą, naudojant tą ryšį. Administratoriai dabar turi daugiau aiškumas dėl siunčiamų duomenų puslapyje **Ryšiai**. Visų vaidmenų naudotojai turi prieigą prie puslapio **Eksportavimai**, tačiau tik administratoriai gali rinktis bendradarbiams leisti redaguoti konkrečius eksportavimus su bendrai naudojamais ryšiais.     
  Daugiau informacijos žr. [Ryšių apžvalga](connections.md) ir [Eksportavimų apžvalga](export-destinations.md).

- **Segmentų eksportavimas į „Campaign Monitor“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „Campaign Monitor“. Dabar galite eksportuoti segmentus iš „Customer Insights“ į „Campaign Monitor“ sąrašus ir juos naudoti kaip jūsų rinkodaros kampanijų pagrindą.    
   Daugiau informacijos žr. [Eksportavimas į „Campaign Monitor“](export-campaign-monitor.md).

- **Segmentų eksportavimas į „Constant Contact“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „Constant Contact“. Dabar galite eksportuoti segmentus iš „Customer Insights“ į „Constant Contact“ sąrašus ir juos naudoti kaip jūsų rinkodaros kampanijų pagrindą.   
   Daugiau informacijos žr. [Eksportavimas į „Constant Contact“](export-constant-contact.md).

- **Segmentų eksportavimas į „RollWorks“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „RollWorks“. Dabar galite eksportuoti segmentus iš „Customer Insights“ į „RollWorks“ auditorijas ir juos naudoti kaip jūsų B2B reklamą.    
   Daugiau informacijos žr. [Eksportavimas į „RollWorks“](export-rollworks.md).

- **Segmentų eksportavimas į „Snapchat“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „Snapchat“. Dabar galite eksportuoti segmentus iš „Customer Insights“ į „Snapchat“ auditorijas ir juos naudoti kaip jūsų reklamą.     
   Daugiau informacijos žr. [Eksportavimas į „Snapchat“](export-snapchat.md).

### <a name="predictions"></a>Prognozės

- **Produktų filtrų naudojimas prognozuojamose produktų rekomendacijose** Pridėjome galimybę naudoti produktų filtrus mūsų produktų rekomendacijų modelyje. Dabar galite sukurti prognozę, kuri naudoja tik antrinius jūsų produktų rinkinius.    
   Daugiau informacijos žr. [Produktų filtrų konfigrūavimas](predict-product-recommendation.md#configure-product-filters).

- **Segmentų kūrimas iš modelių prognozių** Pridėjome greitą būdą segmentams kurit, naudojant prognozės modelio rezultatus. Modelio rezultatų puslapyje galima lengvai sukurti naują segmentą, pasirenkant naują parinktį **Kurti segmentą**.    
  Daugiau informacijos žr. [Segmento kūrimas pagal prognozės modelį](prediction-based-segment.md).

- **Produktų rekomendacijų paaiškinimai** Pridėjome informaciją, aiškinančią pagrindinius veiksnius, kuriuos išmoko AI modelis produktų rekomendacijoms generuoti ir tai, kiek šie faktoriai daro įtakos produktų rekomendacijoms. Ši informacija įtraukiama į modelio rezultatų ekraną.    
   Dėl išsamesnės informacijos, žr. [Peržiūrėti prognozės būseną ir rezultatus](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>2021 m. vasario atnaujinimai

2021 m. vasario naujinimuose yra kelios funkcijos, efektyvumo plėtotės ir klaidų taisymai.

#### <a name="extensibility"></a>Išplėtimas

- **Eksportuoti segmentus į „AdRoll”**

  Mes išplėtėme eksportavimo paskirties vietas įtraukdami „AdRoll”. Dabar galite eksportuoti segmentus iš „Customer Insights” į „AdRoll” auditorijas ir naudoti juos kaip reklamos bazinę liniją. Daugiau informacijos rasite [Jungtis, skirta „AdRoll“](export-adroll.md).

#### <a name="segments"></a>Segmentai
 
- **Dubliuoti segmentą**
  
  Norėdami sukurti naują segmentą remiantis esamu, dabar galite dubliuoti segmentą ir redaguoti dubliuojamą segmentą jo tolesniam patobulinimui. 

- **Įtraukti papildomus atributus į segmentą**

  Dabar galite įtraukti atributus į jūsų segmento išvestį, net jei šie atributai nėra kliento profilio dalis. Pavyzdžiui, įtraukite prenumeratos ID į segmentą, net jei jis yra dalis prenumeratos objekto, turinčio M:1 ryšį su kliento objektu. Tol, kol atributas priklauso su kliento objektu susijusiam objektui, galite įtraukti šiuos atributus.  

#### <a name="predictions"></a>Prognozės

- **Kurkite numatomas produkto rekomendacijas**

  Supratimas, ką klientai domisi pirkti, yra vienas iš pirmųjų žingsnių, reikalingų didinti verslo pajamoms didinti ir skatinti klientų lojalumui didinti naudojant personalizavimą ir įtraukimą. Pateikiant jūsų kliento interesų neatitinkančių produktų rekomendacijas gali atsirasti atotrūkio tarp kliento ir jūsų verslo jausmas ir dėl to galiausiai bus apribotos potencialios pajamos ir kliento patirtis. 

  Naudodami savo duomenis, dabar galite kurti prognozes, kokius produktus klientai, tikėtina, įsigys ateityje. Daugiau informacijos rasite [Produkto rekomendacijos prognozė](predict-product-recommendation.md).

#### <a name="system-administration"></a>Sistemos administravimas

- **Aplinkos kopijavimas palaiko daugiau duomenų šaltinių tipų**

  Administratoriai gali kopijuoti aplinkos konfigūracijas į naują aplinką toje pačioje organizacijoje. Ši funkcija išplečia aplinkos kopijavimo funkcijas tais atvejais, kai naudojami duomenų šaltiniai, pagrįsti „Common Data Service” duomenų telkiniu arba „Common Data Model” aplanku.

## <a name="january-2021-updates"></a>2021 m. sausio mėn. naujinimai

2021 m. sausio naujinimuose yra kelios funkcijos, efektyvumo naujiniai ir klaidų taisymai.

#### <a name="extensibility"></a>Išplėtimas

- **Išplėstinės funkcijos ir didesnis SFPP eksportavimo efektyvumas** Dabar galite eksportuoti visus išvesties objektus iš „Customer Insights” į SFPP pagrindinį kompiuterį. Anksčiau buvo eksportuojama tik į segmento objektus. Be to, SFTP eksportavimo efektyvumas leidžia daugiau duomenų apimties per mažiau laiko, tai priklauso nuo jūsų SFTP pagrindinio kompiuterio efektyvumo.    
  Daugiau informacijos žr. [SFTP jungtis (peržiūra)](export-sftp.md).  

#### <a name="segments"></a>Segmentai

- **Mašininis mokymas siūlomus segmentus metrikos tobulinimui** – naujas būdas atrasti ir kurti segmentus. Sistema naudoja AI modelį, kad galėtų pasiūlyti segmentų, kurie gali padėti tobulinti KPI (priemonę), kurią jau stebite. Rodome atributų, kuriuos pažymite priemonei ar kitam pirminiam atributui, įtaką. Ši informacija padeda rasti potencialių segmentų, kurie pateikia galimybes.    
  Daugiau informacijos žr. [Siūlomi segmentai (peržiūra)](suggested-segments.md).

#### <a name="data-unification"></a>Duomenų susijungimas

- **Patobulintas gretinimas duomenų** suvienodinimo srityje gretinimas buvo atnaujintas. Ji leidžia konfigūruoti ir peržiūrėti gretinimo taisykles, įskaitant išsamią statistiką, kurioje išsamiau paaiškinta, kaip veikia gretinimas. Yra parinkčių, kaip išjungti atitikties taisyklę, kad išsamus konfigūraciją ji nebeaktyvūs, nuvilktumėte ir numestumėte atitikties taisykles bei kt.
  Dėl daugiau informacijos, žr. [Atitikti objektus](match-entities.md).

- **Gretinimo proceso dublikatų naikinimo išvestį galima naudoti kaip objekto** dublikatų naikinimo proceso išvestį iš gretinimo proceso, kad būtų galima tolesnei analizei atlikti. Šį objektą sudaro papildomo dublikavimo procese naudojami laukai ir laimėtojui skirtas įrašas bei atitinkami pakaitiniai įrašai, kurie suliejami su laimėto asmens įrašu.
  Dėl daugiau informacijos žr. [Papildomo dublikavimo išvestį kaip objektą](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Sistemos administravimas

- **Sklandžiai bendrinkite duomenis su „Microsoft Dataverse“** „Customer Insights” rezultatais su programomis „Microsoft Dataverse“ naudodami „Microsoft Dataverse“ sutvarkyto „Data Lake” funkciją. Susieję aplinką „Dataverse“ su „Customer Insights”, galėsite įjungti duomenų bendrinimą.
  Daugiau informacijos žr. [Aplinkų valdymas](manage-environments.md).


## <a name="december-2020-updates"></a>2020 m. gruodžio mėn. naujinimai

2020 m. gruodžio naujinimuose yra kelios funkcijos, efektyvumo naujiniai ir klaidų taisymai.

### <a name="new-and-updated-features-in-december-2020"></a>Naujos ir atnaujintos funkcijos 2020 m. gruodžio mėn.

#### <a name="data-enrichment"></a>Duomenų papildymas

- **Patobulintas prekės ženklo ir susidomėjimo įtraukimas**
  
  Supaprastinome savo bendrų klientų balus, kad jie būtų lengviau suprantami ir naudojami. Dabar galite greitai identifikuoti klientus pagal jų turimą tam tikrą prekės ženklą ar susidomėjimą.

  Be to, įtraukėme naujų konfigūravimo parinkčių, kurios geriau kontroliuoja, kaip norite papildyti klientų profilius. 

  Daugiau informacijos žr. [Klientų profilių papildymas prekių ženklų ir pomėgių panašumais](enrichment-microsoft.md).

- **Valdykite, kuriuos profilius reikia papildyti**

  Dabar galima papildyti tik savo klientų profilių antrinį rinkinį su parinktimi pasirinkti segmento objektą, o ne numatytąjį kliento objektą. Sukurkite segmentą su klientų profiliais, kuriuos norite praturtinti ir pažymėti savo klientų duomenų rinkinio praturtinimo konfigūracijoje.
  Šią funkciją šiuo metu galima naudoti tik „Experian” ir „HERE Technologies” praturtinimus. Greitai leisime šiam pajėgumui labiau papildyti.

  Daugiau informacijos rasite [Klientų profilių papildymas demografais iš „Experian“](enrichment-experian.md)[klientų profilio turtinimai su „HERE Technologies“](enrichment-here.md).

#### <a name="extensibility"></a>Išplėtimas

- **Suaktyvinkite segmentus naudodami automatinį pilotą**

  Eksportuokite segmentus į autopilotą ir naudokite juos rinkodaros tikslais. Daugiau informacijos žr. [Jungtis autopilotui (peržiūra)](export-autopilot.md).

- **Suaktyvinkite segmentus naudodami „SendGrid“**

  Eksportuokite segmentus į „SendGrid“ ir naudokite juos rinkodaros tikslais. Daugiau informacijos žr. [Jungtis „SendGrid“](export-sendgrid.md).

#### <a name="system-administration"></a>Sistemos administravimas

- **Atnaujintos aplinkos valdymo funkcijos**
  
  Dabar galite kurti, redaguoti, panaikinti ir iš naujo nustatyti aplinkas tiesiai iš programos antraštės aplinkos parinkiklio. 
  
  Be to, aplinka, kurią naudojate, bus prisegta prie aplinkos skydo viršuje, kad jums nebereikės jo ieškoti.

  Daugiau informacijos žr. [Aplinkų valdymas](manage-environments.md).

## <a name="november-2020-updates"></a>2020 m. lapkričio mėn. naujinimai

2020 m. lapkričio mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-november-2020"></a>Naujos ir atnaujintos funkcijos 2020 m. lapkričio mėn.

#### <a name="data-enrichment"></a>Duomenų papildymas

- **Talpinkite jūsų turimus praturtintus duomenis per „Secure File Transfer Protocol“ (SFTP) tinkintą importavimą**
  
  SFTP tinkinimas leidžia jums importuoti praturtintus duomenis, kurie neturi vykti duomenų suvienodinimo procese. Sužinokite daugiau apie SFTP tinkintą importavimą.

  Dėl išsamesnės informacijos, žr. [Praturtinti tinkinti profiliai su tinkintais duomenimis (peržiūra)](enrichment-SFTP-custom-import.md).
 
- **Praturtinkite savo tinkintus duomenis su vietos duomenimis iš „HERE Technologies“**

  Su „HERE Technologies“ duomenų praturtinimo paslaugomis galite sukurti tikslesnį supratimą apie jūsų klientų vietą su adreso normalizavimu, pločio ir ilgio išplėtimu ir daugiau. Sužinokite daugiau apie praturtinimą su „HERE Technologies“.

  Dėl išsamesnės informacijos, žr. [Tinkintų profilių praturtinimas su „HERE Technologies“](enrichment-here.md).

#### <a name="data-unification"></a>Duomenų susijungimas

- **Lankstumas skirtas įjungti duomenų profiliavimą pasirinktuose objektuose ir laukeliuose iš jūsų talpinimo paskyros**

  Galite nurodyti, kurie duomenų objektai ir laukeliai bus įjungti iš „Common Data Model“ katalogo jūsų „Azure Data Lake Storage“ paskyrą siekiant įjungti duomenų profiliavimą kaip duomenų suvartojimo proceso dalį.

  Dėl išsamesnės informacijos, žr. [Sujungti su „Common Data Model“ katalogu](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Išplėtimas

- **Aktyvuoti jūsų segmentus per „Google Ads“**

  Eksportuoti segmentus iš „Google Ads“ publikos sąrašų ir naudoti šiuos sąrašus reklamavimui „Google Search“, „Google Display Network“, „YouTube“ ir „Gmail“. Sužinokite daugiau apie jūsų segmentų įjungimą per „Google Ads“.

  Dėl daugiau informacijos, žr. [Jungtis „Google Ads“](export-google-ads.md).

- **Aktyvuoti jūsų segmentus per „Marketo““**

  Eksportuoti segmentus į „Marketo“ publikas ir naudoti šias publikas automatizavimo reklamavimui. Sužinokite daugiau apie jūsų segmentų įjungimą per „Marketo“. 

  Dėl daugiau informacijos, žr. [Jungtis „Marketo“](export-marketo.md).

- **Aktyvuoti jūsų segmentus per „DotDigital“**

  Eksportuoti segmentus į „DotDigital“ naudoti juos reklamavimo tikslais. Sužinokite daugiau apie jūsų segmentų įjungimą per „DotDigital“. 

  Dėl daugiau informacijos, žr. [Jungtis „DotDigital“](export-dotdigital.md).

#### <a name="predictions"></a>Prognozės

- **Nuspėti perdavimo maišytuvą**

  Perdavimo nutraukimo nuspėjimo funkcija jus įjungia be duomenų mokslininko pagalbos tam, kad nuspėtumėte, kada klientas tikėtinai nebepirks produktų ir paslaugų.  Naudodami nuspėjimo balą galite suderinti kitą informaciją apie savo klientus, tokią kaip kliento vertė tam, kad sukurtumėte didelio nutraukimo rizikos ir didelės vertės klientų segmentus. Naudokite šį segmentą tam, kad tiesiogiai dirbtumėte su klientais per publikavimo veiklas, klientų pagalbai ir kitų scenarijų metu sumažinant nutraukimo riziką.
 
  Konfigūruokite nutraukimo sąvoką kaip laiku pagrįstą langą būdingą jūsų verslui ir nustatykite, kada klientai yra laikomi prarastais. Pavyzdžiui, produktų parduotuvė gali galvoti apie nebeperkantį klientą, jei jis nieko nepirko paskutines 30 dienų.
 
  Jums tęsiant nuspėjimo sukūrimą, mes jus instruktuosime, kokių duomenų reikia ir jus įgalinsime sukurti duomenų žemėlapį apie jūsų verslą būtiniems laukeliams tam, kad nuspėtumėte nutrauksiančius klientus. Galite taip pat nustatyti tvarkaraštį tam, kad talpintumėte modeliu pagrįstą naują informaciją savo sistemoje ir pritaikytumėte ją prie besikeičiančių verslo aplinkybių.
 
  Dėl išsamesnės informacijos, žr. [Perdavimo nutraukimo nuspėjimas (peržiūra)](predict-transactional-churn.md).D

#### <a name="system-administration"></a>Sistemos administravimas

- **Nustatyti aplinką iš naujo**

  Iš naujo paleisti viską pasirinkto elemento aplinkoje tam, kad pradėtumėte iš naujo.

  Dėl išsamesnės informacijos, žr. [Esančios aplinkos paleidimas iš naujo](manage-environments.md#reset-an-existing-environment).


- **Prisijunkite prie savo „Azure Data Lake Storage“ paskyros naudodami paslaugų pagrindinį elementą**

  Įrašyti duomenų išvestį ir perskaityti duomenis iš jūsų talpinimo paskyros naudojant „Azure“ pagrindines paslaugas. Esamos paskyros talpinimo jungtys gali ir toliau naudoti paskyros raktą. Jos taip pat siūlo pagerinimo parinktį tam, kad naudotų pagrindines paslaugas einant toliau. Naujos jungtys bus pagrįstos pagrindinio autentifikavimo metodo paslaugomis jūsų talpinimo paskyrai.

  Dėl daugiau informacijos, žr. [Sujungti su „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).

## <a name="october-2020-updates"></a>2020 m. spalio mėn. naujinimai

2020 m. spalio mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-october-2020"></a>Naujos ir atnaujintos funkcijos 2020 m. spalio mėn.

#### <a name="extensibility"></a>Išplėtimas

- **Eksportuoti į „Mailchimp“**

Eksportuoti segmentus į esančius publikos sąrašus „Mailchimp“ siekiant pateikti suasmenintą el. pašto patirtį savo klientams.

Dėl daugiau informacijos, žr. [Jungtis „Mailchimp“](export-mailchimp.md).

#### <a name="data-enrichment"></a>Duomenų papildymas

- **Panaikinti dublikavimą šaltinio įrašuose atitikties objekte**

Nurodyti dublikavimo panaikinimo taisykles objektuose, kurie naudojami suderinti procesą siekiant atpažinti dublikavimo įrašus. Sulieti juos į vieną įrašą ir susieti visus šaltinio įrašus į šį sulietą įrašą. Šis dublikavimo panaikinimo įrašas tuomet bus naudojamas kryžminiame objekto atitikties procese.

Dėl daugiau informacijos, žr. [Nustatyti dublikavimo panaikinimą atitikties objekte](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Sistemos administravimas

- **Organizavimas: Nauja atnaujinimo parinktis Suliejime**

Iki šiandien jums vykdant suliejimo procesą sistema vykdė visą procesą pasroviui, kuris priklausė nuo suliejimo ir tolesnių procesų. Dabar galite patikrinti suliejimo proceso išvestį (suvienodintą kliento objektą) prieš naudodami jį procese pasroviui, tokiame kaip segmentai ar priemonės.
Suliejimo puslapyje dabar galite pasirinkti vykdyti tik suliejimo žingsnį ir vykdyti tik šį procesą. Norėdami atnaujinti procesus pasroviui, galite pasirinkti vykdyti suliejimą ir procesus pasroviui. 

## <a name="september-2020-updates"></a>2020 m. rugsėjo mėn. naujinimai

2020 m. rugsėjo mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-september-2020"></a>2020 m. rugsėjo mėn. naujos ir atnaujintos funkcijos

#### <a name="activities"></a>Veiklos

- **Atributo semantikos intelektualioji prognozė**

Ši nauja funkcija prognozuoja įvesties atributų, perduodamų į duomenų sujungimo procesą, semantinius tipus. Ji naudoja mašininio mokymo modelis, kurie pagerina tikslumą ir taupo laiką.

#### <a name="enrichments"></a>Papildymai

- **Demografijos papildymas iš „Experian“**

Demografijos papildymas iš „Experian“ dabar pasiekiamas peržiūros versijoje. „Experian“ yra pasaulinis vartotojų ir verslo kreditų ataskaitų bei rinkodaros paslaugų lyderis. Naudodami [„Experian” duomenų papildymo paslaugas](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), galite geriau suprasti savo klientus, papildydami savo klientų profilius tokiais demografiniais duomenimis kaip namų ūkių dydis, pajamos ir kt.

Norėdami naudoti šią funkciją, turite turėti aktyvią „Experian” prenumeratą.

Daugiau informacijos žr. [Klientų profilių papildymas demografiniais duomenimis iš „Experian”](enrichment-experian.md)


#### <a name="system-administration"></a>Sistemos administravimas

- **Užduoties išsamios informacijos sritis**

Užduoties išsamios informacijos sritis leidžia peržiūrėti išsamią informaciją apie sistemos vykdomas užduotis. Tai patogus būdas nustatyti su konfigūracijomis susijusias klaidas ir rasti sprendimus.
Klaidų pranešimų peržiūra siekiant pamatyti, kaip sprendžiate galimas problemas.
 
- **Į daugiau puslapių įtrauktos informacijos tvarkymas**

Šiuo patobulinimu įtraukiama informacija apie objektų būseną puslapiuose **Objektai** ir **Klientai**.
 
Be to, šiuose abiejuose puslapiuose galite rasti išsamią informaciją apie procesų eigą bei išsamią užduoties informaciją.

- **Sistemos būsenos puslapio patobulinimai**

Peržiūrėdami duomenų eksportavimą patobulinome būsenos išsamios informacijos lentelės struktūrą dalyje **Sistema** > **Būsena**.
 
Be to, klaidos stulpelyje **Išsami informacija** dabar pateikiamos išsamiau ir su jomis galima atlikti veiksmų. 
 
- **Užduoties grąžinimo į ankstesnę būseną atšaukimas**

Atšaukus užduotį, pvz., gretinimo proceso metu, ji bus grąžinta į savo naujausią būseną. Pavyzdžiui, jei gretinimo procesas buvo užbaigtas vakar, o šiandien jį atšauksite, jis bus grąžintas į vakarykščią sėkmingai užbaigtą būseną.


## <a name="august-2020-updates"></a>2020 m. rugpjūčio mėn. naujinimai

2020 m. rugsėjo mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-august-2020"></a>2020 m. rugpjūčio mėn. naujos ir atnaujintos funkcijos

#### <a name="data-unification"></a>Duomenų susijungimas

- **Pagerinta susiejimo etapo duomenų sujungimo metu patirtis**

  Patirtis, skirta susieti etapą duomenų sujungimo proceso metu, leidžia jums sklandžiau pasirinkti objektus, atributus ir apibrėžti semantiką.

  Pakeitimai apima:
  
  - mažiau reikiamų sąveikų, įtraukiant objektus ir laukus
  - patobulintos ieškos galimybės struktūros puslapyje
  - siūlomo lauko tipo vaizdinis elementas ir lengvas identifikavimas

#### <a name="enrichment"></a>Papildymas

- **Susidomėjimo panašumų pratinimas daugiau rinkoms**

  Išplečiame pasiekiamumą nuo susidomėjimo galimybių papildymo ne tik Jungtinėse Valstijose, bet ir penkiose kitose rinkose: Kanados, Australijos, Didžiosios Britanijos, Prancūzijos ir Vokietijos. Naudodami šį plėtinį galite papildyti savo klientų duomenis taip, kad jie labiau domina šias rinkas. Taip pat papildysime jūsų kliento profilius, esančius šiose rinkose, naudodami vietos nuosavybės teise saugomus duomenis iš „Microsoft“.
  Daugiau informacijos žr. [Klientų profilių papildymas prekių ženklų ir pomėgių panašumais](enrichment-microsoft.md)


## <a name="july-2020-updates"></a>2020 m. liepos mėn. naujinimai

2020 m. liepos mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-july-2020"></a>2020 m. liepos mėn. naujos ir atnaujintos funkcijos

#### <a name="extensibility"></a>Išplėtimas

- **„Power Automate“ baigto sujungimo proceso paleidiklis**

  Išplėtėme „Power Automate“ paleidiklius, kurie leidžia kurti pranešimą arba veiksmą, kai baigiamas sujungimo proceso (susiejimas, sutapdinimas, suliejimas) atnaujinimas.    
  Daugiau informacijos žr. [„Power Automate“ jungtis](export-power-automate.md)

#### <a name="enrichment"></a>Papildymas

- **Prekės ženklo panašumų pratinimas daugiau rinkoms**

  Išplečiame pasiekiamumą nuo prekės ženklo galimybių papildymo ne tik Jungtinėse Valstijose, bet ir penkiose kitose rinkose: Kanados, Australijos, Didžiosios Britanijos, Prancūzijos ir Vokietijos. Naudodami šį plėtinį klientų duomenis galėsite papildyti šių rinkų vietiniais prekių ženklais. Taip pat papildysime jūsų kliento profilius, esančius šiose rinkose, naudodami vietos nuosavybės teise saugomus duomenis iš „Microsoft“.
  Daugiau informacijos žr. [Klientų profilių papildymas prekių ženklų ir pomėgių panašumais](enrichment-microsoft.md)

## <a name="june-2020-updates"></a>2020 m. birželio mėn. naujinimai

2020 m. birželio mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-june-2020"></a>2020 m. birželio mėn. naujos ir atnaujintos funkcijos

#### <a name="enrichment"></a>Papildymas

- **Papildymas įmonės duomenimis iš „Leadspace“**
  
  Nustatykite laukus sujungtuose klientų profiliuose, kurie naudojami norint ieškoti susijusių įmonės duomenų iš „Leadspace“. Atlikus pratinimo procesą, B2B profiliai praturtinti daugiau atributų, įskaitant įmonės dydį, vietą, pramonės šaką ir kt.    
  Šis bendradarbiavimas suteikia galimybę pagerinti jūsų duomenų kokybę naudojant trečiųjų šalių paslaugų duomenis. Norint naudoti šį papildymą reikės „Leadspace“ licencijos, kad galėtumėte naudotis jo B2B įmonių duomenimis. Sistema naudoti šią licenciją tam, kad palaikytų jūsų duomenis nuolat praturtintus.    
  Daugiau informacijos žr. [Įmonių profilių papildymas su „Leadspace“](enrichment-leadspace.md).

- **Papildymo telkinio puslapis**

  Visas galimas duomenų papildymas iš pirmosios ir trečiosios šalies papildymo teikėjų konfigūruojamas toje pačioje vietoje. Duomenų papildymo konfigūravimas yra sklandus procesas, valdomas bendroje vietoje.    
  Daugiau informacijos žr. [Klientų profilių papildymas](enrichment-hub.md).

- **Atskirų prekių ženklų ir pomėgių panašumų papildymas**

  Prekių ženklų ir pomėgių panašumai dabar pasiekiami kaip du nepriklausomi papildymai. Atskiri papildymai leidžia juos atskirai konfigūruoti ir valdyti atsižvelgiant į jūsų verslo reikalavimus ar poreikius.    
  Daugiau informacijos žr. [Klientų profilių papildymas prekių ženklų ir pomėgių panašumais](enrichment-microsoft.md).

#### <a name="extensibility"></a>Išplėtimas

- **Sujungtų veiklų galimi spustelėti URL „Dynamics 365“ kliento kortelės papildinyje**

  Suvienodintos veiklos kliento kortelės priede dabar yra rodomos paspaudus URL, jei šie URL buvo nustatyti veiklų konfigūravimo metu.    
  Norėdami gauti daugiau informacijos, žr. [klientų kortelės priedą](customer-card-add-in.md).

- **„Dynamics 365“ kliento kortelės papildinyje pasiekiami prekių ženklų ir pomėgių panašumai**

  Naujas „Dynamics 365“ kliento kortelės papildinio valdiklis leidžia rodyti prekių ženklų ir pomėgių papildymus kontaktuose klientų įtraukimo programose „Dynamics 365“.    
  Norėdami gauti daugiau informacijos, žr. [klientų kortelės priedą](customer-card-add-in.md).

- **Daugiau „Power Automate“ paleidiklių**

  Išplėtėme „Power Automate“ paleidiklius ir įtraukėme toliau nurodytus paleidiklius.
  - Gauti pranešimą arba atlikti veiksmą, kai baigiamas automatinis visiškas atnaujinimas (duomenų šaltiniai, sujungimas, segmentai, priemonės, eksportas)
  - Verslo priemonės ribinės vertės nustatymas. Pavyzdžiui, galite sukurti pranešimą, kuris bus išsiųstas, kai nustatyta ribinė vertė praeis. Be to, paleidiklis teikia informaciją, leidžiančią kurti sudėtingesnes darbo eigas „Power Automate“.    
  Daugiau informacijos žr. [„Power Automate“ jungtis](export-power-automate.md)

- **Eksportavimas į „Facebook“ reklamos tvarkytuvą**
  
  Šis pajėgumas leidžia jums eksportuoti segmentus į „Facebook“ priedų tvarkytuvą. Segmentai yra eksportuojami kaip tinkintos publikos siekiant naudoti suvienodintus kliento profilius „Facebook“ reklamų kampanijose ir prieduose. Pasirinktines auditorijas taip pat galima naudoti kuriant „Instagram“ kampanijas naudojant „Facebook“ reklamos tvarkytuvą.    
  Daugiau informacijos žr. [„Facebook“ reklamos tvarkytuvo jungtis](export-facebook.md).

#### <a name="predictions"></a>Prognozės

- **Prenumeratos praradimo prognozė**

  Vadovaukitės teikiamais nurodymais ir sukurkite prenumeratos sričių, pavyzdžiui, debesies paslaugų, klientų narystės ir kitų sektorių, praradimo prognozę. 

  Prenumeratos praradimo prognozės funkcija leidžia prognozuoti tikimybę, kad klientas nustos naudoti prenumerata pagrįstus produktus ar paslaugas, nedalyvaujant duomenų mokslininkui. Naudodami prognozė balą, galite sujungti kitą informaciją apie klientus, kad sukurtumėte didelės praradimo rizikos segmentus. Su šiuo segmentu galite tiesiogiai dirbti su klientais reklamuojant, jiems padedant ir kitais scenarijais siekiant sumažinti konkrečių klientų atsisakymo riziką siekiant pagerinti pelną ir sumažinti išlaidas.

  Naudodami šią funkciją galite sukonfigūruoti praradimo, kaip konkretaus jūsų verslo laiku pagrįsto lango, apibrėžtį. Pavyzdžiui, vaizdo įrašų transliacijos verslas, kuriame yra mėnesinės prenumeratos procesas, gali klientą laikyti prarastu praėjus 15 dienų nuo jo prenumeratos pasibaigimo.

  Tęsiant prognozę pateiksime nurodymus dėl reikalingų duomenų ir leisime duomenis apie jūsų verslą susieti su laukais, reikalingais norint prognozuoti klientų praradimą. Keičiantis verslo informacijai sistemoje taip pat galite nustatyti mokymo iš naujo pagal naują informaciją grafiką, kad pritaikytumėte sistemą prie besikeičiančių verslo aplinkybių.    
  Daugiau informacijos žr. [Prenumeratos praradimo prognozė (peržiūros versija)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentai

- **Rasti panašių klientų**
  
  Raskite panašių klientų savo klientų bazėje naudodami dirbtinį intelektą. Dvejetainio klasifikavimo mašininio mokymo modelis priskiria panašumo balą klientams išplėstame segmente. Įvertis grindžiamas panašumu į klientus šaltinio segmente. Atsižvelgiant į panašumo balą klientų profiliai įtraukiami į naujai sukurtą segmentą.

  Kartais tai yra panašus į išvaizdą modeliavimas naudojant skaitmeninę rinkodarą, jis naudoja AI modelį, kad padėtų rasti klientų, kurie yra panašūs į kitą jūsų klientų segmentą, sudėdamas daugiau atributų. Ji ne tik leidžia pasirinkti atributus, bet ir leidžia nurodyti maksimalų klientų, kurie turėtų būti šiame naujame segmente, skaičių. Tada DI modelis apskaičiuos kiekvieno kliento panašumo balus pagal pasirinktus atributus ir suras klientus su didesniu vidutiniu panašumo balu. Gautas segmentas apims klientus, panašius į klientus, esančius pradiniame segmente.    
  Daugiau informacijos žr. [Panašūs klientai](find-similar-customer-segments.md).

- **Segmentų persidengimas ir diferenciatoriai**

  Segmentų persidengimas leidžia matyti, kiek ir kurie klientai yra bendri dviejuose ar daugiau segmentų. Pvz., kaip daug išleidžiančių klientų segmentas persidengia su didelio pasitenkinimo klientų segmentų arba kaip prarandamų klientų segmentas persidengia su mažo pasitenkinimo klientų segmentu. Be to, galite analizuoti, kaip persidengia pokyčiai pagal papildomą jūsų pasirinkimą atributą.

  Segmentų diferenciatoriai nurodo, kuo vienas segmentas skiriasi nuo likusių klientų arba nuo kito segmento. Viskas, ką jums reikia padaryti – nustatyti segmentą, o sistema nustatys profilio atributus ir priemones, kurios išskiria segmentus pagal klasifikuotą diferenciatorių sąrašą – nuo stipriausio iki silpniausio.    
  Daugiau informacijos žr. [Segmentų įžvalgos (peržiūros versija)](segment-insights.md)

- **Segmento egzistavimo laikotarpis**
  
  Nustatykite segmento aktyvinimo arba išjungimo grafiką.    
  Daugiau informacijos žr. [Esamų segmentų valdymas](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>2020 m. gegužės mėn. naujinimai

2020 m. gegužės mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-may-2020"></a>Naujos ir atnaujintos funkcijos 2020 m. gegužės mėn.

#### <a name="data-ingestion"></a>Duomenų įsisavinimas

- **Duomenų įsisavinimas realiuoju laiku: retrospektyvos rodiniai**

  Kai naudojate mūsų API, kad galėtumėte atnaujinti realiuoju laiku, galite matyti agreguotą istoriją iki 30 dienų nuo šio naujinimo. Turite prieigą prie visų sėkmingų arba nepavykusių API skambučių agregatų, įskaitant jų rezultatus, šaltinio sistemą ir kitus naudingus metaduomenis.    
  Daugiau informacijos žr. [Duomenų įtraukimas realiuoju laiku](real-time-data-ingestion.md).

- **Duomenų įsisavinimas realiuoju laiku: profilio naujinimai**

  Šis duomenų įsisavinimo realiuoju laiku išplėtimas leidžia matyti per kelias sekundes tam tikro vartotojo profilio laukų pakeitimus.    
  Kartu su realaus laiko funkcijomis veikloms, sistema palaiko mažos delsos naujinimo profilio laukeliams. Profilio laukų realiojo laiko naujinimai turi galiojimo laiką, todėl jie nekeičiami planuojamiems naujinimams.    
  Daugiau informacijos žr. [Duomenų įtraukimas realiuoju laiku](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Išplėtimas

- **Atnaujinta laiko planavimo juosta kliento kortelės priede**

  Kliento kortelės priedų sprendimas atitinka aktyvumo laiko juostos juostą. Laiko planavimo juostos numeracija pagerinta, rodoma iki 50 veiklos vienu metu. Ji taip pat leidžia į laiko planavimo juostą įkelti daugiau veiklų.    
  Norėdami gauti daugiau informacijos, žr. [klientų kortelės priedą](customer-card-add-in.md).

- **„Power Automate“ segmento pakeitimų paleidiklis**

  Paleidikliai, skirti „Power Automate“, apibrėžia, iš ko galite kurti srautą. Naujai įtrauktas paleidiklis leidžia apibrėžti segmento ribinę vertę. Pavyzdžiui, galite sukurti pranešimą, kuris bus išsiųstas, kai nustatyta ribinė vertė praeis.    
  Išsamesnės informacijos žr. [„Power Automate“ jungtyje](export-power-automate.md).

- **Kelių nuomotojų pasirinktinių modelių palaikymas**

  Sukonfigūruokite pasirinktinių modelių darbo eigas su skirtingų „Azure“ mašininio mokymo nuomotojo žiniatinklio tarnyba. Galite prisijungti prie „Azure Machine Learning“ nuomotojo kuriant naujas darbo eigas tinkintiems modeliams. Ši galimybė papildo esamą galimybę integruoti į savo pasirinktinę „Azure“ mašininio mokymo žiniatinklio tarnybą.    
  Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).

#### <a name="segments"></a>Segmentai

- **Objektų kelio automatizavimas**

  Kuriant segmentą vartotojai turi nustatyti objekto kelią. Šis pajėgumas atliekamas pirmiausia automatizuojant objekto kelio apibrėžimą, kad galėtumėte susitelkti ties segmentavimo kriterijais, kuriuos turite omenyje.    
  Jei objektas, pagal kurį norite segmentuoti klientus, yra tiesiogiai susijęs su vieningu kliento objektu, nebereikės apibrėžti objekto kelio. Tačiau jei yra daugiau nei vienas galimas objekto kelias, vis tiek turėsite jį apibrėžti rankiniu būdu.

- **Veiksmai su keliais segmentais**
  
  Vartotojai gali pažymėti kelis segmentus ir imtis veiksmų su jais, pvz., atnaujinti segmentus vienu spustelėjimu.    

- **Segmentų atnaujinimas**

  Vartotojai gali atnaujinti vieną segmentą arba pažymėti tik norimus atnaujinti segmentus.    

  
- **Sudėtinių segmentų patobulinimai**

  Vartotojai gali kurti, redaguoti ir naikinti segmentus, pagrįstus kitais segmentais. Pavyzdžiui, segmentas, sukurtas kitu segmentu, kuris buvo pastatytas trečiame segmente.    

- **Segmentų sąrašo puslapis**

  Naujajame segmentų puslapio dizaine naudojamas sąrašo formatas, leidžiantis vienu metu matyti daugiau segmentų. Ieškos laukas įtraukiamas greitai ieškant segmentų. Dabar vartotojai vienu metu gali taikyti tokius veiksmus kaip kelių segmentų atsisiuntimas arba naikinimas. Nauja tendencijos patirtis įvedama norint greitai identifikuoti reikšmingus segmentų pakeitimus.    
  Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

#### <a name="system-administration"></a>Sistemos administravimas

- **„Customer Insights“ prieinamas programoje „Microsoft Dynamics 365 Online Government“**

  Atsirandant vis daugiau kanalų, skirtų sąveikoms, piliečių duomenys yra visoje „myriad“ sistemoje, o tai sukuria vienos paskirties duomenis ir suskaidytą informacijos apie piliečių sąveikas rodinį. Be išsamaus kiekvieno piliečio sąveikos kanaluose rodinio, vyriausybės negali modernizuoti tiek, kiek reikia. „Microsoft“ siekia remti vyriausybės technologijų reikmes, kad patenkintų piliečių lūkesčius dėl nuoseklių ir interaktyviųjų patirčių.    
  Su 2020 m. 1-ąja leidimų banga, „Dynamics 365 Customer Insights“ bus prieinami „Government Community Cloud“ (GCC), aplinka, sukurta siekiant patenkinti didesnės atitikties Jungtinių Valstijų valstybinių institucijų agentūrų poreikius. Agentūros gauna vieningąjį piliečių rodinį ir naudoja iš anksto sukurtą AI, kad gautų įžvalgų, kurios pagerintų sąveikas, įgalintų darbuotojus ir pakeistų bendruomenes, tuo pat metu mažintų IT sudėtingumą ir patenkintų Jungtinių Valstijų atitiktį ir saugumo standartus. „Dynamics 365 Government“ atitinka griežtus JAV federalinės rizikos ir autorizacijos valdymo programos (FedRAMP) reikalavimus, leidžiančius Jungtinių Valstijų federalinėms agentūroms pasinaudoti išlaidų taupymu ir griežta „Microsoft Cloud“ sauga.

## <a name="april-2020-updates"></a>2020 m. balandžio mėn. naujinimai

2020 m. balandžio mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="new-and-updated-features-in-april-2020"></a>Naujos ir atnaujintos funkcijos 2020 m. balandžio mėn.

#### <a name="activities"></a>Veiklos

- **Veiklos objekto susiejimas su standartiniu veiklos tipu**
  
  Veiklos konfigūracija ir saugojimas šiuo metu priklauso nuo statinio dizaino, kad juos būtų galima peržiūrėti laiko planavimo juostoje. Veiklos semantikos prasme, kuri turi potencialą kelių naudojimo atvejų AI modeliuose, šiuo metu nėra pilnai naudojama. Planuojame, kad veiklos laiko grafikas būtų dinamiškesnis, remiantis veiklos rūšimi ir didesniu semantikos supratimu. Ši funkcija atpažins veiklos tipą, kaip nurodyta „Common Data Model“, bet kokiai įsisavintai veiklai.
  Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).

#### <a name="data-ingestion"></a>Duomenų įsisavinimas

- **Duomenų įsisavinimas realiuoju laiku: veiklos**
  
  Realaus laiko duomenų suvartojimas pateikia duomenis nedelsiant suvartojimui, kol tolesnis grafikas iš naujo paleidžia šiuos duomenis iš duomenų šaltinio.    
  Daugiau informacijos žr. [Duomenų įtraukimas realiuoju laiku](real-time-data-ingestion.md).

- **Duomenų paruošimo patobulinimai**
  
  Sužinokite daugiau apie objekte įsisavintus duomenis. Naudodami duomenų suvestinę galite suprasti duomenų kokybės charakteristikas, kurios gali padėti imtis atitinkamų veiksmų.    
  Daugiau informacijos ieškokite [Objekto duomenų išbandymas](entities.md#exploring-a-specific-entitys-data).

- **Analitinių duomenų iš „Dynamics 365“ įsisavinimas su „Common Data Service“**
  
  „Common Data Service“ yra prieinamas kaip kelias sukurti duomenų šaltinius. Esami „Dynamics 365“ klientai gali įsisavinti analitinius objektus iš „Common Data Service“ į „Customer Insights“. Vienas duomenų šaltinis gali tuo pačiu metu naudoti tą patį „Common Data Service“-sutvarkytą ežerą „Customer Insights“ aplinkoje.    
  Daugiau informacijos žr. [Prisijungimas prie duomenų, esančių „Common Data Service“ valdomajame duomenų telkinyje](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Išplėtimas

- **Eksportuoti į „LiveRamp“**

  Aktyvinkite savo duomenis „LiveRamp®“, kad prisijungtumėte prie daugiau nei 500 platformų skaitmeninėse, socialinėse ir TV ekosistemose. „LiveRamp” duomenis naudokite norėdami taikyti, suslėgti ir asmeniniams poreikiams pritaikyti reklamos kampanijas.    
  Daugiau informacijos žr. [„LiveRamp“&reg; jungtyje](export-liveramp.md).

- **„Customer Insights Teams“ priedas**
  
  Robotas teikia sujungtų klientų profilių peržvalgos galimybes. Iš gauto kliento profilio pasirodys kortelė su iki 15 laukų. Esant keliems atitikmenims pateikiamas rezultatų sąrašas, kuriame galite pasirinktį profilį.    
  Daugiau informacijos rasite [Komandos robotai, skirti „Customer Insights“ ](export-teams-bot.md).

#### <a name="measures"></a>Matavimai

- **Priemonių sąrašo puslapis**
  
  Priemonių puslapyje patobulinimai apima vieno ir kelių priemonių palaikymo veiksmus vienu metu. Be to, rasite ieškos lauką, kad greitai rastumėte ir sektumėte priemones.    
  Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

- **Sudėtinių priemonių patobulinimai**
  
  Vartotojai gali kurti, redaguoti ir naikinti priemones, pagrįstas kitomis priemonėmis. Pavyzdžiui, priemonė, sukurta kita priemone, kuri buvo pastatytas trečioje priemonėje.

#### <a name="segments"></a>Segmentai

- **Kitas operatorius**
  
  Rinkinio operatorius leidžia klientų segmentaciją pagal kelias galimas eilučių reikšmes. Prieš pridedant šį operatorių, reikėjo pastatyti tokius segmentus su keliomis OR sąlygomis. Rinkinio operatorius leidžia tai atlikti su vieną iš šių sąlygų.    
  Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

#### <a name="system-administration"></a>Sistemos administravimas

- **Konfigūracijos parametrų kopijavimas į naują aplinką**
  
  Nukopijuokite jūsų konfigūravimą iš vienos aplinkos į kitą. Kurdami naują aplinką galite pasirinkti esamą aplinką, iš kurios norite kopijuoti konfigūraciją. Šiuo metu palaikome duomenų šaltinių, duomenų sujungimo, ryšių, priemonių ir segmentų kopijavimą. Duomenų šaltinio kredencialai ir faktiniai duomenys nėra kopijuojami.    
  Daugiau informacijos žr. [Aplinkų valdymas](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]