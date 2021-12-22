---
title: Tvarkyti numatytąsias segmentų sutikimo taisykles
description: Naudodami sutikimo valdymo galimybę, galite išjungti arba pakeisti numatytąsias sutikimo taisykles, jei įgalintos nepaisymos taisyklės.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884180"
---
# <a name="disable-or-change-default-consent-rules"></a>Išjungti arba keisti numatytąsias sutikimo taisykles

Jei jūsų organizacijos naudoja [sutikimo valdymo funkciją](../consent-management/overview.md) kartu su auditorijos įžvalgomis, [administratoriai gali taikyti segmentų sutikimo](activate-consent.md) taisykles. 

Su priverstinio sutikimo taisyklėmis segmento srityje kiekvienas segmentas informuoja apie sutikimo patikrinimo būklę ir taisykles. Jei leidžiami nepaisyimai, tam tikriems segmentams išjungiamos numatytosios sutikimo taisyklės. Kiekvienas segmento kūrėjas gali pridėti daugiau sutikimo taisyklių, be numatytųjų taisyklių, prie segmento. 

## <a name="for-administrators"></a>Administratoriams

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmento daryklė su sutikimo taisyklės parinktimis.":::

**Norėdami išjungti numatytąsias sutikimo taisykles:**

1. Pranešime **Sutikimo** taisyklėse pasirinkite **Peržiūrėti išsamią informaciją**. 

1. Nustatykite **numatytąsias sutikimo** taisykles, kad perjungtumėte į **Išjungta**.

**Norėdami įtraukti daugiau sutikimo taisyklių:**

1. Pranešime **Sutikimo** taisyklėse pasirinkite **Peržiūrėti išsamią informaciją**. 

1. Pasirinkite **Įtraukti sutikimo taisykles** ir **išplečiamajame** išplečiamajame meniu Pasirinkti sutikimo duomenų tipą pasirinkite sutikimo taisyklę.

1. Pasirinkite **Įrašyti**, kad segmentui pritaikytumėte naują taisyklę.

## <a name="for-contributors"></a>Rėmėjams

Norėdami sukurti segmentą be priverstinio sutikimo taisyklių, turite dirbti su administratoriumi, kad jį išjungtumėte segmente. Tačiau galite pridėti savo sutikimo taisykles prie savo valdomų ir valdomų segmentų.

Tai trijų etapų procesas: 
1. [Sukurkite segmentą](segments.md) auditorijos įžvalgose ir įrašykite jį. 

1. Bendrinkite segmento pavadinimą su administratoriumi ir paprašykite jo [įgalinti segmento nepaisymus](activate-consent.md). 

1. Dar kartą atidarykite segmentus. Pranešime **Apie sutikimo taisykles** pasirinkite **Peržiūrėti išsamią informaciją** ir pridėkite norimas taikyti sutikimo taisykles. Tada **įrašykite** ir **paleiskite** segmentą.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
