---
title: Žiniatinklio duomenų integravimas su įtraukimo įžvalgomis auditorijų apžvalgoje
description: Galite pateikti klientų žiniatinklio informaciją nuo įtraukimo įžvalgų iki auditorijos įžvalgų.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033779"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Žiniatinklio duomenų integravimas su įtraukimo įžvalgomis auditorijų apžvalgoje

Klientai dažnai kasdien pavedimus atlieka internetu, naudodami interneto svetaines. Įtraukimo įžvalgų (peržiūros) galimybė yra „Dynamics 365 Customer Insights“ patogus sprendimas integruoti žiniatinklio duomenis kaip šaltinį. Be operacijų, demografinių ar elgsenos duomenų veiklą žiniatinklyje galime matyti vieninguose klientų profiliuose. Naudodami šiuos profilius galime gauti papildomų įžvalgų, pvz., segmentų, priemonių ar auditorijos suaktyvinimo prognozių.

Šiame straipsnyje aprašomi veiksmai, kurių reikia norint klientų žiniatinklio veiklos duomenis pateikti iš įtraukimo įžvalgų į esamą auditorijos įžvalgų aplinką.

Šiame pavyzdyje tarkime, kad aplinkoje yra vieningų klientų profilių. Profiliai buvo suvienodinti su apklausų, mažmeninės prekybos ir bilietų pardavimo sistemos šaltiniais. Čia taip pat rodoma susijusi klientų veikla. 

Dabar norėtume žinoti, ar klientas lankosi mūsų žiniatinklio ypatybėse ir supranta jų veiklą. Veiklos apima, pvz.: peržiūrėtus produktų puslapius iš el. paštu gautų saitų arba peržiūrėtus produktų puslapius.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint integruoti duomenis iš įtraukimo įžvalgų, reikia įvykdyti kelias būtinąsias sąlygas: 

- Integruokite įtraukimo įžvalgų SDK į svetainę. Daugiau informacijos žr. [Kūrėjų resursų apžvalga](../engagement-insights/developer-resources.md).
- Norint eksportuoti žiniatinklio įvykius iš įtraukimo įžvalgų, reikalinga prieiga prie kliento, kuris bus naudojamas žiniatinklio „Azure Data Lake Storage“ įvykių duomenims pereiti prie auditorijos įžvalgų. Daugiau informacijos ieškokite [Terminų atnaujinimas](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Patobulintos įvykių konfigūravimas įtraukimo įžvalgose

Kai administratorius sustoją svetainę su įtraukimo įžvalgų SDK, *pagrindiniai įvykiai* surenkami vartotojui rodius tinklalapį arba spusteli išsamūs. Pagrindiniai įvykiai pateikia išsamią informaciją. Atsižvelgiant į naudojimo atvejį, jums reikalingas tik pagrindinio įvykio duomenų antrinis rinkinys. Naudodami įtraukimo įžvalgas galite kurti *tobulintinus įvykius*, kuriuose yra tik jūsų pasirinkto pagrindinio įvykio ypatybės.     

Daugiau informacijos ieškokite [Patobulintos įvykių kūrimas ir modifikavimas](../engagement-insights/refined-events.md).

Aspektai kuriant tobulintinus įvykius: 

- Teikia prasmingą patikslintame įvykyje pavadinimą. Jis bus naudojamas kaip veiklos pavadinimas auditorijos įžvalgose.
- Jei norite kurti veiklą auditorijos įžvalgose, pasirinkite bent šias ypatybes: 
    - Signal.Action.Name – nurodoma išsami veiklos informacija.
    - Signal.User.Id – naudojama susieti su kliento ID.
    - Signal.View.Uri – naudojamas kaip žiniatinklio adresas kaip segmentų arba priemonių pagrindas.
    - Signal.Export.Id – naudojamas kaip pirminis įvykių raktas.
    - Signal.Timestamp – nustato apklausos veiklos kanalo data ir laikas.

Pažymėkite filtrus, sufokusuojamus į įvykius ir puslapius, kurie susiję su jūsų naudojimo atveju. Šiame pavyzdyje naudosime veiksmo pavadinimą „El. pašto reklama”.

## <a name="export-the-refined-web-events"></a>Eksportuoti tobulintus žiniatinklio įvykius 

Apibrėžę patobulintą įvykį turite sukonfigūruoti įvykių duomenų eksportavimą į, kurį galima nustatyti duomenų šaltinis auditorijos įžvalgų „Azure Data Lake Storage“ prarijus. Iš žiniatinklio ypatybės nuolat eksportuojama kaip įvykiai.

Daugiau informacijos ieškokite [Terminų atnaujinimas](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Pereidami įvykių duomenis prie auditorijos įžvalgų

Dabar, kai apibrėšite patobulintą įvykį ir sukonfigūravote jo eksportavimą, pereisime prie duomenų įkėlimo į auditorijos įžvalgas. Turite sukurti naują duomenų šaltinį pagal aplanką „Įprastas duomenų modelis”. Įveskite saugyklos, į kurią eksportuojate įvykius, išsamią informaciją. *default.cdm.json* faile pažymėkite patobulintą įvykį ir sukurkite objektą auditorijos įžvalgose.

Daugiau informacijos žr. [Prisijungimas prie „Common Data Model“ naudojant „Azure Data Lake” paskyrą](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Patobulinti įvykių duomenys susieti su kliento profilio veikla

Papildę objektą galite sukonfigūruoti kliento profilio veiklą.

Norėdami gauti daugiau informacijos, žr. [Klientų veiklos](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Veiklos puslapis su išplėsta veiklos redagavimo sritimi ir laukais.":::

Sukonfigūruokite naują veiklą naudodami šį susiejimą: 

- **Pirminis raktas**: Signal.Export.Id– unikalus ID, pasiekiamas kiekvienam įvykio įrašui įtraukimo įžvalgų metu. Ši ypatybė generuojama automatiškai.

- **Laiko žyma**: įvykio ypatybės signalo laiko žyma.

- **Įvykis**: Signal.Name, norimo naudoti įvykio pavadinimas.

- **Žiniatinklio adresas**: signal.View.Uri nurodantis įvykį sukūrusio puslapio URI.

- **Išsami informacija**: Signal.Action.Name pateikti informaciją, susijusią su įvykiu. Pažymėta ypatybė tokiu atveju nurodo, kad įvykis skirtas el. pašto reklamai.

- **Veiklos tipas**: šiame pavyzdyje pasirinkite esamą veiklos tipą "WebLog". Šis pasirinkimas yra naudinga filtro parinktis, norint prognozė modelius ar kurti segmentus pagal šį veiklos tipą.

- **Ryšio nustatymas** : šiuo svarbiu parametru veikla susijusi su esamais klientų profiliais. **Signal.User.Id** yra identifikatorius, sukonfigūruotas SDK, kurį reikia rinkti ir kuris susijęs su vartotojo ID kituose duomenų šaltiniuose, sukonfigūruotuose auditorijos įžvalgose. Šiame pavyzdyje konfigūruojame ryšį tarp "Signal.User.Id" ir "RetailCustomers:Customer VideoilId", kuris yra pirminis raktas, kuris buvo nustatytas duomenų suvienodinimo proceso struktūros žingsnyje.

Apdorojus veiklas galite peržiūrėti klientų įrašus ir atidaryti kliento korteles, kad veiklas peržiūrėtumėte iš įtraukimo įžvalgų laiko planavimo juostoje. 

> [!TIP]
> Norėdami rasti kliento ID, kuriame yra įtraukimo įžvalgų veikla, eikite į **Objektai** ir peržiūrėkite objekto UnifiedActivity duomenis. ActivityTypeDisplay = "WebLog" yra įtraukimo įžvalgų veikla, sukonfigūruota aukščiau pateiktame pavyzdyje. Nukopijuokite vieno iš šių įrašų kliento ID ir to ID **klientų** puslapyje.

## <a name="next-steps"></a>Paskesni veiksmai

Dabar galite kurti [segmentus](segments.md), [priemones](measures.md) ir [prognozes](predictions.md) prasmingo ryšio su klientais kūrimui.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
