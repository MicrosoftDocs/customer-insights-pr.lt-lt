---
title: Pradėkite dirbti su „Dynamics 365 Customer Insights“
description: "\"Customer Insights\" apžvalga padeda ištekliams greitai pradėti darbą."
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304621"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Pradėkite dirbti su „Dynamics 365 Customer Insights“

"Customer Insights" gali padėti geriau suprasti savo klientus. Prijunkite duomenis iš įvairių operacijų, elgsenos ir stebėjimo šaltinių, kad sukurtumėte 360 laipsnių kliento rodinį. Naudokite šias įžvalgas, kad valdytumėte į klientus orientuotas funkcijas ir procesus. Suvienodinkite ir supraskite kliento duomenis ir pasitelkite juos protingoms įžvalgoms ir veiksmams.

## <a name="step-1-create-an-environment"></a>1 veiksmas: Aplinkos kūrimas

Pirmiausia sukurkite aplinką, kurioje galėtumėte dirbti. Jei jūsų organizacija jau įsigijo licenciją, žr. [Aplinkos kūrimas](create-environment.md). Norėdami pradėti bandomąją "Customer Insights" versiją, žiūrėkite [Bandomosios versijos aplinkos nustatymas](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2 veiksmas: susipažinkite su klientų įžvalgomis

Kai pirmą kartą prisijungiate prie "Customer Insights", konfigūruojate parametrus ir tyrinėjate produktą.

1. [prisijunkite prie "Customer Insights](https://home.ci.ai.dynamics.com) " naudodami savo "Microsoft" Azure Active Directory (AAD) vartotojo abonementą.

1. Pakeiskite aplinką, kad pamatytumėte demonstracinius duomenis ir [naršytumėte "Customer Insights"](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3 veiksmas: duomenų įtraukimas suvienodinimas ir ryšių nustatymas

Vieningieji profiliai yra pamatai, per kuriuos galima gauti įžvalgų ir atlikti veiksmus su duomenimis. Galite perkelti duomenis iš įvairių šaltinių ir vykdyti duomenų suvienodinimo procesą, kad būtų suderinti vieningieji profiliai. Nurodykite ryšius tarp nurijusių objektų ir naudokite papildymo funkcijas, kad įtrauktumėte informaciją į profilius.

1. Įtraukite duomenis sukurdami duomenų šaltinius iš kelių parinkčių. Pasirinkite, [Azure Data Lake Storage įskaitant "Common Data Model"](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), arba [Microsoft Dataverse](connect-dataverse-managed-lake.md)[Power Query jungtis](connect-power-query.md).

1. Vykdykite [duomenų suvienijimo procesą](data-unification.md) identifikuodami šaltinio [laukus](map-entities.md), pašalindami [dublikatus](remove-duplicates.md), [atitikdami sąlygas](match-entities.md) ir [suvienodindami laukus](merge-entities.md).

1. Supažindinimas su [sistemos kuriamais objektais](entities.md) ir sukurkite [ryšius tarp įterptų objektų](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4 veiksmas: patobulinkite vieninguosius profilius naudodami prognozes, veiklas ir priemones

Nustatę vieningus profilius, patobulinkite savo duomenis ir dar labiau padidinkite jų teikiamą informaciją.

1. Pasirinkite iš besiplečiančios papildymo teikėjų bibliotekos, kad [papildytumėte savo klientų duomenis](enrichment-hub.md).

1. Naudokite [visiškai parengtus modelius](predictions-overview.md), kad prognozuotumėte klientų praradimo tikimybę arba numatomas pajamas.

1. [Konfigūruokite veiklas](activities.md), pagrįstas įterptais duomenimis ir vizualizuokite sąveikas su klientais chronologinėje laiko planavimo juostoje.

1. [Kurkite priemones](measures.md), kad įvertintumėte savo verslo tikslus ir KPI.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5 veiksmas: kurkite segmentus ir aktyvinkite duomenis naudodami įvairias eksportavimo parinktis

Dabar, kai jūsų duomenys yra išsamūs ir juose yra daug informacijos apie klientus, ieškokite būdų, kaip imtis veiksmų su tais duomenimis.

1. [Kurkite segmentus](segments.md), savo klientų bazės antrinius rinkinius, kad užtikrintumėte, jog jūsų veiksmai tinka tiksliniams klientams.

1. Naršykite besiplečiantį [eksportavimo parinkčių](export-destinations.md) katalogą, kuriame galite naudoti kliento duomenis. Pavyzdžiui, galite naudoti duomenis kampanijoms valdyti ir pasiekti klientus su skaitmenine rinkodara.

1. Peržiūrėkite integravimo parinktis, pvz., į kitas "Dynamics 365" programas su [kliento kortelės papildiniu](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
