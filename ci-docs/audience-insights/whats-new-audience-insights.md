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
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547682"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Kas naujo publikos įžvalgų „Dynamics 365 Customer Insights“ pajėgumuose

Džiaugiamės galėdami pranešti apie mūsų naujausius atnaujinimus! Šiame straipsnyje apibendrinamos viešos peržiūros versijos funkcijos, bendro pasiekiamumo patobulinimai ir funkcijų atnaujinimai. Norėdami peržiūrėti ilgalaikius funkcijų planus, peržiūrėkite [„Dynamics 365“ ir „Power Platform“ išleidimo planai](/dynamics365/release-plans/).

Naujinimus atliekame pagal regionus. Taigi tam tikri regionai gali matyti funkcijas prieš kitus. Jei nenurodyta kitaip, jums nereikia imtis jokių veiksmų ir mes automatiškai atnaujinsime programą be prastovų.

> [!TIP]
> Norėdami teikti ir balsuoti už funkcijų užklausas bei produktų pasiūlymus, eikite į [„Dynamics 365“ programos idėjų portalą](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>2022 m. kovo mėn. atnaujinimai

2022 m. kovo mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų taisymus.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec sodrinimas (Peržiūra)

LiveRamp teikia tapatybės sprendimą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo klientų duomenyse su AbiliTec tapatybės grafiku ir gauti AbiliTec ID. Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

Daugiau informacijos ieškokite [Enrich customer profiles with identity data from LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentų ir matų tvarkymas naudojant žymes ir filtrus
Jei jūsų organizacija palaiko daug segmentų ar priemonių, rasti tinkamą kartais gali būti sudėtinga. Ši nauja funkcija leidžia tvarkyti sąrašus naudojant žymes ir stulpelius. Tai padeda greitai ir lengvai rasti duomenis ir tinkinti rodinius.

Daugiau informacijos ieškokite [Work with tags and columns](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Duomenų bendrinimo įgalinimas Dataverse naudojant savo saugyklos abonementą

Jei jūsų aplinka naudoja Azure Data Lake Storage "Customer Insights" duomenims saugoti, dalijimasis duomenimis su Microsoft Dataverse reikia papildomos konfigūracijos.
Anksčiau galėjote įgalinti dalijimąsi duomenimis tik tada Dataverse, kai jūsų duomenys buvo saugomi mūsų tvarkomame duomenų ežere. 

Daugiau informacijos ieškokite [Įgalinti duomenų bendrinimą naudojant Dataverse iš savo Azure Data Lake Storage (Peržiūra)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Naujos eksporto paskirties vietos: "Iterable" ir "Braze"

Mes ir toliau plečiame savo eksporto paskirties vietų ekosistemą naujais ryšiais. Dabar galite eksportuoti segmentus į "Iterable" ir "Braze", kad galėtumėte naudoti jų aktyvinimo paslaugas.

Daugiau informacijos ieškokite [Eksportuoti segmentus į pasikartojančius (peržiūra)](export-iterable.md) ir [Eksportuoti segmentus į Brazę (peržiūra)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>"Marketo" ir "Google Ads" eksporto patobulinimai

Pakeitus API prijungtose tarnybose, jungčių naujinimai veikia patikimai ir sklandžiai. Išleidome keletą eksporto į "Marketo" ir "Google Ads" paslaugas atnaujinimų:

- "Google Ads": nauja "Google Ads" eksportavimo jungties versija supaprastina autentifikavimo patirtį ir dabar leidžia automatiškai kurti naujas "Google Ads" auditorijas. 
- "Marketo": naujoji "Marketo" eksporto jungties versija palaiko "Marketo ID", leidžiančią išvengti duomenų dubliavimosi, atnaujinti esamus įrašus ir kurti naujus įrašus "Marketo". 


## <a name="february-2022-updates"></a>2022 m. vasario atnaujinimai

2022 m. vasario mėn.

### <a name="general-availability-for-prediction-models"></a>Bendras prognozė modelių prieinamumas

"Out-of-the-box" prognozė modeliai, įskaitant **prenumeratos mušimą**, **operacijų srautą** ir **kliento gyvenimo trukmės vertę (CLV),** tampa visuotinai prieinami kaip "Customer Insights" dalis. 

Daugiau informacijos ieškokite [Predictions overview](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nauji duomenų šaltinis: integracija su Azure Synapse Analytics (Peržiūra)

Azure Synapse Analytics tai įmonės analizės paslauga, kuri pagreitina laiką įžvalgoms apie duomenų saugyklas ir didelių duomenų sistemas.

Organizacijos, kurios jau naudoja Azure Synapse Analytics, gali nuryti šiuos duomenis į "Customer Insights". 

Daugiau informacijos ieškokite [Connect a Azure Synapse duomenų šaltinis (Preview)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp sodrinimas (Peržiūra)

LiveRamp teikia tapatybės sprendimą ir klientų duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo klientų duomenyse su AbiliTec tapatybės grafiku ir gauti AbiliTec ID. Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis.

Daugiau informacijos ieškokite [Enrich customer profiles with identity data from LiveRamp (Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Duomenų šaltinių sodrinimas (peržiūra)

Naudokite duomenis iš tokių šaltinių kaip "Microsoft" ir kiti partneriai, kad praturtintumėte savo klientų duomenis prieš duomenų suvienodinimą. Duomenų šaltinis praturtėjimas padeda užtikrinti didesnį duomenų išsamumą ir kokybę, kuri gali padėti pasiekti geresnių rezultatų, kai suvienodinsite duomenis.

Daugiau informacijos ieškokite [Enrichment for data sources (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Keisti aplinkos savininką

Nors keli vartotojai gali turėti administratoriaus teises "Customer Insights", tik vienas vartotojas yra aplinkos savininkas. Patobulinta patirtis leidžia pakeisti aplinkos savininkus ir reikalauti nuosavybės, jei buvęs savininkas paliko organizaciją. 

Daugiau informacijos ieškokite [Keisti aplinkos](manage-environments.md#change-the-owner-of-an-environment) savininką.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Duomenų rengimo procesas išvardija sugadintų įrašų korupcijos priežastis

Duomenų rengimas dabar rodo visų laukų su sugadintais duomenimis korupcijos priežastį. Informacija pateikiama individualiu įrašų lygiu, kad būtų lengviau identifikuoti. 

Daugiau informacijos ieškokite [Corrupted data sources](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Įtraukimo įžvalgų galimybės ataskaitų funkcijų ataskaitų funkcijų peržiūros pabaiga

Dynamics 365 Customer Insights Įtraukimo įžvalgų galimybių peržiūra baigėsi 2022 m. vasario 15 d.  
Šis pakeitimas reiškia, kad "Customer Insights" bandomojoje patirtyje nebėra galimybės kurti piltuvus ar kitas ataskaitų teikimo funkcijas.

Kviečiame ištirti ir įvertinti daugelį kitų "Customer Insights", "Microsoft" klientų duomenų platformos (CDP) funkcijų [...](https://dynamics.microsoft.com/ai/customer-insights/).    
 
Pereinamuoju laikotarpiu esami peržiūros dalyviai vis dar turi prieigą prie kai kurių peržiūros galimybių ir funkcijų:

- Gauti kodą žiniatinklio svetainei arba mobiliųjų įrenginių programėlei kurti 
- Peržiūrėti įvykių ir įvykių ypatybes 
- Padidinkite vieningus profilius su prarytais ir rafinuotais įvykiais, kad galėtumėte pasinaudoti visa klientų duomenų verte
  
Pereinamuoju laikotarpiu užfiksuoti įvykiai vis dar transliuojami į prijungtą Duomenų ežerą. Išjungus šią funkciją, duomenų bendrinimas tarp įtraukimo įžvalgų ir auditorijos įžvalgų bus sustabdytas ir į prijungtą saugyklą nebus siunčiami jokie nauji įvykiai.
Jei turite klausimų apie galimybės peržiūros pabaigą, tiesiogiai kreipkitės į savo "Microsoft" abonemento komandą. Jūsų paskyros komanda informuos jus apie būsimus paleidimus. 

## <a name="january-2022-updates"></a>2022 m. sausio mėn. naujinimai

2022 m. sausio mėnesio atnaujinimai apima naujas funkcijas, našumo atnaujinimus ir klaidų taisymus.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Jūsų kliento atsiliepimų sentimentų analizė

"Customer Insights" suteikia naują dirbtiniu intelektu pagrįstą funkciją, skirtą sintezuoti klientų nuotaikas ir nustatyti konkrečius verslo aspektus kaip tikslinių patobulinimų galimybes. Analizuodami savo klientų rašytinius atsiliepimus, galite gauti tikslių įžvalgų už mažą kainą. Sentimentų analizė, kurią įgalina natūralios kalbos apdorojimo (NLP) modeliai, generuojantys dvi išvestines įžvalgas kiekvienam kliento ID. Sentimentų balas (nuo -5 iki 5) ir taikomų verslo aspektų sąrašas. 

Daugiau informacijos ieškokite [Analizuoti jausmus klientų atsiliepimuose (Peržiūra)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]