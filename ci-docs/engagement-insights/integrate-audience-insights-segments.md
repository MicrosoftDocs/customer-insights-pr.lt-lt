---
title: Naudokite auditorijų įžvalgų segmentus įtraukimo įžvalgų ataskaitoms filtruoti
description: Naudokite auditorijų įžvalgų segmentus interaktyviai naudodami elgsenos duomenis, užfiksuotus įtraukimo įžvalgų kliento svetainėje.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461068"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Naudokite auditorijų įžvalgų segmentus įtraukimo įžvalgų ataskaitoms filtruoti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Su įtraukimo įžvalgomis galite naudoti auditorijų įžvalgų segmentus interaktyviai naudodami elgsenos duomenis, užfiksuotus įtraukimo įžvalgų savo svetainėje.

## <a name="prerequisite"></a>Būtinoji sąlyga

- Įtraukimo įžvalgų aplinka, kurioje yra auditorijos įžvalgų segmentų duomenų, susietų su auditorijos įžvalgų aplinka, kurioje kuriami segmentai ir klientų profiliai. Daugiau informacijos: [Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Kurkite auditorijų įžvalgų segmentus 

> [!IMPORTANT]
> Kad auditorijos įžvalgų segmentai būtų rodomi įtraukimo įžvalgoje, pirmiausia turite [paleisti suliejimo ir pasroviui procesus](../audience-insights/merge-entities.md). Pasroviniai procesai yra svarbūs, nes jie sukuria unikalią lentelę, kuri paruošia auditorijos įžvalgų segmentus, kuriuos reikia bendrai naudoti su įtraukimo įžvalgomis. (Jei sistemos naujinimas suplanuotas, jis automatiškai apims tolesnius procesus).

Galite naudoti auditorijos įžvalgų segmentus savo sukurtose įtraukimo įžvalgų iš anksto sukurtose ataskaitose arba pasirinktinėse ataskaitose. Norėdami gauti daugiau informacijos, eikite į [iš anksto sukurtas profilio ataskaitas](profile-reports.md) ir [Kurkite bei redaguokite pasirinktines ataskaitas](custom-reports.md).

**Norėdami naudoti auditorijų įžvalgų segmentus įtraukimo įžvalgų ataskaitose**

1. Savo **Darbo srities** puslapyje pasirinkite **Duomenys** ir tada pažymėkite **Segmentai** skirtuką.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Pasirinkite Segmentai skirtuką.":::

   >[!NOTE]
   > Jei pažymėsite auditorijos įžvalgų segmentą, pateksite į auditorijos įžvalgas ir išsiaiškinsite, kaip tas segmentas sukurtas pagal taisykles ir logiką. Norėdami gauti daugiau informacijos apie auditorijos įžvalgos segmentus, eikite į [Paržiūrėti ir kurti segmentus](../audience-insights/segments.md).

2. Pažymėkite iš anksto sukurtą ataskaitą arba [sukurkite pasirinktinę ataskaitą](custom-reports.md), tada pažymėkite **Įtraukti sąlygą**. (Šiame pavyzdyje pasirinksime **Puslapių rodiniai** ataskaitą.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Įtraukti sąlygą.":::

3. Pažymėkite **"Filtruoti pagal segmentą"**, išplėskite **Segmento tipo** sąrašą, tada pasirinkite **"Demografiniai"**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Pažymėkite Demografinio segmento tipą.":::

4. Išplėskite **Segmento pavadinimo** sąrašą, tada pasirinkite auditorijos įžvalgų segmentą.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text=" Pasirinkite segmentą.":::

5. Galite taikyti vieną ar daugiau segmentų, įskaitant elgsenos (įtraukimo įžvalgas) ir demografinių (auditorijų įžvalgų) segmentus. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Puslapių rodinių ataskaita skirta tik JAV klientams ir pagrindinio puslapio segmentams.":::

Ankstesniame paveikslėlyje **JAV klientai** ir **Pagrindinio puslapio** segmentai buvo pasirinkti, kas apriboja **Puslapio rodinių** ataskaitą rodyti tik šiuos du segmentus. 


>[!NOTE]
> Galite naudoti auditorijos įžvalgų segmentus filtruoti iš anksto sukurtas ataskaitas, klientų ataskaitas ir nukreipimus įtraukimo įžvalgose. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]