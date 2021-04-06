---
title: Pagrindinis puslapis publikos įžvalgose
description: Pradėkite naršyti programoje pagrindiniame puslapyje.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597245"
---
# <a name="create-a-new-environment"></a>Kurti naują aplinką

## <a name="create-a-trial-environment"></a>Bandomosios aplinkos kūrimas

Galite prisiregistruoti naudoti bandomąją versiją [bandomosios versijos registracijos puslapyje](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Bandomasis laikotarpis baigiasi po 30 dienų.

1. Pasirinkite parinktį **Prisiregistruoti nemokamai naudoti bandomąją versiją** ir pasirinkite **Prisiregistruoti dabar**.

1. Pateikite savo darbo ar mokymosi įstaigos el. pašto adresą, papasakokite apie save ir pasirinkite **Toliau**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Susisiekite užsiregistruoti nemokamai bandomajai versijai gauti":::

1. Įveskite naujos aplinkos **pavadinimą**. 

1. Pasirinkite bandomosios versijos tipą.

1. Pasirinkite aplinkos **sritį**.

1. Pasirinktinai „Dynamics 365“ organizacijos administratoriams: pasirinkite **Išplėstiniai parametrai** ir nurodykite organizacijos URL, kad galėtumėte naudotis prognozės funkcijomis, pvz., klientų praradimu.

1. Pasirinkite **Kurti**. 

Sukūrę aplinką matysite **demonstracinę** aplinką, kurioje galėsite susipažinti su programa ir išgalvotais duomenimis. Galite keisti duomenų pavyzdį, kad jis atitiktų jūsų pramonės šaką. Pasirinkite piktogramą **Parametrai** ir pasirinkite **Demonstraciniai parametrai**. Be to, galite keisti vaizdinę temą. 

Galite [perjungti į aplinką](#switch-environments), sukurtą registracijos proceso metu, ir apdoroti savo duomenis.

## <a name="create-a-new-production-or-sandbox-environment"></a>Naujos gamybos ir smėlio dėžės aplinkos kūrimas

Savo aplinkoje programos antraštėje pasirinkite parinktį **Aplinkos** ir spauskite **Naujas**.

Atlikite veiksmus, kuriuos vykdote [kurdami bandomąją aplinką](#create-a-trial-environment). Pagal numatytuosius parametrus duomenys saugomi „Customer Insights“ valdomame duomenų telkinyje. Rodoma papildoma parinktis, kai pasirenkate **Išplėstiniai parametrai**, kad duomenys būtų saugomi jūsų „Azure Date Lake“. Nurodykite kliento pavadinimą ir kliento raktą, kad užmegztumėte ryšį su savo „Azure Data Lake“. 

> [!IMPORTANT]
> Įrašydami duomenis „Azure Data Lake Storage“ sutinkate, kad duomenys bus perduoti ir saugomi atitinkamoje geografinėje vietoje, numatytoje konkrečiai „Azure“ saugyklos paskyrai, kuri gali skirtis nuo „Dynamics 365 Customer Insights“ duomenų saugojimo vietos. [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Pagrindinio puslapio tyrinėjimas

Galite pasiekti [auditorijos įžvalgas Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/)pagal šį URL:[https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Pagrindiniame puslapyje** rodoma segmentų, priemonių ir papildymo duomenų apžvalga (jei sukonfigūruota) atlikus [išdėstymo](map-entities.md), [gretinimo](match-entities.md) ir [suliejimo](merge-entities.md) etapus.

> [!div class="mx-imgBorder"] 
> ![Pagrindiniame puslapyje rodomos įžvalgos](media/home-page-insights.png "Pagrindiniame puslapyje rodomos įžvalgos")

Dalyje **Naujausi segmentai** matysite klientų grupes pagal demografinius, elgsenos arba operacijų atributus, kuriuos nustatėte. [Kuriant segmentus ](segments.md)galima grupuoti klientų bazę ir geriau nukreipti į verslo veiklas.

**Naujausiose priemonėse** rodoma [plytelė su jūsų apibrėžtais ](measures.md) pagrindiniais efektyvumo indikatoriais (KPI). Pvz.: vidutinė tikimybė, kad prarasite klientą, arba vidutinės internetinės išlaidos vienam klientui.

Skyriuje **Naujausi papildymai** išvardyti neseniai baigto papildymo rezultatai. [Papildymai](enrichment-hub.md) prideda informacijos apie jūsų klientų bazę. Pavyzdžiui, sužinant jų pomėgius ir mėgstamus prekių ženklus.

## <a name="switch-environments"></a>Perjungti aplinką

Norėdami keisti aplinkas, viršutiniame dešiniajame puslapio kampe pasirinkite valdiklį **Aplinka**.

> [!div class="mx-imgBorder"] 
> ![Perjungti aplinką](media/home-page-environment-switcher.png "Perjungti aplinką")

Administratoriai gali kurti ir valdyti [kelias aplinkas](manage-environments.md). Išlaikyti daugiau nei vieną aplinką gali būti naudinga, jei, pavyzdžiui, jūsų organizacija veikia tarptautiniu mastu ir jums reikia atskirti duomenis bei įžvalgas įvairiais būdais.

## <a name="next-step"></a>Kitas veiksmas

Norėdami matyti savo įžvalgas pagrindiniame puslapyje, pirmiausia turite [įtraukti duomenų šaltinius](data-sources.md) ir [suvienodinti](data-unification.md) duomenis, kad sukurtumėte klientų profilius.


[!INCLUDE[footer-include](../includes/footer-banner.md)]