---
title: LiveRamp tapatybės duomenų praturtinimas
description: Praturtinkite klientų profilius "LiveRamp" duomenimis.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643188"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Praturtinkite klientų profilius tapatybės duomenimis iš "LiveRamp" (peržiūra) 

LiveRamp teikia deterministinę autonominę tapatybės skiriamąją gebą ir kliento duomenų konsolidavimą. Galite susieti asmeninius identifikatorius savo kliento duomenyse su AbiliTec tapatybės grafiku ir gauti AbiliTec ID. Tada galite naudoti šiuos ID, kad geriau suvienodintumėte savo klientų duomenis. 

## <a name="prerequisites"></a>Būtinosios sąlygos 

Norint konfigūruoti sodrinimą, turi būti įvykdytos šios būtinosios sąlygos: 

- Turite aktyvią "LiveRamp" prenumeratą. Norėdami gauti prenumeratą, susisiekite su "LiveRamp" abonemento komanda arba norėdami gauti [dynamics@liveramp.com](mailto:dynamics@liveramp.com) daugiau informacijos.   

- Aktyvi "AbiliTec" prenumerata su kliento ID ir slapta prieiga prie API. Daugiau informacijos ieškokite [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai 

Šiuo metu palaikome klientų profilių praturtinimą "LiveRamp" duomenimis tik Jungtinėse Amerikos Valstijose. 

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas 

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**. 

1. Plytelėje Tapatybė pasirinkite **Praturtinti mano duomenis**.**·** 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Tapatybės plytelė sodrinimo apžvalgos puslapyje.":::

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, galite sukurti ryšį pasirinkdami **Įtraukti ryšį**. Išplečiamajame sąraše pasirinkite **LiveRamp**. 

1. Pasirinkite **Pirmyn** ir pasirinkite **kliento duomenų rinkinį**, kurį norite praturtinti "LiveRamp" tapatybės duomenimis. Galite pasirinkti objektą *Klientas*, kad praturtintumėte visus savo klientų profilius, arba pasirinkti segmento *objektą*, kad praturtintumėte tik tame segmente esančius klientų profilius. 

1. Pasirinkite **Pirmyn** ir apibrėžkite, kokio tipo laukai iš jūsų vieningų profilių turėtų būti naudojami ieškant atitinkančių tapatybės duomenų iš "LiveRamp". Reikalingas bent vienas iš laukų **Pavadinimas ir adresas** **, Telefonas** arba **El. paštas**. 

   > [!TIP]
   > Kuo daugiau pagrindinių identifikatorių ir laukų susiejate, tuo didesnė tikimybė, kad atitikmuo bus didesnis 

1. Susiekite laukus iš vieningo *kliento* objekto, kuris bus naudojamas derinant su LiveRamp AbiliTec ID diagrama. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="&quot;LiveRamp&quot; sodrinimo duomenų susiejimo parinktys.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**. 

1. **Pateikite sodrinimo ir išvesties objekto** **pavadinimą**. 

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigūruoti "LiveRamp" ryšį 

Norėdami konfigūruoti ryšius [, turite būti administratorius](connections.md). Konfigūruodami sodrinimą pasirinkite Įtraukti ryšį arba eikite į **AdminConnections** **ir plytelėje LiveRamp** > **pasirinkite** **Nustatyti**.**·** 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigūracijos sritis, skirta nustatyti ryšį su LiveRamp AbiliTec tarnyba.":::

1. Jei norite **rodyti pavadinimą**, įveskite ryšio pavadinimą. 

1. Pateikite galiojantį "LiveRamp" kliento ID ir paslaptį. 

1. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**. 

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją. 

1. Norėdami užbaigti ryšį, pasirinkite **Įrašyti**. 

## <a name="enrichment-results"></a>Papildymo rezultatai 

Norėdami pradėti sodrinimo procesą, komandų juostoje pasirinkite Vykdyti. Taip pat galite leisti sistemai automatiškai paleisti sodrinimą kaip suplanuoto [atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio. 

Baigę sodrinimo procesą, galite peržiūrėti naujai praturtintus klientų profilių duomenis dalyje **Mano sodrinimas**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių. 

Galite pasiekti išsamų kiekvieno praturtinto profilio vaizdą pasirinkdami **"View" praturtintus** duomenis. 

## <a name="next-steps"></a>Paskesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Naudokite AbiliTec ID, kad konsoliduotumėte klientų profilius į asmenį pagrįstą rodinį. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis 

Kai įgalinate Dynamics 365 Customer Insights perduoti duomenis "LiveRamp", leidžiate perduoti duomenis už atitikties ribos, įskaitant potencialiai neskelbtinus Dynamics 365 Customer Insights duomenis, pvz., asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "LiveRamp" laikytųsi visų privatumo ar saugos įsipareigojimų, kuriuos galite turėti. Norėdami gauti daugiau informacijos, peržiūrėkite ["Microsoft" privatumo patvirtinimą](https://go.microsoft.com/fwlink/?linkid=396732). Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
