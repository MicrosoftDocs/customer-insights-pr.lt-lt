---
title: Naudokite demografinius matmenis elgsenos duomenims išskaidyti (kuruotos dimensijos)
description: Naudokite vieningą profilio kuruotą matmenį, kad įgalintumėte auditorijos įžvalgų kliento profilio ypatybes.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233057"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Naudokite demografinius matmenis elgsenos duomenims išskaidyti

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Naudodami vieningas profilio demografinius matmenis, įtraukimo įžvalgų vartotojai gali pasiekti auditorijos įžvalgų profilio ypatybes. Tada galite naudoti šias ypatybes interaktyviame elgsenos duomenų, įskaitant duomenis, užfiksuotas per įtraukimo įžvalgas svetainėje arba mobiliųjų įrenginių programoje, sąveikoje.

>[!NOTE]
> Į įtraukimo įžvalgas įtrauktos visiškai parengtos įvykių ypatybių dimensijos. Daugiau informacijos: [Matmenų peržiūra ir kūrimas](dimensions.md)

## <a name="prerequisite"></a>Būtinoji sąlyga

- Įtraukimo įžvalgų aplinka, kurioje yra kliento profilio duomenų, susietų su auditorijos įžvalgų aplinka, kurioje kuriami klientų profiliai. Daugiau informacijos: [Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Sukūrę ryšį tarp auditorijos įžvalgų ir įtraukimo įžvalgų aplinkos, galbūt norėsite tik duomenų, susijusių su klientų profilio ypatybėmis, kurie gali būti naudingi kaip įtraukimo įžvalgų aspektai. Norėdami gauti daugiau informacijos, eikite į [Įjunkite auditorijos įžvalgų vieningus profilių atributus ir segmentus](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Sukurkite naują pasirinktinę ataskaitą.

1. Kairiojoje srityje pažymėkite **Pasirinktinė** > **Nauja ataskaita**, tada pažymėkite norimą metriką. (Šiame pavyzdyje pasirinksime **Puslapių rodiniai pagal valandą**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Pasirinkite metriką.":::

2. Vizualizacijos rengyklėje pasirinkite **Matmenys** ir tada pasirinkite **Demografika** **Matmenų tipas** išplečiamajame meniu.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Pasirinkite demografiją.":::

3. Pasirinkite **Signal.Customer.*xxx*** matmenis. (Šis pavyzdys rodo Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Pasirinkti matmenį.":::
  
## <a name="limitations"></a>Apribojimai

Šiuo metu galite naudoti tik demografinius matmenis elgsenos duomenims išskaidyti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
