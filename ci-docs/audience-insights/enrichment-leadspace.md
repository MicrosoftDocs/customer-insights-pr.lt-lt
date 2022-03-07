---
title: Bendrovės profilių praturtinimas su trečiosios šalies praturtinimo „Leadspace“
description: Bendra informacija apie „Leadspace“ trečiosios šalies praturtinimą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305212"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Įmonių profilių papildymas su „Leadspace“ (peržiūra)

„Leadspace“ yra duomenų mokslo įmonė, teikianti B2B klientų duomenų platformą. Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis. Papildymai apima daugiau atributų, pvz., įmonės dydį, vietą, pramonės šaką ir daugiau.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti „Leadspace“, turi būti tenkinamos šios būtinosios sąlygos:

- Turite aktyvią „Leadspace“ licenciją.
- Turite įmonių [vieningus klientų profilius](customer-profiles.md).
- „LeadSpace“ ryšį jau sukonfigūravo administratorius arba turite [administratoriaus](permissions.md#administrator) teises bei „neribotą raktą“ (vadinamą **„LeadSpace“ atpažinimo ženklu**). Norėdami gauti išsamios informacijos apie jų produktą, kreipkitės tiesiogiai į [„Leadspace“](https://www.leadspace.com/products/leadspace-on-demand/).

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.

1. „Leadspace“ plytelėje pasirinkite **Papildyti mano duomenis** ir pasirinkite **Darbo pradžia**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace plytos momentinė ekrano nuotrauka.":::

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, ryšį galite sukurti pasirinkdami **Pridėti ryšį** ir **„Leadspace“**. 

1. Norėdami patvirtinti ryšį pasirinkite **Prisijungti prie „Leadspace“**.

1. Pasirinkite **Toliau** ir pasirinkite **Kliento duomenų rinkinys**, kurį norite papildyti įmonės duomenimis iš „Leadspace“. Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Pažymėkite **Toliau** ir apibrėžkite, kurie laukeliai iš vieningųjų profilių naudojami ieškant sutampančių įmonės duomenų iš „Leadspace“. **Bendrovės pavadinimo** laukelis yra būtinas. Didesniam atitikties tikslumui, gali būti įtraukti ne daugiau du laukeliai **Bendrovės interneto svetainė** ir **Bendrovės vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace laukelio žemėlapio sukūrimo juosta.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Nurodykite papildymo pavadinimą ir peržiūrėję pasirinkimus pažymėkite **Išsaugoti papildymą**.


## <a name="configure-the-connection-for-leadspace"></a>„Leadspace“ ryšio konfigūravimas 

Jei norite konfigūruoti ryšius, turite būti administratorius. Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir plytelėje „Leadspace“ pasirinkite **Sąranka**.

1. Pasirinkite **Darbo pradžia**. 

1. Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Nurodykite galiojantį „Leadspace“ atpažinimo ženklą.

1. Pasirinkdami Sutinku, peržiūrėkite **ir pateikite savo sutikimą dėl** duomenų privatumo ir sąlygų **sutinku**.

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigę patikrinimą pasirinkite **Išsaugoti**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="„Leadspace“ ryšio konfigūravimo puslapis.":::

## <a name="enrichment-results"></a>Papildymo rezultatai

Atnaujinę papildymą naujai papildytus įmonės duomenis galite peržiūrėti dalyje [Mano papildymai](enrichment-hub.md). Galite rasti paskutinio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

Daugiau informacijos žr. [„Leadspace“ API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Leadspace“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Leadspace“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
