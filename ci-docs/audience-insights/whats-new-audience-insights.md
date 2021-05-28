---
title: Naujos ir būsimos funkcijos
description: Informacija apie naujas funkcijas, pagerinimus ir klaidų ištaisymus.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988930"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kas naujo publikos įžvalgų „Dynamics 365 Customer Insights“ pajėgumuose

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Džiaugiamės galėdami pranešti apie mūsų naujausius atnaujinimus! Šiame straipsnyje apibendrinamos viešos peržiūros versijos funkcijos, bendro pasiekiamumo patobulinimai ir funkcijų atnaujinimai. Norėdami peržiūrėti ilgalaikius funkcijų planus, peržiūrėkite [„Dynamics 365“ ir „Power Platform“ išleidimo planai](/dynamics365/release-plans/).

Naujinimus atliekame pagal regionus. Taigi tam tikri regionai gali matyti funkcijas prieš kitus. Jei nenurodyta kitaip, jums nereikia imtis jokių veiksmų ir mes automatiškai atnaujinsime programą be prastovų.

> [!TIP]
> Norėdami teikti ir balsuoti už funkcijų užklausas bei produktų pasiūlymus, eikite į [„Dynamics 365“ programos idėjų portalą](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="april-2021-updates"></a>2021 m. balandžio mėn. naujinimai

2021 m. balandžio mėnesio atnaujinimai apima kelias funkcijas, efektyvumo atnaujinimus bei klaidų taisymus.

### <a name="data-unification"></a>Duomenų suvienodinimas
 
- **Patobulinta suliejimo patirtis duomenų suvienodinimui**    
  
   Dabar duomenų suvienodinimo proceso suliejimo konfigūracijoje suteikiame patobulintą vartotojo patirtį. Pakeitimai apima intuityvų sulietų laukų tvarkos nustatymą ir išsamią statistiką apie sujungtus ir pavienius laukus.

- **Objektų pertvarkymas ir visų šaltinio įrašų konfigūravimas į Kliento objektą**  
      
   Dabar galite pertvarkyti ir pašalinti objektus iš esamo suliejimo plano duomenų suvienodinimo procese. Tai suteikia lankstumo pertvarkyti objektus atitikties procese, atsižvelgiant į veiklos poreikius. Be to, į galutinį *Kliento* objektą leidžiame įtraukti visus nesugretinus įrašus, kurie jums leidžia apibrėžti kliento profilio duomenų rinkinį.

### <a name="enrichments"></a>Papildymai

 - **Naujas papildymas: Išplėstiniai adresai**    
  
   Džiaugiamės galėdami pristatyti naują papildymą, skirtą išplėsti klientų duomenų adresams. Adresai jūsų duomenyse gali būti nesusisteminti, neišsamūs arba neteisingi. Ši funkcija naudoja „Microsoft” modelius, kad normalizuotų ir papildytų jūsų adresus į „Common Data Model” formatą geresniam tikslumui ir įžvalgoms.
 
   Daugiau informacijos rasite [Klientų profilių papildymas išplėstiniais adresais](enrichment-enhanced-addresses.md).

- **Interaktyvioji papildymų konfigūravimo patirtis**    
  
   Mes padarėme papildymų konfigūravimo patirtį paprasta ir interaktyvia. Dabar galite naudoti aiškų ir išsamų papildymų kūrimo ir redagavimo procesą.
 
   Be to, atskyrėme trečiųjų šalių papildymų ryšių konfigūraciją, kad tą patį ryšį galėtų naudoti keli papildymai. Naujus ryšius gali konfigūruoti tik administratoriai, tačiau sukurti ryšiai pasiekiami ir administratoriams, ir bendraautoriams.    

   Daugiau informacijos rasite [Ryšių apžvalga](connections.md).

- **Keli to paties tipo papildymai**    
  
   Dabar vartotojams leidžiame kurti ir valdyti kelis to paties tipo papildymus. Pavyzdžiui, dabar galite sukurti du atskirus adreso papildymus, kad papildytumėte du skirtingus klientų segmentus. Yra taikomi apribojimai, kiek to paties tipo papildymų galima sukurti ir skirtis, priklausomai nuo papildymo tipo.
  
   Daugiau informacijos žr. [Klientų profilių papildymas](enrichment-hub.md).

## <a name="march-2021-updates"></a>2021 m. kovo mėn. atnaujinimai

2021 m. kovo mėnesio atnaujinimai apima kelias funkcijas, efektyvumo atnaujinimus bei klaidų taisymus.

### <a name="activities"></a>Veiklos

- **Veiklos vedlys ir semantiniai tipai**

   Patobulinome ir atnaujinome savo veiklos susiejimo patirtį, kad padėtume kurti ir supaprastintumėme veiklos susiejimą. Šiame naujame procese naudotojai gauna interaktyviąją galimybę, kad galėtų atlikti kiekvieną proceso veiksmą. Atliekant veiklos žymėjimo veiksmą, be kelių veiklos tipų pasirinkimo naudotojas gali pasirinkti semantiškai žymėti duomenis *prenumeratai* ir (arba) *„SalesOrderLine“* pagal pramonės standarto schemas, kurias galima naudoti tolesniam vartojimui.   

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]