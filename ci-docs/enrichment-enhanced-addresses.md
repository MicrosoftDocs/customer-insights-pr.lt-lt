---
title: Praturtinkite klientų profilius patobulintais adresais (yra vaizdo įrašų)
description: Papildykite ir normalizuokite klientų profilių adresų informaciją naudodami „Microsoft” modelius.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082075"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Praturtinkite klientų profilius patobulintais adresais

Adresai jūsų duomenyse gali būti nesusisteminti, neišsamūs arba neteisingi. Naudokite „Microsoft” modelius, kad normalizuotumėte ir papildytumėte savo adresus į [„Common Data Model” formatą](/common-data-model/schema/core/applicationcommon/address) geresniam tikslumui ir įžvalgoms.

Taip pat [galite papildyti adresus duomenų šaltiniuose](data-sources-enrichment.md), kad pagerintumėte atitikties tikslumą duomenų suvienijimo procese. 

## <a name="how-we-enhance-addresses"></a>Kaip išplečiame adresus

Mūsų modelis adreso papildymui naudoja dviejų veiksmų procesą. Pirma, jis išanalizuoja adresą, kad galėtų identifikuoti jo komponentus ir pateikti juos susistemintu formatu. Tada AI naudojame adreso reikšmėms pataisyti, užbaigti ir standartizuoti.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Pavyzdžiui

Adreso informacija gali būti non pavadinimo formatu ir jame yra rašybos klaidų. Modelis gali išspręsti šias problemas ir sukurti nuoseklius adresus vieninguosiuose klientų profiliuose.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Apribojimai

Patobulinti adresai veikia tik su tomis reikšmėmis, kurios jau yra jūsų prarytuose adresų duomenyse. Modelis neatlieka šių veiksmų:

1. Netikrina, ar adresas yra tinkamas.
2. Netikrina, ar konkrečios reikšmės, pavyzdžiui, pašto kodai ar gatvių pavadinimai, yra tinkami.
3. Nekeičia reikšmių, kurių neatpažįsta.

Siekiant papildyti adresus, modelis naudoja mašininio mokymo metodus. Kaip ir bet kuriame mašininiu mokymusi pagrįsto modelio atveju, 100 procentų tikslumas nėra garantuotas.

## <a name="supported-countries-or-regions"></a>Palaikomos šalys arba regionai

Šiuo metu palaikome adresų papildymus šiose šalyse ar regionuose:

- Australija
- Kanada
- Prancūzija
- Vokietija
- Italija
- Japonija
- Jungtinė Karalystė
- Jungtinės Valstijos

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis** plytelėje **Papildyti adresai**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Papildytų adresų plytelės vaizdas.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite, kaip jūsų duomenų rinkinyje yra formatuojami adresai. Pasirinkite **Adresas su vienu atributu**, jei jūsų duomenų adresuose naudojamas vienas laukas. Pasirinkite **Adresas su keliais atributais**, jei jūsų duomenų adresuose naudojamas daugiau nei vienas duomenų laukas.

1. Pasirinkite **Pirmyn** ir susiekite adresų laukus iš vieningo kliento objekto.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Išplėstinio adreso laukų susiejimo puslapis.":::

   > [!NOTE]
   > Šalis / regionas privalomai nurodomas ir vieno, ir kelių atributų adresuose. Adresai, kuriuose nėra galiojančių arba palaikomų šalies/regiono reikšmių, nebus papildyti.

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite papildymo ir objekto** **Išvestis pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lauku **praturtintų** klientų skaičius leidžia detalizuoti kiekvieno praturtinto lauko aprėptį.

### <a name="overview-card"></a>Apžvalgos kortelė

Klientų **keitimo apžvalgos** kortelėje rodoma išsami informacija apie papildymo aprėptį:

- **Apdoroti ir pakeisti** adresai: klientų profilių su adresais, kurie buvo sėkmingai papildyti, skaičius.
- **Apdoroti ir nepakeisti** adresai: klientų profilių su adresais, kurie buvo atpažinti, bet nepakeitti, skaičius. Paprastai tai atsitinka, kai įvesties duomenys yra galiojantys ir jų negalima pagerinti praturtinant.
- **Neapdoroti ir nepakeisti** adresai: profilių su neatpažįstamais adresais skaičius. Paprastai įvesties duomenims, kurie yra neteisingi arba nepalaikomi papildymo.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
