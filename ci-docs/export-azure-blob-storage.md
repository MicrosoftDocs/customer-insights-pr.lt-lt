---
title: „Customer Insights“ duomenų eksportavimas į „Azure“ didelių dvejetainių objektų saugyklą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į didelių dvejetainių objektų saugyklą.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 623926bf520b19ee4156b7a05e953241cd819e9e
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947148"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmentų sąrašo ir kitų duomenų eksportavimas į „Azure“ didelių dvejetainių objektų saugyklą (peržiūros versija)

Saugokite savo „Customer Insights“ duomenis didelių dvejetainių objektų saugykloje arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="known-limitations"></a>Žinomi apribojimai

1. Jei naudojate „Azure Blob Storage" didelių dvejetainių objektų saugyklą , galite pasirinkti iš  [Standartinės ir geriausio efektyvumo pakopos](/azure/storage/blobs/storage-blob-performance-tiers). Jei pasirinksite geriausio efektyvumo pakopą, pažymėkite [geriausio bloko didelių dvejetainių objektų kaip kliento tipą](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Ryšio su Didelių dvejetainių objektų saugykla nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure” didelių dvejetainių objektų saugykla**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite **Paskyros pavadinimą**, **Paskyros raktą** ir **Talpyklę** savo „Azure” didelių dvejetainių objektų saugyklai.
    - Jei norite sužinoti daugiau apie didelių dvejetainių objektų „Storage“ paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).
    - Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jei įjungėte negalutinio naikinimo parametrą „Azure” didelių dvejetainių objektų saugyklai, eksportavimai nepavyks. Norėdami eksportuoti duomenis į didelius dvejetainius objektus, išjunkite negalutinio naikinimo funkciją. Daugiau informacijos rasite [Didelių dvejetainių objektų negalutinio naikinimo įgalinimas](/azure/storage/blobs/soft-delete-blob-enable)

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla. Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).

Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).

Eksportuoti duomenys yra saugomi jūsų sukonfigūruotoje „Azure” didelių dvejetainių objektų saugyklos talpyklėje. Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:

- Šaltinio objektams ir objektams sukurtiems sistemos:  
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > Objektų, kuriuose yra daug duomenų, eksportavimas gali sukelti kelis CSV failus tame pačiame aplanke kiekvienam eksportavimui. Eksporto skaidymas vyksta dėl našumo priežasčių, kad būtų sumažintas laikas, kurio reikia eksportui užbaigti.

- Eksportuotiems objektams model.json bus nurodytas %ExportDestinationName% lygiu.  
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
