---
title: Praturtinkite įmonės profilius naudodami "Leadspace" (peržiūra)
description: Bendra informacija apie „Leadspace“ trečiosios šalies praturtinimą.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f45fabc036775e11fc439f69513678d0607729d0
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237960"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Praturtinkite įmonės profilius naudodami "Leadspace" (peržiūra)

„Leadspace" yra duomenų šaltinių įmonė, kuri teikia B2B klientų duomenų platformą. Tai suteikia galimybę sąskaitoms papildyti naudojant vieningus klientų profilius, pagrįstus klientais. Praturtinkite *klientų profilius* atributais, pvz., įmonės dydžiu, vieta ar pramonės šaka. Praturtinkite *kontaktų profilius* naudodami atributus, pvz., pareigas, asmenį arba el. pašto tikrinimą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "Leadspace" licencija.
- [Vieningi klientų profiliai](customer-profiles.md), pagrįsti paskyromis.
- "Leadspace" [ryšį](connections.md)[sukonfigūruoja](#configure-the-connection-for-leadspace) administratorius. Norėdami gauti išsamios informacijos apie jų produktą, kreipkitės tiesiogiai į [„Leadspace“](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>„Leadspace“ ryšio konfigūravimas

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti "nuolatinį raktą" (vadinamą **"Leadspace" prieigos raktu**).

1. Konfigūruojant papildymą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir **pasirinkite Nustatyti** "Leadspace" plytelėje.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="„Leadspace“ ryšio konfigūravimo puslapis.":::

1. Įveskite ryšio pavadinimą ir galiojantį "Leadspace" prieigos raktą.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis** įmonės duomenys **iš**"Leadspace" plytelės.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace plytos momentinė ekrano nuotrauka.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei ryšio nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti įmonės duomenimis iš "Leadspace". *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Apibrėžkite, kokio tipo laukus iš savo vieningųjų profilių naudoti atitikčiai: pirminį ir (arba) antrinį adresą. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, namų ir įmonės adreso atveju. Pasirinkite **Toliau**.

1. Susiekite savo laukus su įmonės duomenimis iš "Leadspace". **Bendrovės pavadinimo** laukelis yra būtinas. Didesniam atitikties tikslumui, gali būti įtraukti ne daugiau du laukeliai **Bendrovės interneto svetainė** ir **Bendrovės vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace laukelio žemėlapio sukūrimo juosta.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Pažymėkite žymės langelį, jei turite *norimų papildyti* kontaktų profilių. "Customer Insights" automatiškai susies reikiamus laukus.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Galimų klientų srities kontaktų įrašų papildymas.":::

1. Pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Daugiau informacijos žr. [„Leadspace“ API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]