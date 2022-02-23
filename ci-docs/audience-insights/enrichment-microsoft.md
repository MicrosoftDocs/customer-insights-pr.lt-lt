---
title: Klientų profilių papildymas naudojant „Microsoft“ duomenis
description: Naudokite patentuotus "Microsoft" duomenis, kad praturtintumėte savo klientų duomenis panašumais ir balso bendrinimu.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/11/2021
ms.locfileid: "7793714"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Praturtinkite klientų profilius panašumais ir balso dalimi (peržiūra)

Naudokite "Microsoft" nuosavybinius duomenis, kad praturtintumėte savo klientų duomenis prekės ženklo panašumais, palūkanų priskyrimais ir balso (SoV) bendrinimu. Šie panašumai ir SoV yra pagrįsti duomenimis iš žmonių, kurių demografija panaši į jūsų klientus. Ši informacija padeda geriau suprasti ir suskirstyti klientus pagal jų panašumus arba SoV į konkrečius prekės ženklus ir interesus.

Auditorijos įžvalgose eikite į **Duomenys** > **Papildymas** ir [konfigūruokite bei peržiūrėkite papildymus](enrichment-hub.md).

Norėdami konfigūruoti prekės ženklo priskyrimus ir SoV sodrinimą, eikite į **skirtuką Atrasti** ir pasirinkite **Praturtinti mano duomenis** **plytelėje** Prekės ženklai.

Norėdami konfigūruoti pomėgių priskyrimus ir SoV praturtėjimą, eikite į **skirtuką Atrasti** ir **·** **plytelėje Pomėgiai pasirinkite Praturtinti mano** duomenis.

   > [!div class="mx-imgBorder"]
   > ![Prekės ženklų ir interesų plytelės.](media/BrandsInterest-tile-Hub.png "Prekės ženklai ir interesų plytelės")

## <a name="how-we-determine-affinities-and-sov"></a>Kaip mes nustatome giminystės ir SoV

Naudojame "Microsoft" internetinės ieškos duomenis, kad rastume prekių ženklų ir pomėgių įvairiuose demografiniuose segmentuose (apibrėžiamų pagal amžių, lytį ar vietą) giminystės ryšiais ir SoV. Prekės ženklo ar palūkanų internetinės paieškos apimtis yra pagrindas giminystės ar SoV nustatymui. Tačiau kiekvienas iš jų suteikia skirtingą perspektyvą suprasti savo klientus.

- Giminystė yra lyginamoji demografinių segmentų dalis. Šią informaciją galite naudoti demografiniams segmentams, kurie turi didžiausią priklausomybę tam tikram prekės ženklui ar pomėgiui, palyginti su kitais segmentais, identifikuoti.

- Balso dalis yra lyginamoji jūsų pasirinktų prekių ženklų ar pomėgių dalis. Šią informaciją galite naudoti norėdami nustatyti, kuris prekės ženklas ar interesas turi didžiausią balso dalį tam tikrame demografiniame segmente, palyginti su kitais pasirinktais prekių ženklais ar interesais.

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

SoV apskaičiuojame 100 balų skalėje. Bendras SoV visuose prekės ženkluose ar pomėgiuose už kiekvieną praturtintą kliento profilį prideda iki 100. Skirtingai nuo panašumų, SoV yra susijęs su jūsų pasirinktais prekių ženklais ir interesais. Pavyzdžiui, "Microsoft" SoV reikšmės gali skirtis, jei pasirinkti prekių ženklai yra ("Microsoft", "GitHub") ir ("Microsoft", "LinkedIn").

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikomos šių šalių ir (arba) regionų parinktys: Australija, Kanada (anglų k.), Prancūzija, Vokietija, Jungtinė Karalystė arba Jungtinės Amerikos Valstijos (anglų k.).

Norėdami pažymėti šalį arba regioną, atidarykite **Prekės ženklų praturtinimas** arba **Intereso praturtinimas** ir pasirinkite **Keisti** šalia **Šalis/regionas**. Srityje **Šalies ir (arba) regiono parametrai** pasirinkite parinktį ir pasirinkite **Taikyti**.

### <a name="implications-related-to-country-selection"></a>Padariniai, susiję su šalies pasirinkimu

- Kai [pasirenkate savo prekių ženklus, ](#define-your-brands-or-interests), sistema teikia pasiūlymus pagal pasirinktą šalį arba regioną.

- Pasirinkę [pramonės šaką](#define-your-brands-or-interests), gausite svarbiausius prekės ženklus arba susiesite pagal pasirinktą šalį arba regioną.

- Praturtindami [profilius praturtinsime](#refresh-enrichment), visus klientų profilius, pagal kuriuos gauname duomenis apie pasirinktus prekių ženklus ir interesams, įskaitant ne pasirinktos šalies ar regiono profilius. Pvz., jei pasirinkote Vokietiją, papildysime JAV esančius duomenis, jei gausime duomenų apie pasirinktus prekių ženklus ir pomėgius JAV.

## <a name="configure-enrichment"></a>Praturtinimo konfigūravimas

Vedama patirtis leidžia peržiūrėti konfigūraciją ir papildymus. 

### <a name="define-your-brands-or-interests"></a>Prekių ženklų arba pomėgių apibrėžimas

Pasirinkite ne daugiau kaip penkis prekių ženklus ar pomėgius naudodami vieną iš šių parinkčių arba jas abi:

- **Pramonės šaka**: išplečiamajame sąraše pasirinkite pramonės šaką ir pasirinkite iš geriausių tos pramonės šakų markių arba domina.
- **Pasirinkite savo**: Įveskite jūsų organizacijai aktualų prekės ženklą arba pomėgį, o tada išsirinkite iš atitinkančių pasiūlymų. Jei jūsų ieškomo prekių ženklo ar pomėgio nėra, atsiųskite mums atsiliepimą naudodami nuorodą **Pasiūlyti**.

### <a name="review-enrichment-preferences"></a>Papildymo nuostatos

Peržiūrėkite numatytąsias pratinimo nuostatas ir prireikus atnaujinkite jas.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Pratinimo nuostatų lango papildymas.":::

### <a name="select-entity-to-enrich"></a>Pasirinkti objektą susiejimui

Pasirinkite **Praturtintas** objektas ir pasirinkite duomenų rinkinį, kurį norite praturtinti "Microsoft" duomenimis. Galite pažymėti objektą Klientas, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

### <a name="map-your-fields"></a>Susiekite savo laukus

Susiekite laukus iš vieningojo kliento objekto ir apibrėžkite demografinį segmentą, kurį sistema turėtų naudoti savo klientų duomenims papildyti. Susiekite šalį / regioną ir bent gimimo datą arba lyties atributus. Turite susieti šalį / regioną. Taip pat turite susieti bent vieną miestą (ir rajoną / apskritį) arba pašto indeksą. Pasirinkite **Redaguoti**, norėdami apibrėžti laukų susiejimą, ir baigę pasirinkite **Taikyti**. Spustelėkite **Įrašyti**, kad baigtumėte susieti laukus.

Palaikomi toliau nurodyti formatai ir reikšmės (reikšmėse didžiosios ir mažosios raidės neskiriamos).

- **Gimimo data**: rekomenduojama, kad duomenų įtraukimo metu gimimo data būtų konvertuota į „DateTime“ formatą. Arba tai gali būti eilutė [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)f ormatu "yyyy-MM-dd" arba "yyyy-MM-ddTHH:mm:ss".
- **Lytis**: vyras, moteris, nežinoma.
- **Pašto indeksas**: Penkių skaitmenų Pašto indeksai, skirti Jungtinėms Amerikos Valstijoms, standartinis pašto indeksas kas daugiau.
- **Miestas**: miesto pavadinimas anglų k.
- **Valstija / provincija**: dviejų raidžių santrumpa JAV ir Kanadoje. Dviejų ar trijų raidžių santrumpa Australijoje. Netaikoma Prancūzijai, Vokietijai ir JK.
- **Šalis / regionas**:

  - JAV: Jungtinės Amerikos Valstijos, Jungtinės Valstijos, JAV, Amerika
  - CA: Kanada, CA
  - GB: Jungtinė Karalystė, JK, Didžioji Britanija, GB, Jungtinė Didžiosios Britanijos ir Šiaurės Airijos Karalystė, Jungtinė Didžiosios Britanijos Karalystė
  - AS: Australia, AU, Australijos Bendrijoje
  - FR: Prancūzija, FR, Prancūzijos Respublika
  - DE: Vokietija, vokiečių, Deutschland, DE, Vokietijos Federacinė Respublika, Vokietijos Respublika

## <a name="review-and-name-the-enrichment"></a>Papildymo peržiūra ir pavadinimas

Galiausiai galite peržiūrėti informaciją ir nurodyti papildymo pavadinimą.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pomėgių peržiūros ir pavadinimo suteikimo puslapis.":::

## <a name="refresh-enrichment"></a>Papildymo atnaujinimas

Papildymą vykdykite sukonfigūravę prekių ženklus, pomėgius ir demografinių duomenų laukų susiejimą. Norėdami pradėti procesą, prekės ženklo arba pomėgio konfigūravimo puslapyje pasirinkite **Vykdyti**. Be to, galite leisti sistemai automatiškai vykdyti papildymą, kai vykdomas suplanuotas atnaujinimas.

Priklausomai nuo jūsų klientų duomenų apimties, papildymas gali užtrukti kelias minutes.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Papildymo rezultatai

Įvykdę papildymo procesą, eikite į **Mano papildymai** ir peržiūrėkite bendrą papildytų klientų skaičių bei prekių ženklų arba pomėgių pasiskirstymą papildytuose klientų profiliuose.

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą.":::

Rasite diagramą su praturtintų klientų profilių skaičiumi laikui bėgant ir praturtėjusių objektų peržiūromis. Peržiūrėkite patobulintus duomenis pasirinkdami **Daugiau informacijos** **affiniteto lygyje** arba balso elementų **diagramoje**. Praturtinti prekių ženklų duomenys atitenka **"BrandAffinityFromMicrosoft"** ir **"BrandShareOfVoiceFromMicrosoft"** subjektams. Interesų duomenys yra **"InterestAffinityFromMicrosoft"** ir **"InterestShareOfVoiceFromMicrosoft"** subjektuose. Šiuos objektus taip pat rasite grupėje **Papildymas**, esančioje **Duomenys** > **Objektai**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Prekės ženklą ir palūkanas SoV taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite prekės ženklo arba dominančios "SoV" diagramas, pagrįstas to kliento demografinio profilio žmonėmis.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis.":::

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
