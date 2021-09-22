---
title: Kurti ir modifikuoti patikslintus įvykius
description: Kaip kurti ir modifikuoti patikslintus įvykius.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034784"
---
# <a name="create-and-modify-refined-events"></a>Kurti ir modifikuoti patikslintus įvykius

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Įvykis yra duomenys, nurodantys vartotojo elgesį, pvz., veiklą svetainėje.

- *Pagrindinis* įvykis, kai vartotojas peržiūrės puslapį (peržiūrės įvykį) arba sąveikauja su turiniu (veiksmo įvykis).
- Patobulintas *įvykis* yra pagrindinio įvykio virtualusis rodinys. Tobulinti įvykiai apibrėžiami šalinant ir įtraukiant ypatybes arba filtruojant įvykius pagal ypatybių reikšmes.

Naudokite patikslintus įvykius siekiant sumažinti pagrindinio apimtį [eksportavimui](export-events.md) ar norėdami pašalinti ypatybes, kurios nebereikalingos rodyti.

## <a name="create-refined-events"></a>Sukurkite išdirbtus įvykius

Yra trys būdai iš pagrindinio įvykio sukurti patobulintą įvykį. 

1. Eikite į **Duomenys**> **Įvykiai** ir rinkitės vieną iš šių parinkčių:
    - Pasirinkite **Nauji įvykiai**, tada – **Kurti patobulintą įvykius**.
    - Pasirinkite pagrindinį įvykį, jei norite atidaryti išsamų rodinį, ir viršutiniame meniu pasirinkite **Kurti patobulintu įvykius**.
    - Rinkitės **Daugiau [...]** norėdami atidaryti trumposios komandos meniu pagrindiniam įvykiui. Tada pasirinkite **Kurti patobulintą įvykius**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Patobulintos įvykių kūrimo parinktys.":::

1. Dialogo lange **Kurti patobulintus įvykius** įveskite toliau nurodytą informaciją:

- Jei kuriate naują **įvykį, pažymėkite** jį išplečiamajame sąraše Pagrindiniai įvykiai.
- Laukelyje **Patobulintų įvykių rodomas pavadinimas** įveskite ryšio pavadinimą.
- Arba atnaujinkite siūlomą **faktinį pavadinimą** nenaudodami tarpų.

3. Pasirinkite **Kurti**, kad būtų taikomi jūsų parametrai.

1. Rafinuojamo įvykio išsamiame rodinyje pažymėkite **Įtraukti ir pašalinti ypatybes**, kad atidarytumėte sritį **Redaguoti ypatybes**. 

1. Naudodami žymės langelius, pažymėkite ypatybes, kurias norite matyti, ir tas, kurias norite slėpti. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Patobulinamų įvykių ypatybės redagavimas.":::

1. Pasirinkite **Patvirtinti**, kad pritaikyumėte savo pasirinkimą.

1. Pasirinkite **Įrašyti**, kad įrašytumėte konfigūravimą.

## <a name="edit-refined-events"></a>Redaguoti patobulintą įvykį

Galite keisti patobulintos įvykio pavadinimą ir ypatybes.

### <a name="edit-event-name"></a>Redaguoti įvykio pavadinimą

1. Eikite į **Duomenys** > **Įvykiai**. 
1. Pasirinkite **Daugiau [...]** įvykiui ir pasirinkite **Redaguoti pavadinimą**.
1. Atnaujinkite įvykio pavadinimą ir pasirinkite **Pervardyti**.

### <a name="edit-selected-properties"></a>Redaguoti pasirinktas ypatybes

1. Eikite į **Duomenys** > **Įvykiai** ir pasirinkite patobulintą įvykius, kad atidarytumėte išsamų rodinį.
1. Pažymėkite **Įtraukti ir šalinti ypatybes**. 
1. Redaguokite žymės langelių žymėjimą.
1. Pasirinkite **Patvirtinti**, tada **Įrašyti**, kad pakeitimai būtų pritaikyti.

Informacijos apie įvykių eksportavimą žr. [Įvykių eksportavimas](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
