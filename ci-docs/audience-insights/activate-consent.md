---
title: Aktyvinti segmentų sutikimo taisykles
description: Atlikite šiuos veiksmus, kad susietumėte sutikimo duomenis ir suaktyvintumėte sutikimo patikrinimus auditorijos įžvalgose. Administratorius taip pat gali išjungti sutikimo patikrinimus.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 45899738d39bd5caa433e123f9fe59020e831998
ms.sourcegitcommit: 79b09498d1328e5551fb8684c44af1fb149f9881
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790786"
---
# <a name="activate-consent-rules"></a>Aktyvinti sutikimo taisykles

[Sutikimo centras (peržiūra)](../consent-management/overview.md) padeda suderinti sutikimo duomenis iš įvairių šaltinių. Naudokite vieningą *sutikimo* objektą, kad pritaikytumėte numatytuosius sutikimo patikrinimus. Importavus sutikimo duomenis į sutikimo centrą ir konfigūravus duomenų taisykles, *sutikimo* objektas automatiškai sinchronizuojamas su auditorijos įžvalgomis.

## <a name="enable-consent-checks"></a>Įjungti sutikimų tikrinimus

Su sutikimo duomenimis, importuotais į sutikimo centrą (peržiūra) ir nustatytomis taisyklėmis, galite įgalinti sutikimo patikrinimus. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Auditorijos įžvalgų nustatymų skirtukas Sutikimas su suaktyvintais sutikimo duomenimis.":::

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Pasirinkite **skirtuką Sutikimas (peržiūra).**

1. **Sekcijoje Įgalinti** sutikimo patikrinimus nustatykite **visų sričių, kurias norite įgalinti, perjungiklį** į Įjungta.

1. Pažymėkite **žymės langelį Leisti nepaisyti numatytųjų sutikimo** taisyklių, kad pašalintumėte numatytuosius sutikimo patikrinimus, vykdomi konkrečiame segmente. 

1. Išplečiamajame meniu pasirinkite vietą, kurioje norite leisti nepaisymus.     

1. **Sekcijoje Susieti sutikimą su klientų profiliais** pasirinkite atributą, kuris naudojamas kaip identifikatorius, kad susietumėte sutikimo duomenis su kliento duomenimis. Tai greičiausiai bus telefono numeris arba el. pašto adresas. 

1. Pasirinkite **·** Įrašyti, kad pritaikytumėte parametrus.

## <a name="disable-consent-checks"></a>Išjungti sutikimo patikrinimus

Norėdami nustoti naudoti sutikimo duomenis auditorijos įžvalgose, administratorius turi atitinkamai atnaujinti sistemos parametrus.

1. Publikos įžvalgose, eikite į **Administravimas** > **Sistema**.

1. Pasirinkite **skirtuką Sutikimas (peržiūra).**

1. **Sekcijoje Įgalinti sutikimo patikrinimus** nustatykite perjungiklį į **Išjungta**.
