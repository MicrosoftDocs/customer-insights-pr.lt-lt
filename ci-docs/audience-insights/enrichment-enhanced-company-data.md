---
title: Įmonės duomenų tobulinimas
description: Praturtinkite ir normalizuokite įmonės duomenis naudodami "Microsoft" modelius.
ms.date: 11/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: d11700c87f31cedc40d32b201251d8a9e2e2c312
ms.sourcegitcommit: dfc4843cc78857f1e3ca49d7b938e3ba77969169
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813928"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Įmonės profilių praturtinimas patobulintais įmonės duomenimis

Naudokite "Microsoft" modelius ir sukompiliuotus įmonės duomenis, kad ištaisytumėte, papildytumėte ir standartizuotumėte savo įmonės profilius. Naudosime ["Common Data Model"](/common-data-model/schema/core/applicationcommon/account) formatą, kad gautume daugiau tikslumo ir įžvalgų.

## <a name="how-we-enhance-company-data"></a>Kaip mes tobuliname įmonės duomenis

Mūsų modelis pereina dviejų etapų procesą, kad pagerintų įmonės profilį. Pirma, jis normalizuoja įmonės pavadinimą. Pavyzdžiui, *"Microsoft Corp"* bus pataisyta ir standartizuota *"Microsoft Corporation"*. Ji bando rasti atitikmenį "Microsoft" sukompiliuotuose įmonės duomenyse. Radę atitikmenį, įmonės profilį praturtiname informacija iš mūsų surinktų įmonės duomenų, įskaitant įmonės pavadinimą.


### <a name="example"></a>Pavyzdžiui

Jūsų įmonės informacija gali nesivadovauti standartizuotu formatu ir joje gali būti rašybos klaidų. Modelis bando išspręsti šias problemas ir sukurti nuoseklią informaciją.

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

Patobulintais duomenimis taikomi keli apribojimai. Modelis nepalaiko toliau pateikto sąrašo elementų.

1.  Patvirtinkite įmonės tapatybę. Netikriname, ar įvestis yra esama organizacija, ar įmonė naudoja išvestį kaip standartinį pavadinimą.
2.  Visapusiškai apimti įmones visame pasaulyje. "Microsoft" surinkti įmonės duomenys apima visą pasaulį, tačiau daugiausia aprėpties yra Australijoje, Kanadoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
3.  Standartizuoti įmonės adresus visame pasaulyje. Šiuo metu palaikome adresų standartizavimą šiose šalyse ar regionuose: Australijoje, Kanadoje, Prancūzijoje, Vokietijoje, Italijoje, Japonijoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
4.  Garantuoti duomenų tikslumą arba šviežumą. Kadangi verslo informacija dažnai keičiasi, negalime garantuoti, kad pateikti patobulinti įmonės duomenys visada bus tikslūs arba atnaujinti.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**.

1. **Plytelėje** Patobulinti įmonės duomenys pasirinkite Praturtinti mano **duomenis**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Sodrinimo plytelės įmonės duomenų sodrinimo centre.":::

1. Pažymėkite **Kliento duomenų rinkinį** ir pasirinkite objektą, kuriame yra norimi papildyti adresai. Galite pasirinkti *Kliento* objektą, kad adresai būtų papildyti visuose jūsų klientų profiliuose, arba pasirinkti segmento objektą, kad adresai būtų papildyti tik to segmento klientų profiliuose.

1. Pasirinkite, kokio tipo laukai iš jūsų įmonės profilių turėtų būti naudojami derinant juos su "Microsoft" sudarytais įmonės duomenimis. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

1.  Susiekite įmonės laukus iš vieningo kliento objekto. Kuo daugiau pagrindinių identifikatorių ir laukų susiejate, tuo didesnė tikimybė, kad atitikimo lygis bus didesnis.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Duomenų susiejimo veiksmas konfigūruojant įmonės sodrinimą.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Pateikite papildymo ir išvesties objekto pavadinimus.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Kiti veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
