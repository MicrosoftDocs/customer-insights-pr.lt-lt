---
title: Įtraukti kodą į savo svetainę
description: Kaip įtraukti naują kodo fragmentas „Dynamics 365 Customer Insights“ įrašyti įvykius svetainėje.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231032"
---
# <a name="install-the-web-sdk-on-a-website"></a>Žiniatinklio SDK diegimas svetainėje

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Šiame straipsnyje aprašoma, kaip administratorius įdiegia žiniatinklio programinės įrangos kūrimo priemonių rinkinį (SDK) svetainėje. Įvykius darbo srityje pradėsite matyti netrukus po to, kai atnaujinsite svetainę. Daugiau informacijos žr. [Tvarkyti darbo sritis ir aplinką](manage-environments-workspaces.md). Norėdami įrašyti įvykius mobiliųjų įrenginių programose, [žr. Kūrėjų išteklių apžvalga](developer-resources.md).


### <a name="prerequisites"></a>Būtinosios sąlygos

* Darbo srityje turite turėti administratoriaus teises duomenims saugoti.
* Jūsų svetainė ar projektas turi būti nuomojami internete, kad būtų galima siųsti veiklos duomenis. Serveris nepripažįsta duomenų, išsiųstų iš vietinio failo.


## <a name="add-web-sdk-to-your-website"></a>Įtraukti žiniatinklio SDK į savo sveatinę

Eikite į **Administratorius** > **Darbo sritis**  ir rinkitės **Diegimo vadovą**. Toliau nurodytos dvi galimos parinktys įdiegti žiniatinklio SDK. Pirmiausia reikia naudoti atsisiuntimo saitą, o antra – įdiegti mazgo paketo tvarkytuvo (NPM) paketą.

### <a name="option-1-using-the-download-link"></a>1 parinktis: Atsisiuntimo saito naudojimas

1. Pažymėkite **Kopijuoti kodą**, jei norite kopijuoti kodo fragmentas. Pagal numatytuosius nustatymus jūsų darbo srities prarijimo raktas yra įtrauktas į kodo fragmentas.
  :::image type="content" source="media/copy-code.png" alt-text="Kodo fragmento puslapio ekrano kopija.":::

1. Į svetainę įtraukite nukopijuotą kodą, prie <head> žymės ir prieš bet kokį kitą scenarijų ar CSS žymas.
1. Publikuokite atnaujintą svetainę ir palaukite kelias minutes, kad užfiksuotumėte gaunamą žiniatinklio srautą.
1. Norėdami peržiūrėti savo duomenis, naršymo srityje pasirinkite darbo sritį iš darbo srities perjungimo įrenginio. Tada pasirinkite vieną iš ataskaitų skyriuje **Atrasti**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2 parinktis: naudoti NPM paketą (rekomenduojama „JavaScript" pagrįstoms žiniatinklio programoms)

1. Eikite į mūsų [NPM tinklalapį](https://www.npmjs.com/package/engagementinsights-web) ir vadovaukitės instrukcijomis, kaip įdiegti ir nustatyti žiniatinklio SDK NPM paketą.
1. Publikuokite atnaujintą svetainę ir palaukite kelias minutes, kad užfiksuotumėte gaunamą žiniatinklio srautą.
1. Norėdami peržiūrėti savo duomenis, naršymo srityje pasirinkite darbo sritį iš darbo srities perjungimo įrenginio. Tada pasirinkite vieną iš ataskaitų skyriuje **Atrasti**.

## <a name="configuration-options"></a>Konfigūracijos parinktys

Šioje konfigūracijoje galite keisti šias kodo fragmentas:

- **prarijimo raktas** : prarijimo raktas, naudojamas siųsti įvykius į darbo sritį. Galite pakeisti kodavimo raktą, kad nusiųstumėte įvykius į kitą darbo sritį. Kodavimo raktas yra unikalus kiekvienai darbo sričiai.
- **automatinis fiksavimas**: nurodo, ar įrašyti puslapio rodiniai ir veiksmai su svetaine. Jame yra dvi parinktys:
    - **rodinys**: nustatyta kaip teisinga norint įrašyti puslapio *rodinius*. Puslapio rodiniai įrašomi kaip *rodinio* [įvykiai](glossary.md#event), pagrindinio [įvykio tipas](glossary.md#base-event).
    - **spustelėkite**: nustatyta kaip *teisinga*, kad žiniatinklio svetainėje būtų užfiksuotas lankytojo bendravimas. Sąveikos apimamos kaip *Veiksmų* [įvykiai](glossary.md#event), pagrindinio [įvykio tipas](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
