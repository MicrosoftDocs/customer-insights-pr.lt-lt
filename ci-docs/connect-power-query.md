---
title: Prisijungimas Power Query prie duomenų šaltinis (yra vaizdo įrašas)
description: Nurykite duomenis per jungtį Power Query (yra vaizdo įrašas).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207055"
---
# <a name="connect-to-a-power-query-data-source"></a>Prisijungimas Power Query prie duomenų šaltinis

Power Query siūlo platų jungčių rinkinį duomenims nuryti. Daugelį šių jungčių palaiko „Dynamics 365 Customer Insights“.

Duomenų šaltinių pridėjimas pagal Power Query jungtis paprastai atliekamas šiame skyriuje aprašytais veiksmais. Tačiau, atsižvelgiant į naudojamą jungtį, reikalinga kita informacija. Norėdami sužinoti daugiau, peržiūrėkite dokumentaciją apie atskiras jungtis jungties nuorodoje [Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Sukurkite naują duomenų šaltinį

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **„Microsoft Power Query“**.

1. Pateikite duomenų šaltinis vardą **ir** pasirinktinį **aprašą** ir pasirinkite **Pirmyn**.

1. Pasirinkite vieną iš [galimų jungčių](#available-power-query-data-sources). Šiame pavyzdyje pasirenkame teksto / CSV **jungtį**.

1. Įveskite reikiamą pasirinktos jungties informaciją dalyje **Ryšio parametrai** ir pasirinkite **Toliau**, kad peržiūrėtumėte duomenis.

1. Pasirinkite **Transformuoti duomenis**.

1. Dialogo **Power Query lange – redaguoti užklausas** galite peržiūrėti ir patikslinti duomenis. Objektai, kuriuos sistema nustatė jūsų pasirinktame duomenų šaltinyje, rodomi kairiosios srities dalyje.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Užklausų redagavimo dialogo langas":::

1. Taip pat galite pertvarkyti savo duomenis. Pažymėkite objektą, kurį norite redaguoti arba pertvarkyti. Naudokite lango parinktis, Power Query kad pritaikytumėte transformacijas. Kiekviena transformacija yra nurodyta dalyje **Taikomi veiksmai**. Power Query suteikia daugybę [iš anksto sukurtų transformacijos](/power-query/power-query-what-is-power-query#transformations) galimybių.

   Rekomenduojame naudoti šias transformacijas:

   - Jei duomenis įtraukiate iš CSV failo, pirmojoje eilutėje dažnai pateikiamos antraštės. Eikite į **Transformavimas** ir pasirinkite **Naudoti pirmąją eilutę kaip antraštes**.
   - Užtikrinkite, kad tinkamai nustatytas duomenų tipas. Pavyzdžiui, datos laukuose pasirinkite datos tipą.

1. Norėdami į duomenų šaltinis įtraukti papildomų objektų dialogo lange Redaguoti **užklausas**, eikite į **Pagrindinis** ir pasirinkite **Gauti duomenis**. Kartokite 5–10 veiksmus, kol įtrauksite visus šio duomenų šaltinis objektus. Jei turite duomenų bazę, kurioje yra keletas duomenų rinkinių, kiekvienas duomenų rinkinys yra savo paties objektas.

1. Pasirinkite **Įrašyti**. Atidaromas **puslapis Duomenų šaltiniai**, kuriame rodoma nauja atnaujinimo būsenos duomenų **šaltinis**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, nurijusius duomenis galima peržiūrėti puslapyje [**Objektai**](entities.md).

> [!CAUTION]
> Duomenų šaltinis, pagrįstas Power Query, sukuria duomenų srautą [Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nekeiskite duomenų srauto Power Platform pavadinimo administravimo centre, kuris naudojamas "Customer Insights". Pervardijus duomenų srautą, kyla problemų dėl nuorodų tarp "Customer Insights" duomenų šaltinis ir duomenų srauto Dataverse.

### <a name="available-power-query-data-sources"></a>Galimi Power Query duomenų šaltiniai

Jungčių, [Power Query kurias galite naudoti norėdami importuoti duomenis į "Customer Insights", jungties nuorodą rasite jungties nuorodoje](/power-query/connectors/).

Jungtys su varnele stulpelyje **"Customer Insights" (duomenų srautai)** yra galimos kuriant naujus duomenų šaltinius pagal Power Query. Peržiūrėkite konkrečios jungties dokumentaciją, kad sužinotumėte daugiau apie jos būtinąsias sąlygas, [užklausos apribojimus](/power-query/power-query-online-limits) ir kitą informaciją.

## <a name="add-data-from-on-premises-data-sources"></a>Duomenų įtraukimas iš vietinių duomenų šaltinių

Duomenų nurijimas iš vietinis duomenų šaltinių palaikomas remiantis Microsoft Power Platform duomenų srautais (PPDF). Galite įgalinti duomenų srautus "Customer Insights [" pateikdami Microsoft Dataverse aplinkos URL](create-environment.md) nustatydami aplinką.

Duomenų šaltiniai, sukurti susiejus Dataverse aplinką su "Customer Insights", pagal numatytuosius nustatymus naudoja [Power Platform duomenų srautus](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus. Galite pašalinti ir atkurti duomenų šaltinius, buvusius prieš Dataverse susiejant [aplinką, naudodami vietinis duomenų šliuzus](/data-integration/gateway/service-gateway-app).

Duomenų šliuzai iš esamos Power BI arba Power Apps aplinkos bus matomi ir galėsite juos pakartotinai naudoti "Customer Insights". Duomenų šaltinių puslapyje rodomi saitai, kuriuos naudojant galima peržiūrėti ir konfigūruoti duomenų „Microsoft Power Platform“ vietinis aplinką.

> [!IMPORTANT]
> Įsitikinkite, kad šliuzai atnaujinti į naujausią versiją. Galite įdiegti naujinimą ir iš naujo sukonfigūruoti šliuzą iš raginimo, rodomo šliuzo ekrane, tiesiogiai arba [atsisiųsti naujausią versiją](https://powerapps.microsoft.com/downloads/). Jei nenaudojate naujausios šliuzo versijos, duomenų srauto atnaujinimas nepavyksta su klaidų pranešimais, pvz. **, Raktinis žodis nepalaikomas: konfigūracijos ypatybės. Parametro pavadinimas: raktinis žodis**.
>
> Klaidas, susijusias su vietinis duomenų šliuzais "Customer Insights", dažnai sukelia konfigūracijos problemos. Daugiau informacijos apie duomenų šliuzų trikčių diagnostiką rasite [vietinis duomenų šliuzo trikčių šalinimas](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Duomenų šaltinių redagavimas Power Query

> [!NOTE]
> Gali būti, kad nebus įmanoma keisti duomenų šaltinių, kurie šiuo metu naudojami viename iš programos procesų (pvz., segmentavimas arba duomenų suvienijimas).
>
> Nustatymų **puslapyje** galite stebėti kiekvieno iš aktyvių procesų eigą. Kai procesas bus užbaigtas, galite grįžti į puslapį **Duomenų šaltiniai** ir atlikti pakeitimus.

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Šalia duomenų šaltinis, kurį norite atnaujinti, pasirinkite **Redaguoti**.

1. Taikykite savo pakeitimus ir transformacijas dialogo lange - Redaguoti užklausas **Power Query**, kaip aprašyta [skyriuje Kurti naują duomenų šaltinis](#create-a-new-data-source).

1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus ir grįžtumėte į **puslapį Duomenų šaltiniai**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
