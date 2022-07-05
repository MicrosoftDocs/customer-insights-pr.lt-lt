---
title: Duomenų suvienodinimo atitikties sąlygos
description: Suderinkite objektus tam, kad sukurtumėte suvienytus kliento profilius.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 770a18f3a7471714a7e044ae034da168a2601010
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082411"
---
# <a name="match-conditions-for-data-unification"></a>Duomenų suvienodinimo atitikties sąlygos

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis suvienijimo veiksmas apibrėžia atitikties tvarką ir kryžminio objekto atitikties taisykles. Šiam veiksmui atlikti reikia bent dviejų objektų.

> [!NOTE]
> Sukūrę atitikties sąlygas ir pasirinkę **Pirmyn**, negalite pašalinti pasirinkto objekto arba atributo. Jei reikia, prieš tęsdami pasirinkite **Atgal**, kad peržiūrėtumėte pasirinktus objektus ir atributus.

## <a name="include-enriched-entities-preview"></a>Papildytųjų objektų įtraukimas (peržiūra)

Jei praturtinote objektus duomenų šaltinis lygiu, kad pagerintumėte suvienijimo rezultatus, pasirinkite juos. Daugiau informacijos ieškokite [Duomenų šaltinių papildymas](data-sources-enrichment.md). Jei puslapyje Besidubliuojantys įrašai pasirinkote papildytus **objektus**, jums nereikia jų dar kartą žymėti.

1. Puslapyje Atitikimo **sąlygos** puslapio viršuje pasirinkite **Naudoti papildytus objektus**.

1. Srityje Naudoti papildytus **objektus** pasirinkite vieną ar daugiau papildytų objektų.

1. Pasirinkite **Atlikta**.

## <a name="specify-the-match-order"></a>Nurodykite atitikties eiliškumą

Kiekvienas atitikmuo suvienodina du ar daugiau objektų į vieną konsoliduotą objektą. Tuo pačiu metu jis saugo unikaliuosius klientų įrašus. Atitikties tvarka nurodo tvarką, kuria sistema bando suderinti įrašus.

> [!IMPORTANT]
> Pirmasis sąrašo objektas vadinamas pirminiu objektu. Pagrindinis objektas yra jūsų vieningųjų profilių duomenų rinkinio pagrindas. Papildomi pasirinkti objektai bus įtraukti į šį objektą.
>
> Svarbios aplinkybės:
>
> - Pasirinkite objektą su išsamiausiais ir patikimiausiais profilio duomenimis apie klientus kaip pagrindinį objektą.
> - Kaip pagrindinį objektą pasirinkite objektą, kurio keli bendrai naudojami atributai su kitais objektais (pvz., vardas, telefono numeris arba el. pašto adresas).

1. Puslapyje Atitikimo **sąlygos** naudokite rodykles judėti aukštyn ir žemyn, kad perkeltumėte objektus norima tvarka, arba vilkite ir numeskite juos. Pavyzdžiui, pasirinkite **Kontaktai:el. prekyba** kaip pagrindinį objektą ir **CustomerLoyalty:Loyalty** kaip antrąjį objektą.

1. Norėdami, kad kiekvienas objekto įrašas būtų unikalus klientas, neatsižvelgiant į tai, ar rasta atitiktis, pasirinkite **Įtraukti visus įrašus**. Visi šio objekto įrašai, neatitinkantys jokių kitų objektų įrašų, įtraukiami į vieningąjį profilį. Įrašai, kurie neturi atitikmens, vadinami singletonais.
  
Pagrindinis objektas *Kontaktai:el. prekyba* yra suderinamas su kitu objektu *CustomerLoyalty:Loyalty*. Duomenų rinkinys, gautas atlikus pirmąjį atitikties veiksmą, suderinamas su toliau nurodytu objektu, jei turite daugiau nei du objektus.

:::image type="content" source="media/m3_match.png" alt-text="Pasirinktos objektų atitikties tvarkos ekrano kopija." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Taisyklių apibrėžimas atitikmenų poroms

Atitikties taisyklėse nurodoma logika, pagal kurią bus derinama konkreti objektų pora. Taisyklę sudaro viena ar daugiau sąlygų.

Įspėjimas šalia objekto pavadinimo reiškia, kad atitikmenų porai nenustatyta atitikties taisyklė.

1. Pasirinkite **Įtraukti taisyklę**, skirtą objektų porai, kad apibrėžtumėte atitikties taisykles.

1. **Srityje Įtraukti taisyklę** konfigūruokite taisyklės sąlygas.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Taisyklės įtraukimo srities ekrano nuotrauka.":::

   - **Pasirinkite Objektas / laukas (pirmoji eilutė)**: pasirinkite susijusį objektą ir atributą, kad nurodytumėte įrašo ypatybę, kuri gali būti unikali klientui. Pavyzdžiui, telefono numeris ar el. pašto adresas. Venkite gretinti pagal veiklos tipo atributus. Pavyzdžiui, tikėtina, kad pirkimo ID neras atitikmens kituose įrašų tipuose.

   - **Pasirinkite Objektas / laukas (antra eilutė)**: pasirinkite atributą, susijusį su pirmoje eilutėje nurodytu objekto atributu.

   - **Normalizuoti** : Pasirinkite iš šių pasirinktų atributų normalizavimo parinkčių.
     - **Skaitmenys**: konvertuoja kitas skaitmenų sistemas, pvz., romėniškus skaitmenis, į arabiškus skaitmenis. *VIII* tampa *8*.
     - **Simboliai**: pašalina visus simbolius ir specialiuosius simbolius. *„Head&Shoulder”* tampa *„HeadShoulder”*.
     - **Tekstas į mažąsias raides**: konvertuoja visus simbolius į mažąsias raides. *VISOS DIDŽIOSIOS ir Pirmos Didžiosios* tampa *visos didžiosios ir pirmos didžiosios*.
     - **Tipas (telefonas, vardas, adresas, organizacija)**: standartizuoja vardus, pavadinimus, telefono numerius, adresus ir organizacijas.
     - **Unicode į ASCII**: konvertuoja unicode žymėjimą į ASCII simbolius. *„/u00B2”* tampa *2*.
     - **Tarpai**: pašalina visus tarpus. *Labas Pasauli* tampa *LabasPasauli*.

   - **Tikslumas**: Nustatykite šiai sąlygai taikytiną tikslumo lygį.
     - **Pagrindinis**: Rinkitės iš *žemo (30%)*, *vidutinio (60%)*, *aukšto (80%)*, ir *tikslaus (100%)*. Pasirinkite **Tiksliai**, kad atitiktų tik tuos įrašus, kurie atitinka 100 procentų.
     - **Pasirinktinis**: Nustatykite procentą, kurį turi atitikti įrašai. Sistema sugretins tik įrašus, perlipusius ribinę reikšmę.

   - **Pavadinimas**: taisyklės pavadinimas.

1. Norėdami suderinti objektus tik tuo atveju, jei atributai atitinka kelias sąlygas, pasirinkite **Įtraukti sąlygą** > **Įtraukti**, kad į atitikties taisyklę įtrauktumėte daugiau sąlygų. Sąlygos yra susijusios su loginiu IR operatoriumi ir todėl vykdomos tik tuo atveju, jeigu įvykdomos visos sąlygos.

1. Pasirinktinai apsvarstykite išplėstines parinktis, pvz. [, išimtis](#add-exceptions-to-a-rule) arba [pasirinktines atitikties sąlygas](#specify-custom-match-conditions).

1. Pasirinkite **Atlikta**, kad užbaigtumėte taisyklę.

1. Pasirinktinai [įtraukite daugiau taisyklių](#add-rules-to-a-match-pair).

1. Spustelėkite **Pirmyn**.

> [!div class="nextstepaction"]
> [Kitas veiksmas: suvienodinti laukus](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Taisyklių įtraukimas į atitikmenų porą

Gretinimo taisyklės reiškia sąlygų rinkinius. Norėdami suderinti objektus pagal sąlygas pagal kelis atributus, įtraukite daugiau taisyklių.

1. Pasirinkite **Įtraukti taisyklę** objekte, į kurį norite įtraukti taisykles.

1. Atlikite veiksmus, nurodytus [Atitikmenų porų taisyklių apibrėžimas](#define-rules-for-match-pairs).

> [!NOTE]
> Taisyklių tvarka yra svarbi. Susiejimo algoritmas bando sutapti su tam tikru kliento įrašu pagal jūsų pirmąją taisyklę ir tęsia antrąją taisyklę tik tuo atveju, jei su pirmąja taisykle nebuvo nustatyta jokių atitikmenų.

## <a name="advanced-options"></a>Išplėstinės parinktys

### <a name="add-exceptions-to-a-rule"></a>Išimčių įtraukimas į taisyklę

Daugeliu atvejų objekto atitikimas veda prie unikalių klientų profilių su konsoliduotais duomenimis. Norėdami dinamiškai reaguoti į retus klaidingų teigiamų ir klaidingų negatyvų atvejus, galite apibrėžti atitikties taisyklės išimtis. Išimtys taikomos apdorojus atitikties taisykles ir vengiant visų įrašų, kurie atitinka išimties kriterijus, atitikimo.

Pavyzdžiui, jei atitikties taisyklė apjungia pavardė, miestą ir gimimo datą, sistema identifikuos dvynius, turinčius tą patį pavardė, kurie gyvena tame pačiame mieste kaip ir tas pats profilis. Galite nurodyti išimtį, kuri neatitinka profilių, jei sujungiamų objektų vardas nėra tas pats.

1. **Srityje Redaguoti taisyklę** pasirinkite **Įtraukti** > **išimtį**.

1. Nurodykite išimties kriterijus.

1. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

### <a name="specify-custom-match-conditions"></a>Nurodykite pasirinktines gretinimo sąlygas

Galite nurodyti sąlygas, kurios perrašo numatytąją atitikties logiką. Galimos keturios parinktys:

|Parinktis  |Aprašą |Pavyzdžiui  |
|---------|---------|---------|
|Visada atitikti     | Apibrėžia reikšmes, kurios visada sutampa.         |  Visada prilygti *Mike'ui* ir *Mike'uiR*.       |
|Niekada neatitinka     | Apibrėžia reikšmes, kurios niekada nesutampa.        | Niekada neprilygti *Johnui* ir *Jonathanui*.        |
|Pasirinktinis apėjimas     | Apibrėžia reikšmes, kurių sistema visada turėtų nepaisyti rungtynių etape. |  Rungtynių metu nepaisykite reikšmių *11111* ir *Nežinomos*.        |
|Pseudonimo susiejimas    | Reikšmių, kurias sistema turėtų laikyti ta pačia verte, apibrėžimas.         | Laikykite Džo *lygiu* Džozefui *·*.        |

1. Pasirinkti **Tinkinimas**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Pasirinktinis mygtukas":::

1. Pasirinkite Pasirinktinis **tipas** ir pasirinkite **Atsisiųsti šabloną**. Kiekvienai rungtynių pasirinkčiai reikia atskiro šablono.

1. Atidarykite atsisiųstą šablono failą ir užpildykite išsamią informaciją. Šablone yra laukų, nurodančių objektą ir objekto pirminių raktų reikšmes, kurias reikia naudoti pasirinktinio atitikimo srityje. Pavyzdžiui, jeigu norite, kad pirminis raktas *„12345”* iš objekto *Pardavimas* visada atitiktų pirminį raktą *„34567”* iš objekto *Kontaktas*, užpildykite šabloną:
    - Objektas1: pardavimai
    - Objekto1kodas: 12345
    - Objektas2: kontaktas
    - Objekto2kodas: 34567

   Tas pats šablono failas gali nurodyti pasirinktinius atitikties įrašus iš kelių objektų.

   Jei norite nurodyti objekto dublikatų naikinimo pasirinktinį gretinimą, pateikite tą patį objektą kaip ir Objektą1, ir Objektą2 ir nustatykite skirtingas pirminio rakto reikšmes.

1. Pridėję visus nepaisymus, išsaugokite šablono failą.

1. Eikite **Duomenys** > **Duomenų šaltiniai** ir permeskite šablonų failus kaip naujus objektus.

1. Įkėlę failus, dar kartą pasirinkite **parinktį Pasirinktinis**. Išskleidžiamajame meniu pasirinkite reikiamus objektus ir pasirinkite **Atlikta**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialogo lango, kai reikia pasirinkti pasirinktinio atitikties scenarijaus perrašymus, ekrano kopija.":::

1. Pasirinktinio atitikties taikymas priklauso nuo atitikties parinkties, kurią norite naudoti.

   - Jei naudojate **"Always match"** arba **"Never match"**, pereikite prie kito veiksmo.
   - Jei naudojate **Apėjimas** arba **Pseudonimo susiejimas**, pasirinkite **Redaguoti** pagal esamą atitikties taisyklę arba sukurkite naują taisyklę. Išskleidžiamajame meniu Normalizacijos pasirinkite **parinktį Pasirinktinis apėjimas** arba **Pseudonimas susiejimas** ir pasirinkite **Atlikta**.

1. Pasirinkite **Atlikta** pasirinktinių **parametrų** srityje, kad pritaikytumėte pasirinktinę atitikties konfigūraciją.

> [!div class="nextstepaction"]
> [Kitas veiksmas: suvienodinti laukus](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
