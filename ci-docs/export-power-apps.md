---
title: „Power Apps“ jungtis (peržiūra)
description: Susijunkite su „Power Apps“ ir „Power Automate“.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055270"
---
# <a name="power-apps-connector-preview"></a>„Power Apps“ jungtis (peržiūra)

Perkelkite sujungtus klientų profilius į individualizuotas programas naudodami „Microsoft Power Apps“.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Susijunkite su „Power Apps“ ir „Dynamics 365 Customer Insights“

„Customer Insights“ yra vienas iš daugelio [galimų duomenų šaltinių naudojant „Power Apps“](/powerapps/maker/canvas-apps/working-with-data-sources).

Žr. „Power Apps“ dokumentaciją, kad sužinotumėte, kaip [į programą įtraukti duomenų ryšį](/powerapps/maker/canvas-apps/add-data-connection). Taip pat rekomenduojame peržiūrėti, [kaip „Power Apps“ naudojamas perdavimas siekiant apdoroti didelius drobės programų duomenų rinkinius](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Galimi objektai

„Customer Insights“ įtraukę kaip duomenų ryšį, „Power Apps“ galite pasirinkti toliau nurodytus objektus.

- **Klientas**: norėdami naudoti duomenis iš  [sujungto kliento profilio](customer-profiles.md).
- **UnifiedActivity** : programoje rodoma [veiklos laiko planavimo](activities.md) juosta.
- **ContactProfile** : rodyti kliento kontaktus. Šis objektas pasiekiamas tik verslo paskyrų "Customer Insights" aplinkose.

## <a name="limitations"></a>Apribojimai

### <a name="retrievable-entities"></a>Gaunamieji objektai

Per jungtį galite nuskaityti **Klientas**, **UnifiedActivity**, **Segmentai**, ir **ContactProfile** laukus per „Power Apps“ jungtį. "ContactProfile" pasiekiamas tik "Customer Insights" egzemplioriuje, skirtame verslo paskyroms. Kiti objektai rodomi, nes pagrindinė jungtis juos palaiko per „Power Automate“ paleidiklius.

Galite atlikti ne daugiau kaip 100 skambučių per 60 sekundžių. Api galinį punktą galite iškviesti kelis kartus naudodami parametrą $skip. [Sužinokite daugiau apie parametrą $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Perdavimas

Perdavimo funkcija veikia su objektais **Klientas** ir **Sujungta veikla**. 

- **Kliento** objekto perdavimas: Šio objekto perdavimo naudojimui, laukeliai turi būti sužymėti [Paieškos ir filtravimo turinyje](search-filter-index.md).  
- **UnifiedActivity** perdavimas: šiame objekte perdavimo funkcija veikia tik su laukais **ActivityId** ir **CustomerId**.  
- **ContactProfile** perdavimas: šio objekto indų indavimas veikia tik laukuose **ContactId** ir **CustomerId**. "ContactProfile" pasiekiamas tik verslo paskyrų "Customer Insights" aplinkose.

Norėdami gauti daugiau informacijos apie pervaldavimą, [„Power Apps“ eikite į deavaluojamas funkcijas ir operacijas](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Galerijos valdiklio pavyzdys

Į galerijos valdiklį galite įtraukti [klientų profilių](/powerapps/maker/canvas-apps/add-gallery).

1. Įtraukite valdiklį **galeriją** į kuriamą programą.

    > [!div class="mx-imgBorder"]
    > ![Galerijos elemento įtraukimas.](media/connector-powerapps9.png "Galerijos elemento įtraukimas.")

2. Pasirinkite **Klientas** kaip elementų duomenų šaltinį.

    > [!div class="mx-imgBorder"]
    > ![Pasirinkti duomenų šaltinį.](media/choose-datasource-powerapps.png "Duomenų šaltinio pasirinkimas.")

3. Galite keisti duomenų skydą dešinėje ir pasirinkti, kurį kliento objekto lauką rodyti galerijoje.

4. Jei galerijoje norite parodyti bet kurį pasirinkto kliento lauką, užpildykite žymos teksto ypatybę **tekstą** naudojant **{Name_of_the_gallery}.Pasirinktas.{property_name}**  
    - Pavyzdys: _Gallery1.Selected.address1_city_

5. Norėdami, kad būtų rodoma sujungta kliento laiko planavimo juosta, įtraukite galerijos elementą ir įtraukite **Elementai** ypatybę su **Filtras('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Pavyzdys: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
