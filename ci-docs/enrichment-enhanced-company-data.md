---
title: Praturtinkite įmonių profilius naudodami patobulintus įmonės duomenis
description: Praturtinkite ir normalizuokite įmonės duomenis naudodami "Microsoft" modelius.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054258"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Praturtinkite įmonių profilius naudodami patobulintus įmonės duomenis

Naudokite "Microsoft" modelius ir surinktus įmonės duomenis, kad ištaisytumėte, papildytumėte ir standartizuotumėte savo įmonės profilius. Naudosime ["Common Data Model" formatą](/common-data-model/schema/core/applicationcommon/account), kad užtikrintume didesnį tikslumą ir įžvalgas.

Taip pat [galite patobulinti įmonės duomenis apie duomenų šaltinius](data-sources-enrichment.md), kad pagerintumėte atitikties tikslumą duomenų suvienijimo procese.

Jav valstybinėms įmonėms yra prieinama tokia informacija kaip pajamos, akcijų žymeklis, pramonė ir kt.  

## <a name="how-we-enhance-company-data"></a>Kaip mes tobuliname įmonės duomenis

Mūsų modelis pereina dviejų etapų procesą, kad pagerintų įmonės profilį. Pirma, tai normalizuoja įmonės pavadinimą. Pavyzdžiui, *"Microsoft Corp* " bus pataisyta ir standartizuota į *"Microsoft Corporation"*. Ji bando rasti atitikmenį "Microsoft" sukompiliuotuose įmonės duomenyse. Jei randama atitiktis, įmonės profilį praturtiname informacija iš mūsų surinktų įmonės duomenų, įskaitant įmonės pavadinimą.

### <a name="example"></a>Pavyzdžiui

Jūsų įmonės informacija gali neatitikti standartizuoto formato ir joje gali būti rašybos klaidų. Modelis bando išspręsti šias problemas ir sukurti nuoseklią informaciją.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Apribojimai

Modelis neatlieka šių veiksmų:

- Patvirtinkite įmonės tapatybę. Netikriname, ar įvestis yra esama organizacija, ar įmonė naudoja išvestį kaip standartinį pavadinimą.
- Visapusiškai aprėpti įmones visame pasaulyje. "Microsoft" surinkti įmonės duomenys apima visą pasaulį, tačiau siūlo daugiausia aprėpties Australijoje, Kanadoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
- Standartizuokite įmonės adresus visame pasaulyje. Šiuo metu palaikome adresų standartizavimą šiose šalyse ar regionuose: Australijoje, Kanadoje, Prancūzijoje, Vokietijoje, Italijoje, Japonijoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
- Garantuokite duomenų tikslumą ar šviežumą. Kadangi verslo informacija dažnai keičiasi, negalime garantuoti, kad pateikti patobulinti įmonės duomenys visada yra tikslūs ar naujausi.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis**, esantį plytelėje **Patobulinti įmonės duomenys**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Papildymo plytelė įmonės duomenų praturtinimo centre.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite, kokio tipo laukus iš savo įmonės profilių naudoti norint suderinti su "Microsoft" sukompiliuotais įmonės duomenimis. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

1. Pasirinkite **Toliau**.

1. Susiekite įmonės laukus su įmonės duomenimis iš "Microsoft". Norėdami gauti didesnį atitikties tikslumą, įtraukite daugiau laukų.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Duomenų susiejimo veiksmas konfigūruojant įmonės papildymą.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite papildymo ir objekto** **Išvestis pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Apžvalgos kortelė

Plytelė Klientų **keitimų apžvalga** rodo išsamią informaciją apie papildymo aprėptį

- **Apdorotos ir pakeistos** įmonės: sėkmingai praturtintų klientų įmonių profilių skaičius.
- **Įmonės apdorotos ir nepakeistos**: klientų įmonių profilių, kurie buvo pripažinti, bet nepasikeitė, skaičius. Paprastai taip atsitinka, kai įvesties duomenys yra galiojantys ir jų negalima pagerinti praturtinant.
- **Neapdorotos ir nepakeistos** įmonės: neatpažįstamų klientų įmonių profilių skaičius. Paprastai taip nutinka įvesties duomenims, kurie yra netinkami arba nepalaikomi papildymo.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
