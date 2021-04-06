---
title: Žiniatinklio duomenų integravimas su įtraukimo įžvalgomis auditorijų apžvalgoje
description: Galite pateikti klientų žiniatinklio informaciją nuo įtraukimo įžvalgų iki auditorijos įžvalgų.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597475"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Žiniatinklio duomenų integravimas su įtraukimo įžvalgomis auditorijų apžvalgoje

Klientai dažnai kasdien pavedimus atlieka internetu, naudodami interneto svetaines. Įtraukimo įžvalgų galimybė, esanti „Dynamics 365 Customer Insights”, yra patogus sprendimas integruoti žiniatinklio duomenis kaip šaltinį. Be operacijų, demografinių ar elgsenos duomenų veiklą žiniatinklyje galime matyti vieninguose klientų profiliuose. Šį profilį naudojame norėdami gauti papildomų įžvalgų, pvz. segmentų, priemonių ar auditorijos suaktyvinimo prognozių.

Šiame straipsnyje aprašomi veiksmai, kurių reikia norint klientų žiniatinklio veiklos duomenis pateikti iš įtraukimo įžvalgų į esamą auditorijos įžvalgų aplinką.

Šiame pavyzdyje tarkime, kad aplinkoje yra vieningų klientų profilių. Profiliai buvo suvienodinti su apklausų, mažmeninės prekybos ir bilietų pardavimo sistemos šaltiniais. Čia taip pat rodoma susijusi klientų veikla. 

Dabar norėtume žinoti, ar klientas lankosi mūsų žiniatinklio ypatybėse ir supranta jų veiklą. Veiklos apima, pvz.: peržiūrėtus produktų puslapius iš el. paštu gautų saitų arba peržiūrėtus produktų puslapius.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint integruoti duomenis iš įtraukimo įžvalgų, reikia įvykdyti kelias būtinąsias sąlygas: 

- Integruokite įtraukimo įžvalgų SDK į svetainę. Daugiau informacijos [žr. Darbo su žiniatinklio SDK pradžia](../engagement-insights/instrument-website.md).
- Norint eksportuoti žiniatinklio įvykius iš įtraukimo įžvalgų, būtina prieiga prie „ADLS Gen 2” saugyklos paskyros, kuri bus naudojama žiniatinklio įvykių duomenims perteikti į auditorijos įžvalgas. Daugiau informacijos ieškokite [Terminų atnaujinimas](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Patobulintos įvykių konfigūravimas įtraukimo įžvalgose

Kai administratorius perkodavo svetainę su įtraukimo įžvalgų SDK, *pagrindiniai įvykiai* surenkami vartotojui peržiūrėjus tinklalapį arba kur nors spustelėjus. Pagrindiniai įvykiai pateikia išsamią informaciją. Atsižvelgiant į naudojimo atvejį, jums reikalingas tik pagrindinio įvykio duomenų antrinis rinkinys. Naudodami įtraukimo įžvalgas galite kurti *tobulintinus įvykius*, kuriuose yra tik jūsų pasirinkto pagrindinio įvykio ypatybės.     

Daugiau informacijos ieškokite [Patobulintos įvykių kūrimas ir modifikavimas](../engagement-insights/refined-events.md).

Aspektai kuriant tobulintinus įvykius: 

- Teikia prasmingą patikslintame įvykyje pavadinimą. Jis naudojamas kaip veiklos pavadinimas auditorijos įžvalgose.
- Jei norite kurti veiklą auditorijos įžvalgose, pasirinkite bent šias ypatybes: 
    - Signal.Action.Name – išsami veiklos informacija
    - Signal.User.Id – naudojama susieti su kliento ID
    - Signal.View.Uri – naudojamas kaip žiniatinklio adresas kaip segmentų arba priemonių pagrindas
    - Signal.Export.Id – naudojamas kaip pirminis įvykių raktas <!-- system generated, do we need to list?-->
    - Signal.Timestamp – veiklos datai ir laikui nustatyti

Pažymėkite filtrus, sufokusuojamus į įvykius ir puslapius, kurie susiję su jūsų naudojimo atveju. Šiame pavyzdyje naudosime veiksmo pavadinimą „El. pašto reklama”.

## <a name="export-the-refined-web-events"></a>Patobulintas žiniatinklio įvykių eksportavimas 

Apibrėžę patobulintą įvykį turite sukonfigūruoti įvykio duomenų eksportavimą, kuriame galima nustatyti duomenų šaltinio auditorijos įžvalgų Azure Data Lake Storage auditorijos įžvalgose. Iš žiniatinklio ypatybės nuolat eksportuojama kaip įvykiai.

Daugiau informacijos ieškokite [Terminų atnaujinimas](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Pereidami įvykių duomenis prie auditorijos įžvalgų

Dabar, kai apibrėšite patobulintą įvykį ir sukonfigūravote jo eksportavimą, pereisime prie duomenų įkėlimo į auditorijos įžvalgas. Turite sukurti naują duomenų šaltinį pagal aplanką „Įprastas duomenų modelis”. Įveskite saugyklos, į kurią eksportuojate įvykius, išsamią informaciją. *default.cdm.json* faile pažymėkite patobulintą įvykį ir sukurkite objektą auditorijos įžvalgose.

Daugiau informacijos žr. [Prisijungimas prie bendro duomenų modelio aplanko naudojant „Azure Data Lake” paskyrą](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Patobulinti įvykių duomenys susieti su kliento profilio veikla

Papildę objektą galite sukonfigūruoti kliento profilio veiklą.

Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Veiklos puslapis su išplėsta veiklos redagavimo sritimi ir laukais.":::

Sukonfigūruokite naują veiklą naudodami šį susiejimą: 

- **Pirminis raktas:** Signal.Export.Id– unikalus ID, pasiekiamas kiekvienam įvykio įrašui įtraukimo įžvalgų metu. Ši ypatybė generuojama automatiškai.

- **Laiko žyma:** įvykio ypatybės signalo laiko žyma.

- **Įvykis**: Signal.Name, norimo naudoti įvykio pavadinimas.

- **Žiniatinklio adresas:** Signal.View.Uri nurodantis įvykį sukūrusio puslapio uri.

- **Išsami informacija**: Signal.Action.Name pateikti informaciją, susijusią su įvykiu. Pažymėta ypatybė tokiu atveju nurodo, kad įvykis skirtas el. pašto reklamai.

- **Veiklos tipas:** šiame pavyzdyje pasirinkite esantį veiklos tipą „WebLog”. Šis pasirinkimas yra naudinga filtro parinktis, norint prognozė modelius ar kurti segmentus pagal šį veiklos tipą.

- **Ryšio nustatymas:** šiuo svarbiu parametru veikla susijusi su esamais klientų profiliais. **Signal.User.Id** yra identifikatorius, sukonfigūruotas SDK, kurį reikia rinkti ir kuris susijęs su vartotojo ID kituose duomenų šaltiniuose, sukonfigūruotuose auditorijos įžvalgose. Šiame pavyzdyje konfigūruojame ryšį tarp „Signal.User.Id” ir „RetailCustomers:CustomerRetailId”, kuris yra pirminis raktas, deinfeduotas duomenų suvienodinimo proceso struktūros žingsnyje.


Apdorojus veiklas galite peržiūrėti klientų įrašus ir atidaryti kliento korteles, kad veiklas peržiūrėtumėte iš įtraukimo įžvalgų laiko planavimo juostoje. 

> [!TIP]
> Norėdami rasti kliento ID, kuriame yra įtraukimo įžvalgų veikla, eikite į **Objektai** ir peržiūrėkite objekto UnifiedActivity duomenis. ActivityTypeDisplay = „WebLog” yra įtraukimo įžvalgų veikla, sukonfigūruota aukščiau pateiktame pavyzdyje. Nukopijuokite vieno iš šių įrašų kliento ID ir to ID **klientų** puslapyje.

## <a name="next-steps"></a>Kiti žingsniai

Dabar galite kurti [segmentus](segments.md), [priemones](measures.md) ir [prognozes](predictions.md) prasmingo ryšio su klientais kūrimui.


[!INCLUDE[footer-include](../includes/footer-banner.md)]