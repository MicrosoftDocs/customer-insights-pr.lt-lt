---
title: "\"Customer Insights\" duomenų eksportavimas į \"InMobi\""
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į "InMobi".
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195898"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>"Customer Insights" duomenų eksportavimas į "InMobi" (peržiūra)

Eksportuokite segmentų sąrašus ar kitus duomenis iš "Customer Insights" egzemplioriaus į ["InMobi"](https://www.inmobi.com/).

## <a name="prerequisites"></a>Būtinosios sąlygos

- ["InMobi" paskyra](https://www.inmobi.com/) ir administratoriaus kredencialai.
- " [Azure Blob" saugyklos paskyros](/azure/storage/blobs/create-data-lake-storage-account) pavadinimas ir paskyros raktas. Norėdami rasti pavadinimą ir raktą, žiūrėkite ["Azure" portalo saugyklos abonemento parametrų valdymas](/azure/storage/common/storage-account-manage).
- " [Azure Blob Storage" konteineris](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container), skirtas eksportuoti "InMobi" duomenis į.
- "InMobi" sukurs tiesioginį ryšį su jūsų "Blob" saugykla ir sukonfigūruos automatinį jūsų duomenų importavimą į "InMobi". Susisiekite su savo "InMobi" atstovu, kad pradėtumėte procesą.

## <a name="known-limitations"></a>Žinomi apribojimai

- Jei naudojate "Azure" didelių dvejetainių objektų saugyklą, pasirinkite standartinį [našumą ir "Premium" našumo pakopą](/azure/storage/blobs/storage-blob-performance-tiers). Jei pasirinksite geriausio efektyvumo pakopą, pažymėkite [geriausio bloko didelių dvejetainių objektų kaip kliento tipą](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Ryšio su "Azure Blob Storage" nustatymas

[Nustatykite ryšį su "Azure" didelių dvejetainių objektų saugykla](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[Konfigūruokite eksportavimą](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
