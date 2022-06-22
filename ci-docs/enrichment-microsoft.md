---
title: Klientų profilių praturtinimas prekių ženklais ir pomėgių duomenimis iš "Microsoft"
description: Naudokite "Microsoft" nuosavybinius duomenis, kad praturtintumėte savo klientų duomenis giminystės ryšiais ir balso bendrinimu.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953775"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Praturtinkite klientų profilius giminystės ryšiais ir balso dalimi (peržiūra)

Naudokite "Microsoft" nuosavybinius duomenis, kad praturtintumėte savo klientų duomenis prekės ženklo ryšiais, pomėgiais ir balso dalimi (SoV). Šie panašumai ir SoV yra pagrįsti žmonių, kurių demografija panaši į jūsų klientų, duomenimis. Ši informacija padeda geriau suprasti ir segmentuoti savo klientus pagal jų panašumus arba SoV į konkrečius prekės ženklus ir interesus.

## <a name="how-we-determine-affinities-and-sov"></a>Kaip mes nustatome giminystės ryšius ir SoV

Mes naudojame "Microsoft" internetinės paieškos duomenis, kad rastume panašumų ir SoV prekių ženklams ir interesams įvairiuose demografiniuose segmentuose (apibrėžtuose pagal amžių, lytį ar vietą). Prekės ženklo ar palūkanų internetinės paieškos apimtis sudaro pagrindą nustatyti giminingumą arba SoV. Tačiau kiekvienas iš jų suteikia skirtingą požiūrį į savo klientų supratimą.

- Afinitetas yra lyginamasis įvairiuose demografiniuose segmentuose. Šią informaciją galite naudoti norėdami nustatyti demografinius segmentus, kurie turi didžiausią ryšį su tam tikru prekės ženklu ar interesais, palyginti su kitais segmentais.

- Balso dalis yra jūsų pasirinktų prekių ženklų ar interesų palyginimas. Šią informaciją galite naudoti norėdami nustatyti, kuris prekės ženklas ar interesas turi didžiausią balso dalį tam tikrame demografiniame segmente, palyginti su kitais pasirinktais prekių ženklais ar interesais.

## <a name="affinity-level-and-score"></a>Priskyrimo lygis ir balas

Kiekviename praturtintame kliento profilyje teikiame dvi susijusias reikšmes – priskyrimo lygį ir balą. Šios reikšmės padeda nustatyti, koks yra šio profilio demografinio segmento susidomėjimas tam tikrą prekės ženklą ar susidomėjimą, palyginti su kitais demografiniais segmentais.

*Priskyrimo lygį* sudaro keturi lygiai, o *priskyrimo balas* apskaičiuojamas 100 balų skalėje, kuri susieta su priskyrimo lygiais.

|Priskyrimo lygis |Patrauklumo balas  |
|---------|---------|
|Labai aukštą     | 85-100       |
|Aukštas     | 70-84        |
|Vidutinį     | 35-69        |
|Žemą     | 1-34        |

Priklausomai nuo to, kaip norite matuoti priskyrimą, galite naudoti arba priskyrimo lygį, arba balą. Priskyrimo balas suteikia tikslesnį valdymą.

## <a name="share-of-voice-sov"></a>Balso dalis (SoV)

Mes apskaičiuojame SoV pagal 100 taškų skalę. Bendras SoV visuose prekės ženkluose ar pomėgiuose kiekvienam praturtintam kliento profiliui sudaro iki 100. Skirtingai nuo giminystės ryšių, SoV yra susijęs su pasirinktais prekių ženklais ir interesais. Pavyzdžiui, "Microsoft" soV reikšmės gali skirtis, jei pasirinkti prekių ženklai yra ("Microsoft", "GitHub") palyginti su "Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikomos šių šalių ir (arba) regionų parinktys: Australija, Kanada (anglų k.), Prancūzija, Vokietija, Jungtinė Karalystė arba Jungtinės Amerikos Valstijos (anglų k.).

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

   - Norėdami konfigūruoti prekės ženklo giminingumą ir SoV sodrinimą, plytelėje **Prekės ženklai** pasirinkite **Praturtinti mano duomenis**.

   - Norėdami konfigūruoti pomėgių giminingumą ir SoV sodrinimą, plytelėje Pomėgiai pasirinkite **Praturtinti mano duomenis** **.**

   > [!div class="mx-imgBorder"]
   > ![Prekės ženklų ir interesų plytelės.](media/BrandsInterest-tile-Hub.png "Prekės ženklai ir interesų plytelės")

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Norėdami pakeisti savo šalį ar regioną, pasirinkite **Keisti** šalia **Šalies / regiono**. **Srityje Šalies / regiono parametrai** pasirinkite palaikomą šalį / regioną [ir](#supported-countriesregions) pasirinkite **Taikyti**.

   > [!NOTE]
   > Kai pasirenkate savo prekių ženklus, , sistema teikia pasiūlymus pagal pasirinktą šalį arba regioną. Pasirinkę pramonės šaką, gausite svarbiausius prekės ženklus arba susiesite pagal pasirinktą šalį arba regioną.

1. Pasirinkite ne daugiau kaip penkis prekių ženklus ar pomėgius naudodami vieną iš šių parinkčių arba jas abi:

   - **Pramonės šaka**: išplečiamajame sąraše pasirinkite pramonės šaką ir pasirinkite iš geriausių tos pramonės šakų markių arba domina.
   - **Pasirinkite savo**: Įveskite jūsų organizacijai aktualų prekės ženklą arba pomėgį, o tada išsirinkite iš atitinkančių pasiūlymų. Jei jūsų ieškomo prekių ženklo ar pomėgio nėra, atsiųskite mums atsiliepimą naudodami nuorodą **Pasiūlyti**.

1. Pasirinkite **Pirmyn** ir peržiūrėkite numatytąsias sodrinimo nuostatas ir, jei reikia, atnaujinkite jas.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Pratinimo nuostatų lango papildymas.":::

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti "Microsoft" duomenimis. Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite **Toliau**.

1. Susiekite laukus iš vieningo kliento objekto į "Microsoft" duomenis.

   > [!NOTE]
   > Reikia bent jau gimimo datos arba lyties požymių. Reikalingi šalies / regiono ir bent jau miesto (ir valstijos / provincijos) arba pašto kodo. Rekomenduojame, kad prarijus duomenis gimimo data būtų konvertuota į DateTime tipą. Arba tai gali būti eilutė [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)f ormatu "yyyy-MM-dd" arba "yyyy-MM-ddTHH:mm:ss".

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Nurodykite papildymo pavadinimą. Išvesties **objekto pavadinimas** pasirenkamas automatiškai.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pomėgių peržiūros ir pavadinimo suteikimo puslapis.":::

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

   Praturtindami profilius praturtinsime, visus klientų profilius, pagal kuriuos gauname duomenis apie pasirinktus prekių ženklus ir interesams, įskaitant ne pasirinktos šalies ar regiono profilius. Pvz., jei pasirinkote Vokietiją, papildysime JAV esančius duomenis, jei gausime duomenų apie pasirinktus prekių ženklus ir pomėgius JAV.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Rezultatai apima **afiniteto lygį** arba **balso** bendrinimo diagramas.

Objektai, sukurti iš sodrinimo, yra įtraukti į **duomenų** subjektų **sodrinimo** > **grupę**. Praturtinti prekių ženklų duomenys atitenka **"BrandAffinityFromMicrosoft"** ir **"BrandShareOfVoiceFromMicrosoft"** subjektams. Interesų duomenys yra **"InterestAffinityFromMicrosoft"** ir **"InterestShareOfVoiceFromMicrosoft"** subjektuose.

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Prekės ženklą ir susidomėjimą SoV taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite prekės ženklo ar pomėgio "SoV" diagramas, pagrįstas to kliento demografinio profilio žmonėmis.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
