---
title: Matų kūrimas ir valdymas
description: Apibrėžkite verslo efektyvumo analizės ir peržiūros priemones.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049260"
---
# <a name="define-and-manage-measures"></a>Matų apibrėžimas ir valdymas

Šios priemonės padeda jums geriau suprasti klientų elgesį ir įmonės efektyvumą. Jos peržvelgia atitinkamas vertes iš [vieningųjų profilių](data-unification.md). Pavyzdžiui, įmonė nori peržiūrėti *bendras kiekvieno kliento išlaidas*, kad suprastų kiekvieno kliento pirkimo istoriją arba išmatuotų *bendrus įmonės pardavimus*, kad galėtų suprasti agregavimo lygio pajmas vidoje įmonėje.  

Priemonės kuriamos naudojant priemonę eilės duomenų užklausos platformą su įvairiais operatoriais ir paprastomis susiejimo parinktimis. Ji leidžia filtruoti duomenis, grupuoti rezultatus, aptikti [objekto ryšio maršrutus](relationships.md), ir peržiūrėti išvestį.

Naudodami matą, galite planuoti verslo veiklas užklausdami klientų duomenis ir išskleisti įžvalgas. Pavyzdžiui, sukūrus *bendrą vienam klientui išleidus sumą* ir *bendrą grąžą klientui* galima nustatyti klientų grupę, kurios išlaidos yra didelės, bet didelė ir grąža. Galite  [sukurti segmentą](segments.md)ir imtis kitų geriausių veiksmų. 

## <a name="build-your-own-measure-from-scratch"></a>Savo priemonės kūrimas nuo pradžių

Šiame skyriuje pateikiama informacija apie naujos priemonės sukūrimą nuo pradžių. Galite sukurti priemonę su duomenų atributais iš duomenų objektų, kurių ryšys nustatytas taip, kad būtų galima prisijungti prie kliento objekto. 

1. Publikos įžvalgose, eikite į **Priemonės**.

1. Pasirinkite **Naujas** ir pasirinkite **Kurti savo**.

1. Pasirinkite **Redaguoti pavadinimą** ir įveskite priemonės **pavadinimą**. 
   > [!NOTE]
   > Jei jūsų naujo matavimo konfigūracijoje yra tik du laukai, pavyzdžiui, Kliento ID ir vienas skaičiavimas, išeiga bus įtraukta kaip naujas stulpelis į sistemos sugeneruotą objektą, pavadintą Kliento matavimas. O priemonės vertę galėsite matyti unifikuotame kliento profilyje. Kitos priemonės sugeneruos nuosavus objektus.

1. Konfigūracijos srityje pasirinkite agregavimo funkciją **Pažymėti funkciją** išplečiamajame meniu. Agregavimo funkcijos yra šios: 
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutinė:** perima paskutinę į duomenų įrašą pridėtą reikšmę

   :::image type="content" source="media/measure-operators.png" alt-text="Apibrėžkite mato skaičiavimus.":::

1. Pasirinkite **Įtraukti** atributą ir pažymėkite duomenis, kurių reikia sukurti šią priemonę.
   
   1. Pasirinkti **Atributus**. 
   1. Duomenų objektas: pasirinkite objektą, kuriame yra atributas, kurį norite matuoti. 
   1. Duomenų atributas: pasirinkite atributą, kurį norite naudoti agregavimo funkcijai apskaičiuoti. Vienu metu galite pasirinkti tik vieną atributą.
   1. Taip pat galite pažymėti duomenų atributą iš esamos priemonės pažymėdami skirtuką **Priemonės**. Arba galite ieškoti objekto arba priemonės pavadinimo. 
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pažymėkite atributą, kuris bus naudojamas skaičiavimams.":::

1. Norėdami sukurti sudėtingesnių matų, galite įtraukti daugiau atributų arba naudoti matavimo funkcijos operatoriais.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Sukurkite sudėtingą matą su operatoriais, kuriuose yra operatoriai.":::

1. Norėdami įtraukti filtrų, konfigūracijos srityje pažymėkite **filtrą**. 
  
   1. Filtrų srities atributų skyriuje **Įtraukti atributą** ir **Filtrai** pažymėkite atributą, kurį norite naudoti kurdami filtrus.
   1. Nustatykite filtro operatorių, kad apibrėžtų kiekvieno pažymėto atributo filtrą.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Norėdami įtraukti dimensijas, konfigūracijos srityje pažymėkite **Dimensijos**. Dimensijų rezultatai bus rodomi kaip stulpeliai.
   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį. Pagal numatytuosius nustatymus, siekiant kurti *kliento lygio matus*, pasirenkama *Kliento ID*. Jei norite kurti verslo lygio priemones, galite pašalinti *numatytąją dimensiją*.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei jūsų duomenyse yra verčių, kurias reikia pakeisti, pavyzdžiui, sveikuoju skaičiumi, reikšmę *null* pakeiskite į *0* ir pasirinkite **Taisyklės**. Sukonfigūruokite taisyklę ir įsitikinkite, kad pakeitimui renkatės tik sveikuosius skaičius.

1. Jei tarp jūsų susietų duomenų objektų ir *Kliento* objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią. 
   1. Pažymėkite **Duomenų nuostatas** ir pasirinkite kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti. Jei yra tik vienas kelias į *Kliento* objektą, šis valdiklis nebus rodomas.
   1. Pasirinkite **Atlikta**, kad pritaikytumėte savo pasirinkimą. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pasirinkite diagramos objektą.":::

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.

1. Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

## <a name="use-a-template-to-build-a-measure"></a>Šablono naudojimas priemonei kurti

Jiems kurti galite naudoti iš anksto apibrėžtus dažniausiai naudojamų priemonių šablonus. Išsamūs šablonų aprašymai ir interaktyvioji patirtis padeda efektyviai matuoti kūrimą. Šablonai kuriami pagal žymimys duomenis iš objekto *„Unified Activity“*. Prieš kurdami priemonę pagal šabloną įsitikinkite, kad sukonfigūravote [kleinto veiklą](activities.md).

Galimi priemonių šablonai: 
- Vidutinė operacijų vertė (ATV)
- Bendra operacijos vertė
- Vidutinės dienos pajamos
- Vidutinės metų pajamos
- Operacijų skaičius
- Gauti lojalumo taškai
- Panaudoti lojalumo taškai
- Lojalumo taškų balansas
- Aktyvaus kliento veiklos trukmė
- Lojalumo narystės trukmė
- Laikas nuo paskutinio pirkimo

Tolesnė procedūra apžvelgia veiksmus, reikalingus naujai priemonei kurti naudojant šabloną.

1. Publikos įžvalgose, eikite į **Priemonės**.

1. Pasirinkite **Naujas** ir pasirinkite **Rinktis šabloną**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Išskleidžiamojo meniu ekrano nuotrauka kuriant naują priemonę su šablono paryškinimu.":::

1. Raskite jūsų poreikius atitinkantį šabloną ir pasirinkite **Rinktis šabloną**.

1. Peržiūrėkite reikiamus duomenis ir pasirinkite **Darbo pradžia**, jei turite visus duomenis.

1. Srityje **Pavadinimo redagavimas** nustatykite savo priemonės pavadinimą ir išvesties objektą. 

1. Pasirinkite **Atlikta**.

1. Skiltyje **Laikotarpio nustatymas** apibrėžkite naudojamų duomenų laiko tarpą. Pasirinkite, ar norite, kad naujoji priemonė apimtų visus nustatytus duomenis, pasirinkdami **Visą laiką**. Arba, jei norite, kad priemonė būtų nukrepta į **konkretų laikotarpį**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Ekrano nuotrauka, kurioje rodoma laikotarpio skiltis konfigūruojant priemonę iš šablono.":::

1. Kitoje skiltyje pasirinkite **Pridėti duomenis** ir pasirinkite veiklas bei pažymėkite attitinkamus duomenis iš savo objekto *Unified Activity*.

    1. 1 veiksmas iš 2: skiltyje **Veiklos tipas** pasirinkite norimo naudoti objekto tipą. Skiltyje **Veiklos** pasirinkite objektus, kuriuos norite žymėti.
    1. 2 veiksmas iš 2: pasirinkite formulės reikalaujamo komponento atributą iš objekto *Unified Activity*. Pvz., jei operacijos vertė vidutinė, tai operacijos vertę vaiduojantis atributas. **Veiklos laiko žymai** pasirinkite atributą iš objekto „Unified Activity“, kuriame vaizduojama veiklos data ir laikas.
   
1. Sėkmingai pažymėjė duomenis būseną galite matyti kaip **Baigta** kartu su pažymėtų veiklų ir atributų pavadinimu.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Baigtų priemonių šablono konfigūravimo ekrano nuotrauka.":::

1. Dabar galite pasirinkti **Vykdyti** ir apskaičiuoti priemonės rezultatus. Jei paiešką vėliau norėsite susiaurinti, pasirinkite **Išsaugoti juodarštį**.

## <a name="manage-your-measures"></a>Matų valdymas

Priemonių sąrašą galima rasti puslapyje **Priemonės**.

Rasite informacijos apie matavimo tipą, kūrėją, kūrimo datą, būseną ir būseną. Kai sąraše pažymite priemonę, galite peržiūrėti išvestį ir atsisiųsti .CSV failą.

Norėdami tuo pačiu metu atnaujinti visus savo matus, spustelėkite **Atnaujinti visus** nepažymėdami konkretaus mato.

> [!div class="mx-imgBorder"]
> ![Atskirų matų valdymo veiksmai](media/measure-actions.png "Atskirų matų valdymo veiksmai")

Sąraše pažymėkite toliau nurodytų parinkčių matą.

- Pažymėkite mato pavadinimą, kad peržiūrėtumėte jo išsamią informaciją.
- **Redaguokite** mato konfigūraciją.
- **Atnaujinkite** priemonę pagal naujausius duomenis.
- **Pervardykite** matą.
- **Panaikinkite** matą.
- **Aktyvuokite** arba **Deaktyvuokite**. Suplanuoto atnaujinimo metu neaktyvūs duomenys nebus [atnaujinti](system.md#schedule-tab).

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="next-step"></a>Kitas veiksmas

Naudodami esamas priemones, vaizdo kamera kuriate [klientų segmentą](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
