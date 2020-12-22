---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Sales“
description: Sužinokite, kaip sukonfigūruoti ryšį su „Dynamics 365 Sales“.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643828"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>„Dynamics 365 for Sales“ jungtis (peržiūra)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Naudokite savo klientų duomenis kurdami rinkodaros sąrašus, vykdydami darbo eigas ir siųsdami pasiūlymus su „Dynamics 365 Sales“.

## <a name="prerequisite"></a>Būtinoji sąlyga

Kontaktiniai įrašai [iš „Dynamics 365 Sales“ suvartotos naudojant „Common Data Service“](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>„Sales“ jungties konfigūravimas

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.

1. Srityje **„Dynamics 365 Sales“** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

1. Lauke **Serverio adresas** įveskite savo organizacijos „Sales“ URL.

1. Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Sales“ klientą.

1. Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.

1. Pasirinkite **Toliau**.

1. Pasirinkite vieną ar daugiau segmentų.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).
