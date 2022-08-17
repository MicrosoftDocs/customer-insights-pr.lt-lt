---
title: Dublikatų šalinimas prieš suvienodinant duomenis
description: Antrasis suvienijimo proceso žingsnis yra pasirinkimas, kurį įrašą saugoti, kai randami dublikatai.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 7f4829cfc14af623f724c6594e834f3fac1c15a9
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213637"
---
# <a name="remove-duplicates-before-unifying-data"></a>Dublikatų šalinimas prieš suvienodinant duomenis

Šis pasirinktinis suvienijimo veiksmas leidžia nustatyti taisykles, kaip pašalinti pasikartojančius įrašus **objekte**. Dubliavimas identifikuoja kelis kliento įrašus ir parenka geriausią saugotiną įrašą (pagal pagrindines suliejimo nuostatas) arba sulieja įrašus į vieną (pagal išplėstines suliejimo nuostatas). Šaltinio įrašai yra susiejami su sulietu įrašu su alternatyviais ID. Jei taisyklės nesukonfigūruotos, taikomos sistemos apibrėžtos taisyklės.

## <a name="default-deduplication"></a>Numatytasis dubliavimas

Sistemos nustatytos taisyklės taikomos, jei neįtraukiamos dubliavimo taisyklės.

- Pirminis raktas yra dubliuojamas.
  Visų įrašų, turinčių tą patį pirminį raktą **, nugalėtojas yra labiausiai užpildytas** įrašas (tas, kurio nulinės reikšmės yra mažiausios).
- Ūkio subjektui taikomos visos kelių objektų atitikties taisyklės.
  Pavyzdžiui: atitikties veiksme, jei objektas A yra suderinamas su objektu B *"FullName"* ir *"DateofBirth*", tada objektas A taip pat dubliuojamas pagal *"FullName" ir*"*DateofBirth*". Kadangi *"FullName" ir*"*DateofBirth*" yra galiojantys raktai, leidžiantys identifikuoti klientą objekte A, šie raktai taip pat galioja identifikuojant besidubliuojančius klientus objekte A.

## <a name="include-enriched-entities-preview"></a>Papildytųjų objektų įtraukimas (peržiūra)

Jei praturtinote objektus duomenų šaltinis lygiu, kad pagerintumėte suvienijimo rezultatus, pasirinkite juos. Daugiau informacijos ieškokite [Duomenų šaltinių](data-sources-enrichment.md) papildymas.

1. **Puslapyje Dubliuoti įrašus** puslapio viršuje pasirinkite **Naudoti papildytus objektus**.

1. Srityje Naudoti papildytus **objektus** pasirinkite vieną ar daugiau papildytų objektų.

1. Pasirinkite **Atlikta**.

## <a name="define-deduplication-rules"></a>Dubliavimo taisyklių apibrėžimas

1. **Puslapyje Dubliuoti įrašus** pasirinkite objektą ir pasirinkite **Įtraukti taisyklę**, kad apibrėžtumėte dublikatų taisykles.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Pasikartojančių įrašų puslapių su paryškintu Rodyti daugiau ekrano nuotrauka":::

   1. **Srityje Įtraukti taisyklę** įveskite šią informaciją:
      - **Pasirinkimo laukas**: pasirinkite iš galimų laukų sąrašo iš objekto, kurio dublikatus norite patikrinti. Pasirinkite laukus, kurie, tikėtina, yra unikalūs kiekvienam klientui. Pavyzdžiui, el. pašto adresas ar vardo, miesto ir telefono numerio derinys.
      - **Normalizuoti** : Pasirinkite iš šių pasirinktų atributų normalizavimo parinkčių.
        - **Skaitmenys**: konvertuoja kitas skaitmenų sistemas, pvz., romėniškus skaitmenis, į arabiškus skaitmenis. *VIII* tampa *8*.
        - **Simboliai**: pašalina visus simbolius ir specialiuosius simbolius. *„Head&Shoulder”* tampa *„HeadShoulder”*.
        - **Tekstas į mažąsias raides: konvertuoja visus simbolius į mažąsias raides**. *VISOS DIDŽIOSIOS ir Pirmos Didžiosios* tampa *visos didžiosios ir pirmos didžiosios*.
        - **Tipas (telefonas, vardas, adresas, organizacija)**: standartizuoja vardus, pavadinimus, telefono numerius, adresus ir kt.
        - **Unicode į ASCII**: konvertuoja unicode žymėjimą į ASCII simbolius. *„/u00B2”* tampa *2*.
        - **Tarpai**: pašalina visus tarpus. *Labas Pasauli* tampa *LabasPasauli*.
      - **Tikslumas**: Nustatykite šiai sąlygai taikytiną tikslumo lygį.
        - **Pagrindinis**: Rinkitės iš *žemo (30%)*, *vidutinio (60%)*, *aukšto (80%)*, ir *tikslaus (100%)*. Pasirinkite **Tiksliai**, kad atitiktų tik tuos įrašus, kurie atitinka 100 procentų.
        - **Pasirinktinis**: Nustatykite procentą, kurį turi atitikti įrašai. Sistema sugretins tik įrašus, perlipusius ribinę reikšmę.
      - **Pavadinimas**: taisyklės pavadinimas.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Taisyklės įtraukimo srities, skirtos dublikatams pašalinti, ekrano nuotrauka.":::

   1. Pasirinktinai pasirinkite **Įtraukti sąlygą** > **Įtraukti**, kad į taisyklę įtrauktumėte daugiau sąlygų. Sąlygos yra susijusios su loginiu IR operatoriumi ir todėl vykdomos tik tuo atveju, jeigu įvykdomos visos sąlygos.

   1. Pasirinktinai įtraukite **įtraukti išimtį** > **,** kad įtrauktumėte [taisyklės](match-entities.md#add-exceptions-to-a-rule) išimčių. Išimtys naudojamos retiems klaidingų teigiamų ir klaidingų neigiamų rezultatų atvejams spręsti.

   1. Pasirinkite **Atlikta**, kad sukurtumėte taisyklę.

1. Pasirinktinai [įtraukite daugiau taisyklių](#define-deduplication-rules).

1. Pasirinkite objektą, tada **Redaguoti suliejimo nuostatas**.

1. **Srityje Suliejimo nuostatos**:
   1. Pasirinkite vieną iš trijų parinkčių, kad nustatytumėte, kurį įrašą saugoti, jei randamas dublikatas:
      - **Labiausiai užpildytas**: Nustato įrašą su labiausiai užpildytais atributo laikais kaip nugalėtoją. Tai yra numatytoji suliejimo parinktis.
      - **Naujausias**: Nustato įrašą laimėtoją pagal naujausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
      - **Seniausias**: Nustato įrašą laimėtoją pagal seniausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
      
      Kaklaraiščio atveju nugalėtojo rekordas yra tas, kuris turi MAX(PK) arba didesnę pirminio rakto reikšmę.
      
   1. Pasirinktinai, norėdami apibrėžti atskirų objekto atributų suliejimo nuostatas, srities apačioje pasirinkite **Išsamiau**. Pavyzdžiui, galite pasirinkti išsaugoti naujausią el. laišką IR išsamiausią adresą iš skirtingų įrašų. Išplėskite objektą, kad pamatytumėte visus jo atributus, ir apibrėžkite, kurią parinktį naudoti atskiriems atributams. Jei pasirinksite recency pagrįstą parinktį, taip pat turėsite nurodyti datos / laiko lauką, kuris apibrėžia naujumą.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Išplėstinė suliejimo nuostatų sritis, kurioje rodomi naujausi el. laiškai ir visas adresas":::

   1. Pasirinkite **Atlikta**, kad pritaikytumėte suliejimo nuostatas.

1. Apibrėžę dublikatų taisykles ir suliejimo nuostatas, pasirinkite **Pirmyn**.
  
> [!div class="nextstepaction"]
> [Kitas vieno objekto veiksmas: laukų suvienodinimas](merge-entities.md)

> [!div class="nextstepaction"]
> [Kitas veiksmas keliems objektams: atitikimo sąlygos](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Dublikatų naikinimo išvestis kaip objektas

Dubliavimo procesas sukuria naują dubliuojamą objektą kiekvienam šaltinio objektui. Šiuos objektus galima rasti kartu su **„ConflationMatchPairs:CustomerInsights”** skyriuje **Sistema**, puslapyje **Objektai**, pavadinimu **„Deduplication_DataSource_Entity”**.

Dublikatų naikinimo išvesties objektas turi šią informaciją:

- ID/Raktai
  - Laukai Pirminis raktas ir Alternatyvus ID. Alternatyvųjį ID lauką sudaro visi alternatyvūs įrašo ID.
  - Dublikatų naikinimo grupės ID lauke rodoma grupė arba klasteris, nustatytas objektu, grupuojantis visus panašius įrašus pagal nurodytus dublikatų naikinimo laukus. Jis naudojamas sistemos apdorojimo tikslais. Jei nėra nurodytų neautomatiniu būdu nurodomų dublikatų naikinimo taisyklių ir taikomos sistemos apibrėžtos dublikatų naikinimo taisyklės, šis laukas gali būti nerandamas dublikatų naikinimo išvesties objektui.
  - „Deduplication_WinnerId”: Šiame lauke yra nustatytų grupių arba grupių laimėtojo ID. Jei „Deduplication_WinnerId” reikšmė yra tokia pati kaip įrašo pirminio rakto reikšmė, tai reiškia, kad įrašas yra nugalėtojas.
- Laukai, naudojami dublikatų naikinimo taisyklėms apibrėžti.
- Taisyklių ir Rezultato laukeliai žymi gretinimo algoritmo grąžintą rezultatą ir, kurios iš dublikatų naikinimo taisyklių buvo taikomos.

[!INCLUDE[footer-include](includes/footer-banner.md)]
