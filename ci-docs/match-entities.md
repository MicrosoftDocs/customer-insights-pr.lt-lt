---
title: Duomenų suvienodinimo atitikties sąlygos
description: Suderinkite objektus tam, kad sukurtumėte suvienytus kliento profilius.
recommendations: false
ms.date: 10/07/2022
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
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721531"
---
# <a name="match-conditions-for-data-unification"></a>Duomenų suvienodinimo atitikties sąlygos

Šis suvienijimo veiksmas apibrėžia atitikties tvarką ir skirtingų subjektų susiejimo taisykles. Šiam veiksmui reikia bent dviejų objektų.

> [!NOTE]
> Sukūrę atitikties sąlygas ir pasirinkę Pirmyn **, negalėsite pašalinti pasirinkto** objekto ar atributo. Jei reikia, pasirinkite **Atgal**, kad prieš tęsdami peržiūrėtumėte pasirinktus objektus ir atributus.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Papildytų objektų įtraukimas (peržiūra)

Jei praturtinote objektus duomenų šaltinis lygiu, kad pagerintumėte suvienijimo rezultatus, pasirinkite juos. Daugiau informacijos ieškokite [Duomenų šaltinių papildymas](data-sources-enrichment.md). Jei puslapyje Dubliuoti įrašus **pasirinkote papildytus objektus**, jums nereikės jų žymėti dar kartą.

1. Puslapio **Atitikimo sąlygos** puslapio viršuje pasirinkite **Naudoti papildytus objektus**.

1. Srityje **Naudoti papildytus objektus** pasirinkite vieną ar daugiau papildytų objektų.

1. Pasirinkite **Atlikta**.

## <a name="specify-the-match-order"></a>Nurodykite atitikties eiliškumą

Kiekvienas atitikmuo suvienodina du ar daugiau objektų į vieną konsoliduotą objektą. Tuo pačiu metu jis saugo unikaliuosius klientų įrašus. Atitikmenų tvarka nurodo tvarką, kuria sistema bando suderinti įrašus.

> [!IMPORTANT]
> Pirmasis objektas vadinamas pirminiu objektu, kuris yra jūsų vieningų profilių pagrindas. Į šį objektą bus įtraukti papildomi pasirinkti objektai.
>
> Svarbios aplinkybės:
>
> - Pasirinkite objektą, turintį išsamiausius ir patikimiausius profilio duomenis apie jūsų klientus, kaip pagrindinį objektą.
> - Pasirinkite objektą, turintį kelis bendrus atributus su kitais objektais (pvz., pavadinimą, telefono numerį arba el. pašto adresą), kaip pagrindinį objektą.

1. Puslapyje **Sugretinimo sąlygos** naudokite rodykles Perkelti aukštyn ir žemyn, kad perkeltumėte objektus norima tvarka arba nuvilkite juos. Pavyzdžiui, pasirinkite **eCommerceCustomers kaip pagrindinį objektą ir** loyCustomers **kaip** antrą objektą.

1. Jei norite, kad kiekvienas objekto įrašas būtų unikalus klientas, neatsižvelgiant į tai, ar rastas atitikmuo, pasirinkite **Įtraukti visus įrašus**. Visi šio objekto įrašai, nesutampantys su bet kurio kito objekto įrašais, įtraukiami į vieningą profilį. Įrašai, kurie neturi atitikmens, vadinami singletonais.
  
Pagrindinis objektas *Kontaktai:el. prekyba* suderinamas su kitu objektu *CustomerLoyalty:Loyalty*. Duomenų rinkinys, gautas atlikus pirmąjį atitikties veiksmą, sugretinamas su toliau nurodytu objektu, jei turite daugiau nei du objektus.

:::image type="content" source="media/m3_match.png" alt-text="Pasirinktos objektų atitikties tvarkos ekrano nuotrauka." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Taisyklių apibrėžimas atitikmenų poroms

Atitikties taisyklėse nurodoma logika, pagal kurią bus derinama konkreti objektų pora. Taisyklę sudaro viena ar daugiau sąlygų.

Įspėjimas šalia objekto pavadinimo reiškia, kad atitikties porai nėra apibrėžta jokia atitikimo taisyklė.

1. Pasirinkite **Įtraukti objektų poros taisyklę**, kad apibrėžtumėte atitikties taisykles.

1. **Srityje Įtraukti taisyklę** sukonfigūruokite taisyklės sąlygas.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Taisyklių srities Įtraukti ekrano nuotrauka.":::

   - **Pasirinkite Objektas / laukas (pirma eilutė)**: pasirinkite objektą ir atributą, kuris gali būti unikalus klientui. Pavyzdžiui, telefono numeris ar el. pašto adresas. Venkite gretinti pagal veiklos tipo atributus. Pavyzdžiui, tikėtina, kad pirkimo ID neras atitikmens kituose įrašų tipuose.

   - **Pasirinkite Entity/Field (antra eilutė)**: pasirinkite atributą, susijusį su pirmoje eilutėje nurodyto objekto atributu.

   - **Normalizuoti** : Pasirinkite iš šių pasirinktų atributų normalizavimo parinkčių.
     - **Skaitmenys**: konvertuoja kitas skaitmenų sistemas, pvz., romėniškus skaitmenis, į arabiškus skaitmenis. *VIII* tampa *8*.
     - **Simboliai**: pašalinami visi simboliai ir specialieji simboliai. *„Head&Shoulder”* tampa *„HeadShoulder”*.
     - **Tekstas rašomas mažosiomis raidėmis**: konvertuoja visus simbolius į mažąsias raides. *VISOS DIDŽIOSIOS ir Pirmos Didžiosios* tampa *visos didžiosios ir pirmos didžiosios*.
     - **Tipas (telefonas, vardas, adresas, organizacija)**: standartizuoja vardus, pareigas, telefono numerius, adresus ir organizacijas.
     - **Unicode į ASCII: konvertuoja unikodo žymėjimą į ASCII** simbolius. *„/u00B2”* tampa *2*.
     - **Tarpai**: pašalina visus tarpus. *Labas Pasauli* tampa *LabasPasauli*.

   - **Tikslumas**: Nustatykite šiai sąlygai taikytiną tikslumo lygį.
     - **Pagrindinis**: rinkitės iš *žemo (30%), vidutinio (60%),* *aukšto (80%) ir* tikslaus (100%)*·* *.* Pasirinkite **Tikslus**, jei norite atitikti tik 100 procentų atitinkančius įrašus.
     - **Pasirinktinis**: Nustatykite procentą, kurį turi atitikti įrašai. Sistema sugretins tik įrašus, perlipusius ribinę reikšmę.

   - **Pavadinimas**: taisyklės pavadinimas.

1. Norėdami sugretinti objektus tik tuo atveju, jei atributai atitinka kelias sąlygas, pasirinkite **Įtraukti** > **sąlygą**, kad į atitikties taisyklę įtrauktumėte daugiau sąlygų. Sąlygos yra susijusios su loginiu IR operatoriumi ir todėl vykdomos tik tuo atveju, jeigu įvykdomos visos sąlygos.

1. Pasirinktinai apsvarstykite išplėstines parinktis, pvz., [išimtis](#add-exceptions-to-a-rule) arba [pasirinktines atitikties sąlygas](#specify-custom-match-conditions).

1. Pasirinkite **Atlikta**, kad užbaigtumėte taisyklę.

1. Pasirinktinai [įtraukite daugiau taisyklių](#add-rules-to-a-match-pair).

1. Spustelėti **Pirmyn**.

> [!div class="nextstepaction"]
> [Kitas veiksmas: laukų suvienodinimas](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Taisyklių įtraukimas į atitikmenų porą

Gretinimo taisyklės reiškia sąlygų rinkinius. Norėdami sugretinti objektus pagal sąlygas, pagrįstas keliais atributais, įtraukite daugiau taisyklių.

1. Pasirinkite **Įtraukti taisyklę** objekte, į kurį norite įtraukti taisykles.

1. Atlikite veiksmus, nurodytus [Atitikmenų porų taisyklių apibrėžimas](#define-rules-for-match-pairs).

> [!NOTE]
> Taisyklių tvarka yra svarbi. Atitikimo algoritmas bando sugretinti tam tikrą kliento įrašą pagal jūsų pirmąją taisyklę ir pereina prie antrosios taisyklės tik tuo atveju, jei nebuvo nustatyta atitikčių pirmajai taisyklei.

## <a name="advanced-options"></a>Išplėstinės parinktys

### <a name="add-exceptions-to-a-rule"></a>Taisyklės išimčių įtraukimas

Daugeliu atvejų objekto atitikimas lemia unikalius klientų profilius su konsoliduotais duomenimis. Jei norite reaguoti į retus klaidingų teigiamų ir neigiamų rezultatų atvejus, apibrėžkite atitikties taisyklės išimtis. Išimtys taikomos apdorojus atitikties taisykles ir vengiant visų įrašų, kurie atitinka išimčių kriterijus, atitikimo.

Pavyzdžiui, jei jūsų atitikties taisyklė sujungia pavardė, miestą ir gimimo datą, sistema identifikuos dvynius su tuo pačiu pavardė, kurie gyvena tame pačiame mieste kaip ir tas pats profilis. Galite nurodyti išimtį, kuri neatitinka profilių, jei sujungtų objektų vardas nėra tas pats.

1. **Srityje Redaguoti taisykles** pasirinkite **Įtraukti** > **išimtį**.

1. Nurodykite išimties kriterijus.

1. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

### <a name="specify-custom-match-conditions"></a>Nurodykite pasirinktines gretinimo sąlygas

Nurodykite sąlygas, kurios perrašo numatytąją atitikties logiką. Galimos keturios parinktys:

|Parinktis  |Aprašą |Pavyzdžiui  |
|---------|---------|---------|
|Visada atitikti     | Apibrėžia pirminių raktų reikšmes, kurios visada sutampa.         |  Visada sujunkite eilutę su pirminiu raktu 12345 *su eilute su pirminiu raktu* *54321*.       |
|Niekada neatitinka     | Apibrėžia pirminių raktų reikšmes, kurios niekada nesutampa.        | Niekada nederinkite eilutės su pirminiu raktu 12345 *su eilute su pirminiu raktu* *54321*.        |
|Apėjimas            | Apibrėžia reikšmes, kurias sistema visada turėtų ignoruoti rungtynių fazėje. |  Rungtynių metu nepaisykite reikšmių *11111* ir *Nežinoma.*        |
|Pseudonimo susiejimas    | Apibrėžkite vertes, kurias sistema turėtų laikyti ta pačia verte.         | Laikykite *Džo lygiaverčiu Juozapui* *·*.        |

1. Pasirinkti **Tinkinimas**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Pasirinktinis mygtukas":::

1. Pasirinkite **pasirinktinį tipą** ir pasirinkite **Atsisiųsti šabloną**. Pervardykite šabloną nenaudodami tarpų. Kiekvienai atitikties parinkčiai naudokite atskirą šabloną.

1. Atidarykite atsisiųstą šablono failą ir užpildykite išsamią informaciją. Šablone yra laukų, nurodančių objektą ir objekto pirminių raktų reikšmes, kurias reikia naudoti pasirinktinio atitikimo srityje. Objektų pavadinimuose skiriamos didžiosios ir mažosios raidės. Pavyzdžiui, jeigu norite, kad pirminis raktas *„12345”* iš objekto *Pardavimas* visada atitiktų pirminį raktą *„34567”* iš objekto *Kontaktas*, užpildykite šabloną:
   - Objektas1: pardavimai
   - Objekto1kodas: 12345
   - Objektas2: kontaktas
   - Objekto2kodas: 34567

   Tas pats šablono failas gali nurodyti pasirinktinius atitikties įrašus iš kelių objektų.

   > [!NOTE]
   > Jei norite nurodyti objekto dublikatų naikinimo pasirinktinį gretinimą, pateikite tą patį objektą kaip ir Objektą1, ir Objektą2 ir nustatykite skirtingas pirminio rakto reikšmes. Norėdami naudoti pasirinktinį atitikimą, objektui turite nustatyti bent vieną dublikatų šalinimo taisyklę.

1. Pridėję visus nepaisymus, išsaugokite šablono failą.

1. Eikite **Duomenys** > **Duomenų šaltiniai** ir permeskite šablonų failus kaip naujus objektus.

1. Įkėlę failus, dar kartą pasirinkite **parinktį Pasirinktinis**. Išskleidžiamajame meniu pasirinkite reikiamus objektus ir pasirinkite **Atlikta**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialogo lango, kai reikia pasirinkti pasirinktinio atitikties scenarijaus perrašymus, ekrano kopija.":::

1. Pasirinktinės atitikties taikymas priklauso nuo norimos naudoti atitikties parinkties.

   - Norėdami visada **suderinti** arba **Niekada nesutapti**, pereikite prie kito veiksmo.
   - Jei norite **apeiti** arba susieti **pseudonimą, pasirinkite Redaguoti** esamą atitikties taisyklę arba **sukurti** naują taisyklę. Išskleidžiamajame meniu Normalizavimas pasirinkite parinktį Pasirinktinis apėjimas **arba Alias susiejimas** ir pasirinkite **Atlikta** **·**.

1. Pasirinkite **Atlikta** pasirinktinėje srityje, **kad pritaikytumėte pasirinktinės** atitikties konfigūraciją.

   Kiekvienas įdėtas šablono failas yra savas duomenų šaltinis. Jei aptinkami įrašai, kuriems reikia specialaus suderinimo apdorojimo, atnaujinkite atitinkamą duomenų šaltinis. Naujinimas bus naudojamas kito suvienijimo proceso metu. Pavyzdžiui, jūs identifikuojate dvynius su beveik tuo pačiu vardu, gyvenančius tuo pačiu adresu, kuris buvo sujungtas kaip vienas asmuo. Atnaujinkite duomenų šaltinis, kad dvyniai būtų identifikuojami kaip atskiri, unikalūs įrašai.

> [!div class="nextstepaction"]
> [Kitas veiksmas: laukų suvienodinimas](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
