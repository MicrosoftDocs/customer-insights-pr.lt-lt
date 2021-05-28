---
title: „Customer Insights“ duomenų eksportavimas į „Azure“ didelių dvejetainių objektų saugyklą
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į didelių dvejetainių objektų saugyklą.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976191"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmentų sąrašo ir kitų duomenų eksportavimas į „Azure“ didelių dvejetainių objektų saugyklą (peržiūros versija)

Saugokite savo „Customer Insights“ duomenis didelių dvejetainių objektų saugykloje arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="set-up-the-connection-to-blob-storage"></a>Ryšio su didelių dvejetainių objektų saugykla nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure” didelių dvejetainių objektų saugykla**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo „Azure” didelių dvejetainių objektų saugyklos **paskyros pavadinimą**, **paskyros raktą** ir **talpyklą**.
    - Jei norite sužinoti daugiau apie didelių dvejetainių objektų saugyklos paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).
    - Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).     
Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Azure” didelių dvejetainių objektų saugyklos talpyklėje. Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:

- Šaltinio objektams ir objektams sukurtiems sistemos: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Eksportuotiems objektams model.json bus nurodytas %ExportDestinationName% lygiu
  - Pavyzdys: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
