---
title: Kas nauja programoje „Dynamics 365 Customer Insights“
description: Informacija apie naujas funkcijas, pagerinimus ir klaidų ištaisymus.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409367"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Kas nauja programoje „Dynamics 365 Customer Insights“

Džiaugiamės galėdami pranešti apie mūsų naujausius atnaujinimus! Šiame straipsnyje apibendrinamos viešos peržiūros versijos funkcijos, bendro pasiekiamumo patobulinimai ir funkcijų atnaujinimai. Norėdami peržiūrėti ilgalaikius funkcijų planus, peržiūrėkite [„Dynamics 365“ ir „Power Platform“ išleidimo planai](/dynamics365/release-plans/).

Naujinimus atliekame pagal regionus. Taigi tam tikri regionai gali matyti funkcijas prieš kitus. Jei nenurodyta kitaip, jums nereikia imtis jokių veiksmų, mes automatiškai atnaujinsime programą be prastovų.

> [!TIP]
> Norėdami teikti ir balsuoti už funkcijų užklausas bei produktų pasiūlymus, eikite į [„Dynamics 365“ programos idėjų portalą](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>2022 m. rugpjūčio mėn. naujinimai

2022 m. rugpjūčio mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontaktų suvienijimas B-to-B aplinkoje

"B-to-B" aplinkos "Customer Insights" dabar palaiko patobulintą duomenų suvienijimo patirtį.

Dabar galite suvienodinti kontaktus, be abonementų, kad gautumėte išsamų verslo kontaktų vaizdą. Vieningieji kontaktai yra susieti su vieningomis paskyromis ir dabar pateikiami klientų kortelėse. 

Daugiau informacijos ieškokite [Vieningojo kontakto profilio kūrimas](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Segmentų kūrimas ir eksportavimas pagal vieningus kontaktus

Dėl naujo kontaktų suvienijimo galite kurti kontaktų segmentus naudodami kontaktų, abonementų arba abiejų kriterijus. Šiuos segmentus galima eksportuoti, kad juos būtų galima suaktyvinti kitose paslaugose.

Daugiau informacijos ieškokite [Eksportavimo apžvalga](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Diegimo regionai suderinti su Microsoft Dataverse

Kurdami naują "Customer Insights" aplinką, galite pasirinkti regioną, kuriame norite, kad paslauga būtų diegiama ir nuomojama. Atnaujinome regiono pasirinkimą, kad jis atitiktų Microsoft Dataverse ir Power Platform.

Dabar galite lengvai pasirinkti tą patį regioną kaip esamą Microsoft Dataverse aplinką arba "Azure Data Lake" saugyklos paskyrą (jei pasirinksite šią parinktį), jei tame regione yra "Customer Insights" pasiekiamumo.

Daugiau informacijos ieškokite [Naujos aplinkos](create-environment.md) kūrimas ir [Produkto pasiekiamumas pagal geografiją](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>2022 m. liepos mėn. naujinimai

2022 m. liepos mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="export-to-moengage"></a>Eksportas į "MoEngage"

Eksportuokite vieningų klientų profilių segmentus į "MoEngage" ir naudokite juos el. pašto rinkodarai "MoEngage".

Daugiau informacijos ieškokite [Segmentų eksportavimas į "MoEngage](export-moengage.md)".

### <a name="ssh-support-for-sftp-based-exports"></a>SSH palaikymas SFTP pagrįstam eksportui

Pasirinkite, ar norite autentifikuoti naudodami SSH, ar vartotojo vardą / slaptažodį ryšiams su SFTP eksporto paskirties vietomis.

Daugiau informacijos ieškokite [Duomenų eksportavimas į SFTP pagrindinius kompiuterius](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Suasmeninkite funkcijas naudodami duomenis apie žinomus ir nežinomus vartotojus

Klientų duomenų tvarkymas nėra naujas iššūkis, tačiau jis tampa vis sudėtingesnis, nes vartotojai naršo įvairiuose prekių ženklų siūlomuose skaitmeniniuose kanaluose. Vartotojas, kuris yra žinomas (autentifikuotas) viename kanale, tampa nežinomas (neautentifikuotas) kitame kanale, jei jis nėra prisijungęs. Problema dažnai yra ta, kad neautentifikuoti (nežinomi) vartotojai neturi bendro ID. Jis gali būti naudojamas prasmingiems profilių atributams susieti ir vieningiems klientų profiliams generuoti. "Customer Insights" padeda išspręsti šią problemą, nurijus duomenis iš sekimo metodų šaltinio sistemose.

Daugiau informacijos ieškokite [Funkcijų suasmeninimas naudojant duomenis apie žinomus ir nežinomus vartotojus](unknown-to-known.md).

## <a name="june-2022-updates"></a>2022 m. birželio mėn. naujinimai

2022 m. birželio mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Atnaujinta naudotojų patirtis, susijusi su duomenų šaltiniais ir duomenų įsisavinimu

Duomenų importavimas iš įvairių duomenų šaltinių yra pagrindas konsoliduoti klientų duomenis Dynamics 365 Customer Insights. Peržiūrėjome duomenų šaltinių importavimo ir prijungimo naudotojų patirtį. Šiuo naujinimu siekiama, kad jums būtų lengviau nuryti duomenis iš "Customer Insights".

Daugiau informacijos ieškokite [Duomenų šaltinių apžvalga](data-sources.md).

### <a name="export-to-inmobi"></a>Eksportavimas į "InMobi"

"InMobi" padeda prekių ženklams suprasti, identifikuoti, sudominti ir įsigyti vartotojų. Segmentus ir kitus duomenis į "InMobi" paslaugą galite eksportuoti naudodami "Azure Blob Storage" paskyras.

Daugiau informacijos ieškokite [Eksportavimas į "InMobi" (peržiūra)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>"Lockbox" palaikymas "Customer Insights"

"Customer Lockbox" suteikia sąsają, leidžiančią peržiūrėti ir patvirtinti (arba atmesti) prieigos prie duomenų užklausas. Šios užklausos atsiranda, kai norint išspręsti palaikymo atvejį, reikalinga prieiga prie klientų duomenų.

Norėdami gauti daugiau informacijos, žiūrėkite [Saugiai pasiekite klientų duomenis naudodami "Customer Lockbox" (peržiūra)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Prisijungimas prie savo duomenų naudojant "Azure Private Link"

"Azure Private Link" leidžia "Customer Insights" prisijungti prie jūsų Azure Data Lake Storage paskyros per privatų virtualaus tinklo galinį punktą. Duomenims, esantiems saugojimo paskyroje, kuri nėra viešajame internete, "Private Link" įgalina ryšį su tuo apribotu tinklu.

Daugiau informacijos ieškokite [Privataus saito naudojimas programoje "Customer Insights](security-overview.md#set-up-an-azure-private-link)".

## <a name="may-2022-updates"></a>2022 m. gegužės mėn. naujinimai

2022 m. gegužės mėnesio naujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="updated-data-unification-experience"></a>Atnaujinta duomenų suvienijimo patirtis

 Duomenų suvienijimas leidžia suvienodinti vieną kartą skirtingus duomenų šaltinius į vieną pagrindinį duomenų rinkinį, kuris pateikia vieningą tų duomenų rodinį. Duomenis galima suvienodinti viename objekte arba keliuose objektuose. Pirmiausia pasirenkate objektus ir šaltinio laukus [, pašalinate pasikartojančius įrašus](map-entities.md), nurodote sąlygų atitikimo [taisykles](remove-duplicates.md) ir apibrėžiate [, kuriuos](match-entities.md) laukus įtraukti į vieningus klientų profilius [.](merge-entities.md)

Daugiau informacijos ieškokite [Duomenų suvienijimo apžvalga](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Atnaujintas pagrindinis puslapis programoje "Customer Insights"

**Pagrindinis** puslapis padės jums atlikti pagrindinių funkcijų konfigūravimo procesą ir pateikia segmentų, matų ir papildymo duomenų apžvalgą. Atnaujinome patirtį, kad iš karto pateiktume aktualesnę informaciją.

Daugiau informacijos ieškokite ["Customer Insights" naršymas](home.md).

### <a name="track-usage-of-a-segment"></a>Segmento naudojimo takelis

Dabar [galite sekti segmento](segments.md#track-usage-of-a-segment) naudojimą programose, pagrįstose Dataverse organizacija, susieta su "Customer Insights". " [Customer Insights" segmentuose, naudojamuose "Dynamics 365 Marketing"](/dynamics365/marketing/real-time-marketing-ci-profile) klientų veiklos cikluose, sistema informuoja jus apie to segmento naudojimą.

### <a name="export-to-criteo"></a>Eksportas į Criteo

Criteo yra internetinė platforma, padedanti vartotojams valdyti skaitmeninę reklamą. Dabar galite eksportuoti vieningų klientų profilių segmentus, kad sukurtumėte kampanijas, teiktumėte rinkodarą el. paštu ir naudotumėte konkrečias klientų grupes naudodami "Criteo".

Daugiau informacijos ieškokite [Segmentų eksportavimas į Criteo (peržiūra)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Patobulinta dokumentacijos struktūra aplinkos kūrimui

Peržiūrėjome pagalbos dokumentus, susijusius su "Customer Insights" aplinkų kūrimu ir valdymu. Dabar straipsniai yra sugrupuoti pagal aplinkos mazgą turinyje. Restruktūrizuoti straipsniai suteikia daugiau gairių apie įvairius būdus, kaip sukurti aplinką ir turėti aiškesnę struktūrą. Jei turite atsiliepimų, kuriuos norite bendrinti, praneškite mums per valdiklius pagalbos straipsnių pabaigoje.

Daugiau informacijos ieškokite [Kaip: sukurti naują aplinką](create-environment.md).

## <a name="april-2022-updates"></a>2022 m. balandžio mėn. naujinimai

2022 m. balandžio mėnesio naujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun &Bradstreet sodrinimas (peržiūra)

"Dun &Bradstreet" teikia komercinius duomenis, analizę ir įžvalgas įmonėms. Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis. Papildymai apima tokius atributus kaip DUNS numeris, įmonės dydis, vieta, pramonė ir kt.

Norėdami gauti daugiau informacijos, žiūrėkite [Įmonės profilių praturtinimas naudojant Dun & Bradstreet (Peržiūra)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Priemonės tipo apibrėžimas kuriant naują priemonę

Dabar galite atskirti atskirų profilių priemones ir matus visoje įmonėje. Nors verslo priemonės rodomos pagrindiniame "Customer Insights" puslapyje, klientų priemonės atskleidžiamos išsamiuose klientų rodiniuose.

Norėdami gauti daugiau informacijos, žiūrėkite [Priemonių kūrimo priemonės naudojimas priemonėms kurti nuo pradžių](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>"Customer Insights" dokumentacijos konsolidavimas

Peržiūrėjome dokumentacijos straipsnius ir pašalinome paminėjimus apie įtraukimo įžvalgas ir auditorijos įžvalgų galimybes. Judėdami į priekį, rašydami apie pagrindines programos funkcijas nuosekliai remsimės produkto pavadinimu "Customer Insights". Šis pakeitimas taip pat lemia reikšmingą pagrindinės dokumentacijos saugyklos turinio, URL struktūros ir failų kelių pertvarkymą. Visos jūsų žymės arba esamos nuorodos toliau veikia ir nukreipia į atnaujintus URL.

Jei norite mums pranešti, kaip suvokiate tą pakeitimą, arba pastebėti, kad kažkas neveikia taip, kaip tikėtasi, pasakykite mums pateikdami [atsiliepimus apie šį puslapį](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>2022 m. kovo mėn. atnaujinimai

2022 m. kovo mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec praturtinimas (peržiūra)

"LiveRamp" teikia tapatybės skiriamąją gebą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su "AbiliTec" tapatybės grafiku ir gauti "AbiliTec ID". Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

Daugiau informacijos ieškokite [Klientų profilių praturtinimas tapatybės duomenimis iš "LiveRamp" (peržiūra)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentų ir matų tvarkymas naudojant žymas ir filtrus

Jei jūsų organizacija išlaiko daug segmentų ar priemonių, rasti tinkamą kartais gali būti sudėtinga. Ši nauja funkcija leidžia tvarkyti sąrašus naudojant žymes ir stulpelius. Tai padeda greitai ir lengvai rasti duomenis ir tinkinti rodinius.

Daugiau informacijos ieškokite [Darbas su žymėmis ir stulpeliais](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Įgalinkite duomenų bendrinimą su Dataverse, kai naudojate savo saugyklos paskyrą

Jei jūsų aplinka naudoja "Customer Insights" duomenims Azure Data Lake Storage saugoti, duomenų bendrinimui su Microsoft Dataverse reikia papildomos konfigūracijos.
Anksčiau duomenų bendrinimą galėjote įgalinti tik tada Dataverse, kai jūsų duomenys buvo saugomi mūsų valdomų duomenų ežere.

Norėdami gauti daugiau informacijos, žiūrėkite [Įgalinti duomenų bendrinimą su Dataverse savo Azure Data Lake Storage (Peržiūra)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Naujos eksporto paskirties vietos: Iterable ir Braze

Mes ir toliau plečiame savo eksporto paskirties vietų ekosistemą naujais ryšiais. Dabar galite eksportuoti segmentus į "Iterable" ir "Braze", kad galėtumėte naudotis jų aktyvinimo paslaugomis.

Daugiau informacijos ieškokite [Segmentų eksportavimas į Iterable (peržiūra)](export-iterable.md) ir [Segmentų eksportavimas į Braze (peržiūra)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>"Marketo" ir "Google Ads" eksportavimo patobulinimai

Pakeitus prijungtų paslaugų API, atnaujinamos jungtys, kad jos veiktų patikimai ir sklandžiai. Išleidome keletą eksportavimo į "Marketo" ir "Google Ads" paslaugas naujinių:

- "Google Ads": nauja "Google Ads" eksportavimo jungties versija supaprastina autentifikavimo funkcijas ir dabar leidžia automatiškai kurti naujas "Google Ads" auditorijas. 
- Marketo: Naujoji Marketo eksporto jungties versija palaiko Marketo ID, todėl galite išvengti duomenų dubliavimosi, atnaujinti esamus įrašus ir kurti naujus įrašus Marketo. 

## <a name="february-2022-updates"></a>2022 m. vasario atnaujinimai

2022 m. vasario mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="general-availability-for-prediction-models"></a>Bendras prognozė modelių prieinamumas

Parengtiniai prognozė modeliai, įskaitant **prenumeratos atsisakymą**, **operacijų nutraukimą** ir **kliento viso gyvenimo vertę (CLV),** tampa visuotinai pasiekiami kaip "Customer Insights" dalis. 

Daugiau informacijos ieškokite [Prognozių apžvalga](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Naujas duomenų šaltinis: integravimas su Azure Synapse Analytics (peržiūra)

Azure Synapse Analytics yra įmonės analizės paslauga, kuri pagreitina laiką iki įžvalgų visose duomenų saugyklose ir didžiųjų duomenų sistemose.

Organizacijos, kurios jau naudoja Azure Synapse Analytics, gali perduoti tuos duomenis "Customer Insights". 

Daugiau informacijos ieškokite [duomenų šaltinis prijungimas Azure Synapse (peržiūra)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>"LiveRamp" papildymas (peržiūra)

"LiveRamp" teikia tapatybės skiriamąją gebą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su "AbiliTec" tapatybės grafiku ir gauti "AbiliTec ID". Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

Daugiau informacijos ieškokite [Klientų profilių praturtinimas tapatybės duomenimis iš "LiveRamp" (peržiūra)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių papildymas (peržiūra)

Naudokite duomenis iš šaltinių, pvz., "Microsoft" ir kitų partnerių, kad praturtintumėte savo klientų duomenis prieš suvienodindami duomenis. Duomenų šaltinis papildymai padeda užtikrinti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų suvienijus duomenis.

Daugiau informacijos ieškokite [Duomenų šaltinių papildymas (peržiūra)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Keisti aplinkos savininką

Nors keli vartotojai gali turėti administratoriaus teises programoje "Customer Insights", tik vienas vartotojas yra aplinkos savininkas. Patobulinta patirtis leidžia pakeisti aplinkos savininkus ir pretenduoti į nuosavybę, jei buvęs savininkas paliko organizaciją. 

Daugiau informacijos ieškokite [Aplinkos savininko keitimas](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Duomenų paruošimo procesas pateikia sugadintų įrašų sugadinimo priežasčių sąrašą

Duomenų rengimas dabar rodo visų laukų, kuriuose yra sugadintų duomenų, sugadinimo priežastį. Informacija pateikiama individualiu įrašų lygiu, kad būtų lengviau identifikuoti. 

Daugiau informacijos ieškokite [Sugadinti duomenų šaltiniai](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Įtraukimo įžvalgų galimybės ataskaitų teikimo funkcijų peržiūros pabaiga

Įtraukimo Dynamics 365 Customer Insights įžvalgų galimybių peržiūra baigėsi 15 m. vasario 2022 d.  
Šis pakeitimas reiškia, kad "Customer Insights" bandomosios versijos funkcijos nebeapima galimybės kurti kanalų ar kitų ataskaitų teikimo funkcijų.

Kviečiame ištirti ir įvertinti daugelį kitų "Customer Insights [", "Microsoft" klientų duomenų platformos (CDP) – funkcijų](https://dynamics.microsoft.com/ai/customer-insights/).    
 
Pereinamuoju laikotarpiu esami peržiūros dalyviai vis dar turi prieigą prie kai kurių peržiūros galimybių ir funkcijų:

- Gauti kodą žiniatinklio svetainei arba mobiliųjų įrenginių programėlei kurti 
- Įvykių ir įvykių ypatybių peržiūra 
- Patobulinkite vieningus profilius naudodami nurijusius ir patobulintus įvykius, kad gautumėte naudos iš visos jų klientų duomenų vertės
  
Pereinamuoju laikotarpiu užfiksuoti įvykiai vis dar transliuojami į prijungtą Duomenų ežerą. Išjungus šią funkciją, duomenų bendrinimas bus sustabdytas ir į prijungtą saugyklą nebus siunčiami jokie nauji įvykiai.
Tiesiogiai susisiekite su savo "Microsoft" paskyros komanda, jei turite klausimų apie galimybių peržiūros pabaigą. Jūsų paskyros komanda informuos jus apie būsimus paleidimus. 

## <a name="january-2022-updates"></a>2022 m. sausio mėn. naujinimai

2022 m. sausio mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų pataisymus.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Klientų atsiliepimų nuotaikų analizė

"Customer Insights" suteikia naują dirbtiniu intelektu pagrįstą funkciją, leidžiančią sintezuoti klientų nuotaikas ir nustatyti konkrečius verslo aspektus kaip tikslinių patobulinimų galimybes. Analizuodami raštiškus klientų atsiliepimus, galite gauti tikslių įžvalgų už mažą kainą. Nuotaikų analizė, pagrįsta natūralios kalbos apdorojimo (NLP) modeliais, kurie generuoja dvi išvestines įžvalgas kiekvienam kliento ID. Nuotaikų balas (nuo –5 iki 5) ir taikomų verslo aspektų sąrašas. 

Norėdami gauti daugiau informacijos, žiūrėkite [Nuotaikų analizė klientų atsiliepimuose (peržiūra)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]