---
title: „Dynamics 365 Customer Insights“ aptarnavimo apribojimai
description: Supraskite apribojimus ir suvaržymus.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350417"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>„Customer Insights“ galimybių aptarnavimo apribojimai

Straipsnis aprašo inkorporuotus apribojimus „Customer Insights“ paslaugoms, kurios yra sukurtos siekiant užtikrinti paslaugų patikimumą ir stabilumą. Bet kokios pakeitimų užklausos gali būti pateiktos per [Idėjų forumą](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Auditorijos įžvalgos

| Plotas  | Apribojimai  | Pastabos |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentai, priemonės ir prognozės | 300  | Bendras [segmentų](audience-insights/segments.md), [priemonių](audience-insights/measures.md) ir [prognozių](audience-insights/predictions.md) skaičius kartu negali viršyti 300.  |
| Ryšiai | 20 gylio lygių santykiuose objektų keliuose. | Kuriant [segmentus](audience-insights/segments.md) ar [priemones](audience-insights/measures.md) naudojant kūrėjo sąsają, objekto keliai gali turėti iki 20 ryšių perėjimų tarp pradinio ir tikslinio objekto.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
