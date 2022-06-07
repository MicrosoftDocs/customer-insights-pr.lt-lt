---
title: Naudokite duomenų šaltinius duomenų suvartojimui
description: Sužinokite, kaip importuoti duomenis iš įvairių šaltinių.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 355d52eabde90e0764817cf479821264ebb2e5eb
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800476"
---
# <a name="data-sources-overview"></a>Duomenų šaltinių apžvalga



Dynamics 365 Customer Insights prisijungia prie duomenų iš plataus šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.

## <a name="add-a-data-source"></a>Įtraukti duomenų šaltinį

Peržiūrėkite išsamius straipsnius, kaip įtraukti duomenų šaltinis, atsižvelgiant į pasirinktą parinktį.

Galite įtraukti šiuos duomenų šaltinius:

- [Per dešimtis Power Query jungčių](connect-power-query.md)
- [Iš „Common Data Model“ aplanko](connect-common-data-model.md)
- [Iš savo „Microsoft Dataverse“ telkinio](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics Iš duomenų bazės](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Duomenų įtraukimas iš vietinių duomenų šaltinių

Duomenų nurijimas iš vietinis duomenų šaltinių palaikomas Microsoft Power Platform remiantis duomenų srautais. Duomenų srautus galite įgalinti "Customer Insights" pateikdami [Microsoft Dataverse aplinkos URL](create-environment.md) nustatydami aplinką.

Duomenų šaltiniai, sukurti susiejus Dataverse aplinką su "Customer Insights", pagal numatytuosius nustatymus naudoja [Power Platform duomenų srautus](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus. Galite pašalinti ir iš naujo nustatyti duomenų šaltinius, egzistavusius prieš susiejant Dataverse [aplinką naudojant vietinis duomenų šliuzus](/data-integration/gateway/service-gateway-app).

Esamos Power BI arba Power Apps aplinkos duomenų tinklų sietuvai bus matomi ir galėsite pakartotinai naudoti „Customer Insights“. Duomenų šaltinių puslapyje rodomi saitai, kuriuos naudojant galima peržiūrėti ir konfigūruoti duomenų „Microsoft Power Platform“ vietinis aplinką.

> [!IMPORTANT]
> Įsitikinkite, kad šliuzai atnaujinti į naujausią versiją. Galite įdiegti naujinimą ir iš naujo sukonfigūruoti šliuzą iš raginimo, rodomo šliuzo ekrane tiesiogiai, arba [atsisiųsti naujausią versiją](https://powerapps.microsoft.com/downloads/). Jei nenaudojate naujausios šliuzo versijos, duomenų srauto atnaujinimas nepavyksta su klaidų pranešimais, pvz. **, Raktinis žodis nepalaikomas: konfigūracijos ypatybės. Parametro pavadinimas: raktažodis**.

## <a name="review-ingested-data"></a>Įtrauktų duomenų peržiūra
Jei jūsų aplinkoje yra Power Platform duomenų srautų, **puslapyje Duomenų šaltiniai** išvardijamos trys sekcijos: 
- **Bendrinama**: duomenų šaltiniai, kuriuos gali valdyti visi "Customer Insights" administratoriai. Power BI duomenų srautai, jūsų pačių saugyklos abonementas ir pridėjimas Dataverse prie valdomo duomenų ežero yra bendrinamų duomenų šaltinių pavyzdžiai.
- **Valdo aš**: Power Platform sukurti duomenų srautai, kuriuos galite valdyti tik jūs. Kiti "Customer Insights" administratoriai gali peržiūrėti tik šias duomenų sekas, bet jų neredaguoti, neatnaujinti ar panaikinti.
- **Valdo kiti**: Power Platform duomenų srautai, kuriuos sukūrė kiti administratoriai. Juos galite tik peržiūrėti. Jame išvardijamas duomenų srauto savininkas, su kuriuo reikia susisiekti dėl bet kokios pagalbos.
> [!NOTE]
> Visus objektus gali peržiūrėti ir naudoti kiti vartotojai. Vartotojo kontekstualumas taikomas tik duomenų šaltiniams, o ne objektams, atsirandantiems iš šių duomenų srautų.

Power Platform Jei duomenų srautai nenaudojami, nematysite jokių grupių ar sekcijų. Puslapyje **Duomenų šaltiniai** yra tik visų duomenų šaltinių sąrašas.

Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką. Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.

> [!div class="mx-imgBorder"]
> ![Įtrauktas duomenų šaltinis.](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**. Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).

## <a name="refresh-a-data-source"></a>Paleisti iš naujo duomenų šaltinį

Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį. 

Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.

Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite atnaujinti, ir išplečiamajame sąraše pasirinkite **Atnaujinti**.

3. Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo. Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.

4. Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.

## <a name="delete-a-data-source"></a>Naikinti duomenų šaltinį

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite vertikalią daugtaškį (&vellip;) šalia duomenų šaltinis norite pašalinti, ir išplečiamajame meniu pasirinkite **Naikinti**.

3. Patvirtinkite šį naikinimą.


[!INCLUDE [footer-include](includes/footer-banner.md)]
