---
title: "\"Customer Insights\" duomenų eksportavimas į \"Autopilot\""
description: Sužinokite, kaip konfigūruoti ryšį su  "Autopilot".
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269248"
---
# <a name="connector-for-autopilot-preview"></a>"Autopilot" jungtis (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į "Autopilot" kontaktų sąrašus ir naudokite juos el. pašto rinkodarai naudojant "Autopilot". 

## <a name="prerequisites"></a>Būtinosios sąlygos

-   Turite [Autopilot abonementą ir atitinkamus](https://www.autopilothq.com/) administratoriaus kredencialus.
-   Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="connect-to-autopilot"></a>Prisijungti prie „AutoPilot“

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Dalyje **Autopilot**, pažymėkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Automatinio užbaigimo ryšio konfigūravimo sritis.":::

1. Įveskite savo **"Autopilot" API raktą**["Autopilot" API raktas](https://autopilot.docs.apiary.io/#).

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su Autopilot.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.: **Vardas** ar **Pavardė**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Primygtinai **rekomenduojame į "Autopilot" eksportuoti ne daugiau nei 100 000 klientų profilių**. 

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

## <a name="known-limitations"></a>Žinomi apribojimai

- "Autopilot" iš viso galima eksportuoti iki 100 000 profilių.
- Eksportavimas į Autopilot ribojamas segmentais.
- Iki 100 000 profilių eksportavimas į Autopilot gali užtrukti iki kelių valandų. 
- Profilių, kuriuos galite eksportuoti į Autopilot, skaičius yra priklausomas ir priklauso nuo jūsų sutarties su Autopilot.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis iš Dynamics 365 Customer Insights į Autopilot, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus Dynamics 365 Customer Insights duomenis, pvz.: asmeninius duomenis. "Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad Autopilot atitiktų privatumo arba saugos reikalavimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]