---
title: Naujos ir būsimos funkcijos
description: Informacija apie naujas funkcijas, pagerinimus ir klaidų ištaisymus.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643728"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Kas nauja programoje „Dynamics 365 Customer Insights“

Džiaugiamės galėdami pranešti apie mūsų naujausius atnaujinimus! Šiame straipsnyje apibendrinamos viešos peržiūros versijos funkcijos, bendro pasiekiamumo patobulinimai ir funkcijų atnaujinimai. Norėdami peržiūrėti ilgalaikius funkcijų planus, peržiūrėkite [„Dynamics 365“ ir „Power Platform“ išleidimo planai](/dynamics365/release-plans/).

Naujinimus atliekame pagal regionus. Taigi tam tikri regionai gali matyti funkcijas prieš kitus. Jei nenurodyta kitaip, jums nereikia imtis jokių veiksmų ir mes automatiškai atnaujinsime programą be prastovų.

> [!TIP]
> Norėdami teikti ir balsuoti už funkcijų užklausas bei produktų pasiūlymus, eikite į [„Dynamics 365“ programos idėjų portalą](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>2022 m. kovo mėn. atnaujinimai

2022 m. kovo mėn.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec sodrinimas (Peržiūra)

"LiveRamp" teikia tapatybės skiriamąją gebą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su AbiliTec tapatybės grafiku ir gauti AbiliTec ID. Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

Daugiau informacijos ieškokite [Enrich customer profiles with identity data from LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentų ir matų tvarkymas su žymėmis ir filtrais
Jei jūsų organizacija palaiko daug segmentų ar priemonių, rasti tinkamą kartais gali jaustis sudėtinga. Ši nauja funkcija leidžia tvarkyti sąrašus naudojant žymes ir stulpelius. Tai padeda greitai ir lengvai rasti duomenis ir pritaikyti rodinius.

Daugiau informacijos ieškokite [Work with tags and columns](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Duomenų bendrinimo Dataverse įgalinimas naudojant savo saugyklos paskyrą

Jei jūsų aplinka naudoja Azure Data Lake Storage "Customer Insights" duomenims saugoti, duomenų bendrinimui su Microsoft Dataverse reikia papildomos konfigūracijos.
Anksčiau duomenų bendrinimą galėjote įjungti tik tada Dataverse, kai jūsų duomenys buvo saugomi mūsų tvarkomame duomenų ežere. 

Daugiau informacijos ieškokite [Enable data sharing with from Dataverse your own Azure Data Lake Storage (Preview)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Naujos eksporto paskirties vietos: Iterable ir Braze

Mes ir toliau plečiame savo eksporto paskirties vietų ekosistemą naujais ryšiais. Dabar galite eksportuoti segmentus į "Iterable" ir "Braze", kad galėtumėte naudotis jų aktyvinimo paslaugomis.

Daugiau informacijos ieškokite [Export segments to Iterable (preview)](export-iterable.md) ir [Export segments to Braze (preview)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>"Marketo" ir "Google Ads" eksporto patobulinimai

Pakeitus API prijungtose tarnybose, jungiamės jungtys gali veikti patikimai ir sklandžiai. Išleidome keletą eksporto į "Marketo" ir "Google Ads" paslaugas naujinimų:

- "Google Ads": nauja "Google Ads" eksportavimo jungties versija supaprastina autentifikavimo patirtį ir dabar leidžia automatiškai kurti naujas "Google Ads" auditorijas. 
- "Marketo": naujoji "Marketo" eksporto jungties versija palaiko "Marketo ID", leidžiančią išvengti duomenų dubliavimosi, atnaujinti esamus įrašus ir kurti naujus įrašus "Marketo". 


## <a name="february-2022-updates"></a>2022 m. vasario atnaujinimai

2022 m. vasario mėnesio naujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų taisymus.

### <a name="general-availability-for-prediction-models"></a>Bendras prognozė modelių prieinamumas

"Out-of-the-box" prognozė modeliai, įskaitant **prenumeratos trūkčiojimą**, **operacijų trūkčiojimą** ir **kliento gyvenimo vertę (CLV), paprastai tampa prieinami kaip "Customer Insights"** dalis. 

Daugiau informacijos ieškokite [Predictions overview](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Naujas duomenų šaltinis: integracija su Azure Synapse Analytics (Peržiūra)

Azure Synapse Analytics yra įmonės analizės paslauga, kuri pagreitina laiką iki įžvalgų duomenų sandėliuose ir didelių duomenų sistemose.

Organizacijos, kurios jau naudoja Azure Synapse Analytics, gali suvartoti šiuos duomenis į "Customer Insights". 

Daugiau informacijos ieškokite [Connect an Azure Synapse duomenų šaltinis (Preview)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp sodrinimas (Peržiūra)

"LiveRamp" teikia tapatybės skiriamąją gebą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su AbiliTec tapatybės grafiku ir gauti AbiliTec ID. Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

Daugiau informacijos ieškokite [Enrich customer profiles with identity data from LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių sodrinimas (Peržiūra)

Naudokite duomenis iš šaltinių, pvz., "Microsoft" ir kitų partnerių, kad praturtintumėte savo klientų duomenis prieš duomenų suvienijimą. Duomenų šaltinis praturtinimai padeda užtikrinti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų suvienijus duomenis.

Daugiau informacijos ieškokite [Enrichment for data sources (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Keisti aplinkos savininką

Nors keli vartotojai gali turėti administratoriaus teises programoje "Customer Insights", tik vienas vartotojas yra aplinkos savininkas. Patobulinta patirtis leidžia pakeisti aplinkos savininkus ir reikalauti nuosavybės, jei buvęs savininkas paliko organizaciją. 

Daugiau informacijos ieškokite [Change the owner of a environment](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Duomenų rengimo procesas išvardija sugadintų įrašų sugadinimo priežastis

Duomenų rengimas dabar rodo visų laukų, kuriuose yra sugadintų duomenų, korupcijos priežastį. Informacija pateikiama individualiu įrašų lygiu, kad būtų lengva identifikuoti. 

Daugiau informacijos ieškokite [Corrupted data sources](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Įtraukimo įžvalgų galimybės ataskaitų funkcijų peržiūros pabaiga

Įtraukimo Dynamics 365 Customer Insights įžvalgų galimybių peržiūra baigėsi vasario 15 d. 2022 m.  
Šis pakeitimas reiškia, kad "Customer Insights" bandomojoje versijoje nebėra galimybės kurti piltuvus ar kitas ataskaitų funkcijas.

Kviečiame išnagrinėti ir įvertinti daugybę kitų "Customer Insights [", "Microsoft" klientų duomenų platformos (CDP), funkcijų](https://dynamics.microsoft.com/ai/customer-insights/).    
 
Pereinamuoju laikotarpiu esami peržiūros dalyviai vis dar turi prieigą prie kai kurių peržiūros galimybių ir funkcijų:

- Gauti kodą žiniatinklio svetainei arba mobiliųjų įrenginių programėlei kurti 
- Įvykių ir įvykių ypatybių peržiūra 
- Patobulinkite vieningus profilius su prarytais ir rafinuotais įvykiais, kad gautumėte naudos iš visos savo klientų duomenų vertės
  
Pereinamuoju laikotarpiu užfiksuoti įvykiai vis dar transliuojami į prijungtą duomenų ežerą. Kai ši funkcija bus išjungta, duomenų bendrinimas bus sustabdytas ir nauji įvykiai nebus siunčiami į prijungtą saugyklą.
Susisiekite su "Microsoft" abonemento komanda tiesiogiai, jei turite klausimų apie pajėgumų peržiūros pabaigą. Jūsų paskyros komanda jus informuos apie būsimus paleidimus. 

## <a name="january-2022-updates"></a>2022 m. sausio mėn. naujinimai

2022 m. sausio mėn.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Jūsų kliento atsiliepimų sentimentų analizė

"Customer Insights" suteikia naują dirbtiniu intelektu pagrįstą funkciją, skirtą sintezuoti klientų nuotaikas ir nustatyti konkrečius verslo aspektus kaip tikslinių patobulinimų galimybes. Analizuodami savo klientų atsiliepimus raštu, galite gauti tikslių įžvalgų už mažą kainą. Sentimentų analizė, pagrįsta natūralios kalbos apdorojimo (NLP) modeliais, kurie generuoja dvi išvestines įžvalgas kiekvienam kliento ID. Sentimentų balas (nuo -5 iki 5) ir taikomų verslo aspektų sąrašas. 

Daugiau informacijos ieškokite [Analyze sentiment in customer feedback (Preview)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]