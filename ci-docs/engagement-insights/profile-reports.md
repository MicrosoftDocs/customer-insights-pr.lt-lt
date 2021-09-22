---
title: Iš anksto nustatyti profilio ataskaitų įgalinimas
description: Kaip kurti iš anksto sukurtas profilio ataskaitas, sugrupuotas pagal kilmę, blyką, o taip pat pagal kilmę arba regioną.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033962"
---
# <a name="out-of-box-profile-reports"></a>Nestandartinės profilio ataskaitos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ataskaita yra duomenų vizualizacijos, padedančios suprasti vartotojų elgesį. Jungiantis prie „Customer Insights“ auditorijos įžvalgų, įtraukimo įžvalgos gali rodyti ataskaitą su informacija apie unifikuotą klientų profilį. Šioje ataskaitoje yra jūsų profilių, sugrupuotų pagal koordinates, anketą ir geografinę vietą, skaičius.

## <a name="prerequisites"></a>Būtinosios sąlygos

Auditorijos įžvalgų aplinkoje duomenys turi būti išsaugoti kliento valdomame „Azure Data Lake Storage“ abonemente.

Jei naudojate auditorijos įžvalgų pajėgumų bandomąją versiją arba aplinką „Customer Insights" valdomuose „data lake“, pagalbos [kreipkitės į](https://go.microsoft.com/fwlink/?linkid=2145734) mus.  


## <a name="enable-the-customer-profile-report"></a>Įjunkite kliento profilio ataskaitą

Aplinkos administratorius turi [sukurti ryšį su auditorijos įžvalgomis](configure-connections.md).

Nurodęs išsamią ryšio informaciją administratorius gali suteikti prieigą prie kitų organizacijos žmonių ir peržiūrėti ataskaitą. Tik aplinkos administratorius nustato ryšį ir automatiškai turi prieigą prie ataskaitos. 

Baigus ryšį **profilių** funkcija bus pasiekiamakairiojoje naršymo srityje. 

- Norėdami peržiūrėti ataskaitą, eikite į **Atrasti** > **Profiliai**.

**Profilių** ataskaitoje pateikiamos vizualizacijos apie sujungtų klientų profilių anonimizavimą, anonimizavimą ir geografinę vietą.

:::image type="content" source="media/customer-profiles.png" alt-text="Kliento profilio ataskaita.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]