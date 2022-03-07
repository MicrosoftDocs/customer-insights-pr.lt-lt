---
title: Aktyvinti segmentų sutikimo taisykles
description: Atlikite šiuos veiksmus, kad susietumėte sutikimo duomenis ir suaktyvintumėte sutikimo patikrinimus auditorijos įžvalgose. Administratorius taip pat gali išjungti sutikimo patikrinimus.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4b55c82229b1a6189c0dd67d145386344286df8a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227503"
---
# <a name="activate-consent-rules"></a>Aktyvinti sutikimo taisykles

Sutikimo [centras (peržiūra)](../consent-management/overview.md) padeda suderinti sutikimo duomenis iš įvairių šaltinių. Naudokite vieningą *sutikimo* objektą, kad pritaikytumėte įsipareigojimų nevykdymo sutikimo patikrinimus. Importavus sutikimo duomenis į sutikimo centrą ir sukonfigūravus duomenų taisykles, *sutikimo* objektas automatiškai sinchronizuojamas su auditorijos įžvalgomis.

## <a name="enable-consent-checks"></a>Įjungti sutikimų tikrinimus

Su sutikimo duomenimis, importuotais į sutikimo centrą (peržiūrą) ir nustatytomis taisyklėmis, galite įgalinti sutikimo patikrinimus. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Sutikimo skirtukas auditorijos įžvalgų nustatymuose su suaktyvintais sutikimo duomenimis.":::

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Pasirinkite skirtuką **Sutikimas (peržiūra).**

1. **Skyriuje Įgalinti sutikimo patikrinimus** nustatykite visų sričių, kurias norite įgalinti, perjungimą į **Įjungti**.

1. **Pažymėkite žymės langelį Leisti nepaisyti numatytųjų sutikimo taisyklių**, kad pašalintumėte tam tikrame segmente vykdomą numatytuosius sutikimo patikrinimus. 

1. Išplečiamajame meniu pasirinkite, kur norite leisti nepaisyti.     

1. Skyriuje Susiejimas **su klientų profiliais** pasirinkite atributą, kuris naudojamas kaip identifikatorius sutikimo duomenims susieti su kliento duomenimis. Tikėtina, kad tai bus telefono numeris arba elektroninio pašto adresas. 

1. Norėdami taikyti parametrus, pasirinkite **Įrašyti**.

## <a name="disable-consent-checks"></a>Išjungti sutikimo patikrinimus

Norėdami nustoti naudoti sutikimo duomenis auditorijos įžvalgose, administratorius turi atitinkamai atnaujinti sistemos parametrus.

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Pasirinkite skirtuką **Sutikimas (peržiūra).**

1. Skyriuje **Įgalinti sutikimo patikrinimus** nustatykite perjungimą į **Išjungta**.

> [!TIP]
> Norėdami nustoti naudoti sutikimo valdymo galimybes, žr [...](../consent-management/system-settings.md).
