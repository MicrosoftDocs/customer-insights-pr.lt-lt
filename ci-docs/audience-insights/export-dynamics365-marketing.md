---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Marketing“
description: Sužinokite, kaip sukonfigūruoti ryšį su „Dynamics 365 Marketing“.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643783"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>„Dynamics 365 for Marketing“ jungtis (peržiūra)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Naudokite [segmentus](segments.md) tam, kad sukurtumėte kampanijas ir susisiektumėte su konkrečiomis klientų grupėmis su „Dynamics 365 Marketing“. Daugiau informacijos žr. [Segmentų naudojimas iš „Dynamics 365 Customer Insights“ su „Dynamics 365 Marketing“](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Būtinoji sąlyga

Kontaktiniai įrašai [iš „Dynamics 365 Marketing“ suvartotos „Common Data Service“](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>„Marketing“ jungties konfigūravimas

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.

1. Srityje **„Dynamics 365 Marketing“** pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

1. Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.

1. Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.

1. Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.

1. Pasirinkite **Toliau**.

1. Pasirinkite vieną ar daugiau segmentų.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).
