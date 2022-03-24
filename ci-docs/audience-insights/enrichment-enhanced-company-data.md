---
title: Įmonės duomenų tobulinimas
description: Praturtinkite ir normalizuokite įmonės duomenis naudodami "Microsoft" modelius.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376362"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Įmonės profilių praturtinimas patobulintais įmonės duomenimis

Naudokite "Microsoft" modelius ir surinktus įmonės duomenis, kad ištaisytumėte, papildytumėte ir standartizuotumėte savo įmonės profilius. Siekdami didesnio tikslumo [ir įžvalgų, naudosime "Common Data Model" formatą](/common-data-model/schema/core/applicationcommon/account).

Taip pat [galite pagerinti įmonės duomenis apie duomenų šaltinius](data-sources-enrichment.md), kad pagerintumėte duomenų suvienijimo proceso atitikimo tikslumą. 

## <a name="how-we-enhance-company-data"></a>Kaip mes tobuliname įmonės duomenis

Mūsų modelis pereina dviejų etapų procesą, kad pagerintų įmonės profilį. Pirma, jis normalizuoja įmonės pavadinimą. Pavyzdžiui, *"Microsoft Corp"* bus ištaisyta ir standartizuota " *Microsoft Corporation"*. Ji bando rasti atitikmenį "Microsoft" sukauptuose įmonės duomenyse. Jei randama atitikmenų, įmonės profilį praturtiname informacija iš mūsų surinktų įmonės duomenų, įskaitant įmonės pavadinimą.


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

Yra keletas apribojimų, susijusių su patobulintais duomenimis. Toliau pateikto sąrašo elementų modelis nepalaiko.

1.  Patvirtinkite įmonės tapatybę. Mes netikriname, ar įvestis yra esama organizacija, ar įmonė naudoja išvestį kaip standartinį pavadinimą.
2.  Išsamiai apima įmones visame pasaulyje. "Microsoft" surinkti įmonės duomenys turi pasaulinę aprėptį, tačiau siūlo didžiausią aprėptį Australijoje, Kanadoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
3.  Standartizuoti įmonės adresus visame pasaulyje. Šiuo metu mes palaikome standartizuotus adresus šiose šalyse ar regionuose: Australijoje, Kanadoje, Prancūzijoje, Vokietijoje, Italijoje, Japonijoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
4.  Užtikrinti duomenų tikslumą ar šviežumą. Kadangi verslo informacija dažnai keičiasi, negalime garantuoti, kad pateikti patobulinti įmonės duomenys visada yra tikslūs arba atnaujinti.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**.

1. PlytelėJe **Patobulinta įmonės duomenys** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Sodrinimo plytelė įmonės duomenų sodrinimo centre.":::

1. Pažymėkite **Kliento duomenų rinkinį** ir pasirinkite objektą, kuriame yra norimi papildyti adresai. Galite pasirinkti *Kliento* objektą, kad adresai būtų papildyti visuose jūsų klientų profiliuose, arba pasirinkti segmento objektą, kad adresai būtų papildyti tik to segmento klientų profiliuose.

1. Pasirinkite, kokio tipo laukai iš jūsų įmonės profilių turėtų būti naudojami derinant su "Microsoft" surinktais įmonės duomenimis. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

1.  Susiekite įmonės laukus iš savo vieningo kliento objekto. Kuo daugiau pagrindinių identifikatorių ir laukų susiejate, tuo didesnė tikimybė, kad atitiks didesnį atitikmenų skaičių.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Duomenų susiejimo veiksmas konfigūruojant įmonės sodrinimą.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Pateikite papildymo ir išvesties objekto pavadinimus.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Praturtintų duomenų pavyzdį galite pamatyti plytelėje **Praturtinti klientai peržiūrėti**. Pasirinkite **Žiūrėti daugiau** ir pasirinkite skirtuką **Duomenys,** kad pasiektumėte išsamų kiekvieno praturtinto profilio rodinį.

### <a name="overview-card"></a>Apžvalgos kortelė

Apžvalgos kortelėje pateikiama išsami informacija apie sodrinimo aprėptį. 

* **Apdorotos ir pakeistos** įmonės: sėkmingai praturtintų klientų įmonės profilių skaičius.

* **Apdorotos ir nepakeistos** įmonės: pripažintų, bet nepakeistų klientų įmonių profilių skaičius. Tai paprastai atsitinka, kai įvesties duomenys yra galiojantys ir negali būti patobulinti sodrinus.

* **Įmonės, kurios nebuvo apdorotos ir nepakeistos**: neatpažintų klientų įmonės profilių skaičius. Tai paprastai atsitinka įvesties duomenims, kurie yra neleistini arba nepalaikomi sodrinimo.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
