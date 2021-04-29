---
title: Klientų profilių papildymas naudojant „Microsoft“ duomenis
description: Norėdami savo kliento duomenis papildyti prekės ženklo ir pomėgių savybėmis, naudokite bendrovės „Microsoft“ duomenis.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896612"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Klientų profilių papildymas informacija apie susidomėjimą prekių ženklais ir pomėgiais (peržiūra)

Norėdami savo kliento duomenis papildyti prekės ženklo ir pomėgių savybėmis, naudokite bendrovės „Microsoft“ duomenis. Šis susidomėjimas nustatomas pagal žmonių, kurių demografiniai rodikliai yra panašūs į jūsų klientų rodiklius, duomenis. Ši informacija padeda geriau suprasti ir skirstyti klientus pagal jų susidomėjimą tam tikrais prekių ženklais ir pomėgiais.

Auditorijos įžvalgose eikite į **Duomenys** > **Papildymas** ir [konfigūruokite bei peržiūrėkite papildymus](enrichment-hub.md).

Norėdami konfigūruoti prekės ženklo panašumo papildymą, eikite į skirtuką **Atrasti** ir pasirinkite **Praturtinti mano duomenis** plytelėje **Prekių ženklai**.

Norėdami konfigūruoti pomėgio panašumo papildymą, eikite į skirtuką **Atrasti** ir pasirinkite **Praturtinti mano duomenis** plytelėje **Pomėgiai**.

   > [!div class="mx-imgBorder"]
   > ![Prekių ženklų ir pomėgių plytelės](media/BrandsInterest-tile-Hub.png "Prekių ženklų ir pomėgių plytelės")

## <a name="how-we-determine-affinities"></a>Kaip apibrėžiame savybes

„Microsoft“ internetinės paieškos duomenis naudojame prekės ženklų ir pomėgių savybėms rasti įvairiuose demografiniuose segmentuose (apibrėžiamuose pagal amžių, lytį arba vietą). Pagal prekių ženklo ar pomėgio paieškos internete apimtį nustatoma, koks yra demografinio segmento susidomėjimas tuo prekių ženklu ar pomėgiu, palyginti su kitais segmentais. prekės ženklas arba pomėgis.

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

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikomos šių šalių ir (arba) regionų parinktys: Australija, Kanada (anglų k.), Prancūzija, Vokietija, Jungtinė Karalystė arba Jungtinės Amerikos Valstijos (anglų k.).

Norėdami pasirinkti šalį, atidarykite **Prekių ženklų papildymas** arba **Pomėgių papildymas** ir pasirinkite **Keisti** šalia **Šalis ir (arba) regionas**. Srityje **Šalies ir (arba) regiono parametrai** pasirinkite parinktį ir pasirinkite **Taikyti**.

### <a name="implications-related-to-country-selection"></a>Padariniai, susiję su šalies pasirinkimu

- Kai [pasirenkate savo prekių ženklus, ](#define-your-brands-or-interests), sistema teikia pasiūlymus pagal pasirinktą šalį arba regioną.

- Pasirinkę [pramonės šaką](#define-your-brands-or-interests), gausite svarbiausius prekės ženklus arba susiesite pagal pasirinktą šalį arba regioną.

- [Praturtindami profilius](#refresh-enrichment), praturtinsime visus klientų profilius, pagal kuriuos gauname duomenis apie pasirinktus prekių ženklus ir susies klientus. Įtraukti profilius, kurių nėra parinktoje šalyje ar regione. Pvz., jei pasirinkote Vokietiją, papildysime JAV esančius duomenis, jei gausime duomenų apie pasirinktus prekių ženklus ir pomėgius JAV.

## <a name="configure-enrichment"></a>Papildymo konfigūravimas

Vedama patirtis leidžia peržiūrėti konfigūraciją ir papildymus. 

### <a name="define-your-brands-or-interests"></a>Prekių ženklų arba pomėgių apibrėžimas

Pažymėkite vieną iš šių parinkčių:

- **Pramonės šaka**: sistema nustato populiariausius jūsų pramonės šakai aktualius prekių ženklus arba pomėgius ir jais papildo klientų duomenis.
- **Pasirinkti savo**: iš prekių ženklų arba pomėgių sąrašo pasirinkite ne daugiau kaip 5 elementus, kurie jūsų organizacijai yra svarbiausi.

Norėdami įtraukti prekių ženklą arba pomėgį, įveskite jį įvesties srityje, kad būtų rodomi pasiūlymai pagal sutampančias sąvokas. Jei jūsų ieškomo prekių ženklo ar pomėgio nėra, atsiųskite mums atsiliepimą naudodami nuorodą **Pasiūlyti**.

### <a name="review-enrichment-preferences"></a>Papildymo nuostatos

Peržiūrėkite numatytąsias pratinimo nuostatas ir prireikus atnaujinkite jas.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Pratinimo nuostatų lango papildymas.":::

### <a name="select-entity-to-enrich"></a>Pasirinkti objektą susiejimui

Pasirinkite **Papildytas objektas** ir pasirinkite duomenų rinkinį, kurį norite papildyti įmonės duomenimis iš „Microsoft“. Galite pažymėti objektą Klientas, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

### <a name="map-your-fields"></a>Susiekite savo laukus

Susiekite laukus iš vieningojo kliento objekto ir apibrėžkite demografinį segmentą, kurį sistema turėtų naudoti savo klientų duomenims papildyti. Susiekite šalį / regioną ir bent gimimo datą arba lyties atributus. Turite susieti šalį / regioną. Taip pat turite susieti bent vieną miestą (ir rajoną / apskritį) arba pašto indeksą. Pasirinkite **Redaguoti**, norėdami apibrėžti laukų susiejimą, ir baigę pasirinkite **Taikyti**. Spustelėkite **Įrašyti**, kad baigtumėte susieti laukus.

Palaikomi toliau nurodyti formatai ir reikšmės; reikšmėse didžiosios ir mažosios raidės neskiriamos.

- **Gimimo data**: rekomenduojama, kad duomenų įtraukimo metu gimimo data būtų konvertuota į „DateTime“ formatą. Arba ji gali būti eilutė pagal [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formatu „YYYY-MM-DD“ arba „yyyy-MM-ddTHH:mm:ssZ“.
- **Lytis**: vyras, moteris, nežinoma
- **Pašto kodas**: penkiaženklis pašto kodas JAV, standartinis pašto kodas visur kitur
- **Miestas**: miesto pavadinimas anglų k.
- **Valstija / provincija**: dviejų raidžių santrumpa JAV ir Kanadoje. Dviejų ar trijų raidžių santrumpa Australijoje. Netaikoma Prancūzijai, Vokietijai ir JK.
- **Šalis / regionas**:

  - JAV: Jungtinės Amerikos Valstijos, Jungtinės Valstijos, JAV, Amerika
  - CA: Kanada, CA
  - GB: Jungtinė Karalystė, JK, Didžioji Britanija, GB, Jungtinė Didžiosios Britanijos ir Šiaurės Airijos Karalystė, Jungtinė Didžiosios Britanijos Karalystė
  - AU: Australija, Australijos Sandrauga
  - FR: Prancūzija, FR, Prancūzijos Respublika
  - DE: Vokietija, vokiečių, Deutschland, DE, Vokietijos Federacinė Respublika, Vokietijos Respublika

## <a name="review-and-name-the-enrichment"></a>Papildymo peržiūra ir pavadinimas

Galiausiai galite peržiūrėti informaciją ir nurodyti papildymo pavadinimą.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Pomėgių peržiūros ir pavadinimo suteikimo puslapis.":::

## <a name="refresh-enrichment"></a>Papildymo atnaujinimas

Papildymą vykdykite sukonfigūravę prekių ženklus, pomėgius ir demografinių duomenų laukų susiejimą. Norėdami pradėti procesą, prekės ženklo arba pomėgio konfigūravimo puslapyje pasirinkite **Vykdyti**. Be to, galite leisti sistemai automatiškai vykdyti papildymą, kai vykdomas suplanuotas atnaujinimas.
Priklausomai nuo jūsų klientų duomenų apimties, papildymas gali užtrukti kelias minutes.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="enrichment-results"></a>Papildymo rezultatai

Įvykdę papildymo procesą, eikite į **Mano papildymai** ir peržiūrėkite bendrą papildytų klientų skaičių bei prekių ženklų arba pomėgių pasiskirstymą papildytuose klientų profiliuose.

:::image type="content" source="media/my-enrichments.png" alt-text="Rezultatų peržiūra atlikus papildymo procesą":::

Peržiūrėkite papildytus duomenis diagramoje spustelėdami **Peržiūrėti papildytus duomenis**. Papildyti prekių ženklų duomenys yra objekte **BrandAffinityFromMicrosoft**. Pomėgių duomenys yra objekte **InterestAffinityFromMicrosoft**. Šiuos objektus taip pat rasite grupėje **Papildymas**, esančioje **Duomenys** > **Objektai**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Žr. papildymo duomenis kliento kortelėje

Susidomėjimą prekių ženklais ir pomėgiais taip pat galima peržiūrėti atskirose klientų kortelėse. Eikite į **Klientai** ir pasirinkite kliento profilį. Kliento kortelėje rasite prekių ženklų arba prekių ženklų, kurie traukia žmones kliento demografiniame profilyje, diagramas.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliento kortelė su papildytais duomenimis":::

## <a name="next-steps"></a>Kiti veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [Segmentai](segments.md), [Matavimai](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]