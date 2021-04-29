---
title: Eksportuoti „ Customer Insights“ duomenis į „Azure Blob“ talpyklą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Blob“ talpyklą.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760199"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmentų sąrašo ir kitų duomenų eksportavimas į „Azure Blob“ talpyklą (peržiūra)

Saugokite savo „Customer Insights“ duomenis „Blob“ saugykloje arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="set-up-the-connection-to-blob-storage"></a>Ryšio su „Blob“ talpyklą nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure Blob“ talpykla**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo „Blob“ talpyklos **paskyros pavadinimą**, **paskyros raktą** ir **talpyklą**.
    - Jei norite sužinoti daugiau apie „Blob“ talpyklos paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).
    - Norėdami sužinoti, kaip sukurti konteinerį, žr. [Konteinerio kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure Blob“ talpykla. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).     
Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Blob“ talpyklos saugykloje. Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:

- Šaltinio objektams ir objektams sukurtiems sistemos: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Eksportuotiems objektams model.json bus nurodytas %ExportDestinationName% lygiu
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
