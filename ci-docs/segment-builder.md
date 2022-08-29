---
title: Sudėtingų segmentų kūrimas naudojant segmentų kūrimo priemonę
description: Naudokite segmentų kūrimo priemonę, kad sukurtumėte sudėtingus klientų segmentus grupuodami juos pagal įvairius atributus.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 7f691fd0b2ea76a2960d5adf766a4b166f02ebb4
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304759"
---
# <a name="create-complex-segments-with-segment-builder"></a>Sudėtingų segmentų kūrimas naudojant segmentų kūrimo priemonę

Apibrėžkite sudėtingus filtrus aplink vieningą klientą arba vieningąjį kontaktą ir su juo susijusius objektus. Kiekvienas segmentas po apdorojimo sukuria kliento arba kontakto įrašų rinkinį, kurį galite eksportuoti ir su kuriais galite imtis veiksmų.

> [!TIP]
> Segmentuose, pagrįstuose **atskirais klientais**, automatiškai įtraukiama prieinama segmento narių kontaktinė informacija. Jei verslo paskyrose **suvienijote** [ir](data-unification.md) klientus, ir kontaktus, pasirinkite, ar segmentas pagrįstas klientais, ar verslo kontaktais. Norėdami eksportuoti į paskirties vietą, tikėdamiesi kontaktinės informacijos, naudokite kontaktų segmentą. Norėdami eksportuoti į paskirties vietą, tikėdamiesi paskyros informacijos, naudokite paskyrų segmentą.

## <a name="segment-builder"></a>Segmentų kūrimo priemonė

Toliau pateiktas vaizdas iliustruoja įvairius segmentų kūrimo priemonės aspektus. Jame rodomas segmentas, sukuriantis klientų grupę. Klientai užsaavo prekes konkrečiu laikotarpiu ir surinko apdovanojimo taškus arba praleido tam tikrą pinigų sumą.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmento kūrimo elementai ." lightbox="media/segment-builder-overview.png":::

1. Suskirstykite segmentą su taisyklėmis ir potaisyklėmis. Kiekvieną taisyklę ar potaisyklę sudaro sąlygos. Sujunkite sąlygas su loginiais operatoriais.

1. Pasirinkite [ryšio kelią](relationships.md) tarp objektų, kuriems taikoma taisyklė. Ryšio kelias nurodo, kuriuos atributus galima naudoti sąlygoje.

1. Valdykite taisykles ir potaisykles. Pakeiskite taisyklės padėtį arba panaikinkite ją.

1. Įtraukite sąlygų ir kurkite tinkamą įdėjimo lygį naudojant potaisykles.

1. Pritaikykite prijungtų taisyklių rinkinio operacijas.

1. Naudokite atributų sritį, jei norite įtraukti galimų objekto atributų arba sukurti sąlygas pagal atributus. Srityje rodomas objektų ir atributų, galimų pasirinkti taisyklei, sąrašas pagal pasirinktą ryšio kelią.

1. Įtraukite sąlygų, pagrįstų esamų taisyklių ir antrinių taisyklių atributais, arba įtraukite į naują taisyklę.

1. Kuriant segmentą anuliuokite ir perdarykite pakeitimus.

Aukščiau pateiktas pavyzdys iliustruoja segmentavimo galimybę. Sukūrėme segmentą klientams, kurie bent už $500 nusipirko prekių internetu *ir* yra suinteresuoti programinės įrangos kūrimu.

## <a name="create-a-new-segment-with-segment-builder"></a>Naujo segmento kūrimas naudojant segmentų kūrimo priemonę

1. Eikite į **Segmentai**.

1. Pažymėkite **Naujas** > **Sukurkite savo**. Segmento segmento apibrėžiate arba kuriate taisykles. Taisyklę sudaro viena ar daugiau sąlygų, apibrėžiaančių klientų rinkinį.

   > [!NOTE]
   > Jei naudojate verslo paskyras pagrįstas aplinkas, pasirinkite **Naujas** > **sąskaitų** segmentas arba **Kontaktų segmentas (peržiūra)** pagal segmento, kurį norite sukurti, tipą. [Jei buvo apibrėžta paskyros hierarchija](relationships.md#set-up-account-hierarchies) ir norite sukurti taisykles, pagal kurias būtų galima filtruoti duomenis pagal vaiko ir tėvų ryšį, pasirinkite **Naudoti hierarchiją? (peržiūra)**, pasirinkite hierarchiją, tada **Taikyti**.
   >
   > :::image type="content" source="media/segment_acct_hierarchy.png" alt-text="Segmentuoti pasirinkite paskyros hierarchijos sritį.":::

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Segmentas Be pavadinimo. Įveskite savo segmento pavadinimą ir atnaujinkite siūlomą **Išvesties objekto pavadinimą** segmentui. Pasirinktinai prie segmento pridėkite aprašą ir [žymes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

1. Sekcijoje **Taisyklė1** pasirinkite objekto, pagal kurį norite filtruoti klientus, atributą. Pasirinkti atributus galite dviem būdais:
   - Peržiūrėkite galimų objektų ir atributų sąrašą srityje **Įtraukti į taisyklę** ir pažymėkite **„+”** piktogramą šalia atributo, kurį norite įtraukti. Pasirinkite, ar norite įtraukti atributą į esamą taisyklę, ar naudoti jį naujai taisyklei kurti.
   - Norėdami peržiūrėti sutampančius pasiūlymus, taisyklės skyriuje įveskite atributo pavadinimą.

1. Pasirinkite operatorius, kad nurodytumėte sąlygos atitikmenų reikšmes. Atributas gali turėti vieną iš keturių duomenų tipų kaip reikšmę: skaitinę, eilutės, datos arba Bulio logikos. Priklausomai nuo atributo duomenų tipo, sąlygą galima nurodyti skirtingais operatoriais.

1. Pasirinkite **Įtraukti sąlygą**, jei į taisyklę norite įtraukti daugiau sąlygų. Norėdami sukurti taisyklę pagal dabartinę taisyklę, pažymėkite **Įtraukti antrinę taisyklę**.

1. Jei taisyklė naudoja kitus objektus nei *objektas Klientas* (arba *objektas ContactProfile*, skirtas B-to-B), pasirinkite **Nustatyti ryšių kelią**, kad susietas pasirinktas objektas būtų susietas su vieninguoju kliento objektu. Jei yra tik vienas galimas ryšio kelias, sistema jį pasirenka automatiškai. Skirtingi [santykių keliai](relationships.md#relationship-paths) gali duoti skirtingus rezultatus. Kiekviena taisyklė gali turėti savo ryšio kelią.

   :::image type="content" source="media/relationship-path.png" alt-text="Galimas ryšio kelias kuriant taisyklę, pagrįstą objektu, susietu su vieninguoju kliento objektu.":::

1. Jei taisyklėje yra kelios sąlygos, pasirinkite, kuris loginis operatorius jas prijungs.  
   - **IR** operatorius: norint į segmentą įtraukti įrašą, visos sąlygos turi būti įvykdytos. Naudokite šią parinktį, kai apibrėžiate skirtingų objektų sąlygas.
   - **ARBA** operatorius: norint į segmentą įtraukti įrašą, viena iš pateiktų sąlygų turi būti įvykdyta. Naudokite šią parinktį, kai apibrėžiate kelias to paties objekto sąlygas.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Taisyklė su dvejomis IR sąlygomis.":::

   Naudojant ARBA operatorių visos sąlygos turi būti pagrįstos į ryšio kelią įtrauktais objektais.

1. Norėdami sukurti skirtingus klientų įrašų rinkinius, sukurkite kelias taisykles. Norėdami įtraukti klientus, reikalingus jūsų verslo atvejui, sujunkite grupes. Tiksliau, jei negalite įtraukti objekto į taisyklę dėl nurodyto ryšio kelio, sukurkite naują taisyklę, kad pasirinktumėte atributus iš jo.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Į segmentą įtraukite naują taisyklę ir pasirinkite rinkinio operatorių.":::

   1. Pasirinkite **Įtraukti taisyklę**.
   1. Pažymėkite vieną iš rinkinio operatorių: **Sąjunga**, **Susikirtimas** arba **Išskyrus**.

      - **Sujungimas** sujungia dvi grupes.
      - **Susikirtimas** persidengia su dviem grupėmis. Vieningoje *grupėje* lieka tik duomenys, kurie dažnai pasitaiko abiejose grupėse.
      - **Išskyrus** sujungia dvi grupes. Saugomi tik A grupės *duomenys* kurie nėra įprasta B grupės duomenims.

1. Pagal numatytuosius nustatymus išvesties objekte bus automatiškai visi klientų profilių atributai, atitinkantys apibrėžtus filtrus. Naudojant objektą *"ContactProfile* " nuo B iki B, automatiškai įtraukiamas paskyros ID. Jei segmentas pagrįstas kitais objektais nei *kliento* objektas arba įtraukti daugiau atributų iš *ContactProfile*, pasirinkite **Projekto atributai**, kad įtrauktumėte daugiau atributų iš šių objektų į išvesties objektą.
 
   Pavyzdžiui: segmentas pagrįstas objektu, kuriame yra pirkimo duomenų, susijusių su *kliento* objektu. Segmentas ieško visų klientų iš Ispanijos, kurie per dabartinius metus įsigijo prekių. Galite pasirinkti pridėti atributus, pvz., prekių kainą arba pirkimo datą, prie visų sutampančių kliento įrašų išvesties objekte. Ši informacija gali būti naudinga analizuojant bendrų išlaidų sezonines sąsajas.

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Projektuotų atributų, pasirinktų šoninėje srityje, kuriuos reikia įtraukti į išvesties objektą, pavyzdys.":::
 
   Segmento, pagrįsto verslo klientais, su projektais kontaktų atributais, rezultatų pavyzdys gali atrodyti taip:

   |ID  |Paskyros pavadinimas  |Įplaukos  |Kontakto pavadinimas  | Kontakto vaidmuo|
   |---------|---------|---------|---------|---|
   |10021     | „Contoso“ | 100K (100K) | [Abbie Moss, Ruth Soto]  | [CEO, Tiekimo vadovas]

   > [!NOTE]
   > - **Projekto atributai** veikia tik objektuose, kurie turi ryšį "vienas su daugeliu" su *objektu Klientas* arba *ContactProfile*. Pavyzdžiui, vienas klientas gali turėti kelias prenumeratas.
   > - Jei atributas, kurį norite projektuoti, yra daugiau nei vienas nukrypimas nuo *objekto Klientas* arba *ContactProfile*, kaip apibrėžta pagal ryšį, tas atributas turėtų būti naudojamas kiekvienoje kuriamos segmento užklausos taisyklėje.
   > - Jei atributas, kurį norite projektuoti, yra tik vienas nukrypimas nuo *objekto Klientas* arba *ContactProfile*, to atributo nebūtinai turi būti kiekvienoje kuriamos segmento užklausos taisyklėje.
   > - **Suplanuoti atributai** yra įtraukiami naudojant rinkinio operatorius.

1. Pasirinkite **Vykdyti**, kad sukurtumėte segmentą. Pasirinkite **Įrašyti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau paleisti segmentą. Rodomas puslapis **Segmentai**.

### <a name="segment-builder-tips"></a>Segmentų kūrimo patarimai

Kurdami segmentą naudodami segmento kūrimo priemonę, atminkite šiuos patarimus:

- Nustatant sąlygų operatorius, segmentų kūrimo priemonė nesiūlys galiojančių objektų reikšmių. Galite eiti į **Duomenis** > **Objektai** ir atsisiųsti objekto duomenis, kad pamatytumėte, kurios reikšmės yra galimos.
- Sąlygos, pagrįstos datomis, leidžia perjungti fiksuotas datas ir slankiąją dienų seką.
- Jei turite kelias segmento taisykles, redaguojate taisyklę šalia jos yra vertikali mėlyna linija.
- Taisykles ir sąlygas galite perkelti į kitas segmento aprašo vietas. Pasirinkite vertikalią daugtaškį (&vellip;) šalia taisyklės arba sąlygos ir pasirinkite, kaip ir kur ją perkelti.
- Naudojant komandų juostoje valdiklius **Anuliuoti** ir Perdaryti galima **atšaukti** keitimus.
- Sukūrus segmentą, kai kurie segmentai leidžia stebėti [segmento](segments.md#track-usage-of-a-segment) naudojimą.

## <a name="next-steps"></a>Paskesni veiksmai

[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [klientų kortelių integravimu](customer-card-add-in.md) naudoti segmentus kitose programose.

[!INCLUDE [footer-include](includes/footer-banner.md)]
