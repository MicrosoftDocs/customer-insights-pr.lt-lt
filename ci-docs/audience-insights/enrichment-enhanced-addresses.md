---
title: Išplėstinio adreso papildymas
description: Papildykite ir normalizuokite klientų profilių adresų informaciją naudodami „Microsoft” modelius.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305442"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Klientų profilių papildymas išplėstiniais adresais

Adresai jūsų duomenyse gali būti nesusisteminti, neišsamūs arba neteisingi. Naudokite „Microsoft” modelius, kad normalizuotumėte ir papildytumėte savo adresus į [„Common Data Model” formatą](/common-data-model/schema/core/applicationcommon/address) geresniam tikslumui ir įžvalgoms.

## <a name="how-we-enhance-addresses"></a>Kaip išplečiame adresus

Mūsų modelis adreso papildymui naudoja dviejų veiksmų procesą. Pirma, jis išanalizuoja adresą, kad galėtų identifikuoti jo komponentus ir pateikti juos susistemintu formatu. Tada AI naudojame adreso reikšmėms pataisyti, užbaigti ir standartizuoti.

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

Išplėstiniai adresai veikia tik su tomis reikšmėmis, kurios jau yra jūsų įtrauktų adresų duomenyse. Modelis neatlieka šių veiksmų: 

1. Netikrina, ar adresas yra tinkamas.
2. Netikrina, ar konkrečios reikšmės, pavyzdžiui, pašto kodai ar gatvių pavadinimai, yra tinkami.
3. Nekeičia reikšmių, kurių neatpažįsta.

Siekiant papildyti adresus, modelis naudoja mašininio mokymo metodus. Nors modeliui pakeičiant įvesties reikšmę taikoma aukšta ribinė reikšmė, kaip ir naudojant mašininį mokomosios sistemos modelį, 100 procentų tikslumas nėra tarpusavio tikslumas.

## <a name="supported-countries-or-regions"></a>Palaikomos šalys arba regionai

Šiuo metu palaikome adresų papildymus šiose šalyse ar regionuose: 

- Australija
- Kanada
- Jungtinė Karalystė
- Jungtinės Valstijos

Adresuose turi būti šalies/regiono reikšmė. Mes neapdorojame nepalaikomų šalių ar regionų adresų ir tų adresų, kuriems nepateikta šalis arba regionas.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**.

1. Pasirinkite **Papildyti mano duomenis** plytelėje **Papildyti adresai**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Papildytų adresų plytelės vaizdas.":::

1. Pažymėkite **Kliento duomenų rinkinį** ir pasirinkite objektą, kuriame yra norimi papildyti adresai. Galite pasirinkti *Kliento* objektą, kad adresai būtų papildyti visuose jūsų klientų profiliuose, arba pasirinkti segmento objektą, kad adresai būtų papildyti tik to segmento klientų profiliuose.

1. Pasirinkite, kaip jūsų duomenų rinkinyje yra formatuojami adresai. Pasirinkite **Adresas su vienu atributu**, jei jūsų duomenų adresuose naudojamas vienas laukas. Pasirinkite **Adresas su keliais atributais**, jei jūsų duomenų adresuose naudojamas daugiau nei vienas duomenų laukas.

   > [!NOTE]
   > Šalis / regionas privalomai nurodomas ir vieno, ir kelių atributų adresuose. Adresai, kuriuose nėra galiojančių arba palaikomų šalies/regiono reikšmių, nebus papildyti.

1.  Susiekite adreso laukus iš jūsų vieningojo kliento objekto.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Išplėstinio adreso laukų susiejimo puslapis.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Pateikite papildymo ir išvesties objekto pavadinimus.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
