---
title: Naudokite duomenų šaltinius duomenų suvartojimui
description: Sužinokite, kaip importuoti duomenis iš įvairių šaltinių.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732165"
---
# <a name="data-sources-overview"></a>Duomenų šaltinių apžvalga

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Auditorijos įžvalgų galimybė Dynamics 365 Customer Insights jungiasi prie duomenų iš plataus šaltinių rinkinio. Prisijungimas prie duomenų šaltinio dažnai vadinamas *duomenų įtraukimo procesu*. Įtraukę duomenis galite juos [suvienodinti](data-unification.md) ir imtis susijusių veiksmų.

## <a name="add-a-data-source"></a>Įtraukti duomenų šaltinį

Informacijos apie tai, kaip įtraukti duomenų šaltinį, atsižvelgiant į pasirinktą parinktį, žr. išsamiuose straipsniuose.

Duomenų šaltinį galite įtraukti trimis pagrindiniais būdais.

- [Per dešimtis „Power Query“ jungčių](connect-power-query.md)
- [Iš „Common Data Model“ aplanko](connect-common-data-model.md)
- [Iš savo Microsoft Dataverse ežero](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Duomenų įtraukimas iš vietinių duomenų šaltinių

Duomenų nurijimas iš vietinis duomenų šaltinių auditorijos įžvalgose palaikomas remiantis Microsoft Power Platform duomenų srautais. Duomenų srautai gali būti įgalinti "Customer Insights" [pateikiant Microsoft Dataverse aplinkos URL nustatant](create-environment.md) aplinką.

Duomenų šaltiniai, sukurti susiejus Dataverse aplinką su "Customer Insights", pagal numatytuosius nustatymus naudos [Power Platform duomenų](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) srautus. Duomenų srautai palaiko vietinį ryšį, naudodami duomenų šliuzus. Pašalinkite ir iš naujo sukurkite duomenų šaltinius, egzistavusius prieš susiejant Dataverse aplinką, kad būtų [galima naudoti vietinis duomenų šliuzus](/data-integration/gateway/service-gateway-app).

Bus matomi esamos Power BI arba Power Apps aplinkos duomenų šliuzai, kuriuos galėsite pakartotinai naudojate "Customer Insights". Duomenų šaltinių puslapyje rodomi saitai, skirti eiti į Microsoft Power Platform aplinką, kurioje galite peržiūrėti ir konfigūruoti vietinis duomenų šliuzus.

## <a name="review-ingested-data"></a>Įtrauktų duomenų peržiūra

Matysite kiekvieno įtraukto duomenų šaltinio pavadinimą, jo būseną ir vėliausio to šaltinio duomenų atnaujinimo laiką. Galite rūšiuoti duomenų šaltinių sąrašą pagal kiekvieną stulpelį.

> [!div class="mx-imgBorder"]
> ![Įtrauktas duomenų šaltinis.](media/configure-data-datasource-added.png "Įtrauktas duomenų šaltinis")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, galima peržiūrėti apdorotus duomenis puslapyje **Objektai**. Norėdami gauti daugiau informacijos, žr. [Objektai](entities.md).

## <a name="refresh-a-data-source"></a>Paleisti iš naujo duomenų šaltinį

Duomenų šaltiniai gali būti paleisti iš naujo automatiniu grafiku arba rankiniu būdu pagal poreikį. 

Eikite į **Administravimas** > **Sistema** > [**Grafikas**](system.md#schedule-tab) norėdami sukonfigūruoti suplanuotus visų jūsų suvartotų duomenų šaltinių paleidimus iš naujo.

Norėdami paleisti iš naujo duomenų šaltinį pagal poreikį, atlikite šiuos veiksmus:

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elešką šalia norimos duomenų naujinti dalies ir **Naujinti** meniu pasirinkite Redaguoti.

3. Šis duomenų šaltinis dabar yra įjungtas rankiniam paleidimui iš naujo. Atnaujinus duomenų šaltinį bus atnaujinta ir objekto schema, ir duomenys, skirti visiems duomenų šaltinyje nurodytiems objektams.

4. Pasirinkite **Stabdyti paleidimą iš naujo** jei norite atšaukti esantį paleidimą iš naujo ir duomenų šaltinis grįš į paskutinę paleidimo iš naujo būseną.

## <a name="delete-a-data-source"></a>Naikinti duomenų šaltinį

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pažymėkite vertikalią elešką šalia norimos duomenų naikinti dalies ir **Naikinti** meniu pasirinkite Redaguoti.

3. Patvirtinkite šį naikinimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
