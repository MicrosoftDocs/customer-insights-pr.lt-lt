---
title: Įmonės duomenų tobulinimas
description: Praturtinkite ir normalizuokite įmonės duomenis naudodami "Microsoft" modelius.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953959"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Įmonės profilių praturtinimas patobulintais įmonės duomenimis

Naudokite "Microsoft" modelius ir sukompiliuotus įmonės duomenis, kad ištaisytumėte, papildytumėte ir standartizuotumėte savo įmonės profilius. Naudosime "Common Data Model" formatą [,](/common-data-model/schema/core/applicationcommon/account) kad būtų užtikrintas didesnis tikslumas ir įžvalgos.

Taip pat [galite pagerinti įmonės duomenis apie duomenų šaltinius](data-sources-enrichment.md), kad pagerintumėte duomenų suvienijimo proceso atitikties tikslumą.

Valstybinėms įmonėms Jungtinėse Amerikos Valstijose yra informacijos, tokios kaip pajamos, akcijų tiksėjimas, pramonė ir kt.  

## <a name="how-we-enhance-company-data"></a>Kaip mes tobuliname įmonės duomenis

Mūsų modelis pereina dviejų etapų procesą, kad pagerintų įmonės profilį. Pirma, tai normalizuoja įmonės pavadinimą. Pavyzdžiui, *"Microsoft Corp* " bus pataisyta ir standartizuota į *"Microsoft Corporation"*. Ji bando rasti atitikmenį "Microsoft" sukompiliuotuose įmonės duomenyse. Jei randama atitiktis, mes praturtiname įmonės profilį informacija iš mūsų surinktų įmonės duomenų, įskaitant įmonės pavadinimą.

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

- Patvirtinkite įmonės tapatybę. Mes netikriname, ar įvestis yra esama organizacija, ar įmonė naudoja išvestį kaip standartinį pavadinimą.
- Visapusiškai apima įmones visame pasaulyje. "Microsoft" surinkti įmonės duomenys turi pasaulinę aprėptį, tačiau siūlo didžiausią aprėptį Australijoje, Kanadoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
- Standartizuoti įmonės adresus visame pasaulyje. Šiuo metu palaikome adresų standartizavimą šiose šalyse ar regionuose: Australijoje, Kanadoje, Prancūzijoje, Vokietijoje, Italijoje, Japonijoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
- Užtikrinti duomenų tikslumą ar šviežumą. Kadangi verslo informacija dažnai keičiasi, negalime garantuoti, kad pateikti patobulinti įmonės duomenys visada bus tikslūs arba atnaujinti.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje **Patobulinti įmonės duomenys** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Sodrinimo plytelės įmonės duomenų sodrinimo centre.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti. Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

1. Pasirinkite, kokio tipo laukus iš įmonės profilių naudoti derinant su "Microsoft" sukompiliuotais įmonės duomenimis. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

1. Pasirinkite **Toliau**.

1. Susiekite savo įmonės laukus su įmonės duomenimis iš "Microsoft". Jei norite didesnio rungtynių tikslumo, pridėkite daugiau laukų.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Duomenų susiejimo veiksmas konfigūruojant įmonės sodrinimą.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite sodrinimo ir išvesties objekto** **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Apžvalgos kortelė

Eilutėje **Klientai keičia apžvalgą** rodoma išsami informacija apie sodrinimo aprėptį

- **Apdorotos ir pakeistos** įmonės: sėkmingai praturtintų klientų įmonių profilių skaičius.
- **Apdorotos ir nepakeistos** įmonės: klientų įmonės profilių, kurie buvo pripažinti, bet nepakeisti, skaičius. Tai paprastai atsitinka, kai įvesties duomenys yra tinkami ir jų negalima pagerinti praturtinant.
- **Įmonės, kurios nebuvo apdorotos ir nepakeistos**: neatpažintų klientų įmonės profilių skaičius. Tai paprastai atsitinka įvesties duomenims, kurie yra neleistini arba nepalaikomi praturtinimo.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
