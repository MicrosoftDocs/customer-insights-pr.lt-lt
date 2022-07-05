---
title: Praturtinkite klientų profilius prekių ženklais ir pomėgių duomenimis iš "Microsoft" (peržiūra)
description: Naudokite patentuotus "Microsoft" duomenis, kad praturtintumėte savo klientų duomenis ryšiais ir balso bendrinimu.
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
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082705"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Praturtinkite klientų profilius prekių ženklais ir pomėgių duomenimis iš "Microsoft" (peržiūra)

Naudokite "Microsoft" patentuotus duomenis, kad praturtintumėte savo klientų duomenis prekės ženklo ryšiais, pomėgių giminystės ryšiais ir balso dalijimusi (SoV). Šie giminystės ryšiai ir SoV yra pagrįsti žmonių, kurių demografiniai rodikliai panašūs į jūsų klientų, duomenimis. Ši informacija padeda geriau suprasti ir segmentuoti klientus pagal jų giminystės ryšius arba SoV su konkrečiais prekių ženklais ir pomėgiais.

## <a name="how-we-determine-affinities-and-sov"></a>Kaip mes nustatome giminingumą ir SoV

Mes naudojame "Microsoft" internetinės ieškos duomenis, kad rastume bendrų interesų ir SoV prekių ženklams ir pomėgiams įvairiuose demografiniuose segmentuose (apibrėžiamuose pagal amžių, lytį ar vietą). Prekės ženklo ar pomėgio internetinės paieškos apimtis yra pagrindas nustatant giminingumą arba SoV. Tačiau kiekvienas iš jų suteikia skirtingą požiūrį į klientų supratimą.

- Giminingumas yra lyginamasis demografinių segmentų palyginimas. Šią informaciją galite naudoti norėdami nustatyti demografinius segmentus, kurie turi didžiausią giminystės ryšį su tam tikru prekės ženklu ar pomėgiu, palyginti su kitais segmentais.

- Balso dalis yra jūsų pasirinktų prekių ženklų ar pomėgių palyginimas. Naudodami šią informaciją galite nustatyti, kuris prekės ženklas ar pomėgis turi didžiausią balso dalį tam tikrame demografiniame segmente, palyginti su kitais pasirinktais prekių ženklais ar pomėgiais.

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

SoV apskaičiuojame 100 balų skalėje. Bendras soV visuose prekės ženkluose ar pomėgiuose kiekvienam praturtintam kliento profiliui prideda iki 100. Skirtingai nuo giminystės ryšių, SoV yra susijęs su jūsų pasirinktais prekių ženklais ir interesais. Pavyzdžiui, "Microsoft" SoV reikšmės gali skirtis, jei pasirinkti prekių ženklai yra ("Microsoft", "GitHub") ir ("Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikomos šių šalių ir (arba) regionų parinktys: Australija, Kanada (anglų k.), Prancūzija, Vokietija, Jungtinė Karalystė arba Jungtinės Amerikos Valstijos (anglų k.).

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

   - Norėdami sukonfigūruoti prekės ženklo panašumus ir SoV praturtinimą, plytelėje **Prekės ženklai** pasirinkite **Praturtinti mano duomenis**.

   - Norėdami konfigūruoti pomėgių pomėgius ir SoV papildymą, plytelėje **Pomėgiai** pasirinkite **Praturtinti mano duomenis**.

   > [!div class="mx-imgBorder"]
   > ![Prekės ženklų ir interesų plytelės.](media/BrandsInterest-tile-Hub.png "Prekės ženklai ir interesų plytelės")

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Norėdami pakeisti šalį ar regioną, pasirinkite **Keisti** šalia **Šalis / regionas**. **Srityje Šalies / regiono parametrai** pasirinkite palaikomą šalį / regioną [ir](#supported-countriesregions) pasirinkite **Taikyti**.

   > [!NOTE]
   > Kai pasirenkate savo prekių ženklus, , sistema teikia pasiūlymus pagal pasirinktą šalį arba regioną. Pasirinkę pramonės šaką, gausite svarbiausius prekės ženklus arba susiesite pagal pasirinktą šalį arba regioną.

1. Pasirinkite ne daugiau kaip penkis prekių ženklus ar pomėgius naudodami vieną iš šių parinkčių arba jas abi:

   - **Pramonės šaka**: išplečiamajame sąraše pasirinkite pramonės šaką ir pasirinkite iš geriausių tos pramonės šakų markių arba domina.
   - **Pasirinkite savo**: Įveskite jūsų organizacijai aktualų prekės ženklą arba pomėgį, o tada išsirinkite iš atitinkančių pasiūlymų. Jei jūsų ieškomo prekių ženklo ar pomėgio nėra, atsiųskite mums atsiliepimą naudodami nuorodą **Pasiūlyti**.

1. Pasirinkite **Pirmyn** ir peržiūrėkite numatytąsias papildymo nuostatas ir, jei reikia, atnaujinkite jas.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Pratinimo nuostatų lango papildymas.":::

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti "Microsoft" duomenimis. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite **Toliau**.

1. Susiekite laukus iš vieningo kliento objekto su "Microsoft" duomenimis.

   > [!NOTE]
   > Būtina bent jau gimimo data arba lyties požymiai. Šalis / regionas ir bent miestas (ir valstija / provincija) arba pašto kodas yra būtini. Rekomenduojame, kad duomenų nurijimo metu gimimo data būtų konvertuota į DateTime tipą. Arba tai gali būti eilutė [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)f ormatu "yyyy-MM-dd" arba "yyyy-MM-ddTHH:mm:ss".

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Nurodykite papildymo pavadinimą. Išvesties **objekto pavadinimas** pasirenkamas automatiškai.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pomėgių peržiūros ir pavadinimo suteikimo puslapis.":::

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

   Praturtindami profilius praturtinsime, visus klientų profilius, pagal kuriuos gauname duomenis apie pasirinktus prekių ženklus ir interesams, įskaitant ne pasirinktos šalies ar regiono profilius. Pvz., jei pasirinkote Vokietiją, papildysime JAV esančius duomenis, jei gausime duomenų apie pasirinktus prekių ženklus ir pomėgius JAV.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Rezultatai apima **bendrų interesų lygį** arba **"Share of Voice"** diagramas.

Objektai, sukurti iš papildymų, yra išvardyti duomenų **objektų** **grupėje** > **Papildymas**. Praturtinti prekių ženklų duomenys patenka į **"BrandAffinityFromMicrosoft"** ir **"BrandShareOfVoiceF" iš "Microsoft"** subjektų. Interesų duomenys yra **"InterestAffinityFromMicrosoft"** ir **"InterestShareOfVoiceF" iš "Microsoft"** objektų.

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Prekės ženklą ir susidomėjimą SoV taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite prekės ženklo ar pomėgio SoV diagramas pagal to kliento demografinio profilio žmones.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
