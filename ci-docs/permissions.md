---
title: Vartotojo teisių priskyrimas
description: Sužinokite apie leidimus ir vartotojo vaidmenis.
ms.date: 08/08/2022
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
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245429"
---
# <a name="assign-user-permissions"></a>Vartotojo teisių priskyrimas

Prieiga prie "Customer Insights" suteikiama tik jūsų organizacijos vartotojams, kuriuos administratorius įtraukia į programą. Administratorius gali pridėti, redaguoti arba pašalinti vartotojus. Vartotojas gali būti vienas vartotojas, grupė arba programa. Yra trijų tipų vaidmenys, kuriuos gali turėti vartotojas:

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
- Visiškas **duomenų suvienijimas**, dėl kurio gaunamas suvienodintas kliento profilio objektas.
- Apibrėžkite **Ryšius** ir **Veiklas**.
- Sukurkite segmentus naudodami **Segmentų** puslapį.
- Kurkite matus naudodami puslapį **Matai**.
- Valdykite konfigūraciją ir papildykite klientų profilius iš puslapio **Papildymas** (tik pirmosios šalies papildymai).
- Valdykite ir kurkite eksportavimą [pagal ryšius, bendrinamus su bendraautoriais](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administratorius

- Dalyviui pasiekiamos visos teisės.
- Keiskite parametrus **puslapyje Sistema**, įskaitant darbo kalbą, atnaujinkite sistemos procesų tvarkaraščius ir eksportuokite diagnostikos žurnalus.
- Pakeiskite parametrus **saugos** puslapyje, įskaitant vartotojus, API raktus, privačias nuorodas ir raktų saugyklą.
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

## <a name="add-users"></a>Įtraukti vartotojus

1. Eikite į **administratoriaus** > **sauga** ir pasirinkite skirtuką **Vartotojai**.

1. Pasirinkite **Įtraukite vartotojus** siekiant atverti **Įtraukti/Redaguoti leidimus** juostą.

1. Naudokite ieškos **lauką**, kad rastumėte vartotoją arba grupę, Azure Active Directory kurią norite įtraukti. Pasirinkite **Vaidmenį**, kurį norite priskirti vartotojui arba grupei.

1. Pasirinkite **Įrašyti**. Dabartinė aplinka automatiškai bendrinama su vartotoju arba grupės nariais. Vartotojai gali pasiekti programą „Customer Insights“ ir veikti pagal nurodytą vaidmenį.

## <a name="view-current-permissions"></a>Dabartinių teisių peržiūra

Eikite į **Administratoriaus** > **sauga** ir pasirinkite skirtuką **Vartotojai**, kad peržiūrėtumėte aktyvių vartotojų ir jų vaidmenų priskyrimų sąrašą. Galite rūšiuoti vartotojų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte konkretų vartotoją.

## <a name="manage-current-users"></a>Dabartinių vartotojų valdymas

Eikite į **administratoriaus** > **sauga** ir pasirinkite skirtuką **Vartotojai** . Galite rūšiuoti vartotojų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte vartotoją, kurį norite tvarkyti.

Pasirinkite vartotoją, kad peržiūrėtumėte galimus veiksmus.

- **Redaguokite**, kad redaguotumėte vartotojo vaidmenį programoje "Customer Insights". Pasirinkite **Išsaugoti**, kad patvirtintumėte pakeitimą.
- **Pašalinkite**, kad pašalintumėte vartotoją iš prieigos prie "Customer Insights". Pasirinkite **Naikinti** naikinimo patvirtinimui.

[!INCLUDE [footer-include](includes/footer-banner.md)]
