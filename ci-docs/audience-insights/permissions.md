---
title: Valdykite vartotojo leidimus
description: Sužinokite apie leidimus ir vartotojo vaidmenis.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689230"
---
# <a name="user-permissions"></a>Vartotojų teisės

**Leidimai** puslapis yra ten, kur nustatysite vaidmenis ir leidimus publikos įžvalgų naudojimui.

Norėdami peržiūrėti puslapį, privalote turėti administratoriaus teises. Norėdami patekti į leidimų puslapį publikos įžvalgose, eikite į **Administravimas** > **Leidimai**.

Yra trys vaidmenų tipai:

## <a name="viewer"></a>Žiūrintysis

- Naršyktie įžvalgose ir segmentuose **Pagrindiniame puslapyje** ir **Segmentų** puslapyje.
- Ieškokite klientų profilių ir juos filtruokite naudodami puslapį **Klientai**. Laukai turi būti tinkami paieškai.
- Peržiūrėkite ir susipažinkite su puslapiu **Papildymas**.
- Naršykite ir eksportuokite objektus, naudodami puslapį **Objektai**.
- Peržiūrėkite sistemos procesų būseną naudodami puslapį **Sistema**.
- Eksportuokite segmentus iš **Segmentų** puslapio.
- Diekite ir naudokite **„Power BI“ „Customer Insights“** ataskaitų sritį.

## <a name="contributor"></a>Bendradarbis

- Žiūrinčiajam pasiekiamos visos teisės.
- Įkelkite ir transformuokite duomenis naudodami **Duomenų šaltinių** puslapį.
- Užbaikite *Duomenų suvienodinimo* skyrius (**Žemėlapis**, **Atitiktis** ir **Suliejimas**), kuris yra suvienodinto kliento profilio objekte.
- Apibrėžkite **Ryšius** ir **Veiklas**.
- Sukurkite segmentus naudodami **Segmentų** puslapį.
- Kurkite matus naudodami puslapį **Matai**.
- Valdykite konfigūraciją ir papildykite klientų profilius iš puslapio **Papildymas** (tik pirmosios šalies papildymai).

## <a name="administrator"></a>Administratorius

- Dalyviui pasiekiamos visos teisės.
- Pakeiskite nustatymus **Sistemos** puslapyje, įskaitant darbo kalbą ir atnaujinkite grafikus jūsų sistemos procesuose.
- Peržiūrėkite ir įtraukite leidimus naudodami **Leidimų** puslapį.
- Nustatykite paieškos ir filtravimo sąvokas klientų puslapiui naudodami **Paieškos ir filtravimo turinio** puslapį (prieinamas per **Klientų** puslapį).
- Apibrėžkite „Dynamics 365 Sales“ segmento paskirtis, naudodami puslapį **Eksportavimo paskirties vietos**.
- Valdykite konfigūraciją ir papildykite klientų profilius iš puslapio **Papildymas** (visi papildymai).
- Įdiekite ir naudokite **Kliento kortelės papildinį**.
- Įtraukite ir naudokite **„Power Apps“ jungtį**.
- Įjunkite [„Customer Insights“ API naudojimą](apis.md).

## <a name="assign-roles-and-permissions"></a>Vaidmenų ir teisių priskyrimas

1. Publikos įžvalgose, eikite į **Administratorius** > **Leidimai**.

1. Pasirinkite **Įtraukite vartotojus** siekiant atverti **Įtraukti/Redaguoti leidimus** juostą.

1. Naudokite lauką **Ieška**, kad surastumėte „Azure Active Directory“ vartotoją arba grupę, kurių teises norite koreguoti. Pasirinkite **Vaidmenį**, kurį norite priskirti vartotojui arba grupei.

1. Pasirinkite **Įrašyti**. Esama aplinka automatiškai bus bendrinama su vartotoju ar grupės nariais, kurios leidimus keitėte. Vartotojai gali pasiekti programą „Customer Insights“ ir veikti pagal nurodytą vaidmenį.

## <a name="view-current-permissions"></a>Dabartinių teisių peržiūra

Publikos įžvalgose eikite į **Administratorius** > **Leidimai** tam, kad pažiūrėtumėte, kokie vaidmens priskyrimai šiuo metu yra įjungti.

- Stulpelyje **Tipas** nurodomas vienas vartotojas, grupė arba programa. Sistema palaiko atskirus vartotojus ir grupes.
- Vaidmenys nurodomi stulpelyje **Vaidmuo**.
- Pažymėkite bet kurį stulpelio pavadinimą, kad rezultatai būtų rikiuojami pagal šio stulpelio reikšmę.
- Naudodami puslapio viršuje esantį lauką **Ieška**, rasite konkrečius vartotojus.