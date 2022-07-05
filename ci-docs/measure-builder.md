---
title: Kurkite naujas priemones naudodami priemonių kūrimo priemonę
description: Kurkite priemones nuo nulio, kad analizuotumėte pagrindinę įmonės metriką.
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
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083020"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Kurkite naujas priemones naudodami priemonių kūrimo priemonę

Šiame straipsnyje paaiškinama, kaip sukurti naują [priemonę](measures.md) nuo nulio. Priemonių kūrimo priemonė leidžia apibrėžti skaičiavimus naudojant matematinius operatorius, agregavimo funkcijas ir filtrus. Galite sukurti matą su atributais iš objektų, susijusių su vieningu *kliento* objektu.

Priemonių kūrimas B-to-C ir B-to-B aplinkose veikia taip pat. Tačiau jei esate B–B aplinkoje [naudojami abonementai su hierarchijomis](relationships.md#set-up-account-hierarchies), galite pasirinkti agreguoti matą susijusiose antrinėse paskyrose.

Taip pat galite greitai sukurti matą pasirinkdami iš dažniausiai naudojamų ir iš anksto nustatytų priemonių rinkinio. Daugiau informacijos ieškokite [Šablono naudojimas priemonei kurti](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Galite kurti priemones atskirų klientų lygiu (kliento atributas, kliento matas) arba verslo / organizacijos lygiu (verslo matas). Kliento atributas ir kliento matas yra dviejų tipų tipai, leidžiantys sekti našumą vienam klientui. Pavyzdžiui, bendra kiekvieno kliento išlaidų suma. Verslo priemonės leidžia stebėti kiekvienos įmonės našumą. Pavyzdžiui, bendros įmonės pajamos.

- Kliento atributas: generuoja išvestį kaip naują atributą, kuris įrašomas kaip naujas stulpelis sistemos sugeneruotame objekte, pavadintame *Customer_Measure*. Atnaujinant kliento atributą, visi kiti kliento atributai Customer_Measure *objekte* atnaujinami vienu metu. Be to, kliento atributai rodomi kliento profilio kortelėje. Paleidę arba išsaugoję kliento atributą, negalite jo pakeisti į kliento matą.

- Kliento matas: generuoja išvestį kaip savo objektą ir negalite jos pakeisti į kliento atributą paleidę arba išsaugoję. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodo savo "Customer Insights" aplinkos pagrindiniame puslapyje.

1. Eikite į **"Measures"**.

1. Pasirinkite **Naujas** ir pasirinkite **Kurti savo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tuščias konfigūracijos ekranas, skirtas B–C matui." lightbox="media/measure-b2c.png":::

1. Norėdami stebėti našumą verslo lygiu, perjunkite **Priemonės tipas** į **Verslo lygis**. **Kliento lygis** pasirenkamas pagal numatytuosius nustatymus. **Kliento lygis** automatiškai įtraukia atributą *CustomerId* į dimensijas, o **verslo lygis** automatiškai jį pašalina.

1. Konfigūracijos srityje pasirinkite agregavimo funkciją išskleidžiamajame **meniu Pasirinkti funkciją**. Agregavimo funkcijos yra šios:
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę
   - **"ArgMax"**: randa duomenų įrašą, suteikiantį maksimalią reikšmę iš tikslinės funkcijos
   - **ArgMin**: randa duomenų įrašą, suteikiantį minimalią reikšmę iš tikslinės funkcijos

1. Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.

   1. Pasirinkti **Atributus**.
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės** arba galite ieškoti objekto arba priemonės pavadinimo.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matui apskaičiuoti bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kurie įtraukiami kaip stulpeliai į išvesties objekto matą.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
   > [!TIP]
   > Jei kaip priemonės tipą **pasirinkote** Kliento lygis **,** atributas CustomerId *jau bus įtrauktas.* Jei pašalinsite atributą, **priemonės tipas** persijungs į **verslo lygį**.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.

1. Pasirinkite vertikalią daugtaškį (&vellip;) skaičiavime į **Dublikatas**, **Pervardyti** arba **Pašalinti** iš mato skaičiavimą.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Priemonės Be pavadinimo. Nurodykite priemonės pavadinimą. Pasirinktinai prie priemonės pridėkite [žymų](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Galite kurti priemones atskirų paskyrų lygiu (kliento matas) arba visų paskyrų lygiu (verslo matas).

- Kliento matas: generuoja išvestį kaip savo objektą. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodo savo "Customer Insights" aplinkos pagrindiniame puslapyje.

1. Eikite į **"Measures"**.

1. Pasirinkite **Nauja**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tuščias konfigūracijos ekranas, skirtas B–B matui.":::

1. Konfigūracijos srityje pasirinkite agregavimo funkciją išskleidžiamajame **meniu Pasirinkti funkciją**. Agregavimo funkcijos yra šios:
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

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matui apskaičiuoti bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kurie įtraukiami kaip stulpeliai į išvesties objekto matą.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
      > [!TIP]
      > Jei kaip priemonės tipą **pasirinkote** Kliento lygis **,** atributas CustomerId *jau bus įtrauktas.* Jei pašalinsite atributą, **matavimo tipas** persijungs į **verslo lygį**.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Galite naudoti antrinių **abonementų sujungimą** jei naudojate [abonementus su hierarchijomis](relationships.md#set-up-account-hierarchies).
   - Jei nustatyta lauko **Išjungta** vertė, matavimo vienetas apskaičiuojamas kiekvienam abonementui. Kiekvienas abonementas gauna rezultatų savį.
   - Jei jis nustatytas kaip **Įjungtas**, rinkitės **Redaguoti** kad pasirinktumėte kliento hierarchiją pagal prarytas hierarchijas. Priemonė duos tik vieną rezultatą, nes jis agreguotas su antriniais klientais.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Pasirinkite vertikalią daugtaškį (&vellip;) skaičiavime į **Dublikatas**, **Pervardyti** arba **Pašalinti** iš mato skaičiavimą.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Priemonės Be pavadinimo. Nurodykite priemonės pavadinimą. Pasirinktinai prie priemonės pridėkite [žymų](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.
