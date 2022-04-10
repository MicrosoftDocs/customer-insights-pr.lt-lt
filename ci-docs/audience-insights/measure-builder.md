---
title: Kurti naujas priemones naudojant matavimo daryklę
description: Kurkite priemones nuo nulio, kad galėtumėte analizuoti pagrindines jūsų verslo metrikas.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359957"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Naudokite matavimo generatorių, kad sukurtumėte priemones nuo nulio

Šiame straipsnyje paaiškinama, kaip sukurti naują [priemonę](measures.md) nuo nulio. Matavimo generatorius leidžia apibrėžti skaičiavimus naudojant matematinius operatorius, agregavimo funkcijas ir filtrus. Galite sukurti priemonę su atributais iš objektų, susijusių su suvienyto *kliento* objektu. 

Priemonių kūrimas B-to-C ir B-to-B aplinkose veikia taip pat. Tačiau jei esate "B-to-B" aplinka [naudoja paskyras su hierarchijomis](relationships.md#set-up-account-hierarchies), galite pasirinkti agreguoti matą susijusiose antrinėse sąskaitose.

Taip pat galite greitai sukurti priemonę pasirinkdami iš dažniausiai naudojamų ir iš anksto nustatytų priemonių rinkinio. Daugiau informacijos ieškokite [Naudokite šabloną priemonei kurti](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Galite kurti priemones atskirų klientų lygiu (kliento atributas, kliento matas) arba verslo / organizacijos lygiu (verslo priemonė). Kliento atributas ir kliento matas yra dviejų tipų, leidžiančių stebėti našumą vienam klientui. Pavyzdžiui, bendros kiekvieno kliento išlaidos. Verslo priemonės leidžia stebėti veiklos rezultatus pagal verslą. Pavyzdžiui, bendros įmonės pajamos.

- Kliento atributas: generuoja išvestį kaip naują atributą, kuris įrašomas kaip naujas stulpelis sistemos sugeneruotame objekte, pavadintame *Customer_Measure*. Atnaujinant kliento atributą, visi kiti kliento atributai Customer_Measure *objekte* atnaujinami vienu metu. Be to, kliento atributai rodomi kliento profilio kortelėje. Paleidus arba įrašius, kliento atributas negali jo pakeisti į kliento matą.

- Kliento matas: generuoja išvestį kaip savo objektą ir negalite jo pakeisti į kliento atributą, kai paleidžiate arba įrašote. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodomas "Customer Insights" aplinkos pagrindiniame puslapyje.

1. Eikite į **priemones**.

1. Pasirinkite **Naujas** ir pasirinkite **Kurti savo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tuščias B-to-C matavimo konfigūracijos ekranas.":::

1. Pasirinkite **Redaguoti pavadinimą** ir įveskite priemonės **pavadinimą**. 

1. Konfigūracijos srityje išplečiamajame meniu Pasirinkti pasirinkite **agregavimo funkciją**. Agregavimo funkcijos yra šios: 
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

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus, apskaičiuojant matą bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kurie į matavimo išvesties objektą įtraukiami kaip stulpeliai.
 
   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį. Pagal numatytuosius nustatymus, siekiant kurti *kliento lygio matus*, pasirenkama *Kliento ID*. Jei norite kurti verslo lygio priemones, galite pašalinti *numatytąją dimensiją*.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sąsočiu, pažymėkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią. 
   
   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą. 

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.

1. Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)


Galite kurti priemones atskirų sąskaitų lygiu (kliento matu) arba visų sąskaitų lygiu (verslo priemonė). 

- Kliento matas: generuoja išvestį kaip savo objektą. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodomas "Customer Insights" aplinkos pagrindiniame puslapyje.

1. Eikite į **priemones**.

1. Pasirinkite **Nauja**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tuščias B-to-B matavimo konfigūracijos ekranas.":::

1. Pasirinkite **Redaguoti pavadinimą** ir įveskite priemonės **pavadinimą**. 

1. Konfigūracijos srityje išplečiamajame meniu Pasirinkti pasirinkite **agregavimo funkciją**. Agregavimo funkcijos yra šios: 
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

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus, apskaičiuojant matą bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kurie į matavimo išvesties objektą įtraukiami kaip stulpeliai.
 
   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį. Pagal numatytuosius nustatymus, siekiant kurti *kliento lygio matus*, pasirenkama *Kliento ID*. Jei norite kurti verslo lygio priemones, galite pašalinti *numatytąją dimensiją*.
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

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

---