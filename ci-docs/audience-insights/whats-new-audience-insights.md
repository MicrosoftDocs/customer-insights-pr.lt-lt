---
title: Naujos ir būsimos funkcijos
description: Informacija apie naujas funkcijas, pagerinimus ir klaidų ištaisymus.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 346ef93e8471580b782618550ca4eb71b3f3c921
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884272"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kas naujo publikos įžvalgų „Dynamics 365 Customer Insights“ pajėgumuose

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Džiaugiamės galėdami pranešti apie mūsų naujausius atnaujinimus! Šiame straipsnyje apibendrinamos viešos peržiūros versijos funkcijos, bendro pasiekiamumo patobulinimai ir funkcijų atnaujinimai. Norėdami peržiūrėti ilgalaikius funkcijų planus, peržiūrėkite [„Dynamics 365“ ir „Power Platform“ išleidimo planai](/dynamics365/release-plans/).

Naujinimus atliekame pagal regionus. Taigi tam tikri regionai gali matyti funkcijas prieš kitus. Jei nenurodyta kitaip, jums nereikia imtis jokių veiksmų ir mes automatiškai atnaujinsime programą be prastovų.

> [!TIP]
> Norėdami teikti ir balsuoti už funkcijų užklausas bei produktų pasiūlymus, eikite į [„Dynamics 365“ programos idėjų portalą](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2021-updates"></a>2021 m. lapkričio mėn. naujinimai

2021 m. lapkričio mėnesio atnaujinimai apima naujas funkcijas, našumo naujinimus ir klaidų taisymus.

### <a name="segment-membership-now-available-in-dataverse"></a>Segmento narystė dabar pasiekiama Dataverse

Klientų profilių segmento narystės informacija dabar pasiekiama Dataverse kartu su klientų profiliais ir įžvalgomis. "Dynamics 365" veiksmų programos ir modeliu pagrįstos programos gali naudoti šiuos duomenis, ieškodami tam tikro kliento segmento narystės informacijos.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Veiklos palaikymo verslo abonementų kontaktinio lygio informacija

Dabar galite konfigūruoti, rodyti ir filtruoti kontaktų veiklas savo verslo abonemento veiklos laiko juostose, kad geriau suprastumėte, kurie abonemento kontaktai dalyvavo konkrečioje veikloje.

## <a name="october-2021-updates"></a>2021 m. spalio mėn. naujinimai

2021 m. spalio mėnesio atnaujinimai apima naujas funkcijas, našumo naujinimus ir klaidų taisymus.

### <a name="b-to-b"></a>Nuo B iki B

Nuo 2021 m. spalio galite dirbti su verslo klientais ir su ja susijusiais kontaktais "Customer Insights". Anksčiau programa daugiausia buvo pritaikyta individualiems vartotojams. Kelios funkcijų sritys buvo atnaujintos, kad būtų palaikomi B-to-B scenarijai, be naujo aplinkos tipo. Peržiūrėkite palaikomas "B-to-B" funkcijas, auditorijos įžvalgose ieškokite [Darbas su verslo paskyromis](work-with-business-accounts.md).

Tolesniuose skyriuose pabrėžiamos kai kurios pagrindinės sritys, kurios buvo pritaikytos verslo sąskaitoms ir atskiriems vartotojams remti.

#### <a name="export-segments-based-on-business-accounts"></a>Eksportuoti segmentus pagal verslo sąskaitas

Visas segmento eksportas auditorijos įžvalgose yra prieinamas verslo sąskaitų kontekste. Daugumai segmentų eksportui reikia papildomos konfigūracijos ir [kontaktinės informacijos, kuri,](segment-builder.md#create-a-new-segment) kaip prognozuojama, yra susijusi su verslo sąskaitomis. Daugiau informacijos ieškokite [Export segments](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>"LinkedIn Ads" eksportavimo naudojimas su verslo paskyromis

"LinkedIn Ads" eksportavimas dabar pasiekiamas kontaktams ir įmonėms taikyti verslo paskyrų kontekste. Pasirinkdami įmonės taikymą kaip pagrindinį "LinkedIn" eksporto dėmesį, galite eksportuoti segmentus, sukurtus verslo paskyrose, nereikia projektuoti kontaktinės informacijos. Norėdami gauti daugiau informacijos, eikite į dokumentus apie ["LinkedIn Ads" eksportavimą](export-linkedin-ads.md) ir skirtumą tarp [kontaktų taikymo ir įmonės taikymo](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting)[...](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Kurti priemones pagal verslo sąskaitas ir jų hierarchiją

Priemonės daryklė leidžia kurti priemones aplink verslo sąskaitas ir pasirinktinai naudoti hierarchijos informaciją. Hierarchijos informacija naudojama matavimo skaičiavimui visoje sąskaitoje ir visose susijusiose antrinėse sąskaitose. Pavyzdžiui, galite sukurti tokias priemones kaip bendros pajamos kiekvienai verslo sąskaitų grupei, kurią identifikuoja jų hierarchija. Dėl daugiau informacijos, žr. [Nustatyti ir valdyti priemones](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Kurti segmentus pagal verslo sąskaitas ir jų hierarchiją

Segmento daryklė leidžia kurti verslo sąskaitų segmentus, kuriuose pasirinktinai įtraukiama kiekvieno segmento kliento kontaktinė informacija. Jei nustatyta sąskaitų hierarchija, galite naudoti sąskaitų hierarchijos informaciją kurdami segmentus. Daugiau informacijos ieškokite [Create a new segment](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Išsaugokite savo verslo sąskaitas su giliomis įžvalgomis apie jų churn tendenciją

Klientų prognozė modelis dabar palaiko ir verslo sąskaitas. Galite įvertinti riziką, kad bus galima įsigyti ne tik sąskaitą, bet ir sąskaitos bei produkto ar paslaugos kategorijos, kurią jie perka iš jūsų, derinį. Šis papildymas padeda suprasti, ar paskyra yra labiau tikėtina, kad nustos pirkti iš jūsų apskritai, ar tik tam tikros kategorijos prekėms ar paslaugoms. Norėdami dar labiau padėti naudoti šį DI modelį, jame taip pat išvardytos priežastys, kodėl paskyra gali sutrūkti. Daugiau informacijos ieškokite [Transaction churn prognozė (preview)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Verslo abonemento kontaktų peržiūra kliento rodinyje

Jei verslo abonementai susieti su susijusiais abonementais, programa "Customer Insights" rodo šiuos susijusius kontaktus kaip kliento išsamios informacijos rodinio dalį. Daugiau informacijos ieškokite [Customer profiles](customer-profiles.md).


## <a name="september-2021-updates"></a>2021 m. rugsėjo mėn. naujinimai

Į 2021 m. rugsėjo mėn. naujinimus įtrauktos naujos funkcijos, efektyvumo naujiniai ir klaidų taisymai.

### <a name="activities"></a>Veiklos

- **Veiklos laiko planavimo juostos** patobulinimai Išplėtė veiklos laiko planavimo juostos filtrus klientų profiliuose. Be to, naudodami naują filtro keptuvę galite filtruoti pagal veiklos tipą ir datą. Datas galima filtruoti naudojant skirtingas sąlygas. Daugiau informacijos žr. [Veiklos laiko planavimo juostų rodymas klientų profiliuose](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Ryšiai

- **Kelių objektų ryšių palaikymas** Konfigūruodami veiklas ir apibrėždami objektų ryšius naudokite kelių objektų ryšius. Kelių objektų ryšiai naudoja išsamų objektą dviem objektams sujungti. Konfigūruodami veiklą galite naudoti kelių kanalų ryšį, kad susietumėte savo veiklos objektą su susiautinu objektu, o tada su kliento objektu. Galite derinti kelių eilučių ryšius su kelių maršrutų ryšiais. Daugiau informacijos rasite [kelių eilučių ryšys](relationships.md#multi-hop-relationship).

- **Kelių kelių ryšių palaikymas** Konfigūruodami veiklas ir apibrėždami kelių ryšius naudokite kelių objektų ryšius. Kelių kelių maršrutų ryšiai šaltinio objektą sieja su daugiau nei vienu objektu. Konfigūruodami veiklą galite naudoti kelių kanalų kelią, kad susietumėte savo veiklos objektą su susiautinu objektu, o tada su daugiau nei vienu kliento objektu. Galite derinti kelių eilučių kelius su kelių maršrutų ryšiais. Daugiau informacijos rasite [kelių kelių ryšys](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>2021 m. rugpjūčio mėn. naujinimai

Į 2021 metų liepos ir rugpjūčio mėnesių naujinimus įtraukta nauja funkcija, efektyvumo patobulinimai ir klaidų taisymai.

### <a name="extensibility"></a>Išplėtimas

- **Eksportuoti segmentus į „Klaviyo”** Išplėtėme mūsų [eksportavimo paskirties vietas, kad būtų įtrauktas „Klaviyo”](export-klaviyo.md). Dabar galite eksportuoti segmentus, kad sukurtumėte kampanijas, vykdytumėte elektroninių laiškų rinkodarą ir naudotumėte konkrečias klientų grupes su „Klaviyo“. 


## <a name="june-2021-updates"></a>2021 m. birželio mėn. naujinimai

2021 m. birželio mėn. naujinimai apima keletą funkcijų, vykdymo pagerinimus ir klaidų ištaisymus.

### <a name="data-ingestion"></a>Duomenų įsisavinimas

- **Patobulinti duomenų suvienodinimo eigos naujinimai** Dabar galite peržiūrėti išsamesnius, patobulintus dinaminių būsenų atnaujinimus [duomenų suvienodinimo proceso](data-unification.md) veiksmuose. Ši funkcija leidžia jums sekti išsamią eigą, kad būtų galima suprasti procesų seką ir, jei reikia, imtis veiksmų.

### <a name="extensibility"></a>Išplėtimas

- **Eksportuoti segmentus ir kitus duomenis į „Salesforce Marketing Cloud”** Išplėtėme eksportavimo paskirties vietas, kad būtų įtrauktas [„Salesforce Marketing Cloud”](export-salesforce.md). Dabar galite eksportuoti segmentus ir kitų tipų duomenis į „Salesforce Marketing Cloud” per trumpąjį SFTP eksportavimą. Duomenų importavimą galima visiškai automatizuoti „Salesforce” ir naudoti norint kurti efektyvesnes rinkodaros kampanijas.  
 
- **Eksportuoti segmentus į „ActiveCampaign”** Išplėtėme eksportavimo paskirties vietas, kad būtų įtraukta [„ActiveCampaign”](export-active-campaign.md). Dabar galite eksportuoti segmentus, kad kurtumėte kampanijas, vykdytumėte elektroninių laiškų rinkodarą ir dirbtumėte su konkrečiomis klientų grupėmis „ActiveCampaign“.
 
- **Eksportuoti segmentus į „Sendinblue”** Išplėtėme eksportavimo paskirties vietas, kad būtų įtrauktas [„Sendinblue”](export-sendinblue.md). Dabar galite eksportuoti segmentus, kad kurtumėte kampanijas, vykdytumėte elektroninių laiškų rinkodarą ir dirbtumėte su konkrečiomis klientų grupėmis „Sendinblue“.
 
### <a name="ux-updates"></a>UX atnaujinimai 

- **Naujas ir patobulintas Klientų puslapis ir profilio išsamios informacijos puslapis** Mes pertvarkėme Klientų puslapį ir išsamios profilių informacijos puslapius, kad pagerintumėte vartotojų patirtį ir efektyvumą. Šie pakeitimai jums leidžia peržiūrėti, rikiuoti, ieškoti ir filtruoti klientus. Filtrai dabar pateikiami URL, kad ieškos rezultatai būtų sklandžiai bendrinami su kitais vartotojais. Ieškos rezultatus taip pat galima įrašyti kaip segmentą.    
  Dabar klientų profilių išsamios informacijos puslapyje duomenys grupuojami į įvairius poskyrius, pavyzdžiui, demografinius duomenis, ID ir kitus profilio atributus dėl patobulinto skaitomumo. Dabar kiti išsamios profilio informacijos puslapio skyriai yra interaktyvesni. Pavyzdžiui, dabar veiklų skyrius leidžia filtruoti ir rikiuoti.


## <a name="may-2021-updates"></a>2021 m. gegužės mėn. naujinimai

2021 m. gegužės mėnesio atnaujinimai apima kelias funkcijas, efektyvumo atnaujinimus bei klaidų taisymus.

### <a name="data-ingestion"></a>Duomenų įsisavinimas

- **Peržiūrėti arba modifikuoti metaduomenų ar objektų aprašus, kai pridedate duomenis iš savo „Azure Data Lake Storage”** Dabar galite peržiūrėti ir redaguoti metaduomenų ar objektų aprašus auditorijos įžvalgose, kai pridedate duomenis iš „Common Data Model” savo „Azure Data Lake Storage”. Ši galimybė pateikia atsiliepimus realiuoju laiku, modelio tikrinimą ir klaidų patikrinimą. Ji leis sklandžiai redaguoti tiek model.json, tiek manifest.json.

### <a name="extensibility"></a>Išplėtimas

- **Patobulintas segmentų eksportavimas, pasirinktinis grafikas ir dublikatų kūrimas** Dabar galite [matyti visus konkretaus segmento eksportavimus](export-destinations.md#view-exports-and-export-details) sąraše. Šis naujas rodinys padeda valdyti konkretaus segmento naudojimą ir pritaikyti esamą arba sukurti naują eksportavimą.    
  Vienu metu [galite apibrėžti pasirinktinius atnaujinimo grafikus](export-destinations.md#schedule-and-run-exports) atskiriems arba keliems eksportavimams. Iki šiol visi eksportavimai būdavo vykdomi kaskart atnaujinus sistemą.    
  Užuot sukūrę naują eksportavimą nuo nulio, galite pradėti dirbti pagal esamą, kad sutaupytumėte laiko.

- **Segmentų eksportavimas į „Microsoft Advertising“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „Microsoft Advertising“. Kurkite klientų atitikties auditorijas „Microsoft Advertising“ pasinaudodami vieningųjų klientų profilių duomenimis ir naudokite šias auditorijas savo reklamos kampanijoms. Daugiau informacijos rasite [Segmentų eksportavimas į „Microsoft Advertising”](export-microsoft-advertising.md).

- **Segmentų eksportavimas į „LinkedIn Ads”** Išplėtėme mūsų eksportavimo paskirties vietas, kad būtų įtraukta „LinkedIn Ads” ir įgalintumėte jus atrakinti Taikymą pagal kontaktus bei Taikymą pagal kompaniją per „LinkedIn”, eksportuodami jūsų vieningojo kliento profilio duomenis. Daugiau informacijos rasite [Segmentų eksportavimas į „LinkedIn Ads”](export-linkedin-ads.md).


- **Segmentų eksportavimas į „Omnisend“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „Omnisend“. Naudodami auditorijos įžvalgose sukurtus segmentus, kurkite kampanijas, teikite rinkodaros el. laiškus ir naudokite konkrečias klientų grupes su „Omnisend“. Daugiau informacijos rasite [Segmentų eksportavimas į „Omnisend”](export-omnisend.md)

### <a name="predictions"></a>Prognozės

- **Įvesties duomenų naudojimo ataskaita** Įvesties duomenų naudojimo ataskaita pateikia klaidų ir įspėjimų, kuriuos gali sugeneruoti jūsų visiškai parengtos prognozės, apibendrintą rodinį. Joje taip pat pateikiama rekomendacijų, kaip pagerinti modelio efektyvumą.    
  Ataskaita yra pasiekiama atlikus modelio mokymo procesą. Ji sukuriama kiekvienam modeliui atskirai, nepriklausomai nuo to, ar jis užbaigtas sėkmingai.
  Šiuo metu ši funkcija yra galima tik su Operacijų praradimo modeliu. Daugiau informacijos rasite [Įvesties duomenų naudojimo ataskaita](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Ryšiai

- **Ryšių vizualizavimo priemonė** Ryšių vizualizavimo priemonė jums leidžia matyti visus esamus ryšius tarp objektų ir jų skaičių. Ryšiai dabar tvarkomi grupėmis: vartotojo sukurti, sistemos ir paveldėti ryšiai. Taip pat galite eksportuoti rodinį kaip vaizdą. Daugiau informacijos ieškokite [Peržiūrėti ryšius](relationships.md#view-relationships). 

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

- **Segmentų eksportavimas į „RollWorks“** Išplėtėme savo eksportavimo paskirties vietas ir įtraukėme „RollWorks“. Dabar galite eksportuoti segmentus iš „Customer Insights“ į „RollWorks" auditorijas ir naudoti juos kaip bazinę B2B reklamos dalį.    
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

  Administratoriai gali kopijuoti aplinkos konfigūracijas į naują aplinką toje pačioje organizacijoje. Ši funkcija išplečia aplinkos kopijavimo funkcijas atvejams, kai naudojami duomenų šaltiniai, pagrįsti „Microsoft Dataverse” valdomu „data lake” arba „Common Data Model” aplanku.

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