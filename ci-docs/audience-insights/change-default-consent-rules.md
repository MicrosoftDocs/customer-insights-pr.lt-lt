---
title: Tvarkyti numatytąsias sutikimo taisykles segmentuose
description: Naudodami sutikimo valdymo galimybę, galite išjungti arba pakeisti numatytąsias sutikimo taisykles, jei įjungtas nepaisymas.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228949"
---
# <a name="disable-or-change-default-consent-rules"></a>Numatytųjų sutikimo taisyklių išjungimas arba keitimas

Jei jūsų organizacijos naudoja sutikimo [valdymo galimybes](../consent-management/overview.md) kartu su auditorijos įžvalgomis, [administratoriai gali vykdyti segmentų sutikimo taisykles](activate-consent.md). 

Su vykdomuoju sutikimo taisyklėmis segmento srityje kiekvienas segmentas informuoja apie sutikimo patikrinimo būklę ir taisykles. Jei leidžiami nepaisysimai, tam tikruose segmentuose išjungiamos numatytosios sutikimo taisyklės. Kiekvienas segmento kūrėjas gali įtraukti daugiau sutikimo taisyklių, papildančių numatytasias taisykles segmentui. 

## <a name="for-administrators"></a>Administratoriams

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmento generatorius su sutikimo taisyklės parinktimis.":::

**Norėdami išjungti numatytąsias sutikimo taisykles:**

1. **Pranešime apie sutikimo taisykles** pasirinkite **Peržiūrėti išsamią informaciją**. 

1. Nustatykite numatytasis **sutikimo taisykles** perjungti į **Išjungta**.

**Norėdami pridėti daugiau sutikimo taisyklių:**

1. **Pranešime apie sutikimo taisykles** pasirinkite **Peržiūrėti išsamią informaciją**. 

1. Pasirinkite **Įtraukti sutikimo taisykles** ir išplečiamajame išplečiamajame meniu Pasirinkti sutikimo duomenų tipą **pasirinkite** sutikimo taisyklę.

1. Pasirinkite **Įrašyti**, kad segmentui taikytumėte naują taisyklę.

## <a name="for-contributors"></a>Bendraautoriai

Norėdami sukurti segmentą be priverstinio sutikimo taisyklių, turite dirbti su administratoriumi, kad išjungtumėte juos savo segmente. Tačiau galite pridėti savo sutikimo taisykles prie segmentų, kuriuos valdote ir valdote.

Tai trijų žingsnių procesas: 
1. [Sukurkite segmentą](segments.md) auditorijos įžvalgose ir įrašykite jį. 

1. Bendrinkite segmento pavadinimą su administratoriumi ir paprašykite, kad jis įgalintų [segmento](activate-consent.md) nepaisus. 

1. Vėl atidarykite segmentus. **Pranešime apie sutikimo taisykles** pasirinkite **Peržiūrėti išsamią informaciją** ir įtraukti norimas taikyti sutikimo taisykles. **Tada įrašykite** ir **paleiskite** savo segmentą.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
