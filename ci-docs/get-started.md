---
title: Darbo su „Dynamics 365 Customer Insights“ pradžia
description: "\"Customer Insights\" apžvalga padeda ištekliams greitai pradėti veiklą."
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741143"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Darbo su „Dynamics 365 Customer Insights“ pradžia

"Customer Insights" gali padėti jums giliau suprasti savo klientus. Prijunkite duomenis iš įvairių operacijų, elgsenos ir stebėjimo šaltinių, kad sukurtumėte 360 laipsnių kliento rodinį. Naudokite šias įžvalgas, kad valdytumėte į klientus orientuotas funkcijas ir procesus. Suvienodinkite ir supraskite kliento duomenis ir pasitelkite juos protingoms įžvalgoms ir veiksmams.

## <a name="step-1-create-an-environment"></a>1 veiksmas: Aplinkos kūrimas

Pirmiausia turite sukurti aplinką, kurioje dirbsite. Jei jūsų organizacija jau įsigijo licenciją, žr. [Aplinkos kūrimas](create-environment.md). Norėdami pradėti bandomąją "Customer Insights" versiją, žr [...](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2 veiksmas: susipažinkite su klientų įžvalgomis

Pirmą kartą prisijungę prie "Customer Insights", galite konfigūruoti parametrus ir naršyti produktą.

1. [prisijunkite prie "Customer Insights](https://home.ci.ai.dynamics.com) " naudodami savo "Microsoft" Azure Active Directory (AAD) vartotojo abonementą.

1. [Pakeiskite aplinką](manage-environments.md#switch-environments), kad pamatytumėte demonstracinius duomenis ir [ištirtumėte "Customer Insights"](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3 veiksmas: duomenų įtraukimas suvienodinimas ir ryšių nustatymas

Vieningieji profiliai yra pamatai, per kuriuos galima gauti įžvalgų ir atlikti veiksmus su duomenimis. Galite perkelti duomenis iš įvairių šaltinių ir vykdyti duomenų suvienodinimo procesą, kad būtų suderinti vieningieji profiliai. Nurodykite ryšius tarp įterptų objektų naudojamų papildymo funkcijų, kad į profilius įtrauktumėte informaciją.

1. Įtraukite duomenis sukurdami duomenų šaltinius iš kelių parinkčių. Pasirinkite jungtis [Power Query](connect-power-query.md), aplanką [...](connect-common-data-model.md)"Common Data Model" arba [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Paleiskite [duomenų suvienijimo procesą](data-unification.md) identifikuodami [šaltinio laukus](map-entities.md), pašalindami [dublikatus](remove-duplicates.md), [gretindami sąlygas](match-entities.md) ir [suvienodindami laukus](merge-entities.md).

1. Supažindinimas su [sistemos kuriamais objektais](entities.md) ir sukurkite [ryšius tarp įterptų objektų](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4 veiksmas: patobulinkite vieninguosius profilius naudodami prognozes, veiklas ir priemones

Nustatę vieninguosius profilius galite papildyti savo duomenis ir toliau didinti jų teikiamą informaciją.

1. Pasirinkite iš besiplečiančios papildymo teikėjų bibliotekos, kad [papildytumėte savo klientų duomenis](enrichment-hub.md).

1. Naudokite [visiškai parengtus modelius](predictions-overview.md), kad prognozuotumėte klientų praradimo tikimybę arba numatomas pajamas.

1. [Konfigūruokite veiklas](activities.md), pagrįstas įterptais duomenimis ir vizualizuokite sąveikas su klientais chronologinėje laiko planavimo juostoje.

1. [Kurkite priemones](measures.md), kad įvertintumėte savo verslo tikslus ir KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5 veiksmas: kurkite segmentus ir aktyvinkite duomenis naudodami įvairias eksportavimo parinktis

Dabar, kai jūsų duomenys yra baigti ir juose yra daug informacijos apie jūsų klientus, laikas ieškoti būdų atlikti veiksmus su tais duomenimis.

1. [Kurkite segmentus](segments.md), savo klientų bazės antrinius rinkinius, kad užtikrintumėte, jog jūsų veiksmai tinka tiksliniams klientams.

1. Naršykite besiplečiantį [eksportavimo parinkčių](export-destinations.md) katalogą, kuriame galite naudoti kliento duomenis. Pavyzdžiui, galite naudoti duomenis kampanijoms valdyti ir pasiekti klientus su skaitmenine rinkodara.

1. Peržiūrėkite integravimo parinktis, pvz., kitas "Dynamics 365" programas su ["Customer Card" priedu](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
