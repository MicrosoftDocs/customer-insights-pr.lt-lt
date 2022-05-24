---
title: Dublikatų šalinimas prieš sujungiant duomenis
description: Antrasis suvienijimo proceso žingsnis yra pasirinkti, kurį įrašą saugoti, kai randami dublikatai.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742975"
---
# <a name="remove-duplicates-before-unifying-data"></a>Dublikatų šalinimas prieš sujungiant duomenis

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis suvienijimo veiksmas pasirinktinai leidžia nustatyti pasikartojančių įrašų tvarkymo objekte taisykles. *Deduplication* identifikuoja įrašų dublikatus ir sujungia juos į vieną įrašą. Šaltinio įrašai yra susiejami su sulietu įrašu su alternatyviais ID. Jei taisyklės nesukonfigūruotos, taikomos sistemos apibrėžtos taisyklės.

## <a name="include-enriched-entities-preview"></a>Įtraukti praturtintus objektus (peržiūra)

Jei praturtinote objektus duomenų šaltinis lygiu, kad padėtumėte pagerinti suvienijimo rezultatus, pasirinkite juos. Daugiau informacijos ieškokite [Enrichment for data sources](data-sources-enrichment.md).

1. **Puslapyje Įrašų** dublikatai puslapio viršuje pasirinkite **Naudoti praturtintus** objektus.

1. **Srityje Naudoti praturtintus** objektus pasirinkite vieną ar daugiau praturtintų objektų.

1. Pasirinkite **Atlikta**.

## <a name="define-deduplication-rules"></a>Apibrėžti deduplication taisykles

1. **Puslapyje Įrašų dublikatas** pasirinkite objektą ir pasirinkite **Įtraukti taisyklę**, kad apibrėžtumėte deduplication taisykles.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Puslapių dublikatų ekrano nuotrauka su paryškintu rodymu Rodyti daugiau paryškintų":::

   1. **Srityje Įtraukti taisyklę** įveskite šią informaciją:
      - **Pasirinkite lauką**: Pasirinkite iš objekto, kuriame norite tikrinti dublikatus, galimų laukų sąrašo. Pasirinkite laukus, kurie, tikėtina, yra unikalūs kiekvienam klientui. Pavyzdžiui, el. pašto adresas ar vardo, miesto ir telefono numerio derinys.
      - **Normalizuoti** : Pasirinkite iš šių pasirinktų atributų normalizavimo parinkčių.
        - **Skaitmenys**: konvertuoja kitas skaitmenų sistemas, pvz., romėniškus skaitmenis, į arabiškus skaitmenis. *VIII* tampa *8*.
        - **Simboliai**: pašalina visus simbolius ir specialius simbolius. *„Head&Shoulder”* tampa *„HeadShoulder”*.
        - **Tekstas į mažąsias raides: konvertuoja visus simbolius į mažąsias raides**. *VISOS DIDŽIOSIOS ir Pirmos Didžiosios* tampa *visos didžiosios ir pirmos didžiosios*.
        - **Tipas (telefonas, vardas, adresas, organizacija)**: standartizuoja vardus, pavadinimus, telefono numerius, adresus ir kt.
        - **Unicode į ASCII**: konvertuoja unicode žymėjimą į ASCII simbolius. *„/u00B2”* tampa *2*.
        - **Tarpas**: pašalina visus tarpus. *Labas Pasauli* tampa *LabasPasauli*.
      - **Tikslumas**: Nustatykite šiai sąlygai taikytiną tikslumo lygį.
        - **Pagrindinis**: pasirinkite iš *mažo (30%)*, *vidutinio (60%)*, *didelio (80%)* ir *tikslaus (100%)*. Pasirinkite **Tiksliai**, kad atitiktumėte tik tuos įrašus, kurie atitinka 100 procentų.
        - **Pasirinktinis**: Nustatykite procentą, kurį turi atitikti įrašai. Sistema sugretins tik įrašus, perlipusius ribinę reikšmę.
      - **Pavadinimas**: Taisyklės pavadinimas.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Srities Įtraukti taisykles dublikatams šalinti ekrano nuotrauka.":::

   1. Pasirinktinai pasirinkite **Įtraukti sąlygą** > **Įtraukti**, kad į taisyklę įtrauktumėte daugiau sąlygų. Sąlygos yra susijusios su loginiu IR operatoriumi ir todėl vykdomos tik tuo atveju, jeigu įvykdomos visos sąlygos.

   1. Pasirinktinai įtraukite **išimtį Įtraukti išimtį** > **,** kad į taisyklę [būtų](match-entities.md#add-exceptions-to-a-rule) įtrauktos išimtys. Išimtys naudojamos retiems klaidingų teigiamų ir klaidingų neigiamų atvejų atvejams spręsti.

   1. Norėdami sukurti taisyklę, pasirinkite **Atlikta**.

1. Pasirinktinai [įtraukite daugiau taisyklių](#define-deduplication-rules).

1. Pasirinkite objektą ir redaguokite **suliejimo nuostatas**.

1. **Srityje Sulieti nuostatas**:
   1. Pasirinkite vieną iš trijų parinkčių, kad nustatytumėte, kurį įrašą saugoti, jei randamas dublikatas:
      - **Labiausiai užpildytas**: Nustato įrašą su labiausiai užpildytais atributo laikais kaip nugalėtoją. Tai yra numatytoji suliejimo parinktis.
      - **Naujausias**: Nustato įrašą laimėtoją pagal naujausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
      - **Seniausias**: Nustato įrašą laimėtoją pagal seniausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
      
      Lygiųjų atveju nugalėtojo įrašas yra tas, kuris turi MAX (PK) arba didesnę pirminio rakto reikšmę.
      
   1. Pasirinktinai, norėdami apibrėžti atskirų objekto atributų suliejimo nuostatas, srities apačioje pasirinkite **Išsamiau**. Pavyzdžiui, galite pasirinkti išsaugoti naujausią el. laišką ir išsamiausią adresą iš skirtingų įrašų. Išplėskite objektą, kad pamatytumėte visus jo atributus, ir apibrėžkite, kurią parinktį naudoti atskiriems atributams. Jei pasirinksite taisymu pagrįstą pasirinktį, taip pat turėsite nurodyti datos / laiko lauką, kuris apibrėžia teisingumą.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Išplėstinė suliejimo nuostatų sritis, kurioje rodomas naujausias el. laiškas ir visas adresas":::

   1. Pasirinkite **Atlikta**, kad pritaikytumėte suliejimo nuostatas.

1. Apibrėžę deduplication taisykles ir suliejimo nuostatas, pasirinkite **Pirmyn**.
  
> [!div class="nextstepaction"]
> [Kitas vieno objekto veiksmas: laukų suvienodinimas](merge-entities.md)

> [!div class="nextstepaction"]
> [Kitas žingsnis keliems objektams: sąlygų atitikimas](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Dublikatų naikinimo išvestis kaip objektas

Deduplication procesas sukuria naują deduplicuotą objektą kiekvienam šaltinio objektui. Šiuos objektus galima rasti kartu su **„ConflationMatchPairs:CustomerInsights”** skyriuje **Sistema**, puslapyje **Objektai**, pavadinimu **„Deduplication_DataSource_Entity”**.

Dublikatų naikinimo išvesties objektas turi šią informaciją:

- ID/Raktai
  - Pirminio rakto ir alternatyvaus ID laukai. Alternatyvus ID laukas susideda iš visų įrašo alternatyvių ID.
  - Dublikatų naikinimo grupės ID lauke rodoma grupė arba klasteris, nustatytas objektu, grupuojantis visus panašius įrašus pagal nurodytus dublikatų naikinimo laukus. Jis naudojamas sistemos apdorojimo tikslais. Jei nėra nurodytų neautomatiniu būdu nurodomų dublikatų naikinimo taisyklių ir taikomos sistemos apibrėžtos dublikatų naikinimo taisyklės, šis laukas gali būti nerandamas dublikatų naikinimo išvesties objektui.
  - „Deduplication_WinnerId”: Šiame lauke yra nustatytų grupių arba grupių laimėtojo ID. Jei „Deduplication_WinnerId” reikšmė yra tokia pati kaip įrašo pirminio rakto reikšmė, tai reiškia, kad įrašas yra nugalėtojas.
- Laukai, naudojami dublikatų naikinimo taisyklėms apibrėžti.
- Taisyklių ir Rezultato laukeliai žymi gretinimo algoritmo grąžintą rezultatą ir, kurios iš dublikatų naikinimo taisyklių buvo taikomos.

[!INCLUDE[footer-include](includes/footer-banner.md)]
