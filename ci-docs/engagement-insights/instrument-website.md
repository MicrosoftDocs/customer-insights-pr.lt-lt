---
title: Įtraukti kodą į savo svetainę
description: Kaip įtraukti naują kodo fragmentas įrašyti įvykius svetainėje.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035104"
---
# <a name="install-the-code-snippet-on-a-website"></a>Įdiegti kodo fragmentą svetainėje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šiame straipsnyje aprašoma, kaip administratorius įdiegia kodo fragmentas svetainėje. Po to, kai į svetainę įtrauksite scenarijų, darbo srityje galėsite pradėti rodyti įvykius. Daugiau informacijos žr. [Tvarkyti darbo sritis ir aplinką](manage-environments-workspaces.md). Norėdami įrašyti įvykius mobiliųjų įrenginių programose, [žr. Kūrėjų išteklių apžvalga](developer-resources.md).


### <a name="prerequisites"></a>Būtinosios sąlygos

* Darbo srityje turite turėti administratoriaus teises duomenims saugoti.
* Jūsų svetainė ar projektas turi būti nuomojami internete, kad būtų galima siųsti veiklos duomenis. Serveris nepripažįsta duomenų, išsiųstų iš vietinio failo.


## <a name="add-code-to-your-website"></a>Įtraukti kodą į savo svetainę
1.  Eikite į **Administratorius** > **Darbo sritis**  ir rinkitės **Diegimo vadovą**.
1. Pažymėkite **Kopijuoti kodą**, jei norite kopijuoti kodo fragmentas. Pagal numatytuosius nustatymus jūsų darbo srities prarijimo raktas yra įtrauktas į kodo fragmentas.
:::image type="content" source="media/copy-code.png" alt-text="Kodo fragmento puslapio ekrano kopija.":::
3. Nukopijuotų duomenų kodo fragmentas į svetainę, šalia <head> žymės ir prieš bet kokį kitą scenarijų ar CSS žymas.
4.  Publikuokite atnaujintą svetainę ir palaukite kelias minutes, kad užfiksuotumėte gaunamą žiniatinklio srautą.
5.  Norėdami peržiūrėti savo duomenis, naršymo srityje pasirinkite darbo sritį iš darbo srities perjungimo įrenginio. Tada pasirinkite vieną iš ataskaitų skyriuje **Atrasti**.

## <a name="configuration-options"></a>Konfigūracijos parinktys

Šioje konfigūracijoje galite keisti šias kodo fragmentas:

- **prarijimo raktas** : prarijimo raktas, naudojamas siųsti įvykius į darbo sritį. Galite pakeisti kodavimo raktą, kad nusiųstumėte įvykius į kitą darbo sritį. Kodavimo raktas yra unikalus kiekvienai darbo sričiai. 
- **automatinis fiksavimas**: nurodo, ar įrašyti puslapio rodiniai ir veiksmai su svetaine. Jame yra dvi parinktys:
    - **rodinys**: nustatyta kaip teisinga norint įrašyti puslapio *rodinius*. Puslapio rodiniai įrašomi kaip *rodinio* [įvykiai](glossary.md#event), pagrindinio [įvykio tipas](glossary.md#base-event).
    - **spustelėkite**: nustatyta kaip *teisinga*, kad žiniatinklio svetainėje būtų užfiksuotas lankytojo bendravimas. Sąveikos apimamos kaip *Veiksmų* [įvykiai](glossary.md#event), pagrindinio [įvykio tipas](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
