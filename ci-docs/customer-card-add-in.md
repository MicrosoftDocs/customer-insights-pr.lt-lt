---
title: "\"Dynamics 365\" programų (peržiūros versija) kliento kortelės papildinys (jame yra vaizdo įrašas)"
description: Rodyti klientų profilio duomenis iš "Customer Insights" "Dynamics 365" programose su šiuo papildiniu.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8b3b6a0d54b80d7df454e9dc925f14cc3c39684c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194933"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Kliento kortelės papildinys, skirtas "Dynamics 365" programoms (peržiūra)

Gaukite 360 laipsnių jūsų klientų rodinį tiesiogiai „Dynamics 365“ programose. Įdiegę kliento kortelės papildinį palaikomoje „Dynamics 365" programoje, galite pasirinkti rodyti klientų profilio laukus, įžvalgas ir veiklos laiko planavimo juostą. Papildinyje duomenys bus nuskaityti iš „Customer Insights” nepaveikiant duomenų prijungtoje „Dynamics 365” programoje.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Būtinosios sąlygos

- "Dynamics 365" modeliu pagrįstos programos, pvz., "Sales" arba "klientų aptarnavimas", 9.0 ir naujesnės versijos.
- Kad jūsų "Dynamics 365" duomenys būtų susieti su "Customer Insights" klientų profiliais, rekomenduojame juos [nuryti iš "Dynamics 365" programos naudojant jungtį Microsoft Dataverse](connect-power-query.md). Jei naudojate kitą metodą, kad nurytumėte "Dynamics 365" kontaktus (arba abonementus), įsitikinkite, kad `contactid` laukas (arba `accountid`) nustatytas kaip [pagrindinis tos duomenų šaltinis raktas duomenų suvienijimo proceso metu](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Visi "Dynamics 365" kliento kortelės papildinio vartotojai turi būti [įtraukti kaip "Customer Insights" vartotojai](permissions.md), kad matytų duomenis.
- [Sukonfigūruotos ieškos ir filtro galimybės](search-filter-index.md) „Customer Insights“.
- Kiekvienas papildinio valdiklis priklauso nuo konkrečių "Customer Insights" duomenų. Kai kuriuos duomenis ir valdiklius galima naudoti tik konkrečių tipų aplinkose. Papildinio konfigūracija informuos jus, jei valdiklis nepasiekiamas dėl pasirinkto aplinkos tipo. Sužinokite daugiau apie [aplinkos naudojimo atvejus](work-with-business-accounts.md).
  - **Matų kontrolei** reikia [sukonfigūruotų kliento atributų matų](measures.md).
  - **Intelekto valdiklis** reikalauja duomenų, sugeneruotų naudojant [prognozes arba pasirinktinius modelius](predictions-overview.md).
  - **Kliento išsamios informacijos valdiklis** rodo visus laukus iš profilio, pasiekiamo vieningame kliento profilyje.
  - **Sodrinimo kontrolei** reikia aktyvių [papildymų](enrichment-hub.md), taikomų klientų profiliams. Kortelės papildinys palaiko šiuos papildymus: ["Microsoft" teikiami prekių ženklai](enrichment-microsoft.md), ["Microsoft" teikiami pomėgiai](enrichment-microsoft.md) ir ["Microsoft" pateikti "Office" įtraukimo duomenys](enrichment-office.md).
  - **Kontaktų valdymui** reikalingas kontakto semantinio objekto tipas.
  - **Laiko planavimo juostos valdymui** reikia [sukonfigūruotų veiklų](activities.md).

## <a name="install-the-customer-card-add-in"></a>Kliento kortelės papildinio diegimas

Kliento kortelės papildinys yra sprendimas, skirtas „Dynamics 365” platformos „Customer Engagement” programoms. Norėdami įdiegti sprendimą:

1. Eikite į AppSource "Dynamics Customer Card" ir ieškokite **jos.**

1. Pasirinkite [papildinį Kliento kortelė svetainėje „AppSource“](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ir pasirinkite **Gauti dabar**.

Norint įdiegti sprendimą gali reikėti prisijungti naudojant „Dynamics 365“ programos administratoriaus kredencialus. Sprendimo diegimas jūsų aplinkoje gali šiek tiek užtrukti.

## <a name="configure-the-customer-card-add-in"></a>Papildinio Kliento kortelė konfigūravimas

1. Kaip administratorius eikite „Dynamics 365“ skyrių **Parametrai** ir pasirinkite **Sprendimai**.

1. Pasirinkite sprendimo **„Dynamics 365 Customer Insights“ papildinys Kliento kortelė (peržiūra)** nuorodą **Rodomas pavadinimas**.

   > [!div class="mx-imgBorder"]
   > ![Rodomo pavadinimo pasirinkimas.](media/select-display-name.png "Rodomo pavadinimo pasirinkimas.")

1. Spustelėkite **Prisijungti** ir įveskite administratoriaus kliento, kurį naudojate „Customer Insights“ konfigūruoti, kredencialus.

   > [!NOTE]
   > Patikrinkite, ar naršyklės iššokančiųjų langų blokavimo programa neblokuoja autentifikavimo lango, kai pasirenkate mygtuką **Prisijungti**.

1. Pasirinkite „Customer Insights“ aplinką, iš kurios norite iškviesti duomenis.

1. Apibrėžkite laukų susiejimą su įrašais „Dynamics 365” programoje. Atsižvelgdami į jūsų „Customer Insights“ duomenis, galite pasirinkti susieti toliau pateiktas parinktis:
   - Norėdami sudaryti žemėlapį su kontaktu, pasirinkite laukelį kliento objekte, kuris atitinka jūsų kontakto objekto ID.
   - Norėdami sudaryti žemėlapį su paskyra, pasirinkite laukelį kliento objekte, kuris atitinka jūsų paskyros objekto ID.

   > [!div class="mx-imgBorder"]
   > ![Kontakto ID laukas.](media/contact-id-field.png "Kontakto ID laukas.")

1. Pasirinkite **Įrašyti konfigūraciją**, kad įrašytumėte šiuos parametrus.

1. Tada reikės priskirti saugos vaidmenis „Dynamics 365“, kad vartotojai galėtų tinkinti ir matyti kliento kortelę. „Dynamics 365“ eikite į **Parametrai** > **Sauga** > **Vartotojai**. Pažymėkite vartotojus, kad redaguotumėte vartotojų vaidmenis, ir pasirinkite **Valdyti vaidmenis**.

1. Vartotojams, kurie tinkins kortelėje rodomą turinį visoje organizacijoje, priskirkite vaidmenį **„Customer Insights“ kortelės tinkintojas**.

## <a name="add-customer-card-controls-to-forms"></a>Įtraukite kliento kortelės valdiklius į formas

Atsižvelgdami į savo scenarijų, galite įtraukti valdiklius į **Kontakto** formą ar **Kliento** formą. Jei jūsų "Customer Insights" aplinka skirta verslo paskyroms, rekomendavome įtraukti valdiklius į formą Paskyra. Tokiu atveju toliau pateikiamuose žingsniuose pakeiskite „kontaktą" į „paskyrą."

1. Norėdami kliento kortelės valdiklius įtraukti į savo kontakto formą, programoje „Dynamics 365“ eikite į **Parametrai** > **Tinkinimai**.

1. Pasirinkite **Tinkinti sistemą**.

1. Eikite į objektą **Kontaktas**, jį išplėskite ir pasirinkite **Formos**.

1. Pažymėkite kontakto formą, į kurią norite įtraukti kliento kortelės valdiklius.

    > [!div class="mx-imgBorder"]
    > ![Kontakto formos pasirinkimas.](media/contact-active-forms.png "Kontakto formos pasirinkimas.")

1. Norėdami įtraukti valdiklį, formų rengyklėje bet kurį lauką iš **Laukų naršyklės** vilkite į tą vietą, kurioje norite matyti demografinį valdiklį.

1. Formoje pažymėkite ką tik įtrauktą lauką, tada pasirinkite **Keisti ypatybes**.

1. Eikite į skirtuką **Valdikliai** ir pasirinkite **Įtraukti valdiklį**. Pasirinkite vieną iš galimų pasirinktinių valdiklių ir spustelėkite **Įtraukti**.

1. Dialogo lange **Lauko ypatybės** išvalykite žymės langelį **Rodyti žymą formoje**.

1. Pasirinkite valdiklio ypatybę **Žiniatinklis**. Naudodami papildymo valdiklį, pasirinkite norimą rodyti papildymo tipą, sukonfigūravę lauką **„enrichmentType“**. Įtraukite atskirą kiekvieno papildymo tipo gerinimo valdiklį.

1. Norėdami publikuoti atnaujintą kontakto formą, pasirinkite **Įrašyti** ir **Publikuoti**.

1. Eikite į publikuotą kontakto formą. Matysite naujai įtrauktą valdiklį. Naudojant jį pirmą kartą, jums gali reikėti prisijungti.

1. Norėdami tinkinti pasirinktiname valdiklyje rodomus duomenis, pasirinkite viršutiniame dešiniajame kampe esantį redagavimo mygtuką.

## <a name="upgrade-customer-card-add-in"></a>Atnaujinti kliento kortelės papildinį

Kliento kortelės papildymas automatiškai neatsijungia. Norėdami atnaujinti į naujausią versiją, atlikite šiuos veiksmus „Dynamics 365" programoje, prie kurios yra įdiegtas priedas.

1. Programoje „Dynamics 365” eikite į **Parametrai** > **Tinkinimas** ir pasirinkite **Sprendimai**.

1. Priedų lentelėje ieškokite **CustomerInsightsCustomerCard** ir pažymėkite eilutę.

1. Veiksmų juostoje pasirinkite **Taikyti sprendimo naujinimą**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atnaujinkite sprendimą „Dynamics 365“ programų tinkinimo srityje.":::

1. Pradėjus naujinimo procesą, matysite įkėlimo indikatorių, kol naujinimas bus baigtas. Jei nėra naujesnės versijos, atnaujinus bus rodomas klaidos pranešimas.

## <a name="troubleshooting"></a>Trikčių šalinimas

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Valdikliai iš kliento kortelės papildinio nerasti duomenų

**Problema:**

Net ir teisingai sukonfigūravus ID laukus, valdikliai negali rasti jokio kliento duomenų.  

**Sprendimas.**

1. Įsitikinkite, kad sukonfigūravote kortelės papildinį pagal instrukcijas: [Kliento kortelės papildinio konfigūravimas](#configure-the-customer-card-add-in)

1. Peržiūrėkite duomenų gavimo konfigūraciją. Redaguokite "Dynamics 365" sistemos, kurioje yra kontakto ID GUID, duomenų šaltinis. Jei kontakto ID GUID redaktoriuje Power Query rodomas didžiosiomis raidėmis, pabandykite atlikti šiuos veiksmus:
    1. Redaguokite duomenų šaltinis, kad atidarytumėte duomenų šaltinis redaktoriuje Power Query.
    1. Pasirinkite kontaktų ID stulpelį.
    1. Antraštės juostoje pasirinkite **Transformuoti**, kad pamatytumėte galimus veiksmus.
    1. Pasirinkite **mažąsias raides**. Patikrinkite, ar lentelėje esantys GUID dabar rašomi mažosiomis raidėmis.
    1. Įrašykite duomenų šaltinį.
    1. Paleiskite duomenų nurijimo, suvienijimo ir pasroviui procesus, kad skleistumėte GUID pakeitimus.

Kai sistema baigs visą atnaujinimą, kliento kortelės papildinio valdikliuose turėtų būti rodomi laukiami duomenys.

[!INCLUDE [footer-include](includes/footer-banner.md)]