---
title: Kurti naujas priemones su priemonės generatoriumi
description: Kurkite priemones nuo nulio, kad analizuotumėte pagrindinius rodiklius apie savo verslą.
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
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: e129a1fa8b020b6bfb6efc3c53fa9d89e1614ad1
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/12/2022
ms.locfileid: "8561543"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Naudokite priemonių daryklę, kad sukurtumėte priemones nuo nulio

Šiame straipsnyje paaiškinama, kaip sukurti naują [priemonę](measures.md) nuo nulio. Matavimo generatorius leidžia apibrėžti skaičiavimus naudojant matematinius operatorius, agregavimo funkcijas ir filtrus. Galite sukurti matą su atributais iš objektų, susijusių su vieningu *Kliento* objektu.

Priemonių kūrimas B-to-C ir B-to-B aplinkose veikia taip pat. Tačiau, jei esate B-to-B aplinka [naudoja paskyras su hierarchijomis](relationships.md#set-up-account-hierarchies), galite pasirinkti agreguoti priemonę susijusiose antrinėse sąskaitose.

Taip pat galite greitai sukurti priemonę pasirinkdami iš dažniausiai naudojamų ir iš anksto nustatytų priemonių rinkinio. Daugiau informacijos ieškokite [Naudoti šabloną priemonei sukurti](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Galite kurti matavimus atskirų klientų lygiu (kliento atributas, kliento matas) arba verslo / organizacijos lygiu (verslo matas). Kliento atributas ir kliento matas yra du tipai, leidžiantys sekti kiekvieno kliento našumą. Pavyzdžiui, visos kiekvieno kliento išlaidos. Verslo priemonės leidžia stebėti kiekvienos įmonės veiklos rezultatus. Pavyzdžiui, visos įmonės pajamos.

- Kliento atributas: generuoja išvestį kaip naują atributą, kuris įrašomas kaip naujas stulpelis sistemos sugeneruotame objekte, pavadintame *Customer_Measure*. Atnaujinant kliento atributą, visi kiti kliento atributai Customer_Measure *objekte* atnaujinami vienu metu. Be to, kliento atributai rodomi kliento profilio kortelėje. Paleidę arba įrašę kliento atributą, negalite jo pakeisti į kliento matą.

- Kliento matas: generuoja išeigą kaip savo objektą ir negalite jo pakeisti į kliento atributą, kai jis paleidžiamas arba įrašomas. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo priemonė: generuoja išeigą kaip savo objektą ir rodoma pagrindiniame "Customer Insights" aplinkos puslapyje.

1. Eikite į **priemones**.

1. Pasirinkite **Naujas** ir pasirinkite **Kurti savo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tuščias B-to-C matavimo konfigūracijos ekranas." lightbox="media/measure-b2c.png":::

1. Norėdami sekti verslo lygio našumą, perjunkite **Priemonės tipą** į **Verslo lygį**. **Pagal numatytuosius nustatymus pasirenkamas kliento lygis**. **Kliento lygis** automatiškai įtraukia CustomerId *atributą* į Dimensijas, o **verslo lygis** automatiškai jį pašalina.

1. Konfigūracijos srityje išplečiamajame meniu Pasirinkti **pasirinkite agregavimo funkciją**. Agregavimo funkcijos yra šios:
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę
   - **"ArgMax**": randa duomenų įrašą, suteikiantį maksimalią tikslinės funkcijos vertę
   - **"ArgMin"**: randa duomenų įrašą, suteikiantį minimalią tikslinės funkcijos vertę

1. Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.

   1. Pasirinkti **Atributus**.
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės** arba galite ieškoti objekto arba priemonės pavadinimo.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matavimui apskaičiuoti bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, jei norite pasirinkti daugiau laukų, įtrauktų kaip stulpeliai į matavimo išvesties objektą.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
   > [!TIP]
   > Jei pasirinkote **Kliento lygį** kaip matavimo **tipą**, *pirkėjo atributas* jau įtrauktas. Jei pašalinsite atributą, **matavimo tipas** persikels į **verslo lygį**.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.

1. Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pasirinkite **Redaguoti išsamią informaciją** šalia priemonės Be pavadinimo. Pateikite priemonės pavadinimą. Pasirinktinai į priemonę pridėkite [žymes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Redaguoti išsamios informacijos dialogo langą.":::

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Galite kurti matavimus atskirų sąskaitų lygiu (kliento matas) arba visų sąskaitų lygiu (verslo matas).

- Kliento matas: generuoja išeigą kaip savo objektą. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo priemonė: generuoja išeigą kaip savo objektą ir rodoma pagrindiniame "Customer Insights" aplinkos puslapyje.

1. Eikite į **priemones**.

1. Pasirinkite **Nauja**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tuščias B-to-B matavimo konfigūracijos ekranas.":::

1. Konfigūracijos srityje išplečiamajame meniu Pasirinkti **pasirinkite agregavimo funkciją**. Agregavimo funkcijos yra šios:
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

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matavimui apskaičiuoti bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, jei norite pasirinkti daugiau laukų, įtrauktų kaip stulpeliai į matavimo išvesties objektą.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
      > [!TIP]
      > Jei pasirinkote **Kliento lygį** kaip matavimo **tipą**, *pirkėjo atributas* jau įtrauktas. Jei pašalinsite atributą, **matavimo tipas** persijungs į **verslo lygį**.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Galite naudoti antrinių **abonementų sujungimą** jei naudojate [abonementus su hierarchijomis](relationships.md#set-up-account-hierarchies).
   - Jei nustatyta lauko **Išjungta** vertė, matavimo vienetas apskaičiuojamas kiekvienam abonementui. Kiekvienas abonementas gauna rezultatų savį.
   - Jei jis nustatytas kaip **Įjungtas**, rinkitės **Redaguoti** kad pasirinktumėte kliento hierarchiją pagal prarytas hierarchijas. Priemonė duos tik vieną rezultatą, nes jis agreguotas su antriniais klientais.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pasirinkite **Redaguoti išsamią informaciją** šalia priemonės Be pavadinimo. Pateikite priemonės pavadinimą. Pasirinktinai į priemonę pridėkite [žymes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Redaguoti išsamios informacijos dialogo langą.":::

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.
