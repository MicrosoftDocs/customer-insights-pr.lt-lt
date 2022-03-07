---
title: Peržiūrėti ir kurti dimensijas
description: Kaip kurti, redaguoti ir naikinti dimensijas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d35c72f73d2f3e202ae3c5a5ef26e9db89360084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226316"
---
# <a name="view-and-create-dimensions"></a>Peržiūrėti ir kurti dimensijas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensija yra įvykio atributas, kuris gali apibūdinti, filtruoti arba grupuoti duomenis. Jei savo svetainėje naudojate rinkodaros reklamą, galite naudoti dimensijas lankytojų rikiavimui į naujus ir sugrįžtančius.  

Į įtraukimo įžvalgas įtrauktos visiškai parengtos (OOB) įvykių ypatybių dimensijos. Pavyzdžiai:

- Naršyklės pavadinimas
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
1. Pasirinkti **naują matmenį**.

   :::image type="content" source="media/add-dimension.png" alt-text="Įtraukti dimensiją į įvykį.":::

1. Srityje **Kurti dimensiją** pasirinkite ypatybę, pagal kurią norite pagrįsti dimensiją. Ypatybių sąraše bus parodytos visos darbo srities ypatybės, nepriskirtos dimensijai.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Kurti naują dimensiją.":::
      
3. Įveskite pavadinimą **Rodomo pavadinimo** lauke. Pasirinktinai galite įtraukti **aprašą**.
4. Pasirinkite **Kurti** dimensijos įrašymui. Gali užtrukti iki vienos minutės, kol galėsite naudoti dimensiją [pasirinktinėje ataskaitoje](custom-reports.md) arba [segmente](segments.md). 

## <a name="edit-a-dimension"></a>Dimensijos redagavimas

Galite pakeisti dimensijos pavadinimą ir aprašą. Galite redaguoti tik vartotojo sukurtus galus, bet negalite redaguoti sistemos neesmes.


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
