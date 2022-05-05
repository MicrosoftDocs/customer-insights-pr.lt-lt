---
title: Įmonės duomenų tobulinimas
description: Praturtinkite ir normalizuokite įmonės duomenis naudodami "Microsoft" modelius.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642994"
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

Yra keletas apribojimų, susijusių su patobulintais duomenimis. Modelis nepalaiko toliau pateikto sąrašo elementų.

1.  Patvirtinkite įmonės tapatybę. Mes netikriname, ar įvestis yra esama organizacija, ar įmonė naudoja išvestį kaip standartinį pavadinimą.
2.  Visapusiškai apima įmones visame pasaulyje. "Microsoft" surinkti įmonės duomenys turi pasaulinę aprėptį, tačiau siūlo didžiausią aprėptį Australijoje, Kanadoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
3.  Standartizuoti įmonės adresus visame pasaulyje. Šiuo metu palaikome adresų standartizavimą šiose šalyse ar regionuose: Australijoje, Kanadoje, Prancūzijoje, Vokietijoje, Italijoje, Japonijoje, Jungtinėje Karalystėje ir Jungtinėse Amerikos Valstijose.
4.  Užtikrinti duomenų tikslumą ar šviežumą. Kadangi verslo informacija dažnai keičiasi, negalime garantuoti, kad pateikti patobulinti įmonės duomenys visada bus tikslūs arba atnaujinti.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**.

1. Plytelėje **Patobulinti įmonės duomenys** pasirinkite **Praturtinti mano duomenis**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Sodrinimo plytelės įmonės duomenų sodrinimo centre.":::

1. Pažymėkite **Kliento duomenų rinkinį** ir pasirinkite objektą, kuriame yra norimi papildyti adresai. Galite pasirinkti *Kliento* objektą, kad adresai būtų papildyti visuose jūsų klientų profiliuose, arba pasirinkti segmento objektą, kad adresai būtų papildyti tik to segmento klientų profiliuose.

1. Pasirinkite, kokio tipo laukai iš jūsų įmonės profilių turėtų būti naudojami derinant su "Microsoft" sukompiliuotais įmonės duomenimis. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

1.  Susiekite įmonės laukus iš savo vieningo kliento objekto. Kuo daugiau pagrindinių identifikatorių ir laukų susiejate, tuo didesnė tikimybė, kad atitikmuo bus didesnis.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Duomenų susiejimo veiksmas konfigūruojant įmonės sodrinimą.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Pateikite papildymo ir išvesties objekto pavadinimus.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Praturtintų duomenų pavyzdį galite pamatyti padidintų **klientų peržiūros** plytelėje. Pasirinkite **Peržiūrėti daugiau** ir pasirinkite skirtuką **Duomenys**, kad pasiektumėte išsamų kiekvieno papildyto profilio rodinį.

### <a name="overview-card"></a>Apžvalgos kortelė

Apžvalgos kortelėje pateikiama išsami informacija apie sodrinimo aprėptį. 

* **Apdorotos ir pakeistos** įmonės: sėkmingai praturtintų klientų įmonių profilių skaičius.

* **Apdorotos ir nepakeistos** įmonės: klientų įmonės profilių, kurie buvo pripažinti, bet nepakeisti, skaičius. Tai paprastai atsitinka, kai įvesties duomenys yra tinkami ir jų negalima pagerinti praturtinant.

* **Įmonės, kurios nebuvo apdorotos ir nepakeistos**: neatpažintų klientų įmonės profilių skaičius. Tai paprastai atsitinka įvesties duomenims, kurie yra neleistini arba nepalaikomi praturtinimo.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
