---
title: Segmentų sutikimo taisyklių aktyvinimas
description: Atlikite šiuos veiksmus, kad susietumėte sutikimo duomenis ir suaktyvintumėte sutikimo patikrinimus Dynamics 365 Customer Insights. Administratorius taip pat gali išjungti sutikimo patikrinimus.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755180"
---
# <a name="activate-consent-rules"></a>Aktyvinti sutikimo taisykles

Sutikimo [centras (peržiūra)](consent-management/overview.md) padeda suderinti sutikimo duomenis iš įvairių šaltinių. Naudokite vieningą *sutikimo* objektą, kad pritaikytumėte numatytuosius sutikimo patikrinimus. Importavus sutikimo duomenis ir konfigūravus žemėlapio *taisykles, objektas Sutikimas* automatiškai sinchronizuojamas su Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Įjungti sutikimų tikrinimus

Su sutikimo duomenimis, importuotais į sutikimo centrą (peržiūra) ir nustatytomis taisyklėmis, galite įgalinti sutikimo patikrinimus. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="&quot;Customer Insights&quot; parametrų skirtukas Sutikimas su suaktyvintais sutikimo duomenimis.":::

1. Programoje „Customer Insights” eikite į **Administratorius** > **Sistema**.

1. Pasirinkite skirtuką **Sutikimas (peržiūra).**

1. Skyriuje Įgalinti sutikimo **patikrinimus** nustatykite perjungimą į **Įjungta** visoms sritims, kurias norite įgalinti.

1. **Pažymėkite žymės langelį Leisti nepaisyti numatytųjų sutikimo taisyklių**, kad pašalintumėte numatytuosius sutikimo patikrinimus, vykdomus tam tikrame segmente. 

1. Išplečiamajame meniu pasirinkite, kur norite leisti nepaisyti.     

1. Skyriuje Sutikimas **su klientų profiliais** saitas pasirinkite atributą, kuris naudojamas kaip identifikatorius, kad susietų sutikimo duomenis su kliento duomenimis. Tai gali būti telefono numeris arba el. Pašto adresas. 

1. Pasirinkite **Įrašyti**, kad pritaikytumėte parametrus.

## <a name="disable-consent-checks"></a>Išjungti sutikimo patikrinimus

Norėdamas nustoti naudoti sutikimo duomenis "Customer Insights", administratorius turi atitinkamai atnaujinti sistemos parametrus.

1. Programoje „Customer Insights” eikite į **Administratorius** > **Sistema**.

1. Pasirinkite skirtuką **Sutikimas (peržiūra).**

1. Skyriuje Įgalinti sutikimo **patikrinimus** nustatykite perjungimą į **Išjungta**.

> [!TIP]
> Norėdami nustoti naudoti sutikimo valdymo galimybę, žr [...](consent-management/system-settings.md).
