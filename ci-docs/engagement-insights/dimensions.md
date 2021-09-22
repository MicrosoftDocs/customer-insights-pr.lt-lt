---
title: Peržiūrėti ir kurti dimensijas
description: Kaip kurti, redaguoti ir naikinti dimensijas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034007"
---
# <a name="view-and-create-dimensions"></a>Peržiūrėti ir kurti dimensijas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensija yra įvykio atributas, kuris gali apibūdinti, filtruoti arba grupuoti duomenis. Jei savo svetainėje naudojate rinkodaros reklamą, galite naudoti dimensijas lankytojų rikiavimui į naujus ir sugrįžtančius.  

Į įtraukimo įžvalgas įtrauktos visiškai parengtos įvykių ypatybių dimensijos. Pavyzdžiai:

- Naršyklės Pavadinimas
- Puslapio pavadinimas
- Įrenginio Modelis
- Operacinė sistema
- Šalis

## <a name="view-dimensions"></a>Peržiūrėti dimensijas

Dimensijos yra pagrįstos esamomis įvykio ypatybėmis. Kai stebėjimo kodą naudojate įsitraukimo įžvalgoms, sistemos dimensijos sukuriamos automatiškai.

1. Eikite į **Duomenys** kairiojoje naršymo srityje. 
1. Pasirinkite **Dimensijos**, kad pamatytumėte visų dimensijų sąrašą darbo srityje. 
   > [!NOTE]
   > Sistemos sugeneruotos dimensijos yra tik skaitomos. Jų redaguoti negalite. Kurti ir redaguoti galite tik pasirinktines dimensijas.

## <a name="create-a-dimension"></a>Kurti dimensiją

Be sistemos sugeneruotų dimensijų, aplinkos ir darbo srities administratoriai gali kurti pasirinktines dimensijas. Pasirinktinės dimensijos yra pagrįstos numatytomis pagrindinių įvykių ypatybėmis arba jos gali naudoti [pasirinktines įvykio ypatybes](advanced-SDK-implementation.md).

1. Eikite į **Duomenys** > **Dimensijos**.
1. Pasirinkite **Įtraukti dimensiją**.

   :::image type="content" source="media/add-dimension.png" alt-text="Įtraukti dimensiją į įvykį.":::

1. Srityje **Kurti dimensiją** pasirinkite ypatybę, pagal kurią norite pagrįsti dimensiją. Ypatybių sąraše bus parodytos visos darbo srities ypatybės, nepriskirtos dimensijai.
1. Įveskite pavadinimą **Rodomo pavadinimo** lauke. Pasirinktinai galite įtraukti aprašą.
1. Pasirinkite **Kurti** dimensijos įrašymui. Gali užtrukti iki vienos minutės, kol galėsite naudoti dimensiją [pasirinktinėje ataskaitoje](custom-reports.md) arba [segmente](segments.md). 

## <a name="edit-a-dimension"></a>Dimensijos redagavimas

Galite pakeisti dimensijos pavadinimą ir aprašą.

1. Eikite į **Duomenys** > **Dimensijos**.
1. Pažymėkite norimą naikinti dimensiją.
1. Srityje **Redaguoti dimensiją** atnaujinkite dimensiją.
1. Pasirinkite **Taikyti**, kad įrašytumėte keitimus.

## <a name="delete-a-dimension"></a>Dimensijos naikinimas

Panaikinti galite tik vartotojo sukurtas dimensijas, tačiau negalite pašalinti sistemos dimensijų.

Dimensijos naikinimas yra galutinis. Ataskaitos ir segmentai, kurie naudoja panaikintą dimensiją, nebeveiks. 

1. Eikite į **Duomenys** > **Dimensijos**.
1. Pažymėkite norimą naikinti dimensiją.
1. Srityje **Redaguoti dimensiją** pasirinkite **Naikinti dimensiją**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Naikinti dimensiją iš įvykio.":::

1. Įveskite **PATVIRTINTI NAIKINIMĄ** (didžiosiomis raidėmis) naikinimo patvirtinimui. 
1. Pasirinkite **Naikinti**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
