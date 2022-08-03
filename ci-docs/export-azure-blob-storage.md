---
title: Duomenų eksportavimas į "Azure" didelių dvejetainių failų saugyklą (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į didelių dvejetainių objektų saugyklą.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195714"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Duomenų eksportavimas į "Azure" didelių dvejetainių failų saugyklą (peržiūra)

Saugokite savo „Customer Insights“ duomenis didelių dvejetainių objektų saugykloje arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Azure Blob" saugyklos paskyros](/azure/storage/blobs/create-data-lake-storage-account) pavadinimas ir paskyros raktas. Norėdami rasti pavadinimą ir raktą, žiūrėkite ["Azure" portalo saugyklos abonemento parametrų valdymas](/azure/storage/common/storage-account-manage).
- Azure [Blob saugyklos konteineris](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Žinomi apribojimai

- Jei naudojate "Azure" didelių dvejetainių objektų saugyklą, pasirinkite standartinį [našumą ir "Premium" našumo pakopą](/azure/storage/blobs/storage-blob-performance-tiers). Jei pasirinksite geriausio efektyvumo pakopą, pažymėkite [geriausio bloko didelių dvejetainių objektų kaip kliento tipą](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Ryšio su "Blob Storage" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **"Azure" didelių dvejetainių objektų saugykla**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite **Paskyros pavadinimą**, **Paskyros raktą** ir **Talpyklę** savo „Azure” didelių dvejetainių objektų saugyklai.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Norėdami sukonfigūruoti šį eksportavimą, turite turėti [šio ryšio tipo teises](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jei įjungėte ["Azure Blob Storage" paskyros minkštojo naikinimo parametrą](/azure/storage/blobs/soft-delete-blob-enable), eksportuoti nepavyks. Norėdami eksportuoti duomenis į didelius dvejetainius objektus, išjunkite negalutinio naikinimo funkciją.

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite Blob saugyklos aplanko pavadinimą.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksportuoti duomenys yra saugomi jūsų sukonfigūruotoje „Azure” didelių dvejetainių objektų saugyklos talpyklėje. Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:

- Šaltinio objektams ir objektams sukurtiems sistemos:  
  „*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*”  

  Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Eksportavus objektus, kuriuose yra daug duomenų, tame pačiame aplanke kiekvienam eksportui gali atsirasti keli CSV failai. Eksporto padalijimas vyksta dėl našumo priežasčių, kad būtų sumažintas laikas, per kurį eksportavimas užbaigiamas.

- Eksportuotų objektų model.json yra *%ExportDestinationName%* lygyje.  
  
  Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
