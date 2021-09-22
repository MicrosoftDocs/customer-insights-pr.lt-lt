---
title: Eksportuoti patobulintą įvykį
description: Kaip eksportuoti patobulintą įvykius ir bazės įvykius.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032395"
---
# <a name="export-events"></a>Eksportuoti įvykius

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Įvykis atitinka vartotojo elgseną. Jis įrašo, kai vartotojas peržiūrės puslapį (peržiūrės įvykį) arba sąveikauja su turiniu (veiksmo įvykis). Kai nuspręsite, kurias duomenų, kuriuos norite rodyti ataskaitoje, ypatybes, šis virtualus duomenų rodinys vadinamas *patobulintą įvykį*. 

- Įvykius ir patobulintą įvykius galite eksportuoti į išorinę saugyklą. 
- Eksportuojami išankstiniai duomenų srautai. Negalite iš naujo pakeisti srauto. 
- Eksportuojamos fiksuotos schemos. Jei į įvykį įtrauksite pasirinktinių ypatybės, jos nebus įtrauktos. Turėsite sukurti naują eksportavimą.

## <a name="prerequisites"></a>Būtinosios sąlygos

Prieš nustatydami eksportavimą turite turėti prieigą ir aktyvią „Azure" portalo prenumeratą. Eksportavimo proceso metu jums reikės saugyklos kliento informacijos. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Kurti „Azure Data Lake Storage Gen 2“ paskyras

1. Prisijunkite prie „Azure" portalo ir [sukurkite naują saugyklos paskyrą](/azure/storage/common/storage-account-create). 

1. Įsitikinkite, kad įjungę **hierarchinę vardų** sritį skirtuke **Išplėstinis**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Įjungti hierarchijos pavadinimų tarpus papildomame skirtuke":::

1. Įdiegę, eikite į naujai sukurtą saugyklos abonementą. Naršymo srityje pasirinkite **Nustatymai** > **Prieigos raktai**. 

1. Nukopijuokite **abonemento pavadinimą** ir **raktą**, kad juos naudosite kurdami naują eksportavimą.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Prieigos raktai talpyklos paskyroje.":::

## <a name="export-events"></a>Eksportuoti įvykius

Yra du būdai eksportuoti įvykius: 
- Nueikite į **Duomenys** > **Eksportavimai** ir pasirinkite **Naujas eksportavimas**.
- Eikite į  **Duomenys** > **Įvykiai**, pasirinkite **Daugiau [...]** šalia įvykio, kurį norite **eksportuoti** išplečiamajame meniu. 

Valdote eksportavimo kūrimo veiksmus:

1. Pateikti **eksportavimo pavadinimą**.

1. Žymėjimo **įvykių išplečiamajame** sąraše pasirinkite į eksportavimą įtraukti pasirinktus įvykius ir įvykius. 

1. Dalyje **Failo struktūra pažymėkite** atminties struktūrą ir paskirties saugykloje sukurkite naujų failų. Atvykus įvykiai eksportuojami nuolat.

1. Pažymėkite eksportavimo formatą. Galite pasirinkti **„Common Data Model“**, **CSV** ir **JSON**. Jei norite naudoti eksportavimą su kitomis „Dynamics 365" programomis, rekomenduojame naudoti „Common Data Model" formatą.

1. Veiksme **Pasirinkti paskirtį** nurodykite „Azure Data Lake Storage Gen 2“ vietą.
    1. **„ADLS Gen 2“ kliento pavadinimas** yra saugyklos abonemento, į kurį norite įrašyti eksportavimą, pavadinimas. 
    1. **Aplanko kelias** apibrėžia, kur eksportavimas turi būti saugomas failų sistemoje ir saugyklos abonemento katalogų struktūroje.
    1. **Bendrintą raktą** galima pasiekti naudojant saugyklos paskyros „Azure" portalą.

1. Peržiūrėti ir patvirtinti savo pasirinkimus.

## <a name="view-and-manage-exports"></a>Peržiūrėti ir valdyti eksportavimus

Kai nustatėte eksportavimą, eikitė į **Duomenys** > **Eksportavimai** norėdami peržiūrėti. Rinkitės **Daugiau [...]** iš bet kurio esančio eksportavimo norėdami redaguoti ar naikinti.


[!INCLUDE[footer-include](../includes/footer-banner.md)]