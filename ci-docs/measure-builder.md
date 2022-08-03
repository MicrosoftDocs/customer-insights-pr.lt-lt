---
title: Priemonių kūrimas naudojant matų kūrimo priemonę
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170862"
---
# <a name="create-measures-with-measure-builder"></a>Priemonių kūrimas naudojant matų kūrimo priemonę

Priemonių kūrimo priemonė leidžia apibrėžti skaičiavimus naudojant matematinius operatorius, agregavimo funkcijas ir filtrus. Apibrėžkite priemones naudodami objektų atributus, susijusius su vieningu *kliento* objektu.

Priemonių kūrimas B-to-C ir B-to-B aplinkose veikia taip pat. Tačiau jei jūsų B–B aplinkoje [naudojami abonementai su hierarchijomis](relationships.md#set-up-account-hierarchies), pasirinkite, ar agreguoti matą susijusiose antrinėse paskyrose.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Kurkite priemones atskirų klientų lygiu (kliento atributas, kliento matas) arba verslo / organizacijos lygiu (verslo matas). Kliento atributas ir kliento matas leidžia stebėti kiekvieno kliento našumą. Pavyzdžiui, bendra kiekvieno kliento išlaidų suma. Verslo matai stebi kiekvienos įmonės veiklos rezultatus. Pavyzdžiui, bendros įmonės pajamos.

- Kliento atributas: generuoja išvestį kaip naują atributą, kuris įrašomas kaip naujas stulpelis sistemos sugeneruotame objekte, pavadintame *Customer_Measure*. Atnaujinant kliento atributą, visi kiti kliento atributai Customer_Measure *objekte* atnaujinami vienu metu. Be to, kliento atributai rodomi kliento profilio kortelėje. Paleidę arba išsaugoję negalite pakeisti kliento atributo į kliento matą.

- Kliento matas: generuoja išvestį kaip savo objektą ir negalite jos pakeisti į kliento atributą paleidę arba išsaugoję. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodo informaciją "Customer Insights" aplinkos pagrindiniame puslapyje.

1. Eikite į **"Measures"**.

1. Pažymėkite **Naujas** > **Sukurkite savo**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tuščias konfigūracijos ekranas, skirtas B–C matui." lightbox="media/measure-b2c.png":::

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Priemonės Be pavadinimo. Nurodykite priemonės pavadinimą. Pasirinktinai prie priemonės pridėkite [žymų](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

1. Pasirinkite **Atlikta**.

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

1. Pasirinkite **Pridėti atributą**, kad pasirinktumėte duomenis, kad sukurtumėte šį matą.

   1. Pasirinkti **Atributus**.
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Pasirinktinai pasirinkite duomenų atributą iš esamo mato pasirinkdami skirtuką **Matai** arba ieškokite objekto ar priemonės pavadinimo.
   1. Pasirinkite **Įtraukti**.

1. Norėdami sukurti sudėtingesnius matus, įtraukite daugiau atributų arba naudokite matematikos operatorius savo matavimo funkcijoje.

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matui apskaičiuoti bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Taikyti**.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kuriuos norite įtraukti kaip stulpelius į matuojamo išvesties objektą.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
      > [!TIP]
      > Jei kaip priemonės tipą **pasirinkote** Kliento lygis **,** atributas CustomerId *jau bus įtrauktas.* Jei pašalinsite atributą, **priemonės tipas** persijungs į **verslo lygį**.
   1. Pasirinkite **Atlikta**.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sveikuoju skaičiumi, pasirinkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Jei tarp susieto duomenų objekto ir objekto *Klientas* yra keli keliai, pasirinkite vieną iš identifikuotų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**.

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Naujiems skaičiavimams naudokite tik tame pačiame objekto maršrute esančius objektus. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai. Jei norite, pasirinkite **Redaguoti vardą**, kad sukurtumėte skaičiavimo pavadinimą.

1. Pasirinkite vertikalią daugtaškį (&vellip;) skaičiavime į **Dublikatas** arba **Pašalinti** skaičiavimą iš mato.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę. Rodomas **puslapis Matai**.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Sukurkite priemones atskirų sąskaitų lygiu (kliento matas) arba visų sąskaitų lygiu (verslo matas).

- Kliento matas: generuoja išvestį kaip savo objektą. Kliento priemonės nerodomos kliento profilio kortelėje.

- Verslo matas: generuoja išvestį kaip savo objektą ir rodo informaciją "Customer Insights" aplinkos pagrindiniame puslapyje.

1. Eikite į **"Measures"**.

1. Pasirinkite **Nauja**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tuščias konfigūracijos ekranas, skirtas B–B matui.":::

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Priemonės Be pavadinimo. Nurodykite priemonės pavadinimą. Pasirinktinai prie priemonės pridėkite [žymų](work-with-tags-columns.md#manage-tags). 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

1. Pasirinkite **Atlikta**.

1. Konfigūracijos srityje pasirinkite agregavimo funkciją išskleidžiamajame **meniu Pasirinkti funkciją**. Agregavimo funkcijos yra šios:
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę

1. Pasirinkite **Pridėti atributą**, kad pasirinktumėte duomenis, kad sukurtumėte šį matą.

   1. Pasirinkti **Atributus**.
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti.
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Pasirinktinai pasirinkite duomenų atributą iš esamo mato pasirinkdami skirtuką **Matai** arba ieškokite objekto ar priemonės pavadinimo.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Norėdami sukurti sudėtingesnius matus, įtraukite daugiau atributų arba naudokite matematikos operatorius savo matavimo funkcijoje.

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. Taikant filtrus matui apskaičiuoti bus naudojami tik filtrus atitinkantys įrašai.
  
   1. Filtrų **srities skyriuje** Įtraukti atributą **pažymėkite** atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Pasirinkite **Dimensija**, kad pasirinktumėte daugiau laukų, kuriuos norite įtraukti kaip stulpelius į matuojamo išvesties objektą.

   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį.
      > [!TIP]
      > Atributas *CustomerId* jau įtrauktas, nurodantis, kad tai yra kliento lygio priemonės tipas. Jei pašalinsite atributą, mato tipas pasikeis į verslo lygį.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra reikšmių, kurias reikia pakeisti sveikuoju skaičiumi, pasirinkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius. Pavyzdžiui, nulines *reikšmes* pakeiskite *nuliu*.

1. Jei naudojate [paskyras su hierarchijomis](relationships.md#set-up-account-hierarchies), peržiūrėkite **Sukaupti antrines paskyras**.
   - Jei nustatyta lauko **Išjungta** vertė, matavimo vienetas apskaičiuojamas kiekvienam abonementui. Kiekviena sąskaita gauna savo rezultatą.
   - Jei jis nustatytas kaip **Įjungtas**, rinkitės **Redaguoti** kad pasirinktumėte kliento hierarchiją pagal prarytas hierarchijas. Priemonė duos tik vieną rezultatą, nes ji bus sujungta su subsąskaitomis.

1. Jei tarp susieto duomenų objekto ir objekto *Klientas* yra keli keliai, pasirinkite vieną iš identifikuotų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.

   1. Pažymėkite **ryšio kelią** ir pasirinkite objekto kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą.

1. Pasirinkite vertikalią daugtaškį (&vellip;) skaičiavime į **Dublikatas** arba **Pašalinti** skaičiavimą iš mato.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę. Rodomas **puslapis Matai**.

---

## <a name="next-step"></a>Tolesnis veiksmas

Naudokite esamas priemones, kad sukurtumėte [klientų segmentą](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
