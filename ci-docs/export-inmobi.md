---
title: "\"Customer Insights\" duomenų eksportavimas į \"InMobi\""
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į "InMobi".
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059614"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segmentų sąrašo ir kitų duomenų eksportavimas į "InMobi" (peržiūra)

Eksportuokite segmentų sąrašus ar kitus duomenis iš "Customer Insights" egzemplioriaus į ["InMobi"](https://www.inmobi.com/).

## <a name="prerequisites"></a>Būtinosios sąlygos

1. Turite ["InMobi" paskyrą](https://www.inmobi.com/) ir administratoriaus kredencialus.
1. Turite "Azure Blob" saugyklos paskyros pavadinimą ir atitinkamą paskyros raktą. Daugiau informacijos ieškokite [Saugyklos abonemento parametrų valdymas "Azure" portale](/azure/storage/common/storage-account-manage). Saugojimo paskyroje yra konteineris, į kurį galima eksportuoti "Mobi" duomenis. Daugiau informacijos ieškokite [Konteinerio kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. "InMobi" sukurs tiesioginį ryšį su jūsų "Blob" saugykla ir sukonfigūruos automatinį jūsų duomenų importavimą į "InMobi". Susisiekite su savo "InMobi" atstovu, kad pradėtumėte procesą.

## <a name="known-limitations"></a>Žinomi apribojimai

1. "Azure" didelių dvejetainių objektų saugykloje galite pasirinkti standartinį [našumą ir "Premium" našumo pakopą](/azure/storage/blobs/storage-blob-performance-tiers). Jei pasirinksite geriausio efektyvumo pakopą, pažymėkite [geriausio bloko didelių dvejetainių objektų kaip kliento tipą](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Ryšio su "Azure" didelių dvejetainių objektų saugykla nustatymas ir eksportavimo konfigūravimas

1. Vykdykite instrukcijas, kad nustatytumėte [ryšį su "Azure" didelių dvejetainių objektų saugykla](export-azure-blob-storage.md).
2. Vykdykite eksportavimo konfigūravimo [instrukcijas](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
