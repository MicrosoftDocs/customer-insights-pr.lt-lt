---
title: Segmentų kūrimas ir valdymas
description: Kurkite klientų segmentus, kad jie būtų sugrupuoti pagal įvairius atributus.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406429"
---
# <a name="create-and-manage-segments"></a>Segmentų kūrimas ir valdymas

Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes. Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.

Galite apibrėžti sudėtinius filtrus kliento profilio objektui ir su juo susijusiams objektams. Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus. Kai kurie [paslaugų apribojimai](service-limits.md) yra taikomi.

Nebent nurodyta kitaip, visi segmentai yra **„Dynamic“ segmentai**, kurie yra paleidžiami iš naujo pasikartojančiame grafike.

Tolesnis pavyzdys rodo segmento pajėgumą. Nustatėme klientų, kurie per paskutines 90 dienų užsisakė prekių bent už 500 $ *ir* kurie atliko klientų aptarnavimo skambutį, kuris buvo perskirtas, segmentą.

> [!div class="mx-imgBorder"]
> ![Sudėtinės grupės](media/segmentation-group1-2.png "Sudėtinės grupės")

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Segmentai yra valdomi **Segmentų** puslapyje.

1. Publikos įžvalgose, eikite į **Segmentai** puslapį.

2. Pasirinkite **Naujas** > **Tuščias segmentas**.

3. Srityje **Naujas segmentas** pasirinkite segmento tipą ir nurodykite **pavadinimą**.

   Galite pasirinktinai nurodyti rodomą pavadinimą ir aprašą, padedantį identifikuoti segmentą.

4. Norėdami atidaryti **segmentų kūrimo priemonės** puslapį, kuriame apibrėžėte grupė, pasirinkite **Kitas**. Grupė yra klientų rinkinys.

5. Pasirinkite objektą, kuriame yra atributas, pagal kurį norite segmentuoti.

6. Pasirinkite atributą, pagal kurį norite segmentuoti. Šis atributas gali turėti vieną iš keturių reikšmių tipų: skaičiaus, eilutės, datos arba Bulio.

7. Pasirinkite operatorių ir pasirinkto atributo reikšmę.

   > [!div class="mx-imgBorder"]
   > ![Pasirinktinis grupės filtras](media/customer-group-numbers.png "Klientų grupės filtras")

   |Numeris |Apibrėžtis  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributas          |
   |3    |Operatorius         |
   |4    |Vertė         |

8. Jei objektas yra sujungtas su sujungtu kliento objektu naudojant [ryšius](relationships.md), turite apibrėžti ryšio kelią, kad sukurtumėte tinkamą segmentą. Įtraukite objektus iš ryšio kelio, kol išplečiamajame sąraše galėsite pasirinkti objektą **Customer : CustomerInsights**. Tada prie kiekvienos sąlygos pasirinkite **Visi įrašai**.

   > [!div class="mx-imgBorder"]
   > ![Ryšių kelias kuriant segmentą](media/segments-multiple-relationships.png "Ryšių kelias kuriant segmentą")

9. Pasirinkite **Įrašyti**, kad įrašytumėte segmentą. Jūsų segmentas bus įrašytas ir apdorojamas, jei visi reikalavimai bus patvirtinti. Kitu atveju jis bus Išsaugota kaip juodraštis.

10. Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.

## <a name="manage-existing-segments"></a>Esamų segmentų tvarkymas

Puslapyje **„Segmentai“**, galite peržiūrėti visus įrašytus segmentus ir juos valdyti.

Kiekvieną segmentą atitinka eilutė, kurioje pateikta papildoma informacija apie segmentą.

Galite rikiuoti segmentus stulpelyje spustelėdami stulpelio antraštę.

Norėdami filtruoti segmentus, naudokite viršutiniame dešiniajame kampe esantį lauką **Ieška**.

> [!div class="mx-imgBorder"]
> ![Esamo segmento valdymo parinktys](media/segments-selected-segment.png "Esamo segmento valdymo parinktys")

Pasirinkus segmentą pasiekiami toliau nurodyti veiksmai.

- **Peržiūrėti** segmento išsamią informaciją, įskaitant narių skaičių, tendencijas ir segmento narių peržiūrą.
- **Redaguoti** segmentą ir pakeisti jo ypatybes.
- **Atnaujinti** segmentą, kad būtų įtraukti naujausi duomenys.
- **Aktyvinti** arba **Išjungti** segmentą. Segmentai turi dvi galimas būsenas – aktyvią arba neaktyvią. Šios būsenos yra naudingos redaguojant segmentą. Neaktyvių segmentų aprašas yra, bet į jį dar neįtraukta klientų. Suaktyvinus segmentą, jo būsena keičiasi iš neaktyvios į aktyvią, ir jis pradeda ieškoti klientų, atitinkančių segmento aprašą. Jei [suplanuotas atnaujinimas](system.md#schedule-tab) yra sukonfigūruotas, neaktyvių segmentų **Būsena** nurodoma kaip **Praleista** – tai reiškia, kad net nebuvo bandyta atnaujinti. Suaktyvinus neaktyvų segmentą, jis bus atnaujintas ir įtrauktas į suplanuotus atnaujinimus.
  Taip pat galite naudoti funkciją **Planuoti vėliau**, esančią iškleidžiamajame meniu **Aktyvinti / išjungti**, kad nurodytumėte būsimą datą ir laiką, kada reikia aktyvinti ir išjungti tam tikrą segmentą.
- **Pervardyti** segmentą.
- **Atsisiųsti** narių sąrašą kaip .CSV failą.
- Parinktis **Įtraukti į** siunčia klientų ID sąrašą į segmentą apdoroti kitoje programoje.
- **Naikinti** segmentą.

## <a name="refresh-segments"></a>Segmentų atnaujinimas

Visus segmentus galite atnaujinti vienu metu pažymėdami **Atnaujinti viską** puslapyje **Segmentai** arba galite atnaujinti vieną ar kelis segmentus, kai juos pažymite ir parinktyse pasirenkate **Atnaujinti**. Taip pat galite sukonfigūruoti pasikartojantį atnaujinimą dalyje **Administravimas** > **Sistemas** > **Planuoti**.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="download-and-export-segments"></a>Segmentų atsisiuntimas ir eksportavimas

Galite atsisiųsti segmentus į CSV failą arba juos eksportuoti į „Dynamics 365 Sales“.

### <a name="download-segments-to-a-csv-file"></a>Segmentų atsisiuntimas į CSV failą

1. Publikos įžvalgose, eikite į **Segmentai** puslapį.

2. Konkretaus segmento plytelėje spustelėkite daugtaškį.

3. Veiksmų išplečiamajame sąraše pasirinkite **Atsisiųsti kaip CSV**.

### <a name="export-segments-to-dynamics-365-sales"></a>Segmentų eksportavimas į „Dynamics 365 Sales“

Prieš eksportuojant segmentus į „Dynamics 365 Sales“ administratorius turi [sukurti „Dynamics 365 Sales“ eksportavimo paskirties vietą](export-destinations.md).

1. Publikos įžvalgose, eikite į **Segmentai** puslapį.

2. Konkretaus segmento plytelėje spustelėkite daugtaškį.

3. Spustelėkite **Įtraukti į** veiksmų išplečiamajame sąraše ir pasirinkite eksportavimo paskirties vietą, į kurią norite siųsti duomenis.

## <a name="draft-mode-for-segments"></a>Segmentų juodraščio režimas

Jei ne visi segmento apdorojimo reikalavimai įvykdyti, galite įrašyti segmentą kaip juodraštį ir pasiekti jį puslapyje **Segmentai**.

Jis bus įrašytas kaip neaktyvus segmentas ir jo negalima aktyvinti tol, kol jis nebus tinkamas.

## <a name="add-more-conditions-to-a-group"></a>Įtraukti daugiau sąlygų į grupę

Norėdami įtraukti daugiau sąlygų į grupę, galite naudoti du loginius operatorius:

- Operatorius **IR**: abi sąlygos turi būti įvykdytos kaip segmentavimo proceso dalis. Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.

- Operatorius **ARBA**: viena iš sąlygų turi būti įvykdyta kaip segmentavimo proceso dalis. Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.

   > [!div class="mx-imgBorder"]
   > ![Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta](media/segmentation-either-condition.png "Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta")

Šiuo metu galima įtraukti operatorių **Arba** į operatorių **Ir**, o ne atvirkščiai.

## <a name="combine-multiple-groups"></a>Kelių grupių derinimas

Kiekviena grupė sukuria konkretų klientų rinkinį. Galite jungti šias grupes, kad įtrauktumėte klientus, reikalingus jūsų verslo atvejui.

1. Publikos įžvalgose eikite į **Segmentų** puslapį ir pasirinkite segmentą.

2. Pažymėkite **Įtraukti grupę**.

   > [!div class="mx-imgBorder"]
   > ![Klientų grupės grupės įtraukimas](media/customer-group-add-group.png "Klientų grupės grupės įtraukimas")

3. Pasirinkite vieną iš šių rinkinio operatorių: **Sujungimas**, **Susikirtimas** arba **Išskyrus**.

   > [!div class="mx-imgBorder"]
   > ![Klientų grupės sujungimo įtraukimas](media/customer-group-union.png "Klientų grupės sujungimo įtraukimas")

   Pasirinkite rinkinio operatorių, kad apibrėžtumėte naują grupę. Įrašykite skirtingas grupes tam, kad nustatytumėte, kokie duomenys bus laikomi:

   - **Sujungimas** sujungia dvi grupes.

   - **Susikirtimas** persidengia su dviem grupėmis. Tik duomenys, kurie *yra bendri* abiem grupėms yra laikomi vieningoje grupėje.

   - **Išskyrus** sujungia dvi grupes. Laikomi tik duomenys, kurie yra A grupėje ir *nėra bendri* duomenims grupėje B.

## <a name="view-processing-history-and-segment-members"></a>Apdorojimo retrospektyvos ir segmento narių peržiūra

Konsoliduotus duomenis apie segmentą galite peržiūrėti peržiūrėdami išsamią informaciją.

Puslapyje **Segmentai** pažymėkite segmentą, kurį norite peržiūrėti.

Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius. Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data.

Galite atnaujinti vizualizacijos laiko tarpą.

> [!div class="mx-imgBorder"]
> ![Segmento laiko diapazonas](media/segment-time-range.png "Segmento laiko diapazonas")

Apatinėje dalyje yra segmento narių sąrašas.

> [!NOTE]
> Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.
>
>Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia. Norėdami peržiūrėti visu sutampančius įrašus, turite [eksportuoti segmentą](export-destinations.md).

## <a name="quick-segments"></a>Spartieji segmentai

Kartu su segmentų kūrimo įrankiu, yra kitas kelias sukurti segmentus. Naudodami sparčiuosius segmentus galite greitai kurti paprastus segmentus su vienu operatoriumi su tiesioginėmis įžvalgomis.

1. Puslapyje **Segmentai** pasirinkite **Naujas** > **Greitai kurti naudojant**.

   - Pažymėkite parinktį **Profiliai** ir sukurkite segmentą, pagrįstą vieningu kliento objektu.
   - Pažymėkite parinktį **Priemonės**, kad sukurtumėte segmentą kiekvienam kliento atributo priemonių tipam, kuriuos anksčiau sukūrėte puslapyje **Priemonės**.
   - Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.

2. Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**.

3. Sistema pateiks keletą papildomų įžvalgų, kurios padės kurti geresnius klientų segmentus.
   - Pagal kategorinius laukus parodysime 10 geriausių klientų skaičių. Pasirinkite **Reikšmė** ir pažymėkie **Peržiūra**.

   - Jei yra skaičiaus atributas, sistema parodys, kokią atributo reikšmę turi kiekvienas kliento procentilis. Pasirinkite **operatorių** ir **reikšmę**, tada pažymėkte **Peržiūra**.

4. Sistema parodys **numatomą segmento dydį**. Galite pasirinkti, ar generuoti apibrėžtą segmentą arba iš naujo jį peržiūrėti ir gauti kitą segmento dydį.

    > [!div class="mx-imgBorder"]
    > ![Sparčiojo segmento pavadinimas ir įvertinimas](media/quick-segment-name.png "Sparčiojo segmento pavadinimas ir įvertinimas")

5. Įveskite segmento **Pavadinimą**. Pasrinktinai įveskite **rodomą pavadinimą**.

6. Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą.

7. Ka segmento apdorojimas baigtas, jį galite peržiūrėti kaip bet kurį kitą sukurtą segmentą.

Toliau nurodytais atvejais patariama naudoti segmentų kūrimo priemonę, o ne rekomenduojamas segmentų galimybes:

- Segmentų kūrimas naudojant filtrus laukams, skirstomiems į kategorijas, kai operatorius skiriasi nuo operatoriaus **Yra**
- Segmentų kūrimas naudojant filtrus skaičiaus laukams, kai operatorius skiriasi nuo operatorių **Tarp**, **Didesnis nei** ir **Mažesnis nei**
- Segmentų su datos tipo laukų filtrais kūrimas

## <a name="next-steps"></a>Kiti veiksmai

[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [kliento kortele](customer-card-add-in.md) bei [jungtimis](export-power-bi.md), kad gautumėte įžvalgų apie kliento lygį.
