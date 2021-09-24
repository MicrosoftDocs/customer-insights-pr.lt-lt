---
title: Pradėkite naudotis auditorijos įžvalgų funkcija „Dynamics 365 Customer Insights”
description: Auditorijos įžvalgų pagalbos išteklių, skirtų greitam darbo pradėjimui, apžvalga.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466587"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Pradėkite naudotis „Dynamics 365 Customer Insights” auditorijos įžvalgų funkcija

Auditorijos įžvalgos gali padėti jums geriau suprasti klientus. Prijunkite duomenis iš įvairių operacijų, elgsenos ir stebėjimo šaltinių, kad sukurtumėte 360 laipsnių kliento rodinį. Naudokite šias įžvalgas, kad valdytumėte į klientus orientuotas funkcijas ir procesus. Suvienodinkite ir supraskite kliento duomenis ir pasitelkite juos protingoms įžvalgoms ir veiksmams.

## <a name="step-1-create-an-environment"></a>1 veiksmas: Aplinkos kūrimas

Pirmiausia turite sukurti aplinką, kurioje dirbsite. Jei jūsų organizacija jau įsigijo licenciją, skaitykite [Darbo su apmokėta prenumerata pradžia](get-started-paid.md). Norėdami pradėti auditorijos įžvalgų bandomąją versiją, skaitykite [Bandomosios versijos aplinkos nustatymas](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>2 veiksmas: Tyrinėkite auditorijos įžvalgas

Pirmą kartą prisijungę prie auditorijos įžvalgų galite konfigūruoti parametrus ir tyrinėti produktą.

1. [Prisijunkite prie auditorijos įžvalgų](https://home.ci.ai.dynamics.com) naudodami savo „Microsoft Azure Active Directory” (AAD) vartotojo paskyrą.

1. [Pakeiskite aplinką](manage-environments.md#switch-environments) tam, kad pamatytumėte demonstracinius duomenis ir [tyrinėtumėte auditorijos įžvalgas](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3 veiksmas: duomenų įtraukimas suvienodinimas ir ryšių nustatymas

Vieningieji profiliai yra pamatai, per kuriuos galima gauti įžvalgų ir atlikti veiksmus su duomenimis. Galite perkelti duomenis iš įvairių šaltinių ir vykdyti duomenų suvienodinimo procesą, kad būtų suderinti vieningieji profiliai. Nurodykite ryšius tarp įterptų objektų naudojamų papildymo funkcijų, kad į profilius įtrauktumėte informaciją. 

1. Įtraukite duomenis sukurdami duomenų šaltinius iš kelių parinkčių. Pasirinkite iš [„Power Query” jungčių](connect-power-query.md), [„Common Data Model” aplanko](connect-common-data-model.md) arba [„Microsoft Dataverse”](connect-common-data-service-lake.md). 

1. Vykdykite [duomenų suvienodinimo procesą](data-unification.md) pereidami per [susiejimo](map-entities.md), [sugretinimo](match-entities.md) ir [suliejimo](merge-entities.md) etapus.

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

1. Peržiūrėkite integravimo parinktis, pavyzdžiui, su [tiesioginiu ryšiu su įtraukimo įžvalgomis](../engagement-insights/integrate-audience-insights-engagement-insights.md) arba su kitomis „Dynamics 365” programomis kartu su [Kliento kortelės papildiniu](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
