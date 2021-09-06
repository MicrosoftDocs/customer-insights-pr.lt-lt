---
title: Segmentų kūrimas ir valdymas
description: Kurkite klientų segmentus, kad jie būtų sugrupuoti pagal įvairius atributus.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377798"
---
# <a name="create-and-manage-segments"></a>Segmentų kūrimas ir valdymas

> [!IMPORTANT]
> Yra keli segmentų kūrimo patirties pakeitimai, pasirodantys 2021 m. rugsėjį: 
> - Segmentų daryklė atrodys šiek tiek kitokia su atnaujinto stiliaus elementais ir pagerintu vartotojų srautu.
> - Segmentų daryklėje įgalinti nauji datos ir laiko operatoriai bei patobulintas datų parinkiklis.
> - Į segmentus galėsite įtraukti arba iš jų pašalinti sąlygas ir taisykles. 
> - Taps prieinamos įdėtosios taisyklės, kurios prasideda sąlyga OR. Jums nebereikia sąlygos AND išoriniame sluoksnyje.
> - Atributų pasirinkimo šoninė sritis bus nuolat pasiekiama.
> - Objekto ryšio kelių pasirinkimo parinktis.
> Norėdami išbandyti naują segmentų daryklę, nusiųskite elektroninį laišką su tema „Prašymas įjungti naują segmento daryklę” „cihelp” [adresu] microsoft.com. Įtraukite savo organizacijos pavadinimą ir smėlio dėžės aplinkos ID.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Segmento kūrimo elementai ." lightbox="media/segment-builder-overview.png":::
>
> 1 – suskirstykite segmentą su taisyklėmis ir potaisyklėmis. Kiekvieną taisyklę ar potaisyklę sudaro sąlygos. Sąlygas derinkite su loginiais operatoriais
>
> 2 – pasirinkite [ryšio kelią](relationships.md) tarp objektų, kuriems taikoma taisyklė. Ryšio kelias nurodo, kuriuos atributus galima naudoti sąlygoje.
>
> 3 – valdykite taisykles ir potaisykles. Pakeiskite taisyklės padėtį arba panaikinkite ją.
>
> 4 – įtraukite sąlygų ir kurkite tinkamą įdėjimo lygį naudojant potaisykles.
>
> 5 – pritaikykite prijungtų taisyklių rinkinio operacijas.
>
> 6 – naudokite atributų sritį, jei norite įtraukti galimų objekto atributų arba sukurti sąlygas pagal atributus. Srityje rodomas objektų ir atributų, galimų pasirinkti taisyklei, sąrašas pagal pasirinktą ryšio kelią.
>
> 7 – įtraukite sąlygų, pagrįstų esamų taisyklių ir antrinių taisyklių atributais, arba įtraukite į naują taisyklę.
>
> 8 – kuriant segmentą anuliuokite ir perdarykite pakeitimus.

Apibrėžkite vieningojo kliento objekto ir su juo susijusių objektų sudėtinius filtrus. Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus. Segmentai yra valdomi **Segmentų** puslapyje. 

Tolesnis pavyzdys rodo segmento pajėgumą. Nustatėme klientų, kurie per paskutines 90 dienų užsisakė prekių bent už 500 $ *ir* kurie atliko klientų aptarnavimo skambutį, kuris buvo perskirtas, segmentą.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Segmento kūrimo priemonės vieningosios sąsajos su dvejomis grupėmis, nurodančiomis kliento segmentą, ekrano kopija.":::

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Naują segmentą galima sukurti keliais būdais. Šiame skyriuje aprašoma, kaip sukurti *tuščią segmentą* nuo nulio. Taip pat galite sukurti *spartųjį segmentą*, pagrįstą esamais objektais, arba naudoti mašininio mokymo modelį, kad gautumėte *siūlomus segmentus*. Daugiau informacijos: [Segmentų apžvalga](segments.md).

Kurdami segmentą, jūs galite įrašyti juodraštį. Jis bus įrašytas kaip neaktyvusis segmentas ir jo nebus galima suaktyvinti užbaigus jį naudojant tinkamą konfigūraciją.

1. Eikite į puslapį **Segmentai**.

1. Pasirinkite **Naujas** > **Tuščias segmentas**.

1. Srityje **Naujas segmentas** pasirinkite segmento tipą:

   - **Dinaminiai segmentai** [atnaujinami](segments.md#refresh-segments) pagal pasikartojantį grafiką.
   - **Statiniai segmentai** paleidžiami vieną kartą, kai juos kuriate.

1. Įveskite segmento **Išvesties objekto pavadinimą**. Galite pasirinktinai nurodyti rodomą pavadinimą ir aprašą, padedantį identifikuoti segmentą.

1. Norėdami atidaryti **segmentų kūrimo priemonės** puslapį, kuriame apibrėžėte grupė, pasirinkite **Kitas**. Grupė yra klientų rinkinys.

1. Pasirinkite objektą, kuriame yra atributas, pagal kurį norite segmentuoti.

1. Pasirinkite atributą, pagal kurį norite segmentuoti. Šis atributas gali turėti vieną iš keturių reikšmių tipų: skaičiaus, eilutės, datos arba Bulio.

1. Pasirinkite operatorių ir pasirinkto atributo reikšmę.

   > [!div class="mx-imgBorder"]
   > ![Pasirinktinis grupės filtras.](media/customer-group-numbers.png "Klientų grupės filtras")

   |Skaičius |Apibrėžtis  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributas          |
   |3    |Operatorius         |
   |4    |Reikšmė         |

   1. Norėdami įtraukti daugiau sąlygų į grupę, galite naudoti du loginius operatorius:

      - Operatorius **IR**: abi sąlygos turi būti įvykdytos kaip segmentavimo proceso dalis. Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.

      - Operatorius **ARBA**: viena iš sąlygų turi būti įvykdyta kaip segmentavimo proceso dalis. Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.

      > [!div class="mx-imgBorder"]
      > ![Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta.](media/segmentation-either-condition.png "Operatorius Ir, kuriame viena iš sąlygų turi būti įvykdyta")

      Šiuo metu galima įtraukti operatorių **Arba** į operatorių **Ir**, o ne atvirkščiai.

   1. Kiekviena grupė atitinka klientų rinkinį. Galite sujungti grupes, kad įtrauktumėte klientus, reikalingus jūsų veiklos atvejui.    
   Pažymėkite **Įtraukti grupę**.

      > [!div class="mx-imgBorder"]
      > ![Klientų grupės grupės įtraukimas.](media/customer-group-add-group.png "Klientų grupės grupės įtraukimas")

   1. Pažymėkite vieną iš rinkinio operatorių: **Sąjunga**, **Susikirtimas** arba **Išskyrus**.

   > [!div class="mx-imgBorder"]
   > ![Klientų grupės sujungimo įtraukimas.](media/customer-group-union.png "Klientų grupės sujungimo įtraukimas")

   - **Sujungimas** sujungia dvi grupes.

   - **Susikirtimas** persidengia su dviem grupėmis. Tik duomenys, kurie *yra bendri* abiem grupėms yra laikomi vieningoje grupėje.

   - **Išskyrus** sujungia dvi grupes. Laikomi tik duomenys, kurie yra A grupėje ir *nėra bendri* duomenims grupėje B.

1. Jei objektas yra sujungtas su sujungtu kliento objektu naudojant [ryšius](relationships.md), turite apibrėžti ryšio kelią, kad sukurtumėte tinkamą segmentą. Įtraukite objektus iš ryšio kelio, kol išplečiamajame sąraše galėsite pasirinkti objektą **Customer : CustomerInsights**. Tada pasirinkite **Visi įrašai** kiekvienam veiksmui.

   > [!div class="mx-imgBorder"]
   > ![Ryšių kelias kuriant segmentą.](media/segments-multiple-relationships.png "Ryšių kelias kuriant segmentą")

1. Pagal numatytuosius nustatymus, segmentai generuoja išvesties objektą, kuriame yra visi klientų profilių atributai, atitinkantys nustatytus filtrus. Jei segmentas pagrįstas kitais objektais nei *Kliento* objektas, į išvesties objektą galite įtraukti daugiau atributų iš šių objektų. Pažymėkite **Projekto atributai**, kad pasirinktumėte atributus, kurie bus pridėti prie išvesties objekto.  
  
   Pavyzdys: segmentas A yra pagrįstas objektu, kuriame yra kliento veiklos duomenų, susijusių su *Kliento* objektu. Segmentas ieško visų klientų, skambinusių pagalbos tarnybai per pastarąsias 60 dienų. Galite pasirinkti pridėti skambučio trukmę ir skambučių skaičių prie visų sutampančių išvesties objekto kliento įrašų. Ši informacija gali būti naudinga siunčiant el. laišką su naudingomis nuorodomis į internetinius žinyno straipsnius ir DUK dažnai skambinusiems klientams.

   > [!NOTE]
   > - Suplanuoti atributai veikia tik tiems objektams, kurie turi „vienas su daugeliu” ryšį su kliento objektu. Pavyzdžiui, vienas klientas gali turėti kelias prenumeratas.
   > - Suplanuoti atributus galite tik iš to objekto, kuris yra naudojamas kiekvienoje jūsų kuriamų segmentų užklausų grupėje.
   > - Suplanuoti atributai yra įtraukiami naudojant rinkinio operatorius.

1. Pasirinkite **Įrašyti**, kad įrašytumėte segmentą. Jūsų segmentas bus įrašytas ir apdorojamas, jei visi reikalavimai bus patvirtinti. Kitu atveju jis bus Išsaugota kaip juodraštis.

1. Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.



## <a name="quick-segments"></a>Spartieji segmentai

Spartieji segmentai leidžia jums greitai sukurti paprastus segmentus naudojant vieną operatorių, kad įžvalgos būtų greitesnės.

1. Puslapyje **Segmentai** pasirinkite **Naujas** > **Kurti iš**.

   - Pažymėkite parinktį **Profiliai**, kad sukurtumėte segmentą, pagrįstą *vieningojo klientu* objektu.
   - Pažymėkite parinktį **Matavimai**, kad sukurtumėte segmentą pagal anksčiau jūsų sukurtus matavimus.
   - Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.

2. Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**.

3. Sistema pateiks keletą papildomų įžvalgų, kurios padės kurti geresnius klientų segmentus.
   - Pagal kategorinius laukus parodysime 10 geriausių klientų skaičių. Pasirinkite **Reikšmė** ir pažymėkite **Peržiūra**.

   - Jei yra skaičiaus atributas, sistema parodys, kokią atributo reikšmę turi kiekvienas kliento procentilis. Pasirinkite **operatorių** ir **reikšmę**, tada pažymėktie **Peržiūra**.

4. Sistema parodys **numatomą segmento dydį**. Galite pasirinkti, ar generuoti apibrėžtą segmentą arba iš naujo jį peržiūrėti ir gauti kitą segmento dydį.

    > [!div class="mx-imgBorder"]
    > ![Sparčiojo segmento pavadinimas ir įvertinimas.](media/quick-segment-name.png "Sparčiojo segmento pavadinimas ir įvertinimas")

5. Įveskite segmento **Pavadinimą**. Pasirinktinai įveskite **rodomą pavadinimą**.

6. Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą.

7. Kai segmento apdorojimas baigtas, jį galite peržiūrėti kaip bet kurį kitą sukurtą segmentą.

## <a name="next-steps"></a>Kiti veiksmai

[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [klientų kortelių integravimu](customer-card-add-in.md) naudoti segmentus kitose programose.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
