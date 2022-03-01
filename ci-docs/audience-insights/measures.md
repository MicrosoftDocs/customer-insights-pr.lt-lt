---
title: Sukurti ir redaguoti priemones
description: Apibrėžkite su klientu susijusius matus, kad galėtumėte analizuoti ir pateikti tam tikrų verslo sričių rezultatus.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406420"
---
# <a name="define-and-manage-measures"></a>Matų apibrėžimas ir valdymas

**Matai** pateikia pagrindinius veiklos rodiklius (KPI), kurie atspindi tam tikrų verslo sričių našumą ir būseną. Publikos įžvalgos pateikia intuityvią patirtį skirtą sukurti skirtingus priemonių tipus naudojant laukimo kūrimo įrankį, kuriam neprivalote koduoti ar patvirtinti savo priemones rankiniu būdu. **Pagrindiniame** puslapyje galite sekti savo verslo matus, matyti konkrečių klientų matus **kliento kortelėje** ir naudoti matus klientų segmentams apibrėžti **segmentų** puslapyje.

## <a name="create-a-measure"></a>Sukurti matą

Šis skyrius padės jums sukurti matą nuo nulio. Galite kurti matus su duomenimis iš kelių duomenų šaltinių, sujungtų su kliento objektu. Kai kurie [paslaugų apribojimai](service-limits.md) yra taikomi.

1. Publikos įžvalgose, eikite į **Priemonės**.

2. Pasirinkite **naujas matas**

3. Pasirinkite mato **tipą**:

   - **Kliento atributas**: vienas kliento laukas, kuris atspindi kliento rezultatą, vertę arba būseną. Kliento atributai kuriami kaip atributai naujame sistemos sugeneruotame objekte, vadinamame **kliento matu**.

   - **Kliento matas**: įžvalgos apie kliento elgseną pagal pažymėtų matmenų suskirstymą. Naujas objektas yra sukuriamas kiekvienam matui, galimai su keliais įrašais klientui.

   - **Verslo matas**: seka jūsų verslo veiklos rezultatus ir įmonės būseną. Verslo matai gali turėti dvi skirtingas išvestis: skaitmeninę išvestį, kuri rodoma **pagrindiniame** puslapyje arba naują objektą, kurį galite rasti **objektų** puslapyje.

4. Įveskite **pavadinimą** ir pasirinktinai **rodomą pavadinimą**, tada pasirinkite **toliau**.

5. **Objektų** skyriuje, pasirinkite pirmą objektą iš išskleidžiamojo sąrašo. Šiuo metu turite nuspręsti, ar jūsų mato apibrėžimui yra reikalingi papildomi objektai.

   > [!div class="mx-imgBorder"]
   > ![Matavimo apibrėžimas](media/measure-definition.png "Matavimo apibrėžimas")

   Norėdami įtraukti daugiau objektų, pasirinkite **pridėti objektą** ir pasirinkite objektus, kuriuos norite naudoti matui.

   > [!NOTE]
   > Galite pasirinkti tik tuos objektus, kurie turi ryšį su jūsų pradžios objektu. Daugiau informacijos apie ryšių apibrėžimą, žr. [ryšiai](relationships.md).

6. Pasirinktinai galite konfigūruoti kintamuosius. **Kintamųjų** skyriuje pasirinkite **naują kintamąjį**.

   Kintamieji yra kiekvienam pasirinktam įrašui atliekami skaičiavimai. Pavyzdžiui, pardavimo vietos (POS) ir pardavimo internetu, kiekvienam jūsų kliento įrašui, apibendrinimas.

7. Pateikite kintamojo **pavadinimą**.

8. **Išraiškos** srityje pasirinkite lauką, kad pradėtumėte skaičiavimą.

9. Įveskite išraišką **išraiškos** srityje kol renkatės daugiau į apskaičiavimą įtraukiamų laukų.

   > [!NOTE]
   > Šiuo metu tik aritmetinės išraiškos yra palaikomos. Be to, kintamųjų skaičiavimas nepalaikomas objektams iš skirtingų [objektų maršrutų](relationships.md).

10. Pasirinkite **Atlikta**.

11. **Mato apibrėžimo** skyriuje apibrėšite, kaip jūsų pasirinkti objektai ir apskaičiuoti kintamieji yra sujungiami į naują objekto ar atributo matmenį.

12. Pasirinkti **naują matmenį**. Galite galvoti apie matmenį kaip apie *grupuoti pagal* funkciją. Jūsų mato objekto ar atributo duomenų išvestis bus sugrupuota pagal visus apibrėžtus matmenis.

    > [!div class="mx-imgBorder"]
    > ![Pasirinkti sujungimo ciklą](media/measures-businessreport-measure-definition2.png "Pasirinkti sujungimo ciklą")

    Savo matmenų apibrėžimui pasirinkite arba įveskite šią informaciją:

    - **Objektas**: jei nustatote matavimo objektą, jis turi turėti bent vieną atributą. Jei apibrėžiate matavimo atributą, pagal numatytąją reikšmę jis apims tik vieną atributą. Šis pasirinkimas yra apie objekto, kuris turi atributą, pasirinkimą.
    - **Laukas**: pasirinkite konkretų atributą, kuris bus įtrauktas į matavimo objektą arba atributą.
    - **Talpykla**: pasirinkite, ar norite kaupti duomenis kasdien, kas mėnesį ar kas metus. Tai būtina pasirinkti tik tuo atveju, jei pasirinkote atributą Datos tipas.
    - **Kaip**: apibrėžia naujo lauko pavadinimą.
    - **Rodomas pavadinimas**: apibrėžia jūsų lauko rodomą pavadinimą.

    > [!NOTE]
    > Jūsų verslo matas bus išsaugotas kaip vieno skaičiaus objektas ir atsiras **pagrindiniame** puslapyje, nebent pridėsite daugiau matmenų. Pridėjus daugiau matmenų, matas *nebus* rodomas **pagrindiniame** puslapyje.

13. Pasirinktinai įtraukite sujungimo funkcijas. Bet kokia jūsų sukurta agregacija pavirsta nauja jūsų mato objekto ar atributo reikšme. Palaikomos sujungimo funkcijos yra: **min**, **maks**, **vidurkis**, **mediana**, **suma**, **unikalus skaičius**, **pirmas** (užima pirmąjį matmens reikšmės įrašą) ir **paskutinis** (užima paskutinį įrašą, įtrauktą į matmens vertę).

14. Pasirinkite **išsaugoti** norėdami pritaikyti mato pakeitimus.

## <a name="manage-your-measures"></a>Matų valdymas

Jums sukūrus mažiausiai vieną priemonę, matysite priemonių sąrašą **Priemonių** puslapyje.

Rasite informaciją apie mato tipą, kūrėją, sukūrimo datą ir laiką, paskutinę redagavimo datą ir laiką, būseną (ar matas aktyvus, nesuaktyvintas arba nepavykęs) ir paskutinę naujinimo datą ir laiką. Iš sąrašo pasirinkę matą galite peržiūrėti jo išvesties peržiūrą.

Norėdami tuo pačiu metu atnaujinti visus savo matus, spustelėkite **Atnaujinti visus** nepažymėdami konkretaus mato.

> [!div class="mx-imgBorder"]
> ![Atskirų matų valdymo veiksmai](media/measure-actions.png "Atskirų matų valdymo veiksmai")

Arba pasirinkite priemonę iš sąrašo ir atlikite vieną iš toliau nurodytų veiksmų.

- Pažymėkite mato pavadinimą, kad peržiūrėtumėte jo išsamią informaciją.
- **Redaguokite** mato konfigūraciją.
- **Pervardykite** matą.
- **Panaikinkite** matą.
- Pažymėkite elipsę (...), tada pasirinkite **Atnaujinti**, kad būtų pradėtas mato atnaujinimo procesas.
- Pažymėkite elipsę (...), tada pasirinkite **Atsisiųsti**, kad gautumėte mato .CSV failą.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="next-step"></a>Kitas veiksmas

Galite naudoti esančius matus, jei norite sukurti savo pirmą kliento segmentą **segmentų** puslapyje. Daugiau informacijos galite rasti čia [segmentas](segments.md).
