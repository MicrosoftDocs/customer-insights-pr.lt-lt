---
title: „Customer Insights” duomenų eksportavimas į „Azure Data Lake Storage Gen2”
description: Sužinokite, kaip konfigūruoti ryšį su „Azure Data Lake Storage Gen2”.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cc0b3aac11a33facc366e9c57071d1fb8be4ecc4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231684"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Segmentų sąrašo ir kitų duomenų eksportavimas į „Azure Data Lake Storage Gen2" (peržiūra)

Saugokite savo „Customer Insights“ duomenis saugykloje „Azure Data Lake Storage Gen2“ paskyros arba naudokite ją norėdami perkelti duomenis į kitas programas.

## <a name="known-limitations"></a>Žinomi apribojimai

1. Kai kuriate „Azure Data Lake Storage Gen2" duomenų saugyklos paskyrą, galite rinktis [ iš standartinės efektyvumo ir geriausio efektyvumo pakopos](/azure/storage/blobs/create-data-lake-storage-account). Jei pasirinksite geriausio efektyvumo pakopą, pažymėkite geriausio bloko didelių dvejetainių objektų kaip kliento tipą. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Nustatyti ryšį su „Azure Data Lake Storage Gen2“ 


1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure Data Lake Gen 2“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite **Paskyros vardą**, **Kliento raktą** ir **Konteinerį** savo „Azure Data Lake Storage Gen2”.
    - Norėdami sužinoti, kaip sukurti saugyklos paskyrą su „Azure Data Lake Storage Gen2”, žr. [Saugyklos paskyros kūrimas](/azure/storage/blobs/create-data-lake-storage-account). 
    - Jei norite sužinoti daugiau apie „Azure Data Lake Gen2“ talpyklos paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys su eksportavimu** pasirinkite ryšį iš laukelio **„Azure Data Lake“**. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pažymėkite laukelį šalia kiekvieno objekto, kurį norite eksportuoti į šią paskirties vietą.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

Eksportuoti duomenys saugomi jūsų sukonfigūruotoje „Azure Data Lake Gen 2“ talpyklos saugykloje. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
