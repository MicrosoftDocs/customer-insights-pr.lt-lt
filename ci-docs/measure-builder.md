---
title: Kurti naujas priemones naudojant matavimo priemonę
description: Kurkite priemones nuo nulio, kad galėtumėte analizuoti pagrindines verslo metrikas.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: d003d054145343cc2feeefeeee413810df43185a
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800336"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Naudokite matavimo generatorių, kad sukurtumėte priemones nuo nulio

Šiame straipsnyje paaiškinama, kaip sukurti naują [priemonę](measures.md) nuo nulio. Matavimo daryklė leidžia nustatyti skaičiavimus naudojant matematinius operatorius, agregavimo funkcijas ir filtrus. Galite sukurti matą su atributais iš objektų, susijusių su vieningu *kliento* objektu.

Priemonių kūrimas B-to-C ir B-to-B aplinkose veikia taip pat. Tačiau, jei esate B-to-B aplinka [, kurioje naudojamos paskyros su hierarchijomis](relationships.md#set-up-account-hierarchies), galite pasirinkti sujungti matą į susijusias antrines sąskaitas.

Taip pat galite greitai sukurti priemonę pasirinkdami iš dažniausiai naudojamų ir iš anksto nustatytų priemonių rinkinio. Norėdami gauti daugiau informacijos, žr [...](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Galite kurti priemones atskirų pirkėjų lygiu (kliento atributas, kliento matas) arba verslo / organizacijos lygiu (verslo matas). Kliento atributas ir kliento matas yra du tipai, leidžiantys stebėti kiekvieno kliento našumą. Pavyzdžiui, bendros kiekvieno kliento išlaidos. Verslo priemonės leidžia stebėti kiekvienos įmonės veiklos rezultatus. Pavyzdžiui, visos įmonės pajamos.

- Kliento atributas: generuoja išvestį kaip naują atributą, kuris įrašomas kaip naujas sistemos sugeneruoto objekto, pavadinto Customer_Measure, *stulpelis*. Atnaujinant kliento atributą, visi kiti kliento atributai, esantys Customer_Measure *objekte*, atnaujinami vienu metu. Be to, kliento atributai rodomi kliento profilio kortelėje. Paleidus arba įrašius, kliento atributo negalite pakeisti į kliento matą.

- Kliento matas: generuoja išvestį kaip savo objektą ir negalite jos pakeisti į kliento atributą, kai būsite paleisti arba įrašyti. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodo pagrindiniame "Customer Insights" aplinkos puslapyje.

1. Eikite į **priemones**.

1. Pasirinkite **Naujas** ir pasirinkite **Kurti savo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tuščias konfigūracijos ekranas B-to-C matui." lightbox="media/measure-b2c.png":::

1. Norėdami stebėti verslo lygio našumą, perjunkite **priemonės tipą** į **verslo lygį**. **Kliento lygis** pasirenkamas pagal numatytuosius nustatymus. **Kliento lygis** automatiškai įtraukia atributą *CustomerId* į Dimensijas, o **verslo lygis** automatiškai jį pašalina.

1. Konfigūracijos srityje išplečiamajame meniu Pasirinkti funkciją **pasirinkite agregavimo funkciją**. Agregavimo funkcijos yra šios:
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę
   - **"ArgMax"**: randa duomenų įrašą, suteikiantį maksimalią reikšmę iš tikslinės funkcijos
   - **"ArgMin"**: randa duomenų įrašą, suteikiantį minimalią reikšmę iš tikslinės funkcijos

1. Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.

   1. Pasirinkti **Atributus**.
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės** arba galite ieškoti objekto arba priemonės pavadinimo.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matui apskaičiuoti bus naudojami tik tie įrašai, kurie atitinka filtrus.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kurie į matavimo išeigos objektą įtraukiami kaip stulpeliai.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
   > [!TIP]
   > Jei pirkėjo lygį pasirinkote **kaip matavimo tipą** **,** atributas CustomerId *jau* įtrauktas. Jei pašalinsite atributą, **matavimo tipas** perjungs į **verslo lygį**.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.

1. Skaičiavime pasirinkite vertikalią daugtaškį (&vellip;) į **Dubliuoti**, **Pervardyti** arba **Pašalinti** skaičiavimą iš matavimo.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Šalia Matas Be pavadinimo pasirinkite **Redaguoti išsamią informaciją**. Nurodykite priemonės pavadinimą. Pasirinktinai į matą įtraukite [žymes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Išsamios informacijos redagavimas.":::

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Galite kurti priemones atskirų sąskaitų (kliento mato) arba visų sąskaitų (verslo priemonės) lygiu.

- Kliento matas: generuoja išvestį kaip savo objektą. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodo pagrindiniame "Customer Insights" aplinkos puslapyje.

1. Eikite į **priemones**.

1. Pasirinkite **Nauja**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tuščias konfigūracijos ekranas B-to-B matui.":::

1. Konfigūracijos srityje išplečiamajame meniu Pasirinkti funkciją **pasirinkite agregavimo funkciją**. Agregavimo funkcijos yra šios:
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę

1. Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.

   1. Pasirinkti **Atributus**.
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės** arba galite ieškoti objekto arba priemonės pavadinimo.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matui apskaičiuoti bus naudojami tik tie įrašai, kurie atitinka filtrus.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kurie į matavimo išeigos objektą įtraukiami kaip stulpeliai.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
      > [!TIP]
      > Jei pirkėjo lygį pasirinkote **kaip matavimo tipą** **,** atributas CustomerId *jau* įtrauktas. Jei pašalinsite atributą, **matavimo tipas** pereis į **verslo lygį**.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Galite naudoti antrinių **abonementų sujungimą** jei naudojate [abonementus su hierarchijomis](relationships.md#set-up-account-hierarchies).
   - Jei nustatyta lauko **Išjungta** vertė, matavimo vienetas apskaičiuojamas kiekvienam abonementui. Kiekvienas abonementas gauna rezultatų savį.
   - Jei jis nustatytas kaip **Įjungtas**, rinkitės **Redaguoti** kad pasirinktumėte kliento hierarchiją pagal prarytas hierarchijas. Priemonė duos tik vieną rezultatą, nes jis agreguotas su antriniais klientais.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Skaičiavime pasirinkite vertikalią daugtaškį (&vellip;) į **Dubliuoti**, **Pervardyti** arba **Pašalinti** skaičiavimą iš matavimo.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Šalia Matas Be pavadinimo pasirinkite **Redaguoti išsamią informaciją**. Nurodykite priemonės pavadinimą. Pasirinktinai į matą įtraukite [žymes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Išsamios informacijos redagavimas.":::

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.
