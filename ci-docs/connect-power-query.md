---
title: Prisijungimas Power Query prie duomenų šaltinis (yra vaizdo įrašas)
description: Nurykite duomenis per jungtį Power Query (yra vaizdo įrašas).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609900"
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

1. Peržiūrėkite ir patikslinkite duomenis **Power Query puslapyje - Redaguoti užklausas**. Objektai, kuriuos sistema nustatė jūsų pasirinktame duomenų šaltinyje, rodomi kairiosios srities dalyje.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Užklausų redagavimo dialogo langas":::

1. Transformuokite savo duomenis. Pažymėkite objektą, kurį norite redaguoti arba pertvarkyti. Naudokite lango parinktis, Power Query kad pritaikytumėte transformacijas. Kiekviena transformacija yra nurodyta dalyje **Taikomi veiksmai**. Power Query suteikia daugybę [iš anksto sukurtų transformacijos](/power-query/power-query-what-is-power-query#transformations) galimybių.

   > [!IMPORTANT]
   > Rekomenduojame naudoti šias transformacijas:
   >
   > - Jei duomenis įtraukiate iš CSV failo, pirmojoje eilutėje dažnai pateikiamos antraštės. Eikite į **Transformavimas** ir pasirinkite **Naudoti pirmąją eilutę kaip antraštes**.
   > - Įsitikinkite, kad duomenų tipas yra tinkamai nustatytas ir atitinka duomenis. Pavyzdžiui, datos laukuose pasirinkite datos tipą.

1. Norėdami į duomenų šaltinis įtraukti papildomų objektų dialogo lange Redaguoti **užklausas**, eikite į **Pagrindinis** ir pasirinkite **Gauti duomenis**. Kartokite 5–10 veiksmus, kol įtrauksite visus šio duomenų šaltinis objektus. Jei turite duomenų bazę, kurioje yra keletas duomenų rinkinių, kiekvienas duomenų rinkinys yra savo paties objektas.

1. Pasirinkite **Įrašyti**. Atidaromas **puslapis Duomenų šaltiniai**, kuriame rodoma nauja atnaujinimo būsenos duomenų **šaltinis**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, nurijusius duomenis galima peržiūrėti puslapyje [**Objektai**](entities.md).

> [!CAUTION]
>
> - Duomenų šaltinis, pagrįstas Power Query, sukuria duomenų srautą [Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Nekeiskite duomenų srauto Power Platform pavadinimo administravimo centre, kuris naudojamas "Customer Insights". Pervardijus duomenų srautą, kyla problemų dėl nuorodų tarp "Customer Insights" duomenų šaltinis ir duomenų srauto Dataverse.
> - Vienu metu atliekami duomenų šaltinių įvertinimai Power Query "Customer Insights" turi tuos pačius [atnaujinimo apribojimus, kaip ir "Dataflows" PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Jei nepavyksta atnaujinti duomenų, nes jis pasiekė vertinimo ribą, rekomenduojame pakoreguoti kiekvieno duomenų srauto atnaujinimo tvarkaraštį, kad duomenų šaltiniai nebūtų apdorojami tuo pačiu metu.

### <a name="available-power-query-data-sources"></a>Galimi Power Query duomenų šaltiniai

Jungčių, [Power Query kurias galite naudoti norėdami importuoti duomenis į "Customer Insights", jungties nuorodą rasite jungties nuorodoje](/power-query/connectors/).

Jungtys su varnele stulpelyje **"Customer Insights" (duomenų srautai)** yra galimos kuriant naujus duomenų šaltinius pagal Power Query. Peržiūrėkite konkrečios jungties dokumentaciją, kad sužinotumėte daugiau apie jos būtinąsias sąlygas, [užklausos apribojimus](/power-query/power-query-online-limits) ir kitą informaciją.

## <a name="add-data-from-on-premises-data-sources"></a>Duomenų įtraukimas iš vietinių duomenų šaltinių

Duomenų nurijimas iš vietinis duomenų šaltinių palaikomas remiantis Microsoft Power Platform duomenų srautais (PPDF). Galite įgalinti duomenų srautus "Customer Insights [" pateikdami Microsoft Dataverse aplinkos URL](create-environment.md) nustatydami aplinką.

Duomenų šaltiniai, sukurti susiejus Dataverse aplinką su "Customer Insights", pagal numatytuosius nustatymus naudoja [Power Platform duomenų srautus](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus. Naudodami vietinis duomenų šliuzus galite pašalinti ir atkurti duomenų šaltinius, buvusius prieš Dataverse susiejant [aplinką](/data-integration/gateway/service-gateway-app).

Duomenų šliuzai iš esamos Power BI arba Power Apps aplinkos bus matomi ir galėsite juos pakartotinai naudoti "Customer Insights", jei duomenų šliuzas ir "Customer Insights" aplinka yra tame pačiame "Azure" regione. Duomenų šaltinių puslapyje rodomi saitai, kuriuos naudojant galima peržiūrėti ir konfigūruoti duomenų „Microsoft Power Platform“ vietinis aplinką.

> [!IMPORTANT]
> Įsitikinkite, kad šliuzai atnaujinti į naujausią versiją. Galite įdiegti naujinimą ir iš naujo sukonfigūruoti šliuzą iš raginimo, rodomo šliuzo ekrane, tiesiogiai arba [atsisiųsti naujausią versiją](https://powerapps.microsoft.com/downloads/). Jei nenaudojate naujausios šliuzo versijos, duomenų srauto atnaujinimas nepavyksta su klaidų pranešimais, pvz. **, Raktinis žodis nepalaikomas: konfigūracijos ypatybės. Parametro pavadinimas: raktinis žodis**.
>
> Klaidas, susijusias su vietinis duomenų šliuzais "Customer Insights", dažnai sukelia konfigūracijos problemos. Daugiau informacijos apie duomenų šliuzų trikčių diagnostiką rasite [vietinis duomenų šliuzo](/data-integration/gateway/service-gateway-tshoot) trikčių diagnostika.

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

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Dažniausios nurijimo klaidų arba sugadintų duomenų priežastys

### <a name="data-type-does-not-match-data"></a>Duomenų tipas nesutampa su duomenimis

Dažniausias duomenų tipo neatitikimas įvyksta, kai datos laukas nenustatytas kaip tinkamas datos formatas.

Duomenys gali būti fiksuoti šaltinyje ir vėl praryti. Arba pataisykite transformaciją "Customer Insights". Norėdami pataisyti transformaciją:

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Šalia duomenų šaltinis su sugadintais duomenimis pasirinkite **Redaguoti**.

1. Pasirinkite **Toliau**.

1. Pasirinkite kiekvieną užklausą ir ieškokite transformacijų, taikomų skiltyje "Taikomi veiksmai", kurios yra neteisingos, arba datos stulpelių, kurie nebuvo pakeisti datos formatu.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Redaguoti, rodant neteisingą datos formatą":::

1. Pakeiskite duomenų tipą, kad jis teisingai atitiktų duomenis.

1. Pasirinkite **Įrašyti**. Tas duomenų šaltinis yra atnaujintas.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>PPDF Power Query pagrįstų duomenų šaltinis atnaujinimo problemų šalinimas

Jei duomenys pasenę arba po duomenų šaltinis atnaujinimo gaunate klaidų, atlikite šiuos veiksmus:

1. Eikite į [Power Platform](https://make.powerapps.com).

1. **Pasirinkite "Customer Insights" egzemplioriaus aplinką**.

1. Eikite į **Dataflows**.

1. Duomenų srautui, atitinkančiam "Customer Insights" duomenų šaltinis, pasirinkite vertikalią daugtaškį (&vellip;), tada pasirinkite **Rodyti atnaujinimo retrospektyvą**.

1. **Jei duomenų srauto būsena** yra **Sėkmė**, galėjo pasikeisti Power Query duomenų šaltinis pagrįsto duomenų šaltinis nuosavybė:

   1. Peržiūrėkite atnaujinimo tvarkaraštį iš atnaujinimo retrospektyvos.
   1. Nustatykite naujo savininko tvarkaraštį ir išsaugokite nustatymus.

1. **Jei duomenų srauto būsena** yra **Nepavyko**:

   1. Atsisiųskite atnaujinimo istorijos failą.
   1. Peržiūrėkite atsisiųstą failą dėl gedimo priežasties.
   1. Jei klaidos negalima išspręsti, pasirinkite **?** , kad atidarytumėte palaikymo bilietą. Įtraukite atsisiųstą atnaujinimo istorijos failą.


[!INCLUDE [footer-include](includes/footer-banner.md)]
