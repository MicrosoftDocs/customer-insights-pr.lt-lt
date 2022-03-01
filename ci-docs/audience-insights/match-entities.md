---
title: Suderinkite objektus duomenų suvienodinimui
description: Sugretinkite objektus, kad derinti duomenų rinkinius ir sukurtumėte vieningus klientų profilius.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 67e17495fa6da1cfac7ee4ee165e798364f6cb27
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648218"
---
# <a name="match-entities"></a>Susiekite objektus

Atitikimo etapas nurodo, kaip sujungti jūsų duomenų rinkinius į vieningą kliento profilio duomenų rinkinį. Atlikę [susiejimo veiksmą](map-entities.md) duomenų suvienodinimo procese, esate pasirengę suderinti savo objektus. Atitikties etapui reikia bent dviejų susietų objektų.

Suderinimo puslapį sudaro trys dalys: 
- Pagrindinės metrikos, apibendrinančios suderintų įrašų skaičių
- Gretinimo tarp objektų tvarka ir taisyklės
- Sugretintų objektų dublikatų naikinimo taisyklės

## <a name="specify-the-match-order"></a>Nurodykite atitikties eiliškumą

Eikite į **Duomenys** > **Duomenų suvienodinimas** > **Derinimas** ir pasirinkite **Nustatyti tvarką**, kad būtų pradedamas atitikties etapas.

Kiekvienas atitikmuo suvienodina du ar daugiau objektų į vieną konsoliduotą objektą. Tuo pačiu metu jis saugo unikaliuosius klientų įrašus. Pavyzdžiui, mes pasirinkome du objektus: **„eCommerce:eCommerceContacts”** kaip pirminį, o **„LoyaltyScheme:loyCustomers”** kaip antrąjį objektą. Objektų tvarka nurodo, kokia tvarka sistema bandys sugretinti įrašus.

:::image type="content" source="media/match-page.png" alt-text="Atitikmenų puslapio, esančio duomenų suvienijimo proceso srityje Suvienodinti, ekrano kopija.":::
  
Pirminio objekto *„eCommerce:eCommerceContacts”* sugretinami su kitu objektu *„LoyaltyScheme:loyCustomers”*. Duomenų rinkinys, gautas atlikus pirmąjį gretinimo veiksmą, sugretinamas su šiuo objektu, jeigu turite daugiau nei du objektus.

> [!IMPORTANT]
> Objektas, kurį pasirinkote savo pirminiu objektu, bus naudojamas kaip suvienyto profilių duomenų rinkinio pagrindas. Papildomi objektai, kurie yra pasirenkami per atitikties etapą, bus pridėti prie šio objekto. Tai nereiškia, kad suvienytame objekte bus *visi* duomenys, įtraukti į šį objektą.
>
> Yra dvi aplinkybės, kurios gali padėti pasirinkti jūsų objektų hierarchiją:
>
> - Kaip pagrindinį objektą pasirinkite tokį, kuris turi pačius išsamiausius ir patikimiausius duomenis apie jūsų klientus.
> - Kaip pagrindinį objektą pasirinkite objektą, kuriame yra keli atributai, bendri su kitais objektais (pavyzdžiui, pavadinimas, telefono numeris arba el. pašto adresas).

Nurodę gretinimo tvarką, matysite apibrėžtas atitikmenų poras skyriuje **Sugretintų įrašų informacija**, esančiame **Duomenys** > **Suvienodinti** > **Atitikmuo**. Pagrindinės metrikos bus tuščios tol, kol bus baigtas gretinimo procesas.

## <a name="define-rules-for-match-pairs"></a>Taisyklių apibrėžimas atitikmenų poroms

Atitikties taisyklėse nurodoma logika, pagal kurią bus derinama konkreti objektų pora.

Šalia objekto pavadinimo esantis įspėjimas **Reikia taisyklių** rodo, kad atitikmenų porai neapibrėžta jokia gretinimo taisyklė. 

:::image type="content" source="media/match-rule-add.png" alt-text="Skyriaus Sugretinto įrašo informacija su pažymėtu taisyklių įtraukimo valdikliu, ekrano kopija.":::

1. Pasirinkite **Įtraukti taisykles** po skyriaus **Sugretinto įrašo informacija** objektu apibrėžti sugretinimo taisyklėms.

1. Srityje **Kurti taisyklę** sukonfigūruokite sąlygas taisyklei.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Atidarytos gretinimo taisyklės su įtrauktomis sąlygomis ekrano kopija.":::

   - **Objektas/Laukas (pirmoji eilutė)**: Pasirinkite susijusį objektą ir atributą, kad nurodytumėte įrašo ypatybę, kuri, tikėtina, yra unikali klientui. Pavyzdžiui, telefono numeris ar el. pašto adresas. Venkite gretinti pagal veiklos tipo atributus. Pavyzdžiui, tikėtina, kad pirkimo ID neras atitikmens kituose įrašų tipuose.

   - **Objektas/Laukas (antroji eilutė)**: Pasirinkite atributą, susijusį su pirmoje eilutėje nurodyto objekto atributu.

   - **Normalizuoti** : Pasirinkite iš šių pasirinktų atributų normalizavimo parinkčių. 
     - Tarpas: Pašalina visus tarpus. *Labas Pasauli* tampa *LabasPasauli*.
     - Simboliai: Pašalina visus simbolius ir specialiuosius simbolius. *„Head&Shoulder”* tampa *„HeadShoulder”*.
     - Tekstas į mažąsias raides: Konvertuoja visus simbolius į mažąsias raides. *VISOS DIDŽIOSIOS ir Pirmos Didžiosios* tampa *visos didžiosios ir pirmos didžiosios*.
     - „Unicode” į ASCII: Konvertuoja „Unicode” notaciją į ASCII simbolius. *„/u00B2”* tampa *2*.
     - Skaitmenys: Konvertuoja kitas skaičių sistemas, pavyzdžiui, romėniškus skaitmenis į arabiškus skaitmenis. *VIII* tampa *8*.
     - Semantiniai tipai: Standartizuoja vardus, pavadinimus, telefono numerius, adresus ir kita. 

   - **Tikslumas**: Nustatykite šiai sąlygai taikytiną tikslumo lygį. 
     - **Pagrindinis**: Pasirinkite iš *Žemas*, *Vidutinis*, *Aukštas* ir *Tikslus*. Pasirinkite **tikslus**, kai norite suderinti įrašus, kurie atitinka 100 procentų. Pasirinkite bet kurį kitą lygį, kai norite suderinti įrašus, kurie nėra vienodi 100 procentų.
     - **Pasirinktinis**: Nustatykite procentą, kurį turi atitikti įrašai. Sistema sugretins tik įrašus, perlipusius ribinę reikšmę.

1. Pateikite **Pavadinimą** taisyklei.

1. [Įtraukite daugiau sąlygų](#add-conditions-to-a-rule) arba pasirinkite **Atlikta**, kad užbaigtumėte taisyklę.

1. Pasirinktinai [įtraukite daugiau taisyklių](#add-rules-to-a-match-pair).

1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

### <a name="add-conditions-to-a-rule"></a>Įtraukite sąlygas į taisyklę

Norėdami sugretinti objektus tik tuo atveju, jei atributai atitinka kelias sąlygas, į atitikties taisyklę įtraukite daugiau sąlygų. Sąlygos yra susijusios su loginiu IR operatoriumi ir todėl vykdomos tik tuo atveju, jeigu įvykdomos visos sąlygos.

1. Eikite į **Duomenys** > **Suvienodinti** > **Atitikmuo** ir pasirinkite **Redaguoti** taisyklėje, į kurią norite įtraukti sąlygas.

1. Srityje **redaguoti taisyklę** pasirinkite **įtraukti sąlygą**.

1. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

### <a name="add-rules-to-a-match-pair"></a>Taisyklių įtraukimas į atitikmenų porą

Gretinimo taisyklės reiškia sąlygų rinkinius. Norėdami sugretinti objektus pagal keletą objekto atributų, įtraukite daugiau taisyklių

1.  Eikite į **Duomenys** > **Suvienodinti** > **Atitikmuo** ir pasirinkite **Įtraukti taisyklę** objekte, į kurį norite įtraukti taisykles.

2. Atlikite veiksmus, nurodytus [Atitikmenų porų taisyklių apibrėžimas](#define-rules-for-match-pairs).

> [!NOTE]
> Taisyklių tvarka yra svarbi. Gretinimo algoritmas bando sugretinti pagal jūsų pirmąją taisyklę ir eina prie antrosios taisyklės tik tuo atveju, jei jokie atitikmenys nebuvo identifikuoti su pirmąja taisykle.

### <a name="change-the-entity-order-in-match-rules"></a>Objekto tvarkos keitimas atitikties taisyklėse

Galite pertvarkyti objektus, kad atitikties taisyklės pakeistų jų apdorojimo tvarką. Taisyklės, kurios prieštaraus viena kitai dėl pakeisto tvarkos, bus pašalintos. Turite iš naujo sukurti pašalintas taisykles naudodami atnaujintą konfigūraciją.

1. Eikite į **Duomenis** > **Suvienodinti** > **Atitiktis** ir pasirinkite **Redaguoti**.

1. Srityje **Redaguoti taisyklę** pasirinkite valdiklį **Judėti aukštyn/žemyn** arba nuvilkite objektus, kad pakeistumėte tvarką.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Parinktys, skirtos pakeisti objektų apdorojimo tvarką atitikties etapu.":::

1. Norėdami išsaugoti taisyklę, pasirinkite **atlikta**.

## <a name="define-deduplication-on-a-match-entity"></a>Nustatykite papildomą dublikavimą suderintame objekte

Be [kelių objektų gretinimo taisyklių](#define-rules-for-match-pairs), taip pat galite nurodyti dublikatų naikinimo taisykles. *Dublikatų naikinimas* yra dar vienas įrašų sugretinimo procesu metu vykstantis procesas. Jis aptinka pasikartojančius įrašus ir sulieja juos į vieną įrašą. Šaltinio įrašai yra susiejami su sulietu įrašu su alternatyviais ID.

Panaikinti pasikartojantys įrašai bus naudojami gretinimo procese tarp objektų. Dublikatų naikinimas vyksta atskiruose objektuose ir gali būti konfigūruojamas kiekvienam objektui, naudojamam atitikmenų porose.

Dublikatų naikinimo taisyklių nurodymas nėra būtinas. Jei nėra nustatytų tokių taisyklių, taikomos sistemos nustatytos taisyklės. Dėl didesnio efektyvumo jos sujungia visus įrašus į vieną įrašą prieš perduodant objekto duomenis gretinimui tarp objektų.

### <a name="add-deduplication-rules"></a>Įtraukti papildomo dublikavimo taisykles

1. Eikite į **Duomenys** > **Suvienodinti”** > **Atitikmuo**.

1. Skyriuje **Sulieti dublikatai** pasirinkite **Nustatyti objektus**. Tuo atveju, jei dublikatų naikinimo taisyklės jau sukurtos, pasirinkite **Redaguoti**.

1. Srityje **Suliejimo nuostatos** pasirinkite objektus, kuriems norite vykdyti dublikatų naikinimą.

1. Nurodykite, kaip sujungti pasikartojančius įrašus ir pasirinkite vieną iš trijų parinkčių:
   - **Labiausiai užpildytas**: Nustato įrašą su labiausiai užpildytais atributo laikais kaip nugalėtoją. Tai yra numatytoji suliejimo parinktis.
   - **Naujausias**: Nustato įrašą laimėtoją pagal naujausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
   - **Seniausias**: Nustato įrašą laimėtoją pagal seniausius duomenis. Reikalauja datos ar skaičių laukelio, skirto nustatyti naujumą.
 
   > [!div class="mx-imgBorder"]
   > ![Dublikatų naikinimo taisyklių veiksmas 1.](media/match-selfconflation.png "Dublikatų naikinimo taisyklių 1 veiksmas")
 
1. Pasirinkę objektus ir nustatę jų suliejimo nuostatą, pasirinkite **Įtraukti taisyklę**, kad nustatytumėte dublikatų naikinimo taisykles objekto lygiu.
   - **Pasirinkti lauką** išvardijami visi galimi to objekto laukai. Pasirinkite lauką, kurio dublikatų norite ieškoti. Pasirinkite laukus, kurie, tikėtina, yra unikalūs kiekvienam klientui. Pavyzdžiui, el. pašto adresas ar vardo, miesto ir telefono numerio derinys.
   - Nurodykite normalizacijos ir tikslumo parametrus.
   - Apibrėžkite daugiau sąlygų pasirinkdami **Įtraukti sąlygą**.
 
   > [!div class="mx-imgBorder"]
   > ![Dublikatų naikinimo taisyklių veiksmas 2.](media/match-selfconflation-rules.png "Dublikatų naikinimo taisyklių 2 veiksmas")

  Galite sukurti keletą dublikatų naikinimo taisyklių objektui. 

1. Suderinimo proceso vykdymas dabar grupuoja įrašus pagal sąlygas, nustatytas dublikatų naikinimo taisyklėse. Po įrašų grupavimo, suliejimo strategija yra taikoma siekiant nustatyti laimėjusį įrašą.

1. Tada šis pagrindinis įrašas ir nelaimėję įrašai (pavyzdžiui, alternatyvūs ID) perduodami kelių objektų atitikmeniui, kad pagerėtų atitikimo kokybę.

1. Bet kuri apibrėžta pasirinktinė gretinimo taisyklė perrašo dublikatų naikinimo taisykles. Jei dublikatų naikinimo taisyklė nustato atitikties įrašus ir tinkinta atitikties taisyklė yra nustatyta taip, kad niekada neatitiktų tų įrašų, tuomet šie du įrašai nebebus suderinti.

1. Paleidę [gretinimo procesą](#run-the-match-process), pagrindinių metrikų plytelėse matysite dublikatų naikinimo statistiką.

### <a name="deduplication-output-as-an-entity"></a>Dublikatų naikinimo išvestis kaip objektas

Dublikatų naikinimo procesas sukuria naują objektą kiekvienam objektui iš atitikmenų porų, kad būtų galima identifikuoti panaikintus pasikartojančius įrašus. Šiuos objektus galima rasti kartu su **„ConflationMatchPairs:CustomerInsights”** skyriuje **Sistema**, puslapyje **Objektai**, pavadinimu **„Deduplication_DataSource_Entity”**.

Dublikatų naikinimo išvesties objektas turi šią informaciją:
- ID/Raktai
  - Pirminio rakto laukas ir jo alternatyvus ID laukas. Alternatyvų ID lauką sudaro visi nustatyti įrašo alternatyvūs ID.
  - Dublikatų naikinimo grupės ID lauke rodoma grupė arba klasteris, nustatytas objektu, grupuojantis visus panašius įrašus pagal nurodytus dublikatų naikinimo laukus. Jis naudojamas sistemos apdorojimo tikslais. Jei nėra nurodytų neautomatiniu būdu nurodomų dublikatų naikinimo taisyklių ir taikomos sistemos apibrėžtos dublikatų naikinimo taisyklės, šis laukas gali būti nerandamas dublikatų naikinimo išvesties objektui.
  - „Deduplication_WinnerId”: Šiame lauke yra nustatytų grupių arba grupių laimėtojo ID. Jei „Deduplication_WinnerId” reikšmė yra tokia pati kaip įrašo pirminio rakto reikšmė, tai reiškia, kad įrašas yra nugalėtojas.
- Laukai, naudojami dublikatų naikinimo taisyklėms apibrėžti.
- Taisyklių ir Rezultato laukeliai žymi gretinimo algoritmo grąžintą rezultatą ir, kurios iš dublikatų naikinimo taisyklių buvo taikomos.
   
## <a name="run-the-match-process"></a>Gretinimo proceso vykdymas

Sukonfigūravę gretinimo taisykles, įskaitant gretinimą tarp objektų ir dublikatų naikinimo taisykles, galite vykdyti gretinimo procesą. 

Eikite į **Duomenys** > **Suvienodinti** > **Atitikmuo** ir pasirinkite **Vykdyti** procesui pradėti. Gretinimo algoritmo įvykdymas užtrunka šiek tiek laiko ir jūs negalite pakeisti konfigūracijos, kol ji nebus baigta. Norėdami atlikti pakeitimus, galite atšaukti vykdymą. Pasirinkite užduoties būseną ir srityje **Eigos informacija** pasirinkite **Atšaukti užduotį**.

Sėkmingo atlikimo rezultatą – vieningąjį kliento profilio objektą, rasite **Objektų** puslapyje. Jūsų vieningasis kliento objektas yra pavadintas **Klientai** skyriuje **Profiliai**. Pirmasis sėkmingas vykdymas sukuria vieningąjį *Kliento* objektą. Visi tolesni gretinimo vykdymai išplečia tą objektą.

> [!TIP]
> Paleidę atitikties procesą, pasirinkite proceso būseną, kad atidarytumėte **Išsamios užduočių informacijos** sritį. Joje apžvelgiamas apdorojimo laikas, paskutinio apdorojimo data ir visos su užduotimi susijusios klaidos ir įspėjimai. Pasirinkite **Peržiūrėti išsamią informaciją**, kad sužinotumėte, kurie objektai dalyvavo gretinimo procese, kokios taisyklės jiems buvo pritaikytos ir tai, ar naujinimai buvo sėkmingai publikuoti.  
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Detalizavimo kelias, kuriuo galima apdoroti išsamią informaciją iš užduoties būsenos saito.":::

## <a name="review-and-validate-your-matches"></a>Peržiūrėkite ir patvirtinkite savo atitiktis

Eikite į **Duomenis** > **Suvienodinti** > **Atitikmuo**, kad įvertintumėte savo atitikmenų porų kokybę ir jas patikslintumėte, jeigu reikia.

Puslapio viršuje esančiose plytelėse rodoma pagrindinė metrika, apibendrinanti suderintų įrašų ir dublikatų skaičių.

:::image type="content" source="media/match-KPIs.png" alt-text="Apkarpyta Atitikties puslapio pagrindinės metrikos su skaičiais ir išsamia informacija ekrano kopija.":::

- **Unikalūs šaltinio įrašai** rodo atskirų šaltinio įrašų, apdorotų paskutiniame sugretinimo vykdyme, skaičių.
- **Suderinti ir nesuderinti įrašai** išryškina, kiek unikalių įrašų lieka apdorojus gretinimo taisykles.
- **Tik suderinti įrašai** rodo atitikmenų skaičių visose jūsų sugretintose porose.

Kiekvienos atitikmenų poros rezultatus ir taisykles galite pasiekti lentelėje **Išsami suderintų įrašų informacija**. Palyginkite įrašų iš atitikmenų porų skaičių su sėkmingai suderintų įrašų procentu.

Peržiūrėkite atitikties poros taisykles, kad pamatytumėte sėkmingai suderintų įrašų procentą taisyklės lygiu. Pasirinkite daugtaškį (...) ir tada pasirinkite **Atitikties peržiūra**, kad peržiūrėtumėte visus šiuos įrašus taisyklės lygiu. Mes rekomenduojame peržiūrėti kai kuriuos įrašus, kad patikrintumėte, ar jie buvo tinkamai suderinti.

Išbandykite skirtingas sąlygų ribines vertes optimaliai vertei rasti.

  1. Pasirinkite daugtaškį (...) taisyklei, su kuria norite eksperimentuoti ir pasirinkite **Redaguoti**.

  2. Pakeiskite tikslumo vertes sąlygose, kurias norite peržiūrėti.

  3. Pasirinkite **Peržiūra**, kad pamatytumėte pasirinktos sąlygos suderintų ir nesuderintų įrašų skaičių.

## <a name="manage-match-rules"></a>Sugretinimo taisyklių valdymas

Galite konfigūruoti iš naujo ir tiksliai nustatyti daugumą atitikties parametrų.

:::image type="content" source="media/match-rules-management.png" alt-text="Išplečiamojo meniu vaizdas su atitikties taisyklės parinktimis.":::

- **Pakeiskite taisyklių eiliškumą**, jeigu apibrėžėte kelias taisykles. Galite pakeisti gretinimo taisyklių tvarką pasirinkdami parinktis **Perkelti aukštyn** ir **Perkelti žemyn** arba nuvilkdami.

- **Pakeiskite taisyklės sąlygas** pasirinkdami **Redaguoti** ir pasirinkite skirtingus laukus.

- **Išjunkite taisyklę** išlaiko gretinimo taisyklę, bet neįtraukia jos į gretinimo procesą.

- **Dubliuokite savo taisykles**, jei nustatėte gretinimo taisyklę ir norite sukurti panašią taisyklę su modifikacijomis, pasirinkite **Dublikatas**.

- **Panaikinkite taisyklę** pasirinkdami **Naikinti** simbolį.

## <a name="specify-custom-match-conditions"></a>Nurodykite pasirinktines gretinimo sąlygas

Galite nurodyti sąlygas, pagal kurias tam tikri įrašai turi visada atitikti arba neatitikti. Šias taisykles galima nusiųsti standartinio gretinimo proceso perrašymui. Pavyzdžiui, jei mūsų įrašuose yra Rimvydas Saulis I ir Rimvydas Saulis II, sistema gali juos sugretinti kaip vieną asmenį. Pasirinktinės gretinimo taisyklės leidžia nurodyti, kad jų profiliai būtų skirti skirtingiems asmenims. 

1. Eikite į **Duomenys** > **Suvienodinti** > **Atitikmuo** ir pasirinkite **Pasirinktinis atitikmuo** skyriuje **Suderintų įrašų informacija**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Skyriaus Gretinimo taisyklės su pažymėtu pasirinktinio atitikmens valdikliu ekrano kopija.":::

1. Jeigu neturite pasirinktinių gretinimo taisyklių rinkinio, pamatysite naują **Pasirinktinio gretinimo** sritį su daugiau informacijos.

1. Pasirinkite **Užpildyti šabloną**, jei norite gauti šabloną, nurodantį, kurie įrašai iš kurių objektų turi visada atitikti arba neatitikti. Dviejuose skirtinguose failuose turėsite atskirai užpildyti „visada atitinka“ ir „niekada neatitinka“ įrašus.

1. Šablone yra laukų, nurodančių objektą ir objekto pirminių raktų reikšmes, kurias reikia naudoti pasirinktinio atitikimo srityje. Pavyzdžiui, jeigu norite, kad pirminis raktas *„12345”* iš objekto *Pardavimas* visada atitiktų pirminį raktą *„34567”* iš objekto *Kontaktas*, užpildykite šabloną:
    - Objektas1: pardavimai
    - Objekto1kodas: 12345
    - Objektas2: kontaktas
    - Objekto2kodas: 34567

   Tas pats šablono failas gali nurodyti pasirinktinius atitikties įrašus iš kelių objektų.
   
   Jei norite nurodyti objekto dublikatų naikinimo pasirinktinį gretinimą, pateikite tą patį objektą kaip ir Objektą1, ir Objektą2 ir nustatykite skirtingas pirminio rakto reikšmes.

1. Įtraukę visus pageidaujamus perrašymus, išsaugokite šablono failą.

1. Eikite **Duomenys** > **Duomenų šaltiniai** ir permeskite šablonų failus kaip naujus objektus. Kai failai paversti, galite juos naudoti atitikties konfigūracijai.

1. Kai galite įkelti failus ir objektus, pasirinkite **pasirinktinės atitikties** parinktį dar kartą, Matysite parametrus, nurodančius objektus, kuriuos norite įtraukti. Išplečiamajame meniu pažymėkite reikiamus objektus.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialogo lango, kai reikia pasirinkti pasirinktinio atitikties scenarijaus perrašymus, ekrano kopija.":::

1. Pasirinkite objektus, kuriuos norite naudoti **visada atitinka** ir **niekada neatitinka**, tada pažymėkite **atlikta**.

1. Pasirinkite **Įrašyti** puslapyje **Atitikmuo** pasirinktinės gretinimo konfigūracijos pritaikymui.

1. Pasirinkite **Vykdyti** puslapyje **Atitikmuo** gretinimo procesui pradėti. Kitas nurodytas gretinimo taisykles perrašo pasirinktinė gretinimo konfigūracija.

> [!TIP]
> Eikite **Duomenys** > **Objektai** ir peržiūrėkite objektą **„ConflationMatchPair”** patvirtinti, kad pritaikyti perrašymai.

## <a name="next-step"></a>Kitas veiksmas

Kai užbaigsite bent vienos atitinkančios poros gretinimo procesą, galėsite išspręsti galimus duomenų prieštaravimus [**suliejimo**](merge-entities.md) temoje.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
