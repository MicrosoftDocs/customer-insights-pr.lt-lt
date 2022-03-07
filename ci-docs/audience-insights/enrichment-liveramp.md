---
title: LiveRamp tapatybės duomenų sodrinimas
description: Praturtinkite klientų profilius "LiveRamp" duomenimis.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373074"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Klientų profilių praturtinimas tapatybės duomenimis iš "LiveRamp" (peržiūra) 

"LiveRamp" teikia deterministinę neprisijungusios tapatybės sprendimą ir klientų duomenų konsolidavimą. Galite susieti kliento duomenų asmeninius identifikatorius su AbiliTec tapatybės diagrama ir gauti AbiliTec asmens tapatybės identifikatorius. Tada galite naudoti šiuos asmens duomenis, kad geriau suvienodinkite savo klientų duomenis. 

## <a name="prerequisites"></a>Būtinosios sąlygos 

Norint konfigūruoti sodrinimą, reikia įvykdyti šias būtinas sąlygas: 

- Turite aktyvią LiveRamp prenumeratą. Norėdami gauti prenumeratą, kreipkitės į "LiveRamp" abonemento komandą arba norėdami [dynamics@liveramp.com](mailto:dynamics@liveramp.com) gauti daugiau informacijos.   

- Aktyvi AbiliTec prenumerata su kliento ID ir slapta prieiga prie API. Daugiau informacijos ieškokite [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai 

Šiuo metu mes palaikome klientų profilių praturtinimą "LiveRamp" duomenimis tik Jungtinėse Amerikos Valstijose. 

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas 

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**. 

1. Plytelėje Tapatybė pasirinkite **Praturtinti mano duomenis**.**·** 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Tapatybės plytelė sodrinimo apžvalgos puslapyje.":::

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, galite sukurti ryšį pasirinkdami **Įtraukti ryšį**. Išplečiamajame sąraše pasirinkite **LiveRamp**. 

1. Pasirinkite **Pirmyn** ir pasirinkite Kliento duomenų rinkinį **,** kurį norite praturtinti "LiveRamp" tapatybės duomenimis. Galite pasirinkti kliento *objektą*, kuris papildys visus jūsų klientų profilius, arba pasirinkti segmento *objektą*, kad praturtintumėte tik tame segmente esančius klientų profilius. 

1. Pasirinkite **Pirmyn** ir nurodykite, kokio tipo laukai iš vieningų profilių turėtų būti naudojami norint ieškoti "LiveRamp" tapatybės duomenų atitikimo. Reikia bent vieno iš laukų **Pavadinimas ir adresas** **, Telefonas** arba **El. paštas**. 

   > [!TIP]
   > Kuo daugiau pagrindinių identifikatorių ir laukų susiejate, tuo didesnė tikimybė, kad atitikmuo bus didesnis 

1. Susiekite laukus iš suvienyto *kliento* objekto, kuris bus naudojamas gretinant su LiveRamp AbiliTec ID grafiku. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="&quot;LiveRamp&quot; sodrinimo duomenų susiejimo parinktys.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**. 

1. Pateikite **sodrinimo pavadinimą** ir išvesties **objektą**. 

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**. 

## <a name="configure-the-connection-for-liveramp"></a>Konfigūruoti "LiveRamp" ryšį 

Norėdami konfigūruoti ryšius, turite būti [administratorius](connections.md). Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **AdminConnections** > **ir** plytelėje **LiveRamp** pasirinkite **Nustatyti**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfigūracijos sritis, kurioje bus nustatytas ryšys su &quot;LiveRamp AbiliTec&quot; tarnyba.":::

1. Norėdami **rodyti pavadinimą**, įveskite ryšio pavadinimą. 

1. Pateikite galiojantį LiveRamp kliento ID ir paslaptį. 

1. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**. 

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją. 

1. Norėdami užbaigti ryšį, pasirinkite **Įrašyti**. 

## <a name="enrichment-results"></a>Papildymo rezultatai 

Norėdami pradėti sodrinimo procesą, komandų juostoje pasirinkite Vykdyti. Taip pat galite leisti sistemai automatiškai paleisti sodrinimą kaip suplanuoto [atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio. 

Užbaigę sodrinimo procesą, galite peržiūrėti naujai praturtintus klientų profilių duomenis dalyjeMy **sodrinimas**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių. 

Galite pasiekti išsamų kiekvieno praturtinto profilio rodinį pasirinkdami **Peržiūrėti praturtintus** duomenis. 

## <a name="next-steps"></a>Paskesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Naudokite AbiliTec ID, kad konsoliduotumėte klientų profilius į asmens rodinį. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis 

Kai leidžiate Dynamics 365 Customer Insights perduoti duomenis "LiveRamp", leidžiate perduoti duomenis už atitikties ribų, įskaitant potencialiai neskelbtinus Dynamics 365 Customer Insights duomenis, pvz., Asmens duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad "LiveRamp" atitiktų visus privatumo ar saugos įsipareigojimus, kuriuos galite turėti. Norėdami gauti daugiau informacijos, peržiūrėkite ["Microsoft" privatumo patvirtinimą](https://go.microsoft.com/fwlink/?linkid=396732). Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
