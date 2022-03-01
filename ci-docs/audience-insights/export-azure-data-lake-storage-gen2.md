---
title: "\"Customer Insights\" duomenų eksportavimas į Azure Data Lake Storage \"Gen2\""
description: Sužinokite, kaip konfigūruoti ryšį su Azure Data Lake Storage "Gen2".
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477189"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage"Gen2" jungtis (peržiūra)

Saugokite savo „Customer Insights“ duomenis saugykloje Azure Data Lake Storage "Gen 2" arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage "Gen2" jungties konfigūravimas

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.

1. Dalyje **Azure Data Lake Storage "Gen2"** pažymėkite **Nustatyti**.

1. Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.

1. Įveskite **Paskyros vardą**, **Kliento raktą** ir **Konteinerį** savo Azure Data Lake Storage Gen2.
    - Norėdami sužinoti, kaip sukurti saugyklos paskyrą su Azure Data Lake Storage "Gen2", [žr. Saugyklos paskyros](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account) kūrimas. 
    - Jei norite sužinoti daugiau apie tai, kaip rasti "Azure Data Lake Gen2" saugyklos kliento pavadinimą ir kliento raktą, [žr. Saugyklos paskyros parametrų valdymas "Azure" portale](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Pasirinkite **Toliau**.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md#export-data-on-demand). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).
