---
title: Pagrindinis puslapis publikos įžvalgose
description: Pradėkite naršyti programoje pagrindiniame puslapyje.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406407"
---
# <a name="create-a-new-environment"></a>Kurti naują aplinką

## <a name="create-a-trial-environment"></a>Bandomosios aplinkos kūrimas

Galite prisiregistruoti naudoti bandomąją versiją [bandomosios versijos registracijos puslapyje](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Bandomasis laikotarpis baigiasi po 30 dienų.

1. Pasirinkite parinktį **Prisiregistruoti nemokamai naudoti bandomąją versiją** ir pasirinkite **Prisiregistruoti dabar**.

1. Pateikite savo darbo ar mokymosi įstaigos el. pašto adresą, papasakokite apie save ir pasirinkite **Toliau**.

1. Įveskite naujos aplinkos **pavadinimą**. 

1. Pasirinkite bandomosios versijos tipą.

1. Pasirinkite aplinkos **sritį**.

1. Pasirinktinai „Dynamics 365“ organizacijos administratoriams: pasirinkite **Išplėstiniai parametrai** ir nurodykite organizacijos URL, kad galėtumėte naudotis prognozės funkcijomis, pvz., klientų praradimu.

1. Pasirinkite **Kurti**. 

Sukūrę aplinką matysite **demonstracinę** aplinką, kurioje galėsite susipažinti su programa ir išgalvotais duomenimis. Galite keisti duomenų pavyzdį, kad jis atitiktų jūsų pramonės šaką. Pasirinkite piktogramą **Parametrai** ir pasirinkite **Demonstraciniai parametrai**. Be to, galite keisti vaizdinę temą. 

Galite [perjungti į aplinką](#change-between-environments), sukurtą registracijos proceso metu, ir apdoroti savo duomenis.

## <a name="create-a-new-production-or-sandbox-environment"></a>Naujos gamybos ir smėlio dėžės aplinkos kūrimas

Savo aplinkos antraštėje pasirinkite piktogramą **Parametrai** ir pasirinkite **Nauja aplinka**.

Atlikite veiksmus, kuriuos vykdote [kurdami bandomąją aplinką](#create-a-trial-environment). Rodoma papildoma parinktis, kai pasirenkate **Išplėstiniai parametrai**, kad duomenys būtų saugomi jūsų „Azure Date Lake“. Nurodykite kliento pavadinimą ir kliento raktą, kad užmegztumėte ryšį su savo „Azure Data Lake“. Pagal numatytuosius parametrus duomenys saugomi „Customer Insights“ valdomame „Data Lake“.

> [!IMPORTANT]
> Įrašydami duomenis „Azure Data Lake Storage“ sutinkate, kad duomenys bus perduoti ir saugomi atitinkamoje geografinėje vietoje, numatytoje konkrečiai „Azure“ saugyklos paskyrai, kuri gali skirtis nuo „Dynamics 365 Customer Insights“ duomenų saugojimo vietos. [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Pagrindinio puslapio tyrinėjimas

Galite [prieiti prie savo „Customer Insights“ aplinkos](https://home.ci.ai.dynamics.com/) tolesniame URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Pagrindiniame** puslapyje pateikiama klientų bazės apžvalga ir pagrindinė metrika, skirta verslo būklei sekti.

> [!div class="mx-imgBorder"] 
> ![Pagrindiniame puslapyje rodomos įžvalgos](media/home-page-insights.png "Pagrindiniame puslapyje rodomos įžvalgos")

Dalyje **Naujausi segmentai** matysite klientų grupes pagal demografinius, elgsenos arba operacijų atributus, kuriuos nustatėte. [Segmentų kūrimas](segments.md) padeda geriau nukreipti verslo veiklas.

Dalyje **Naujausi matai** rodomos plytelės su [matais](measures.md). Matai yra pagrindiniai efektyvumo indikatoriai (KPI), kuriuos nustatėte. Pavyzdžiui, vidutinė klientų praradimo tikimybė arba vidutinis kliento laiko leidimas internete.

Skyriuje **Naujausi papildymai** išvardyti neseniai baigto papildymo rezultatai. Papildymais įtrauktiama informacijos apie klientų bazę. Pavyzdžiui, sužinant jų pomėgius ir mėgstamus prekių ženklus. Šią informaciją galima atblokuoti naudojant [papildymo](enrichment-microsoft-graph.md)galimybes, užbaigus [susiejimo](map-entities.md), [atitikties](match-entities.md) ir [suliejimo](merge-entities.md) etapus.

## <a name="change-between-environments"></a>Aplinkų keitimas

Nustatę ir sukonfigūravę [duomenų šaltinius](data-sources.md), norėsite pereiti iš demonstracinės aplinkos į tiesioginę aplinką. Naudodami gamybos aplinką, galite dirbti su savo klientų duomenimis. Norėdami keisti aplinkas, viršutiniame dešiniajame puslapio kampe pasirinkite valdiklį **Aplinka**.

> [!div class="mx-imgBorder"] 
> ![Perjungti aplinką](media/home-page-environment-switcher.png "Perjungti aplinką")

Administratoriai gali kurti ir valdyti [kelias aplinkas](manage-environments.md). Išlaikyti daugiau nei vieną aplinką gali būti naudinga, jei, pavyzdžiui, jūsų organizacija veikia tarptautiniu mastu ir jums reikia atskirti duomenis bei įžvalgas įvairiais būdais.

## <a name="next-step"></a>Kitas veiksmas

Norėdami matyti savo įžvalgas pagrindiniame puslapyje, pirmiausia turite [įtraukti duomenų šaltinius](data-sources.md) ir [suvienodinti](data-unification.md) duomenis, kad sukurtumėte klientų profilius.
