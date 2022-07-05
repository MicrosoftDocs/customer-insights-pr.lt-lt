---
title: Valdykite vartotojo leidimus
description: Sužinokite apie leidimus ir vartotojo vaidmenis.
ms.date: 02/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: 30b37645cad4e795ef20579e20e3f2bbdb2afbf6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054886"
---
# <a name="manage-user-permissions"></a>Valdykite vartotojo leidimus

Teisių **puslapyje** nustatysite vaidmenis ir teises naudoti "Customer Insights".

Norėdami peržiūrėti puslapį, privalote turėti administratoriaus teises. Norėdami pasiekti teisių puslapį, eikite į **Administratoriaus** > **saugos** > **vartotojai**.

Yra trys vaidmenų tipai:

## <a name="viewer"></a>Žiūrintysis

- Naršykite įžvalgose ir segmentuose **Pagrindiniame puslapyje** ir **Segmentų** puslapyje.
- Ieškokite klientų profilių ir juos filtruokite naudodami puslapį **Klientai**. Laukai turi būti tinkami paieškai.
- Peržiūrėkite ir susipažinkite su puslapiu **Papildymas**.
- Naršykite ir eksportuokite objektus, naudodami puslapį **Objektai**.
- Peržiūrėkite sistemos procesų būseną naudodami puslapį **Sistema**.
- Eksportavimus peržiūrėkite puslapyje **Eksportavimai**.
- Diekite ir naudokite **„Power BI“ „Customer Insights“** ataskaitų sritį.

## <a name="contributor"></a>Dalyvis

- Žiūrinčiajam pasiekiamos visos teisės.
- Įkelkite ir transformuokite duomenis naudodami **Duomenų šaltinių** puslapį.
- Užbaigti ***Duomenų suvienijimą**, dėl kurio gaunamas vieningas kliento profilio objektas.
- Apibrėžkite **Ryšius** ir **Veiklas**.
- Sukurkite segmentus naudodami **Segmentų** puslapį.
- Kurkite matus naudodami puslapį **Matai**.
- Valdykite konfigūraciją ir papildykite klientų profilius iš puslapio **Papildymas** (tik pirmosios šalies papildymai).
- Tvarkykite ir kurkite eksportavimus pagal su bendradarbiais bendrinamus ryšius. [Sužinokite daugiau apie tai, kaip administratoriai leidžia bendradarbiams naudoti ryšį eksportavimui](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administravimas

- Dalyviui pasiekiamos visos teisės.
- Pakeiskite nustatymus **Sistemos** puslapyje, įskaitant darbo kalbą ir atnaujinkite grafikus jūsų sistemos procesuose.
- Peržiūrėkite ir įtraukite leidimus naudodami **Leidimų** puslapį.
- Nustatykite paieškos ir filtravimo sąvokas klientų puslapiui naudodami **Paieškos ir filtravimo turinio** puslapį (prieinamas per **Klientų** puslapį).
- Tvarkykite ryšius ir leiskite jais naudotis kitiems naudotojų vaidmenims puslapyje **Ryšiai**.
- Valdykite konfigūraciją ir papildykite klientų profilius iš puslapio **Papildymas** (visi papildymai).
- Tvarkykite ir kurkite eksportavimus puslapyje **Eksportavimai**.
- Įdiekite ir naudokite **Kliento kortelės papildinį**.
- Įtraukite ir naudokite **„Power Apps“ jungtį**.
- Įjunkite [„Customer Insights“ API naudojimą](apis.md).
- [Priskirkite aplinkos nuosavybę](manage-environments.md#change-the-owner-of-an-environment) kitam administratoriui.

## <a name="admin-owner"></a>Administratorius (savininkas)

- Visi administratoriaus turimi leidimai.
- [Iš naujo nustatykite ir ištrinkite](manage-environments.md#reset-an-existing-environment-preview) aplinką.

## <a name="assign-roles-and-permissions"></a>Vaidmenų ir teisių priskyrimas

1. Eikite į **administratoriaus** > **saugos** > **Vartotojai***.

1. Pasirinkite **Įtraukite vartotojus** siekiant atverti **Įtraukti/Redaguoti leidimus** juostą.

1. Naudokite lauką **Ieška**, kad surastumėte „Azure Active Directory“ vartotoją arba grupę, kurių teises norite koreguoti. Pasirinkite **Vaidmenį**, kurį norite priskirti vartotojui arba grupei.

1. Pasirinkite **Įrašyti**. Esama aplinka automatiškai bus bendrinama su vartotoju ar grupės nariais, kurios leidimus keitėte. Vartotojai gali pasiekti programą „Customer Insights“ ir veikti pagal nurodytą vaidmenį.

## <a name="view-current-permissions"></a>Dabartinių teisių peržiūra

Eikite į **administratoriaus** > **saugos** > **vartotojai** ir sužinokite, kokie vaidmenų priskyrimai šiuo metu yra aktyvūs.

- Stulpelyje **Tipas** nurodomas vienas vartotojas, grupė arba programa. Sistema palaiko atskirus vartotojus ir grupes.
- Vaidmenys nurodomi stulpelyje **Vaidmuo**.
- Pažymėkite bet kurį stulpelio pavadinimą, kad rezultatai būtų rikiuojami pagal šio stulpelio reikšmę.
- Naudodami puslapio viršuje esantį lauką **Ieška**, rasite konkrečius vartotojus.


[!INCLUDE [footer-include](includes/footer-banner.md)]
