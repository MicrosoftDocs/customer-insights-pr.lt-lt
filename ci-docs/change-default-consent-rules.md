---
title: Tvarkyti numatytąsias sutikimo taisykles segmentuose
description: Turėdami sutikimo valdymo galimybę, galite išjungti arba pakeisti numatytąsias sutikimo taisykles, jei įgalinti nepaisymai.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643206"
---
# <a name="disable-or-change-default-consent-rules"></a>Išjungti arba keisti numatytąsias sutikimo taisykles

Jei jūsų organizacijos naudoja sutikimo [valdymo galimybes](consent-management/overview.md) su Dynamics 365 Customer Insights, [administratoriai gali įgalinti segmentų sutikimo taisykles](activate-consent.md). 

Taikant priverstinio sutikimo taisykles segmento srityje, kiekvienas segmentas informuoja apie sutikimo patikrinimo būklę ir taisykles. Jei leidžiami nepaisymai, numatytosios sutikimo taisyklės išjungiamos konkretiems segmentams. Kiekvienas segmento kūrėjas gali pridėti daugiau sutikimo taisyklių prie numatytųjų taisyklių segmente. 

## <a name="for-administrators"></a>Administratoriams

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Segmento daryklė su sutikimo taisyklės parinktimis.":::

**Norėdami išjungti numatytąsias sutikimo taisykles, atlikite toliau nurodytus veiksmus.**

1. Pranešime Sutikimo taisyklės pasirinkite **Peržiūrėti išsamią informaciją**.**·** 

1. Nustatykite numatytąsias **sutikimo taisykles**, kad pereitumėte į **Išjungta**.

**Norėdami įtraukti daugiau sutikimo taisyklių, atlikite toliau nurodytus veiksmus.**

1. Pranešime Sutikimo taisyklės pasirinkite **Peržiūrėti išsamią informaciją**.**·** 

1. Išplečiamajame sąraše Pasirinkti sutikimo duomenų tipą pasirinkite **Įtraukti sutikimo taisykles** ir pasirinkite sutikimo **taisyklę**.

1. Pasirinkite **Įrašyti**, jei norite taikyti naują taisyklę segmentui.

## <a name="for-contributors"></a>Bendraautoriams

Norėdami sukurti segmentą be priverstinio sutikimo taisyklių, turite dirbti su administratoriumi, kad juos išjungtumėte savo segmente. Tačiau galite pridėti savo sutikimo taisykles prie jums priklausančių ir valdomų segmentų.

Tai trijų etapų procesas: 
1. [Sukurkite segmentą](segments.md) "Customer Insights" ir įrašykite jį. 

1. Bendrinkite segmento pavadinimą su administratoriumi ir paprašykite jo įgalinti [segmento](activate-consent.md) nepaisymus. 

1. Dar kartą atidarykite segmentus. Pranešime Apie sutikimo **taisykles pasirinkite** Peržiūrėti išsamią informaciją **ir pridėkite sutikimo taisykles,** kurias norite taikyti. Tada įrašykite **ir** **paleiskite** segmentą.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
