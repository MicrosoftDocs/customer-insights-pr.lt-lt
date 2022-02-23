---
title: Aktyvinti segmentų sutikimo taisykles
description: Atlikite šiuos veiksmus, kad susietumėte sutikimo duomenis ir suaktyvintumėte sutikimo patikrinimus auditorijos įžvalgose. Administratorius taip pat gali išjungti sutikimo patikrinimus.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884084"
---
# <a name="activate-consent-rules"></a>Aktyvinti sutikimo taisykles

[Sutikimo centras (peržiūra)](../consent-management/overview.md) padeda suderinti sutikimo duomenis iš įvairių šaltinių. Naudokite vieningą *sutikimo* objektą, kad taikytumėte numatytuosius sutikimo patikrinimus. Į kontaktų centrą importavus sutikimo duomenis ir sukonfigūravus duomenų taisykles, *sutikimo* objektas automatiškai sinchronizuojamas su auditorijos įžvalgomis.

## <a name="enable-consent-checks"></a>Įjungti sutikimų tikrinimus

Naudodami sutikimo duomenis, importuotus į sutikimo centrą (peržiūrą) ir nustatytas taisykles, galite įgalinti sutikimo patikrinimus. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Sutikimo skirtukas auditorijos įžvalgų nustatymuose su suaktyvintais sutikimo duomenimis.":::

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Pasirinkite **skirtuką Sutikimas** (peržiūra).

1. **Sekcijoje Įgalinti sutikimo patikrinimus** nustatykite perjungimą į **Įjungti** visose srityse, kurias norite įgalinti.

1. Pažymėkite **žymės langelį Leisti nepaisyti numatytųjų sutikimo** taisyklių, kad pašalintumėte numatytuosius sutikimo patikrinimus, vykdomus konkrečiame segmente. 

1. Išplečiamajame meniu pasirinkite, kur norite leisti nepaisymus.     

1. **Skyriuje Ryšys su klientų profiliais** pasirinkite atributą, kuris naudojamas kaip identifikatorius, kad sutikimo duomenys būtų susieti su kliento duomenimis. Tikėtina, kad tai bus telefono numeris arba elektroninio pašto adresas. 

1. Pasirinkite **Įrašyti**, kad pritaikytumėte parametrus.

## <a name="disable-consent-checks"></a>Išjungti sutikimo patikrinimus

Norėdami nustoti naudoti sutikimo duomenis auditorijos įžvalgose, administratorius turi atitinkamai atnaujinti sistemos parametrus.

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Pasirinkite **skirtuką Sutikimas** (peržiūra).

1. **Skyriuje Įgalinti sutikimo patikrinimus** nustatykite perjungimą į **Išjungta**.

> [!TIP]
> Norėdami nustoti naudoti sutikimo valdymo galimybes, [žr](../consent-management/system-settings.md).
