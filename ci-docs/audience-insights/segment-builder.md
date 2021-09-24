---
title: Kurkite segmentus naudodami segmentų kūrimo priemonę
description: Kurkite klientų segmentus, kad jie būtų sugrupuoti pagal įvairius atributus.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494512"
---
# <a name="create-segments"></a>Kurti segmentus

Apibrėžkite vieningojo kliento objekto ir su juo susijusių objektų sudėtinius filtrus. Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus. Segmentai yra valdomi **Segmentų** puslapyje. Galite [kurti naujus segmentus](#create-a-new-segment) naudodami [segmentų kūrimo priemonę](#segment-builder) arba [kurti sparčiuosius segmentus](#quick-segments) iš kitų programos sričių.

## <a name="segment-builder"></a>Segmentų kūrimo priemonė

Toliau pateiktas vaizdas iliustruoja įvairius segmentų kūrimo priemonės aspektus. Jame rodomas segmentas, sukuriantis klientų grupę. Klientai užsisakė prekes konkrečiu laikotarpiu ir surinko daug taškų arba išleido tam tikrą pinigų sumą. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmento kūrimo elementai ." lightbox="media/segment-builder-overview.png":::

1 – suskirstykite segmentą su taisyklėmis ir potaisyklėmis. Kiekvieną taisyklę ar potaisyklę sudaro sąlygos. Sąlygas derinkite su loginiais operatoriais

2 – pasirinkite [ryšio kelią](relationships.md) tarp objektų, kuriems taikoma taisyklė. Ryšio kelias nurodo, kuriuos atributus galima naudoti sąlygoje.

3 – valdykite taisykles ir potaisykles. Pakeiskite taisyklės padėtį arba panaikinkite ją.

4 – įtraukite sąlygų ir kurkite tinkamą įdėjimo lygį naudojant potaisykles.

5 – pritaikykite prijungtų taisyklių rinkinio operacijas.

6 – naudokite atributų sritį, jei norite įtraukti galimų objekto atributų arba sukurti sąlygas pagal atributus. Srityje rodomas objektų ir atributų, galimų pasirinkti taisyklei, sąrašas pagal pasirinktą ryšio kelią.

7 – įtraukite sąlygų, pagrįstų esamų taisyklių ir antrinių taisyklių atributais, arba įtraukite į naują taisyklę.

8 – kuriant segmentą anuliuokite ir perdarykite pakeitimus.

Aukščiau pateiktas pavyzdys iliustruoja segmentavimo galimybę. Sukūrėme segmentą klientams, kurie bent už $500 nusipirko prekių internetu *ir* yra suinteresuoti programinės įrangos kūrimu.

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Naują segmentą galima sukurti keliais būdais. Šiame skyriuje aprašoma, kaip sukurti savo segmentą nuo nulio. Taip pat galite sukurti *spartųjį segmentą*, pagrįstą esamais objektais, arba naudoti mašininio mokymo modelį, kad gautumėte *siūlomus segmentus*. Daugiau informacijos: [Segmentų apžvalga](segments.md).

Kurdami segmentą, jūs galite įrašyti juodraštį. Jis bus įrašytas kaip neaktyvusis segmentas ir jo nebus galima suaktyvinti užbaigus jį naudojant tinkamą konfigūraciją.

1. Eikite į puslapį **Segmentai**.

1. Pažymėkite **Naujas** > **Sukurkite savo**.

1. Segmentų kūrimo priemonės puslapyje apibrėžiate pirmą taisyklę. Taisyklę sudaro viena ar daugiau sąlygų ir ji apibrėžia klientų rinkinį.

1. Skyriuje **1 taisyklė** pasirinkite objekto atributą, pagal kurį norite filtruoti klientus. Pasirinkti atributus galite dviem būdais: 
   - Peržiūrėkite galimų objektų ir atributų sąrašą srityje **Įtraukti į taisyklę** ir pažymėkite **„+”** piktogramą šalia atributo, kurį norite įtraukti. Pasirinkite, ar norite įtraukti atributą į esamą taisyklę, ar naudoti jį naujai taisyklei kurti.
   - Norėdami peržiūrėti sutampančius pasiūlymus, taisyklės skyriuje įveskite atributo pavadinimą.

1. Pasirinkite operatorius, kad nurodytumėte sąlygos atitikmenų reikšmes. Atributas gali turėti vieną iš keturių duomenų tipų kaip reikšmę: skaitinę, eilutės, datos arba Bulio logikos. Priklausomai nuo atributo duomenų tipo, sąlygą galima nurodyti skirtingais operatoriais. 

1. Pasirinkite **Įtraukti sąlygą**, jei į taisyklę norite įtraukti daugiau sąlygų. Norėdami sukurti taisyklę pagal dabartinę taisyklę, pažymėkite **Įtraukti antrinę taisyklę**.

1. Jei taisyklė naudoja kitus objektus, o ne *Kliento* objektą, turite nustatyti ryšio kelią. Ryšio kelias reikalingas informuoti sistemą, per kuriuos ryšius jūs norite pasiekti vieningąjį kliento objektą. Pasirinkite **Nustatyti ryšio kelią**, kad pažymėtą objektą būtų galima susieti su vieninguoju kliento objektu. Jei yra tik vienas galimas ryšio kelias, sistema jį pasirinks automatiškai. Įvairūs ryšio keliai gali pateikti skirtingus rezultatus. Kiekviena taisyklė gali turėti savo ryšio kelią.

   :::image type="content" source="media/relationship-path.png" alt-text="Galimas ryšio kelias kuriant taisyklę, pagrįstą objektu, susietu su vieninguoju kliento objektu.":::

   Pavyzdžiui, objektas *„eCommerce_eCommercePurchases”* ekrano kopijoje turi keturias susiejimo su *Kliento* objektu parinktis: 
   - „eCommerce_eCommercePurchases” > „eCommerce_eCommerceContacts” > Klientas
   - eCommerce_eCommercePurchases > klientas
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > klientas
   - „eCommerce_eCommercePurchases” > „eCommerce_eCommerceContacts” > „POS_posPurchases” > „loyaltyScheme_loyCustomers” > „Customer” Kai pasirenkate paskutinę parinktį, į taisyklės sąlygas galime įtraukti atributus iš visų išvardytų objektų. Tikriausiai gausime mažiau rezultatų, nes sutampantys klientų įrašai turi būti visų objektų dalis. Šiame pavyzdyje jie turi būti įsigiję prekes per elektroninę prekybą(*„eCommerce_eCommercePurchases”*), pardavimo vietoje (*„POS_posPurchases”*) ir dalyvauti mūsų lojalumo programoje (*„loyaltyScheme_loyCustomers”*). Pasirinkdami antrą parinktį galime pasirinkti tik atributus iš *„eCommerce_eCommercePurchases”* ir *Kliento* objektų. Tikėtina, jog dėl to atsiras daugiau klientų profilių.

1. Jeigu taisyklėje yra kelios sąlygos, galite pasirinkti, kuris loginis operatorius juos prijungs.

   - **IR** operatorius: norint į segmentą įtraukti įrašą, visos sąlygos turi būti įvykdytos. Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.

   - **ARBA** operatorius: norint į segmentą įtraukti įrašą, viena iš pateiktų sąlygų turi būti įvykdyta. Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Taisyklė su dvejomis IR sąlygomis.":::

   Naudojant ARBA operatorių visos sąlygos turi būti pagrįstos į ryšio kelią įtrauktais objektais.

   1. Galite sukurti kelias taisykles skirtingiems klientų įrašų rinkiniams kurti. Galite sujungti grupes, kad įtrauktumėte klientus, reikalingus jūsų veiklos atvejui. Pasirinkite **Įtraukti taisyklę**, kad sukurtumėte naują taisyklę. Jei į taisyklę negalite įtraukti objekto dėl nurodyto ryšio kelio, turite sukurti naują taisyklę, pagal kurią būtų galima pasirinkti atributų formą.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Į segmentą įtraukite naują taisyklę ir pasirinkite rinkinio operatorių.":::

   1. Pažymėkite vieną iš rinkinio operatorių: **Sąjunga**, **Susikirtimas** arba **Išskyrus**.

   - **Sujungimas** sujungia dvi grupes.

   - **Susikirtimas** persidengia su dviem grupėmis. Tik duomenys, kurie *yra bendri* abiem grupėms yra laikomi vieningoje grupėje.

   - **Išskyrus** sujungia dvi grupes. Laikomi tik duomenys, kurie yra A grupėje ir *nėra bendri* duomenims grupėje B.

1. Pagal numatytuosius nustatymus segmentai sugeneruoja išvesties objektą, kuriame yra visi klientų profilių atributai, atitinkantys apibrėžtus filtrus. Jei segmentas pagrįstas kitais objektais nei *Kliento* objektas, į išvesties objektą galite įtraukti daugiau atributų iš šių objektų. Pažymėkite **Projekto atributai**, kad pasirinktumėte atributus, kurie bus pridėti prie išvesties objekto.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Projektuotų atributų, pasirinktų šoninėje srityje, kuriuos reikia įtraukti į išvesties objektą, pavyzdys.":::
  
   Pavyzdys: segmentas yra pagrįstas objektu, kuriame yra pirkimo duomenų, susijusių su *Kliento* objektu. Segmentas ieško visų klientų iš Ispanijos, kurie per dabartinius metus įsigijo prekių. Galite pasirinkti pridėti atributus, pavyzdžiui, prekių kainą, arba pirkimo datą visiems atitinkantiems kliento įrašams išvesties objekte. Ši informacija gali būti naudinga analizuojant bendrų išlaidų sezonines sąsajas.

   > [!NOTE]
   > - Suplanuoti atributai veikia tik tiems objektams, kurie turi „vienas su daugeliu” ryšį su kliento objektu. Pavyzdžiui, vienas klientas gali turėti kelias prenumeratas.
   > - Jūs galite projektuoti atributus tik iš to objekto, kuris yra naudojamas kiekvienoje jūsų kuriamoje segmento užklausos taisyklėje.
   > - Suplanuoti atributai yra įtraukiami naudojant rinkinio operatorius.

1. Prieš įrašydami ir paleisdami segmentą, pasirinkite **Redaguoti išsamią informaciją** šalia segmento pavadinimo. Įveskite savo segmento pavadinimą ir atnaujinkite siūlomą **Išvesties objekto pavadinimą** segmentui. Į segmentą taip pat galite įtraukti aprašą.

1. Pasirinkite **Vykdyti**, kad įrašytumėte ir apdorotumėte segmentą, jei visi reikalavimai patikrinti. Kitu atveju jis bus įrašytas kaip neaktyvusis segmento juodraštis.

1. Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.

> [!TIP]
> - Nustatant sąlygų operatorius, segmentų kūrimo priemonė nesiūlys galiojančių objektų reikšmių. Galite eiti į **Duomenis** > **Objektai** ir atsisiųsti objekto duomenis, kad pamatytumėte, kurios reikšmės yra galimos.
> - Datomis pagrįstos sąlygos leidžia jums perjungti tarp fiksuotų datų ir slankiojo kablelio datų intervalo.
> - Jei savo segmente turite kelias taisykles, galite rasti mėlyną juostą prie redaguojamos taisyklės.
> - Taisykles ir sąlygas galite perkelti į kitas segmento aprašo vietas. Pasirinkite [...] šalia taisyklės arba sąlygos ir pasirinkite, kaip ir kur ją perkelti.
> - Naudojant komandų juostos valdiklius **Anuliuoti** ir **Perdaryti** galima atšaukti keitimus.

## <a name="quick-segments"></a>Spartieji segmentai

Spartieji segmentai leidžia jums greitai sukurti paprastus segmentus naudojant vieną operatorių, kad įžvalgos būtų greitesnės.

1. Puslapyje **Segmentai** pasirinkite **Naujas** > **Kurti iš**.

   - Pažymėkite parinktį **Profiliai**, kad sukurtumėte segmentą, pagrįstą *vieningojo klientu* objektu.
   - Pažymėkite parinktį **Matavimai**, kad sukurtumėte segmentą pagal anksčiau jūsų sukurtus matavimus.
   - Pasirinkite parinktį **Įžvalgos**, norėdami sukurti segmentą naudojant vieną iš išvesties objektų, kuriuos sugeneravote naudodami galimybes **Prognozės** arba **Pasirinktiniai modeliai**.

2. Dialogo lange **Naujas spartusis segmentas** pasirinkite atributą iš išplečiamojo sąrašo **Laukas**.

3. Sistema pateiks daugiau įžvalgų, padėsiančių jums kurti geresnius klientų segmentus.
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
