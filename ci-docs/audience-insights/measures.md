---
title: Matų kūrimas ir valdymas
description: Apibrėžkite verslo efektyvumo analizės ir peržiūros priemones.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269938"
---
# <a name="define-and-manage-measures"></a>Matų apibrėžimas ir valdymas

Priemonės padeda jums geriau suprasti klientų elgesį ir verslo našumą nuskaitant atitinkamas reikšmes iš [vieningųjų profilių](data-unification.md). Pavyzdžiui, įmonė nori, kad *bendras vienam klientui skirtas išlaidas* būtų galima pamatyti norint suprasti atskirų klientų pirkimo retrospektyvą. Arba *matuokite visą įmonės* pardavimą, kad suprastumėte agregavimo lygio pajamas visoje įmonėje.  

Priemonės kuriamos naudojant priemonę eilės duomenų užklausos platformą su įvairiais operatoriais ir paprastomis susiejimo parinktimis. Ji leidžia filtruoti duomenis, grupuoti rezultatus, aptikti [objekto ryšio maršrutus](relationships.md), ir peržiūrėti išvestį.

Naudodami matą, galite planuoti verslo veiklas užklausdami klientų duomenis ir išskleisti įžvalgas. Pavyzdžiui, sukūrus *bendrą vienam klientui išleidus sumą* ir *bendrą grąžą klientui* galima nustatyti klientų grupę, kurios išlaidos yra didelės, bet didelė ir grąža. Galite  [sukurti segmentą](segments.md)ir imtis kitų geriausių veiksmų. 

## <a name="create-a-measure"></a>Sukurti matą

Šiame skyriuje pateikiama informacija apie naujos priemonės sukūrimą nuo pradžių. Galite sukurti priemonę su duomenų atributais iš duomenų objektų, kurių ryšys nustatytas taip, kad būtų galima prisijungti prie kliento objekto. 

1. Publikos įžvalgose, eikite į **Priemonės**.

1. Pasirinkite **Naujas**.

1. Pasirinkite **Redaguoti pavadinimą** ir įveskite priemonės **pavadinimą**. 
   > [!NOTE]
   > Jei jūsų naujo matavimo konfigūracijoje yra tik du laukai: iškvietai, "CustomerID" ir vienam skaičiavimui rezultatai bus įtraukti kaip naujas stulpelis į sistemos sugeneruotą objektą, kurio pavadinimas Customer_Measure. O priemonės vertę galėsite matyti unifikuotame kliento profilyje. Kitos priemonės sugeneruos nuosavus objektus.

1. Konfigūracijos srityje pasirinkite agregavimo funkciją **Pažymėti funkciją** išplečiamajame meniu. Agregavimo funkcijos yra šios: 
   - **Sum**
   - **Vidurkis**
   - **Skaičius**
   - **Unikalusis skaičius**
   - **Didžiausia**
   - **Min**
   - **Pirma:** perima pirmą duomenų įrašo reikšmę
   - **Paskutin:** perima paskutinę į duomenų įrašą pridėtą reikšmę

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
   1. Pasirinkite **Redaguoti dimensijas** reikšmę ir įtraukite duomenų atributų, pagal kuriuos norite grupuoti matavimo reikšmes. Pvz.: miestą arba lytį. Pagal numatytuosius nustatymus, siekiant kurti *kliento lygio matus*, pasirenkama *"CustomerID"*. Jei norite kurti verslo lygio priemones, galite pašalinti *numatytąją dimensiją*.
   1. Pasirinkite **Pridėti**, kad pridėtumėte pasirinktus atributus ir priemones.

1. Jei tarp jūsų susietų duomenų objektų ir kliento objekto yra keli keliai, turite pasirinkti vieną iš nustatytų [objekto ryšio kelių](relationships.md). Matavimo rezultatai gali skirtis atsižvelgiant į pasirinktą kelią.
   1. Pažymėkite **Duomenų nuostatas** ir pasirinkite kelią, kurį reikėtų naudoti jūsų priemonei identifikuoti.
   1. Pasirinkite **Atlikta**, kad pritaikyumėte savo pasirinkimą. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pasirinkite diagramos objektą.":::

1. Jei norite įtraukti daugiau matavimo skaičiavimų, pažymėkite  **Naujas skaičiavimas**. Norėdami atlikti naujus skaičiavimus, galite naudoti tik objektus tame pačiame objekto kelyje. naujų skaičiavimų rezultatai bus rodomi kaip stulpeliai.

1. Pažymėkite **...** skaičiavimuose, kad **Duplikuotumėte**, **Pervardykite** arba **Pašalinkite**  skaičiavimą iš priemonės.

1. **Peržiūros** srityje matysite išvesties objekto matavimo duomenų schemą, įskaitant filtrus ir dimensijas. Peržiūra dinamiškai keičiasi ir pasikeičia konfigūracija.

1. Pažymėkite **Vykdyti**, kad apskaičiuotų sukonfigūruoto matavimo rezultatus. Pasirinkite **Įrašyti ir uždaryti**, jei norite išlaikyti dabartinę konfigūraciją ir vėliau vykdyti priemonę.

1. Eikite į **Priemonės**, kad peržiūrėtumėte naujai sukurtą priemonę sąraše.

## <a name="manage-your-measures"></a>Matų valdymas

Sukūrę [priemonę](#create-a-measure), matų sąrašą matysite puslapyje **Priemonės**.

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