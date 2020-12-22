---
title: Eksportuoti „ Customer Insights“ duomenis į „Azure Blob“ talpinimą
description: Sužinokite, kaip sukonfigūruoti ryšį su „Azure“ didelių dvejetainių objektų saugykla.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667149"
---
# <a name="connector-for-azure-blob-storage-preview"></a>„Azure“ didelių dvejetainių objektų saugyklos jungtis (peržiūra)

Talpinkite savo „ Customer Insights“ duomenis į „Azure Blob“ talpinimą ar naudokite jį jūsų duomenų perdavimui į kitas programas.

## <a name="configure-the-connector-for-azure-blob-storage"></a>„Azure“ didelių dvejetainių objektų saugyklos jungties konfigūravimas

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.

1. Dalyje **„Azure“ didelių dvejetainių objektų saugykla** pasirinkite **Nustatyti**.

1. Įveskite „Azure“ didelių dvejetainių objektų saugyklos **Kliento pavadinimą**, **Kliento raktą** ir **Konteinerį**.
    - Jei norite sužinoti daugiau apie tai, kaip rasti „Azure“ didelių dvejetainių objektų saugyklos kliento pavadinimą ir kliento raktą, žr. [Saugyklos kliento parametrų valdymas „Azure“ portale](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Norėdami sužinoti, kaip sukurti konteinerį, žr. [Konteinerio kūrimas](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.

1. Pasirinkite **Toliau**.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

Eksportuoti duomenys saugomi sukonfigūruotoje „Azure“ didelių dvejetainių objektų saugykloje. Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:

- Šaltinio objektams ir objektams sukurtiems sistemos: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Eksportuotų objektų modelis .json išliks lygiu %ExportDestinationName%
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](/export-destinations.md#export-data-on-demand). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).
