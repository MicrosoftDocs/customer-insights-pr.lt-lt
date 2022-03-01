---
title: Bendrovės profilių praturtinimas su trečiosios šalies praturtinimo „Leadspace“
description: Bendra informacija apie „Leadspace“ trečiosios šalies praturtinimą.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668733"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Įmonių profilių papildymas su „Leadspace“ (peržiūra)

„Leadspace“ yra duomenų mokslo įmonė, teikianti B2B klientų duomenų platformą. Tai leidžia klientams su vieningais įmonių klientų profiliais papildyti savo duomenis. Praturtinimai apima papildomos atributus, tokius kaip bendrovės dydis, vieta, pramonė ir daugiau.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti „Leadspace“, turi būti tenkinamos šios būtinosios sąlygos:

- Turite aktyvią „Leadspace“ licenciją ir „nuolatinį raktą“ (vadinamą **„Leadspace“ žyma**). Susisiekite tiesiogiai su [„Leadspace“](https://www.leadspace.com/products/leadspace-on-demand/), norėdami gauti informacijos apie jų produktą.
- Turite [Administratoriaus](permissions.md#administrator) teises.
- Turite įmonių [vieningus klientų profilius](customer-profiles.md).

## <a name="configuration"></a>Konfigūracija

1. Publikos įžvalgose, eikite į **Duomenys** > **Praturtinimas**.

1. Pažymėkite **Papildyti mano duomenis** plytelėje „Leadspace“.

   :::image type="content" source="media/leadspace-tile.png" alt-text="„Leadspace“ plytos momentinė ekrano nuotrauka.":::

1. Pasirinkite **Pradėti** ir tada įveskite aktyvią **„Leadspace“ žymą** (nuolatinį raktą). Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**. Patvirtinkite abi įvestis pasirinkdami **Sujungti su „Leadspace“**.

1. Pasirinkite **Sukurti duomenų žemėlapį** ir nustatykite, kurie laukeliai iš jūsų suvienodintų profilių turi būti naudojami ieškoti atitinkančių bendrovės duomenų iš „Leadspace“. **Bendrovės pavadinimo** laukelis yra būtinas. Didesniam atitikties tikslumui, gali būti įtraukti ne daugiau du laukeliai **Bendrovės interneto svetainė** ir **Bendrovės vieta**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="„Leadspace“ laukelio žemėlapio sukūrimo juosta.":::
   
1. Pasirinkite **Taikyti** tam, kad užbaigtumėte laukelio žemėlapio kūrimą.

1. Pasirinkite **Vykdyti**, kad papildytumėte įmonės profilius. Kiek praturtinimas užtrunka priklauso nuo suvienodintų kliento profilių skaičiaus.

## <a name="enrichment-results"></a>Papildymo rezultatai

Atnaujinę papildymą naujai papildytus įmonės duomenis galite peržiūrėti dalyje [Mano papildymai](enrichment-hub.md). Galite rasti paskutinio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

Daugiau informacijos žr. [„Leadspace“ API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Leadspace“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Leadspace“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.