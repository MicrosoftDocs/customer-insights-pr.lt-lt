---
title: Bendrovės profilių praturtinimas su trečiosios šalies praturtinimo „Leadspace“
description: Bendra informacija apie „Leadspace“ trečiosios šalies praturtinimą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ca53f15bd7c71b3b4acb396c4daf52d7c7aff9eb
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954189"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Įmonių profilių papildymas su „Leadspace“ (peržiūra)

„Leadspace" yra duomenų šaltinių įmonė, kuri teikia B2B klientų duomenų platformą. Tai suteikia galimybę sąskaitoms papildyti naudojant vieningus klientų profilius, pagrįstus klientais. Praturtinkite *klientų profilius* atributais, pvz., įmonės dydžiu, vieta ar pramonės šaka. Praturtinkite *kontaktų profilius* naudodami atributus, pvz., pareigas, asmenį arba el. pašto tikrinimą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi "Leadspace" licencija.
- [Vieningi klientų profiliai pagal sąskaitas](customer-profiles.md).
- "Leadspace" [ryšį](connections.md)[konfigūruoja](#configure-the-connection-for-leadspace) administratorius. Norėdami gauti išsamios informacijos apie jų produktą, kreipkitės tiesiogiai į [„Leadspace“](https://www.leadspace.com/leadspace-microsoft-dynamics-365/).

## <a name="configure-the-connection-for-leadspace"></a>„Leadspace“ ryšio konfigūravimas

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti "nuolatinį raktą" (vadinamą **"Leadspace" atpažinimo ženklu**).

1. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje Švino sritis pasirinkite **Nustatyti**.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="„Leadspace“ ryšio konfigūravimo puslapis.":::

1. Įveskite ryšio pavadinimą ir tinkamą švino srities atpažinimo ženklą.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Leadspace“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Leadspace“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Praturtinti mano duomenis** **įmonės duomenų** iš "Leadspace" plytelės.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace plytos momentinė ekrano nuotrauka.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei jo nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti įmonės duomenimis iš "Leadspace". Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Nurodykite, kokio tipo laukus iš vieningų profilių naudoti gretinimui: pirminį ir (arba) antrinį adresą. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, namų adresui ir įmonės adresui. Pasirinkite **Toliau**.

1. Susiekite laukus su įmonės duomenimis iš "Leadspace". **Bendrovės pavadinimo** laukelis yra būtinas. Didesniam atitikties tikslumui, gali būti įtraukti ne daugiau du laukeliai **Bendrovės interneto svetainė** ir **Bendrovės vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace laukelio žemėlapio sukūrimo juosta.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Pažymėkite žymės langelį, jei turite *norimų papildyti* kontaktų profilių. "Customer Insights" automatiškai susies reikiamus laukus.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Galimų klientų srities kontaktų įrašų papildymas.":::

1. Pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Daugiau informacijos žr. [„Leadspace“ API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
