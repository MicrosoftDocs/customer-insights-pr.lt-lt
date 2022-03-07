---
title: Kurti ir keisti įvykius
description: Kaip kurti ir modifikuoti įvykius.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228213"
---
# <a name="create-and-modify-events"></a>Kurti ir keisti įvykius

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Įvykis yra duomenys, nurodantys vartotojo elgesį, pvz., veiklą svetainėje.

- *Pagrindinis* įvykis, kai vartotojas peržiūrės puslapį (peržiūrės įvykį) arba sąveikauja su turiniu (veiksmo įvykis).
- Patobulintas *įvykis* yra pagrindinio įvykio virtualusis rodinys. Tobulinti įvykiai apibrėžiami šalinant ir įtraukiant ypatybes arba filtruojant įvykius pagal ypatybių reikšmes.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norėdami kurti įvykius, prijunkite savo svetainės duomenis prie įtraukimo įžvalgų naudodami paprastą kodo fragmentą. Daugiau informacijos žr. [Žiniatinklio SDK diegimas svetainėje](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Pirmiausia prijunkite savo duomenis.":::

## <a name="create-refined-events"></a>Kurti patikslintus įvykius

Naudokite patikslintus įvykius siekiant sumažinti pagrindinio apimtį [eksportavimui](export-events.md) ar norėdami pašalinti ypatybes, kurios nebereikalingos rodyti.

> [!NOTE]
> Į svetainę įtraukę žiniatinklio SDK, galite peržiūrėti savo bazės įvykius ir kurti patobulintą įvykius. 

Norėdami peržiūrėti savo pagrindinę įvykius:

1. Eikite į **Duomenys** kairiojoje naršymo srityje.

1. Pažymėkite **Įvykiai**, kad darbo srityje būtų rodomas visų įvykių sąrašas.

    :::image type="content" source="media/data-events.png" alt-text="Peržiūrėti įvykius.":::

Jei norite kurti patobulintą įvykį iš pagrindinio įvykio: 

1. Eikite į **Duomenys** > **įvykiai** ir rinkitės **+ Nauji įvykiai** ekrano viršuje.

1. Dialogo lange **Nauji įvykiai** lauką ir rinkitės **Kurti patobulintus įvykius** ir tada pažymėkite **Kitas**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Naujo įvykių vedlio kūrimas.":::
     
1. Dialogo **lange Nauji** įvykiai įveskite šią informaciją:

   - Pažymėkite įvykį **išplečiamajame sąraše** Pagrindiniai įvykiai.
   - Laukelyje **Patobulintų įvykių rodomas pavadinimas** įveskite ryšio pavadinimą.
   - Arba atnaujinkite siūlomą **faktinį pavadinimą** nenaudodami tarpų.

1. Pasirinkite **Kurti**, kad būtų taikomi jūsų parametrai.

Dabar patobulintas įvykis bus rodomas jūsų **įvykių** sąraše.

### <a name="edit-event-name"></a>Redaguoti įvykio pavadinimą

Galite keisti pagrindinio arba patikslintame įvykyje pavadinimą ir ypatybes.

1. Eikite į **Duomenys** > **Įvykiai**. 

1. Pasirinkite **Daugiau [...]** įvykiui ir pasirinkite **Redaguoti pavadinimą**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Patobulintos įvykių kūrimo parinktys.":::

3. Atnaujinkite įvykio pavadinimą ir pasirinkite **Pervardyti**.

### <a name="view-the-details-of-a-refined-event"></a>Peržiūrėkite patobulintą įvykį:

1. Įvykių **sąraše** pažymėkite pagrindinį arba patobulintą įvykį. 

1. Ekrano **viršuje pasirinkite Įtraukti** arba pašalinti ypatybes, kad atidarytumėte sritį **Redaguoti ypatybes**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Įtraukti ir pašalinti ypatybes.":::

1. Naudodami žymės langelius, pažymėkite ypatybes, kurias norite matyti, ir tas, kurias norite slėpti. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Patobulinamų įvykių ypatybės redagavimas.":::

1. Pasirinkite **Patvirtinti**, kad pritaikytumėte savo pasirinkimą, tada pasirinkite **Įrašyti**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Redaguoti parinktas patikslintas įvykio ypatybes

1. Eikite į **Duomenys** > **Įvykiai** ir pasirinkite patobulintą įvykius, kad atidarytumėte išsamų rodinį.
1. Pažymėkite **Įtraukti ir šalinti ypatybes**. 
1. Redaguokite žymės langelių žymėjimą.
1. Pasirinkite **Patvirtinti**, tada **Įrašyti**, kad pakeitimai būtų pritaikyti.

Informacijos apie įvykių eksportavimą žr. [Įvykių eksportavimas](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
