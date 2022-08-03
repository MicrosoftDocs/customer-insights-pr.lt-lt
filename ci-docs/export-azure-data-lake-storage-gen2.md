---
title: Duomenų eksportavimas į Azure Data Lake Storage Gen2 (peržiūra)
description: Sužinokite, kaip konfigūruoti ryšį su „Azure Data Lake Storage Gen2”.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196450"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Duomenų eksportavimas į Azure Data Lake Storage Gen2 (peržiūra)

Saugokite savo „Customer Insights“ duomenis saugykloje „Azure Data Lake Storage Gen2“ paskyros arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Saugyklos [paskyra, kurią galima naudoti su "Azure Data Lake Gen2"](/azure/storage/blobs/create-data-lake-storage-account). Norėdami rasti saugyklos abonemento pavadinimą ir raktą, žiūrėkite [Saugyklos abonemento parametrų valdymas "Azure" portale](/azure/storage/common/storage-account-manage).
- Azure [Blob saugyklos konteineris](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Žinomi apribojimai

- Jei naudojate Azure Data Lake Storage "Gen2", pasirinkite standartinį [našumą ir "Premium" našumo pakopą](/azure/storage/blobs/create-data-lake-storage-account). Jei pasirinksite geriausio efektyvumo pakopą, pažymėkite [geriausio bloko didelių dvejetainių objektų kaip kliento tipą](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Ryšio su Azure Data Lake Storage Gen2 nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Azure Data Lake Gen 2**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite **Paskyros vardą**, **Kliento raktą** ir **Konteinerį** savo „Azure Data Lake Storage Gen2”.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. **Lauke Ryšys eksportavimui** pasirinkite ryšį iš sekcijos Azure Data Lake. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite Gen2 saugyklos aplanko pavadinimą Azure Data Lake Storage.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Azure Data Lake Gen 2“ talpyklos saugykloje.

> [!TIP]
> Eksportavus objektus, kuriuose yra daug duomenų, tame pačiame aplanke kiekvienam eksportui gali atsirasti keli CSV failai. Eksporto padalijimas vyksta dėl našumo priežasčių, kad būtų sumažintas laikas, per kurį eksportavimas užbaigiamas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
