---
title: Kurti segmentus
description: Kurkite klientų segmentus, kad sugrupuotumėte juos pagal įvairius atributus naudodami segmentų kūrimo priemonę arba sparčiuosius segmentus.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: b99d9575d3b6af91758d80eb04170773b08cc9ab
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053982"
---
# <a name="create-segments"></a>Kurti segmentus

Apibrėžkite vieningojo kliento objekto ir su juo susijusių objektų sudėtinius filtrus. Apdorojus, kiekvienas segmentas sukuria klientų duomenų rinkinį, kurį galite eksportuoti, ir su kuriuo galite atlikti veiksmus. Segmentai yra valdomi **Segmentų** puslapyje. Galite [kurti naujus segmentus](#create-a-new-segment) naudodami segmentų kūrimo priemonę ar [kurti sparčiuosius segmentus](#quick-segments) iš kitų programos sričių.

> [!TIP]
> - Sparčiuosius segmentus galima naudoti tik atskirų **klientų aplinkose**.
> - Segmentuose, pagrįstuose **atskirais klientais**, automatiškai įtraukiama prieinama segmento narių kontaktinė informacija. Verslo paskyrų **aplinkose segmentai** grindžiami klientais (įmonėmis arba antrinėmis įmonėmis). Norėdami į segmentą įtraukti kontaktinę informaciją, naudokite **projekto atributų** funkcijas segmento atributų atributuose. Užtikrinkite, kad kontaktų duomenų šaltiniai [būtų automatiškai susieti su „ContactProfile"](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) objektu.

## <a name="segment-builder"></a>Segmentų kūrimo priemonė

Toliau pateiktas vaizdas iliustruoja įvairius segmentų kūrimo priemonės aspektus. Jame rodomas segmentas, sukuriantis klientų grupę. Klientai užsaavo prekes konkrečiu laikotarpiu ir surinko apdovanojimo taškus arba praleido tam tikrą pinigų sumą.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmento kūrimo elementai ." lightbox="media/segment-builder-overview.png":::

1. Suskirstykite segmentą su taisyklėmis ir potaisyklėmis. Kiekvieną taisyklę ar potaisyklę sudaro sąlygos. Sąlygas derinkite su loginiais operatoriais

1. Pasirinkite [ryšio kelią](relationships.md) tarp objektų, kuriems taikoma taisyklė. Ryšio kelias nurodo, kuriuos atributus galima naudoti sąlygoje.

1. Valdykite taisykles ir potaisykles. Pakeiskite taisyklės padėtį arba panaikinkite ją.

1. Įtraukite sąlygų ir kurkite tinkamą įdėjimo lygį naudojant potaisykles.

1. Pritaikykite prijungtų taisyklių rinkinio operacijas.

1. Naudokite atributų sritį, jei norite įtraukti galimų objekto atributų arba sukurti sąlygas pagal atributus. Srityje rodomas objektų ir atributų, galimų pasirinkti taisyklei, sąrašas pagal pasirinktą ryšio kelią.

1. Įtraukite sąlygų, pagrįstų esamų taisyklių ir antrinių taisyklių atributais, arba įtraukite į naują taisyklę.

1. Kuriant segmentą anuliuokite ir perdarykite pakeitimus.

Aukščiau pateiktas pavyzdys iliustruoja segmentavimo galimybę. Sukūrėme segmentą klientams, kurie bent už $500 nusipirko prekių internetu *ir* yra suinteresuoti programinės įrangos kūrimu.

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Naują segmentą galima sukurti keliais būdais. Šiame skyriuje aprašoma, kaip sukurti savo segmentą nuo nulio. Taip pat galite sukurti *spartųjį segmentą*, pagrįstą esamais objektais, arba naudoti mašininio mokymo modelį, kad gautumėte *siūlomus segmentus*. Norėdami gauti daugiau informacijos, eikite į [Segmentų apžvalga](segments.md).

Kurdami segmentą, jūs galite įrašyti juodraštį. Juodraščio etapo segmentas įrašomas kaip neaktyvusis segmentas. Baigę konfigūruoti segmentą, paleiskite jį, kad suaktyvintumėte segmentą. Arba galite taip pat **Aktyvinti** segmentą iš puslapio **Visi segmentai**.

1. Eikite į puslapį **Segmentai**.

1. Pažymėkite **Naujas** > **Sukurkite savo**.

1. Segmento segmento apibrėžiate arba kuriate taisykles. Taisyklę sudaro viena ar daugiau sąlygų, apibrėžiaančių klientų rinkinį.

1. Sekcijoje **Taisyklė1** pasirinkite objekto, pagal kurį norite filtruoti klientus, atributą. Pasirinkti atributus galite dviem būdais:
   - Peržiūrėkite galimų objektų ir atributų sąrašą srityje **Įtraukti į taisyklę** ir pažymėkite **„+”** piktogramą šalia atributo, kurį norite įtraukti. Pasirinkite, ar norite įtraukti atributą į esamą taisyklę, ar naudoti jį naujai taisyklei kurti.
   - Norėdami peržiūrėti sutampančius pasiūlymus, taisyklės skyriuje įveskite atributo pavadinimą.

1. Pasirinkite operatorius, kad nurodytumėte sąlygos atitikmenų reikšmes. Atributas gali turėti vieną iš keturių duomenų tipų kaip reikšmę: skaitinę, eilutės, datos arba Bulio logikos. Priklausomai nuo atributo duomenų tipo, sąlygą galima nurodyti skirtingais operatoriais. Segmentuose su verslo klientais galimi du specialūs operatoriai, kad būtų galima įtraukti potencialias iki šiol suskirstytas paskyras. Norėdami įtraukti *susijusius* ir *pagrindinius* operatorius į susijusias paskyras.

1. Pasirinkite **Įtraukti sąlygą**, jei į taisyklę norite įtraukti daugiau sąlygų. Norėdami sukurti taisyklę pagal dabartinę taisyklę, pažymėkite **Įtraukti antrinę taisyklę**.

1. Jei taisyklė naudoja kitus objektus, o ne *Kliento* objektą, turite nustatyti ryšio kelią. Ryšio kelias reikalingas informuoti sistemą, per kuriuos ryšius jūs norite pasiekti vieningąjį kliento objektą. Pasirinkite **Nustatyti ryšio kelią**, kad pažymėtą objektą būtų galima susieti su vieninguoju kliento objektu. Jei yra tik vienas galimas ryšio kelias, sistema jį pasirinks automatiškai. Įvairūs ryšio keliai gali pateikti skirtingus rezultatus. Kiekviena taisyklė gali turėti savo ryšio kelią.

   :::image type="content" source="media/relationship-path.png" alt-text="Galimas ryšio kelias kuriant taisyklę, pagrįstą objektu, susietu su vieninguoju kliento objektu.":::

   Pavyzdžiui, objektas *„eCommerce_eCommercePurchases”* ekrano kopijoje turi keturias susiejimo su *Kliento* objektu parinktis:
   - „eCommerce_eCommercePurchases” > „eCommerce_eCommerceContacts” > Klientas
   - eCommerce_eCommercePurchases > klientas
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > klientas
   - „eCommerce_eCommercePurchases” > „eCommerce_eCommerceContacts” > „POS_posPurchases” > „loyaltyScheme_loyCustomers” > „Customer” Kai pasirenkate paskutinę parinktį, į taisyklės sąlygas galime įtraukti atributus iš visų išvardytų objektų. Tikriausiai gausime mažiau rezultatų, nes sutampantys klientų įrašai turės būti visų objektų dalis. Šiame pavyzdyje jie turi būti įsigiję prekes per elektroninę prekybą(*„eCommerce_eCommercePurchases”*), pardavimo vietoje (*„POS_posPurchases”*) ir dalyvauti mūsų lojalumo programoje (*„loyaltyScheme_loyCustomers”*). Pasirinkdami antrą parinktį galime pasirinkti tik atributus iš *„eCommerce_eCommercePurchases”* ir *Kliento* objektų. Tikėtina, jog dėl to atsiras daugiau klientų profilių.

1. Jeigu taisyklėje yra kelios sąlygos, galite pasirinkti, kuris loginis operatorius juos prijungs.  
   - **IR** operatorius: norint į segmentą įtraukti įrašą, visos sąlygos turi būti įvykdytos. Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.
   - **ARBA** operatorius: norint į segmentą įtraukti įrašą, viena iš pateiktų sąlygų turi būti įvykdyta. Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Taisyklė su dvejomis IR sąlygomis.":::

   Naudojant ARBA operatorių visos sąlygos turi būti pagrįstos į ryšio kelią įtrauktais objektais.

   - Galite sukurti kelias taisykles skirtingiems klientų įrašų rinkiniams kurti. Galite sujungti grupes, kad įtrauktumėte klientus, reikalingus jūsų veiklos atvejui. Pasirinkite **Įtraukti taisyklę**, kad sukurtumėte naują taisyklę. Konkrečiau, jei negalite įtraukti taisyklės ir į ją įtraukti objekto dėl nurodyto ryšio maršruto, turite sukurti naują taisyklę, pagal kurią būtų galima pasirinkti atributų formą.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Į segmentą įtraukite naują taisyklę ir pasirinkite rinkinio operatorių.":::

   - Pažymėkite vieną iš rinkinio operatorių: **Sąjunga**, **Susikirtimas** arba **Išskyrus**.

      - **Sujungimas** sujungia dvi grupes.
      - **Susikirtimas** persidengia su dviem grupėmis. Vieningoje *grupėje* lieka tik duomenys, kurie dažnai pasitaiko abiejose grupėse.
      - **Išskyrus** sujungia dvi grupes. Saugomi tik A grupės *duomenys* kurie nėra įprasta B grupės duomenims.

1. Pagal numatytuosius nustatymus segmentai sugeneruoja išvesties objektą, kuriame yra visi klientų profilių atributai, atitinkantys apibrėžtus filtrus. Jei segmentas pagrįstas kitais objektais nei *Kliento* objektas, į išvesties objektą galite įtraukti daugiau atributų iš šių objektų. Pažymėkite **Projekto atributai**, kad pasirinktumėte atributus, kurie bus pridėti prie išvesties objekto.

   > [!IMPORTANT]
   > Segmentams, pagrįstims verslo klientais, į segmentą reikia įtraukti išsamią informaciją apie vieną ar daugiau kiekvieno kliento kontaktų, kad tą segmentą būtų galima aktyvuoti arba eksportuoti iš *ContactProfile* į paskirties vietas, kurioms reikia kontaktinės informacijos. Daugiau informacijos apie *ContactProfile* objektą ieškokite [Semantiniai susiejimai](semantic-mappings.md).
   > Segmento, pagrįsto verslo klientais, su projektais kontaktų atributais, rezultatų pavyzdys gali atrodyti taip:
   >
   > |ID  |Paskyros pavadinimas  |Įplaukos  |Kontakto pavadinimas  | Kontakto vaidmuo|
   > |---------|---------|---------|---------|---|
   > |10021     | „Contoso“ | 100K (100K) | [Abbie Moss, Ruth Soto]  | [CEO, Tiekimo vadovas]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Projektuotų atributų, pasirinktų šoninėje srityje, kuriuos reikia įtraukti į išvesties objektą, pavyzdys.":::
  
   Pavyzdžiui: segmentas pagrįstas objektu, kuriame yra pirkimo duomenų, susijusių su *kliento* objektu. Segmentas ieško visų klientų iš Ispanijos, kurie per dabartinius metus įsigijo prekių. Galite pasirinkti pridėti atributus, pavyzdžiui, prekių kainą, arba pirkimo datą visiems atitinkantiems kliento įrašams išvesties objekte. Ši informacija gali būti naudinga analizuojant bendrų išlaidų sezonines sąsajas.

   > [!NOTE]
   > - **Projekto atributai** veikia tik objektams, kurie turi ryšį "vienas su daugeliu" su kliento objektu. Pavyzdžiui, vienas klientas gali turėti kelias prenumeratas.
   > - Jei atributas, kurį norite įtraukti į projektą, yra daugiau nei vienas objekto klientas, kaip apibrėžta ryšio, šis atributas turi būti naudojamas kiekvienoje *kuriamos* segmento užklausos taisyklėje.
   > - Jei atributas, kurį norite įtraukti į projektą, yra daugiau nei vienas objekto klientas, kaip apibrėžta ryšio, šis atributas neturi būti rodomas kiekvienoje *kuriamos* segmento užklausos taisyklėje.
   > - **Suplanuoti atributai** yra įtraukiami naudojant rinkinio operatorius.

1. Pasirinkite **Redaguoti išsamią informaciją** šalia Segmentas Be pavadinimo. Įveskite savo segmento pavadinimą ir atnaujinkite siūlomą **Išvesties objekto pavadinimą** segmentui. Pasirinktinai prie segmento pridėkite aprašą ir [žymes](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialogo langas Redaguoti išsamią informaciją.":::

1. Pasirinkite **Vykdyti**, kad įrašytumėte segmentą, jį suaktyvintumėte ir pradėkite apdoroti segmentą pagal visas taisykles ir sąlygas. Priešingu atveju jis bus įrašytas kaip neaktyvusis segmentas.

1. Pasirinkite **Atgal į segmentus**, kad sugrįžtumėte į puslapį **Segmentai**.

1. Pagal numatytuosius nustatymus segmentas sukuriamas kaip dinaminis segmentas. Tai reiškia, kad sistemos atnaujinimo metu segmentas atnaujinamas. Norėdami [sustabdyti automatinį naujinimą](segments.md#manage-existing-segments), pažymėkite segmentą ir pasirinkite parinktį **Atlikti statinį**. Statinius segmentus galima [naujinti rankiniu būdu](segments.md#refresh-segments) bet kuriuo metu.

> [!TIP]
> - Nustatant sąlygų operatorius, segmentų kūrimo priemonė nesiūlys galiojančių objektų reikšmių. Galite eiti į **Duomenis** > **Objektai** ir atsisiųsti objekto duomenis, kad pamatytumėte, kurios reikšmės yra galimos.
> - Datomis pagrįstos sąlygos leidžia jums perjungti tarp fiksuotų datų ir slankiojo kablelio datų intervalo.
> - Jei turite kelias segmento taisykles, redaguojate taisyklę šalia jos yra vertikali mėlyna linija.
> - Taisykles ir sąlygas galite perkelti į kitas segmento aprašo vietas. Pasirinkite vertikalią daugtaškį (&vellip;) šalia taisyklės arba sąlygos ir pasirinkite, kaip ir kur ją perkelti.
> - Naudojant komandų juostoje valdiklius **Anuliuoti** ir Perdaryti galima **atšaukti** keitimus.
> - Sukūrus segmentą, kai kurie segmentai leidžia stebėti [segmento](segments.md#track-usage-of-a-segment) naudojimą.

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

   :::image type="content" source="media/quick-segment-name.png" alt-text="Sparčiojo segmento pavadinimas ir įvertinimas.":::

5. Pateikite segmento **pavadinimo** ir **išvesties objekto pavadinimą**. Pasirinktinai pridėkite [žymų](work-with-tags-columns.md#manage-tags).

6. Pasirinkite **Įrašyti**, kad sukurtumėte savo segmentą.

7. Kai segmento apdorojimas baigtas, jį galite peržiūrėti kaip bet kurį kitą sukurtą segmentą.

## <a name="next-steps"></a>Kiti veiksmai

[Eksportuokite segmentą](export-destinations.md) ir susipažinkite su [klientų kortelių integravimu](customer-card-add-in.md) naudoti segmentus kitose programose.

[!INCLUDE [footer-include](includes/footer-banner.md)]
