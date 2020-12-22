---
title: Praturinkite klientų profilius su „Microsoft Graph“
description: Naudodami „Microsoft Graph“ patentuotus duomenis papildykite kliento duomenis informacija apie susidomėjimą prekių ženklais ir pomėgiais.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406389"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Klientų profilių papildymas informacija apie susidomėjimą prekių ženklais ir pomėgiais (peržiūra)

Naudodami „Microsoft Graph“ patentuotus duomenis papildykite kliento duomenis informacija apie susidomėjimą prekių ženklais ir pomėgiais. Šis susidomėjimas nustatomas pagal žmonių, kurių demografiniai rodikliai yra panašūs į jūsų klientų rodiklius, duomenis. Ši informacija padeda geriau suprasti ir skirstyti klientus pagal jų susidomėjimą tam tikrais prekių ženklais ir pomėgiais.

Publikos įžvalgose eikite į **Duomenys** > **Praturtinimas** tam, kad [konfigūruotumėte ir peržiūrėtumėte praturtinimus](enrichment-hub.md).

Norėdami konfigūruoti prekės ženklo panašumo papildymą, eikite į skirtuką **Atrasti** ir pasirinkite **Praturtinti mano duomenis** plytelėje **Prekių ženklai**.

Norėdami konfigūruoti pomėgio panašumo papildymą, eikite į skirtuką **Atrasti** ir pasirinkite **Praturtinti mano duomenis** plytelėje **Pomėgiai**.

   > [!div class="mx-imgBorder"]
   > ![Prekių ženklų ir pomėgių plytelės](media/BrandsInterest-tile-Hub.png "Prekių ženklų ir pomėgių plytelės")

## <a name="about-microsoft-graph"></a>Apie „Microsoft Graph“

Naudojame „Microsoft Graph“ paieškos internete duomenis, kad rastumėme informaciją apie susidomėjimą prekių ženklais ir pomėgiais įvairiuose demografiniuose segmentuose (nustatytuose pagal amžių, lytį ar vietą). Pagal prekių ženklo ar pomėgio paieškos internete apimtį nustatoma, koks yra demografinio segmento susidomėjimas tuo prekių ženklu ar pomėgiu, palyginti su kitais segmentais.

[Sužinokite daugiau apie „Microsoft Graph“](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Susidomėjimo vertinimas ir pasikliovimas

**Susidomėjimo vertinimas** apskaičiuojamas pagal 100 taškų skalę, kur 100 reiškia segmentą, kuriame susidomėjimas prekės ženklu arba pomėgiu yra aukščiausias.

**Pasikliovimas susidomėjimu** taip pat apskaičiuojamas pagal 100 taškų skalę. Jis nurodo sistemos pasikliovimo, kad segmentas yra susidomėjęs prekių ženklu ar pomėgiu, lygį. Pasikliovimo lygis pagrįstas segmento dydžiu ir segmento detalumu. Segmento dydis nustatomas pagal turimų duomenų apie tą segmentą kiekį. Segmento detalumą lemia tai, kiek atributų (amžius, lytis, vieta) pasiekiama profilyje.

Nenormalizuojame jūsų duomenų rinkinio rezultatų. Todėl galite matyti ne visas galimas duomenų rinkinio susidomėjimo rezultatų reikšmes. Pavyzdžiui, tarp jūsų duomenų gali nebūti jokio papildyto kliento profilio, kurio susidomėjimo vertinimas būtų 100. Tai įmanoma, jei demografiniame segmente nėra klientų, kurių susidomėjimo atitinkamu prekių ženklu ar pomėgiu vertinimas būtų 100.

> [!TIP]
> [Kurdami segmentus](segments.md) pagal susidomėjimo rezultatus, prieš nuspręsdami dėl atitinkamų rezultatų ribinių verčių, peržiūrėkite duomenų rinkinio susidomėjimo rezultatų paskirstymą. Pavyzdžiui, susidomėjimo rezultatas 10 gali būti laikomas reikšmingu duomenų rinkinyje, kurio didžiausias susidomėjimo tam tikru prekės ženklu arba pomėgiu rezultatas yra tik 25.

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikomos šių šalių ir (arba) regionų parinktys: Australija, Kanada (anglų k.), Prancūzija, Vokietija, Jungtinė Karalystė arba Jungtinės Amerikos Valstijos (anglų k.).

Norėdami pasirinkti šalį, atidarykite **Prekių ženklų papildymas** arba **Pomėgių papildymas** ir pasirinkite **Keisti** šalia **Šalis ir (arba) regionas**. Srityje **Šalies ir (arba) regiono parametrai** pasirinkite parinktį ir pasirinkite **Taikyti**.

### <a name="implications-related-to-country-selection"></a>Padariniai, susiję su šalies pasirinkimu

- Kai [renkatės savo prekių ženklus](#define-your-brands-or-interests), pateiksime pasiūlymus pagal pasirinktą šalį ir (arba) regioną.

- [Renkantis veiklos sritį](#define-your-brands-or-interests), identifikuosime svarbiausius prekės ženklus arba interesus pagal pasirinktą šalį / regioną.

- Kai [siejate laukus](#map-your-fields), jei šalies ir (arba) regiono laukas nesusietas, jūsų kliento profiliai bus papildyti naudojant pasirinktos šalies ir (arba) regiono „Microsoft Graph“ duomenis. Naudodami tą pasirinkimą taip pat papildysime klientų profilius, kurie neturi šalies ir (arba) regiono duomenų.

- [Papildant profilius](#refresh-enrichment) bus papildyti visi klientų profiliai, dėl kurių yra pasirinktų prekių ženklų ir pomėgių „Microsoft Graph“ duomenų, įskaitant profilius, kurie nėra pasirinktoje šalyje ir (arba) regione. Pavyzdžiui, jei pasirinkote Vokietiją, papildysime profilius, esančius Jungtinėse Valstijose, jei turėsime pasirinktų prekių ženklų ir pomėgių JAV „Microsoft Graph“ duomenų.

## <a name="configure-enrichment"></a>Papildymo konfigūravimas

Prekių ženklų arba pomėgių papildymo konfigūravimas susideda iš dviejų veiksmų:

### <a name="define-your-brands-or-interests"></a>Prekių ženklų arba pomėgių apibrėžimas

Pažymėkite vieną iš šių parinkčių:

- **Pramonės šaka**: sistema nustato populiariausius jūsų pramonės šakai aktualius prekių ženklus arba pomėgius ir jais papildo klientų duomenis.
- **Pasirinkti savo**: iš prekių ženklų arba pomėgių sąrašo pasirinkite ne daugiau kaip 5 elementus, kurie jūsų organizacijai yra svarbiausi.

Norėdami įtraukti prekių ženklą arba pomėgį, įveskite jį įvesties srityje, kad būtų rodomi pasiūlymai pagal sutampančias sąvokas. Jei jūsų ieškomo prekių ženklo ar pomėgio nėra, atsiųskite mums atsiliepimą naudodami nuorodą **Pasiūlyti**.

### <a name="map-your-fields"></a>Susiekite savo laukus

Susiekite sujungto kliento objekto laukus su bent dviem atributais, kad apibrėžtumėte demografinį segmentą, kurį norite naudoti kliento duomenims papildyti. Pasirinkite **Redaguoti**, norėdami apibrėžti laukų susiejimą, ir baigę pasirinkite **Taikyti**. Spustelėkite **Įrašyti**, kad baigtumėte susieti laukus.

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
