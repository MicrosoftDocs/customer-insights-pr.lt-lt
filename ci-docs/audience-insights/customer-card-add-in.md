---
title: Įdiegti ir konfigūruoti kliento kortelės papildinį
description: „Dynamics 365 Customer Insights“ kliento kortelės papildinio diegimas ir konfigūravimas.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268054"
---
# <a name="customer-card-add-in-preview"></a>Papildinys Kliento kortelė (peržiūra)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gaukite 360 laipsnių jūsų klientų rodinį tiesiogiai „Dynamics 365“ programose. Peržiūrėkite demografinius duomenis, įžvalgas ir veiklos laiko planavimo juostas naudodami papildinį Kliento kortelė.

## <a name="prerequisites"></a>Būtinosios sąlygos

- „Dynamics 365“ programa (pvz., pardavimo telkinys arba klientų aptarnavimo telkinys), 9.0 arba naujesnė versija su įjungta vieningąja sąsaja.
- Kliento profiliai [vartokite iš „Dynamics 365“ programos naudodami „Common Data Service“](connect-power-query.md).
- Kliento kortelės papildinio naudotojai turi būti [įtraukti kaip vartotojai](permissions.md) publikos įžvalgose.
- [Konfigūruokite paiešką ir filtruokite pajėgumus](search-filter-index.md).
- Demografijos valdymas: Demografijos laukeliai, tokie kaip amžius ar lytis yra prieinami suvienodintame kliento profilyje.
- Papildymo valdiklis: reikalingi aktyvieji [papildymai](enrichment-hub.md), pritaikyti klientų profiliams.
- Protingumo valdymas: Jam būtini duomenys sukurti su „Azure Machine Learning“ ([Nuspėjimais](predictions.md) ar [Tinkintais modeliais](custom-models.md))
- Priemonės valdymas: Jam būtinos [konfigūruotos priemonės](measures.md).
- Laiko juostos valdymas: Jam būtinos [konfigūruotos veiklos](activities.md).

## <a name="install-the-customer-card-add-in"></a>Kliento kortelės papildinio diegimas

Kliento kortelės papildinys yra sprendimas, skirtas „Dynamics 365 Customer Engagement“ programoms. Norėdami įdiegti sprendimą, eikite į „AppSource“ ir ieškokite **„Dynamics“ kliento kortelės**. Pasirinkite [papildinį Kliento kortelė svetainėje „AppSource“](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ir pasirinkite **Gauti dabar**.

Norint įdiegti sprendimą gali reikėti prisijungti naudojant „Dynamics 365“ programos administratoriaus kredencialus.

Sprendimo diegimas jūsų aplinkoje gali šiek tiek užtrukti.

## <a name="configure-the-customer-card-add-in"></a>Papildinio Kliento kortelė konfigūravimas

1. Kaip administratorius eikite „Dynamics 365“ skyrių **Parametrai** ir pasirinkite **Sprendimai**.

1. Pasirinkite sprendimo **„Dynamics 365 Customer Insights“ papildinys Kliento kortelė (peržiūra)** nuorodą **Rodomas pavadinimas**.

   > [!div class="mx-imgBorder"]
   > ![Rodomo pavadinimo pasirinkimas](media/select-display-name.png "Rodomo pavadinimo pasirinkimas")

1. Spustelėkite **Prisijungti** ir įveskite administratoriaus kliento, kurį naudojate „Customer Insights“ konfigūruoti, kredencialus.

   > [!NOTE]
   > Patikrinkite, ar naršyklės iššokančiųjų langų blokavimo programa neblokuoja autentifikavimo lango, kai pasirenkate mygtuką **Prisijungti**.

1. Pasirinkite aplinką, iš kurios reikia naudoti duomenis.

1. Nustatykite, kuris laukelių žemėlapis įrašomas į „Dynamics 365“ programą.
   - Norėdami sudaryti žemėlapį su kontaktu, pasirinkte laukelį kliento objekte, kuris atitinka jūsų kontakto objekto ID.
   - Norėdami sudaryti žemėlapį su paskyra, pasirinkte laukelį kliento objekte, kuris atitinka jūsų paskyros objekto ID.

   > [!div class="mx-imgBorder"]
   > ![„Kontakto ID laukas](media/contact-id-field.png "Kontakto ID laukas")

1. Pasirinkite **Įrašyti konfigūraciją**, kad įrašytumėte šiuos parametrus.

1. Tada reikės priskirti saugos vaidmenis „Dynamics 365“, kad vartotojai galėtų tinkinti ir matyti kliento kortelę. „Dynamics 365“ eikite į **Parametrai** > **Sauga** > **Vartotojai**. Pažymėkite vartotojus, kad redaguotumėte vartotojų vaidmenis, ir pasirinkite **Valdyti vaidmenis**.

1. Vartotojams, kurie tinkins kortelėje rodomą turinį visoje organizacijoje, priskirkite vaidmenį **„Customer Insights“ kortelės tinkintojas**.

## <a name="add-customer-card-controls-to-forms"></a>Įtraukite kliento kortelės valdiklius į formas
  
1. Norėdami kliento kortelės valdiklius įtraukti į savo kontakto formą, programoje „Dynamics 365“ eikite į **Parametrai** > **Tinkinimai**.

1. Pasirinkite **Tinkinti sistemą**.

1. Eikite į objektą **Kontaktas**, jį išplėskite ir pasirinkite **Formos**.

1. Pasirinkite kontakto formą, į kurią norite įtraukti kliento kortelės valdiklius.

    > [!div class="mx-imgBorder"]
    > ![Kontakto formos pasirinkimas](media/contact-active-forms.png "Kontakto formos pasirinkimas")

1. Norėdami įtraukti valdiklį, formų rengyklėje bet kurį lauką iš **Laukų naršyklės** vilkite į tą vietą, kurioje norite matyti demografinį valdiklį.

1. Formoje pažymėkite ką tik įtrauktą lauką, tada pasirinkite **Keisti ypatybes**.

1. Eikite į skirtuką **Valdikliai** ir pasirinkite **Įtraukti valdiklį**. Pasirinkite vieną iš galimų pasirinktinių valdiklių ir spustelėkite **Įtraukti**.

1. Dialogo lange **Lauko ypatybės** išvalykite žymės langelį **Rodyti žymą formoje**.

1. Pasirinkite valdiklio ypatybę **Žiniatinklis**. Naudodami papildymo valdiklį, pasirinkite norimą rodyti papildymo tipą, sukonfigūravę lauką **„enrichmentType“**. Įtraukite atskirą kiekvieno papildymo tipo gerinimo valdiklį.

1. Norėdami publikuoti atnaujintą kontakto formą, pasirinkite **Įrašyti** ir **Publikuoti**.

1. Eikite į publikuotą kontakto formą. Matysite naujai įtrauktą valdiklį. Naudojant jį pirmą kartą, jums gali reikėti prisijungti.

1. Norėdami tinkinti pasirinktiname valdiklyje rodomus duomenis, pasirinkite viršutiniame dešiniajame kampe esantį redagavimo mygtuką.

## <a name="upgrade-customer-card-add-in"></a>Atnaujinti kliento kortelės papildinį
Kliento kortelės papildymas automatiškai neatsijungia. Norėdami atnaujinti į naujausią versiją, atlikite šią procedūrą "Dynamics 365" programoje, kuri turi įdiegtą priedą.

1. Programoje "Dynamics 365" eikite į **Parametrai** > **Tinkinimas** ir pasirinkite **Sprendimai**.

1. Priedų lentelėje ieškokite **"CustomerInsightsCustomerCard"** ir pažymėkite eilutę.

1. Veiksmų juostroje pasirinkite **Taikyti sprendimo naujinimą**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atnaujinkite sprendimą "Dynamics 365" programų tinkinimo srityje":::

1. Pradėjus naujinimo procesą, matysite įkėlimo indikatorių, kol naujinimas bus baigtas. Jei nėra naujesnės versijos, atnaujinus bus rodomas klaidos pranešimas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]