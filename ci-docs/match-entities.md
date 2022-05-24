---
title: Suderinkite objektus duomenų suvienodinimui
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
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740959"
---
# <a name="match-conditions"></a>Rungtynių sąlygos

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šis suvienijimo veiksmas apibrėžia atitikties tvarką ir kelių subjektų gretinimo taisykles. Šiam žingsniui atlikti reikia bent dviejų subjektų.

> [!NOTE]
> Sukūrę atitikmens sąlygas ir pasirinkę **Pirmyn**, negalite pašalinti pasirinkto objekto ar atributo. Jei reikia, prieš tęsdami pasirinkite **Atgal**, kad peržiūrėtumėte pasirinktus objektus ir atributus.

## <a name="include-enriched-entities-preview"></a>Įtraukti praturtintus objektus (peržiūra)

Jei praturtinote objektus duomenų šaltinis lygiu, kad padėtumėte pagerinti suvienijimo rezultatus, pasirinkite juos. Daugiau informacijos ieškokite [Enrichment for data sources](data-sources-enrichment.md). Jei puslapyje Įrašų **dublikatai pasirinkote** praturtintus objektus, jų dar kartą pasirinkti nereikia.

1. **Puslapyje Gretinimo sąlygos** puslapio viršuje pasirinkite **Naudoti praturtintus** objektus.

1. **Srityje Naudoti praturtintus** objektus pasirinkite vieną ar daugiau praturtintų objektų.

1. Pasirinkite **Atlikta**.

## <a name="specify-the-match-order"></a>Nurodykite atitikties eiliškumą

Kiekvienas atitikmuo suvienodina du ar daugiau objektų į vieną konsoliduotą objektą. Tuo pačiu metu jis saugo unikaliuosius klientų įrašus. Atitikties tvarka nurodo tvarką, kuria sistema bando suderinti įrašus.

> [!IMPORTANT]
> Pirmasis sąrašo objektas vadinamas pirminiu objektu. Pirminis objektas yra jūsų vieningo profilių duomenų rinkinio pagrindas. Į šį objektą bus įtraukti papildomi pasirinkti objektai.
>
> Svarbūs aspektai:
>
> - Pasirinkite objektą, turintį išsamiausius ir patikimiausius profilio duomenis apie savo klientus kaip pagrindinį objektą.
> - Kaip pagrindinį objektą pasirinkite objektą, turintį kelis atributus kartu su kitais objektais (pvz., pavadinimą, telefono numerį arba el. pašto adresą).

1. **Puslapyje Gretinimo sąlygos** naudokite rodykles aukštyn ir žemyn, kad perkeltumėte objektus norima tvarka, arba vilkite ir numeskite juos. Pavyzdžiui, kaip pagrindinį objektą pasirinkite **Kontaktai:el. prekyba**, o **kaip antrąjį objektą – CustomerLoyalty:Loyalty:Loyalty**.

1. Jei norite, kad kiekvienas objekto įrašas būtų unikalus klientas, neatsižvelgiant į tai, ar rastas atitikmuo, pasirinkite **Įtraukti visus įrašus**. Visi šio objekto įrašai, neatitinkantys įrašų kituose objektuose, įtraukiami į vieningą profilį. Įrašai, kuriuose nėra rungtynių, vadinami singletonais.
  
Pirminis objektas *Kontaktai:el. prekyba* atitinka kitą objektą *CustomerLoyalty:Loyalty*. Duomenų rinkinys, gautas atlikus pirmąjį atitikties veiksmą, yra suderintas su šiuo objektu, jei turite daugiau nei du objektus.

:::image type="content" source="media/m3_match.png" alt-text="Pasirinkto objektų atitikties užsakymo ekrano nuotrauka." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Taisyklių apibrėžimas atitikmenų poroms

Atitikties taisyklėse nurodoma logika, pagal kurią bus derinama konkreti objektų pora. Taisyklė susideda iš vienos ar daugiau sąlygų.

Įspėjimas šalia objekto pavadinimo reiškia, kad rungtynių porai nenustatyta atitikties taisyklė.

1. Pasirinkite **Įtraukti taisyklę** objektų porai, kad apibrėžtumėte atitikties taisykles.

1. **Srityje Įtraukti taisyklę** sukonfigūruokite taisyklės sąlygas.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Srities Įtraukti taisyklę ekrano nuotrauka.":::

   - **Pasirinkite Objektą/ lauką (pirmoji eilutė)**: pasirinkite susijusį objektą ir atributą, kad nurodytumėte įrašo ypatybę, kuri gali būti unikali klientui. Pavyzdžiui, telefono numeris ar el. pašto adresas. Venkite gretinti pagal veiklos tipo atributus. Pavyzdžiui, tikėtina, kad pirkimo ID neras atitikmens kituose įrašų tipuose.

   - **Pasirinkite Objektą/lauką (antroji eilutė)**: pasirinkite atributą, susijusį su pirmoje eilutėje nurodyto objekto atributu.

   - **Normalizuoti** : Pasirinkite iš šių pasirinktų atributų normalizavimo parinkčių.
     - **Skaitmenys**: konvertuoja kitas skaitmenų sistemas, pvz., romėniškus skaitmenis, į arabiškus skaitmenis. *VIII* tampa *8*.
     - **Simboliai**: pašalina visus simbolius ir specialius simbolius. *„Head&Shoulder”* tampa *„HeadShoulder”*.
     - **Tekstas į mažąsias raides**: konvertuoja visus simbolius į mažąsias raides. *VISOS DIDŽIOSIOS ir Pirmos Didžiosios* tampa *visos didžiosios ir pirmos didžiosios*.
     - **Tipas (telefonas, vardas, adresas, organizacija)**: standartizuoja vardus, pavadinimus, telefono numerius, adresus ir organizacijas.
     - **Unicode į ASCII**: konvertuoja unicode žymėjimą į ASCII simbolius. *„/u00B2”* tampa *2*.
     - **Tarpas**: pašalina visus tarpus. *Labas Pasauli* tampa *LabasPasauli*.

   - **Tikslumas**: Nustatykite šiai sąlygai taikytiną tikslumo lygį.
     - **Pagrindinis**: pasirinkite iš *mažo (30%)*, *vidutinio (60%)*, *didelio (80%)* ir *tikslaus (100%)*. Pasirinkite **Tiksliai**, kad atitiktumėte tik tuos įrašus, kurie atitinka 100 procentų.
     - **Pasirinktinis**: Nustatykite procentą, kurį turi atitikti įrašai. Sistema sugretins tik įrašus, perlipusius ribinę reikšmę.

   - **Pavadinimas**: Taisyklės pavadinimas.

1. Norėdami suderinti objektus tik tuo atveju, jei atributai atitinka kelias sąlygas, pasirinkite **Įtraukti sąlygą** > **Įtraukti**, kad į atitikties taisyklę įtrauktumėte daugiau sąlygų. Sąlygos yra susijusios su loginiu IR operatoriumi ir todėl vykdomos tik tuo atveju, jeigu įvykdomos visos sąlygos.

1. Pasirinktinai apsvarstykite išplėstines parinktis, pvz., [išimtis](#add-exceptions-to-a-rule) arba [pasirinktines atitikties sąlygas](#specify-custom-match-conditions).

1. Pasirinkite **Atlikta**, kad užbaigtumėte taisyklę.

1. Pasirinktinai [įtraukite daugiau taisyklių](#add-rules-to-a-match-pair).

1. Spustelėkite **Pirmyn**.

> [!div class="nextstepaction"]
> [Kitas žingsnis: laukų suvienodinimas](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Taisyklių įtraukimas į atitikmenų porą

Gretinimo taisyklės reiškia sąlygų rinkinius. Norėdami suderinti objektus pagal sąlygas, pagrįstas keliais atributais, įtraukite daugiau taisyklių.

1. Pasirinkite **Įtraukti taisyklę** objekte, į kurį norite įtraukti taisykles.

1. Atlikite veiksmus, nurodytus [Atitikmenų porų taisyklių apibrėžimas](#define-rules-for-match-pairs).

> [!NOTE]
> Taisyklių tvarka yra svarbi. Atitikimo algoritmas bando suderinti tam tikrą kliento įrašą pagal jūsų pirmąją taisyklę ir tęsia antrąją taisyklę tik tuo atveju, jei atitikmenys nebuvo identifikuoti su pirmąja taisykle.

## <a name="advanced-options"></a>Išplėstinės parinktys

### <a name="add-exceptions-to-a-rule"></a>Išimčių įtraukimas į taisyklę

Daugeliu atvejų objekto gretinimas lemia unikalius klientų profilius su konsoliduotais duomenimis. Norėdami dinamiškai spręsti retus klaidingų teigiamų ir klaidingų negatyvų atvejus, galite nustatyti atitikties taisyklės išimtis. Išimtys taikomos apdorojus rungtynių taisykles ir išvengiant visų įrašų, kurie atitinka išimties kriterijus, suderinimo.

Pavyzdžiui, jei jūsų rungtynių taisyklė sujungia pavardė, miestą ir gimimo datą, sistema identifikuos dvynius, turinčius tą patį pavardė, kurie gyvena tame pačiame mieste kaip ir tas pats profilis. Galite nurodyti išimtį, kuri neatitinka profilių, jei vardas jūsų jungiamuose objektuose nėra vienodi.

1. **Srityje Redaguoti taisyklę** pasirinkite **Įtraukti išimtį** > **·**.

1. Nurodykite išimties kriterijus.

1. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

### <a name="specify-custom-match-conditions"></a>Nurodykite pasirinktines gretinimo sąlygas

Galite nurodyti sąlygas, kurios nepaiso numatytosios atitikties logikos. Galimi keturi variantai:

|Parinktis  |Aprašą |Pavyzdžiui  |
|---------|---------|---------|
|Visada atitikti     | Apibrėžia reikšmes, kurios visada sutampa.         |  Visada rungtyniaukite su *Mike'u* ir *MikeR*.       |
|Niekada neatitinka     | Apibrėžia reikšmes, kurios niekada nesutampa.        | Niekada neprilygti *Džonui* ir *Džonatanui*.        |
|Pasirinktinis apėjimas     | Apibrėžia reikšmes, kurių sistema visada turėtų nepaisyti rungtynių etape. |  Nepaisyti reikšmių *11111* ir *Nežinomų* rungtynių metu.        |
|Pseudonimo susiejimas    | Apibrėžiant reikšmes, kurias sistema turėtų laikyti ta pačia verte.         | Manau, *kad Džo* yra lygus *Juozapui*.        |

1. Pasirinkti **Tinkinimas**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Pasirinktinis mygtukas":::

1. Pasirinkite **pasirinktinį tipą** ir pasirinkite **Atsisiųsti šabloną**. Kiekvienai atitikmens galimybei reikia atskiro šablono.

1. Atidarykite atsisiųstą šablono failą ir užpildykite išsamią informaciją. Šablone yra laukų, nurodančių objektą ir objekto pirminių raktų reikšmes, kurias reikia naudoti pasirinktinio atitikimo srityje. Pavyzdžiui, jeigu norite, kad pirminis raktas *„12345”* iš objekto *Pardavimas* visada atitiktų pirminį raktą *„34567”* iš objekto *Kontaktas*, užpildykite šabloną:
    - Objektas1: pardavimai
    - Objekto1kodas: 12345
    - Objektas2: kontaktas
    - Objekto2kodas: 34567

   Tas pats šablono failas gali nurodyti pasirinktinius atitikties įrašus iš kelių objektų.

   Jei norite nurodyti objekto dublikatų naikinimo pasirinktinį gretinimą, pateikite tą patį objektą kaip ir Objektą1, ir Objektą2 ir nustatykite skirtingas pirminio rakto reikšmes.

1. Įtraukę visus nepaisymus, įrašykite šablono failą.

1. Eikite **Duomenys** > **Duomenų šaltiniai** ir permeskite šablonų failus kaip naujus objektus.

1. Nusiuntę failus, dar kartą pasirinkite **parinktį Pasirinktinė**. Išplečiamajame meniu pasirinkite reikiamus objektus ir pasirinkite **Atlikta**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialogo lango, kai reikia pasirinkti pasirinktinio atitikties scenarijaus perrašymus, ekrano kopija.":::

1. Pasirinktinio atitikmens taikymas priklauso nuo norimos naudoti atitikties parinkties.

   - Jei norite **visada rungtyniauti** arba **niekada nerungtyniauti**, pereikite prie kito veiksmo.
   - Jei norite **susieti aplinkkelį** arba **Pseudonimą**, pasirinkite **Redaguoti** esamą atitikties taisyklę arba sukurkite naują taisyklę. Išplečiamajame sąraše Normalizavimas pasirinkite parinktį Pasirinktinis **aplinkkelis** arba **Pseudonimas ir** pasirinkite **Atlikta**.

1. Norėdami taikyti pasirinktinę atitikties konfigūraciją, **pasirinktinėje** srityje pasirinkite **Atlikta**.

> [!div class="nextstepaction"]
> [Kitas žingsnis: laukų suvienodinimas](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
