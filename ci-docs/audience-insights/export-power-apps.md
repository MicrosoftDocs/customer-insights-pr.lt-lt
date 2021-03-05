---
title: „Power Apps“ jungtis
description: Susijunkite su „Power Apps“ ir „Power Automate“.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268926"
---
# <a name="microsoft-power-apps-connector-preview"></a>„Microsoft Power Apps“ jungtis (peržiūra)

Perkelkite sujungtus klientų profilius į individualizuotas programas naudodami „Power Apps“.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Susijunkite su „Power Apps“ ir „Dynamics 365 Customer Insights“

„Customer Insights“ yra vienas iš daugelio [galimų duomenų šaltinių naudojant „Power Apps“](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Žr. „Power Apps“ dokumentaciją, kad sužinotumėte, kaip [į programą įtraukti duomenų ryšį](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Taip pat rekomenduojame peržiūrėti, [kaip „Power Apps“ naudojamas perdavimas siekiant apdoroti didelius drobės programų duomenų rinkinius](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Galimi objektai

„Customer Insights“ įtraukę kaip duomenų ryšį, „Power Apps“ galite pasirinkti toliau nurodytus objektus.

- Klientas: norėdami naudoti duomenis iš [sujungto kliento profilio](customer-profiles.md).
- Sujungta klientų veikla: norėdami, kad programėlėje būtų rodoma [sujungta laiko juosta](activities.md).

## <a name="limitations"></a>Apribojimai

### <a name="retrievable-entities"></a>Gaunamieji objektai

Naudodami „Power Apps“ jungtį, galite gauti tik objektus **Klientas**, **UnifiedActivity** ir **Segmentai**. Kiti objektai rodomi, nes pagrindinė jungtis juos palaiko per „Power Automate“ paleidiklius.  

### <a name="delegation"></a>Perdavimas

Perdavimo funkcija veikia su objektais Customer ir UnifiedActivity. 

- **Kliento** objekto perdavimas: Šio objekto perdavimo naudojimui, laukeliai turi būti sužymėti [Paieškos ir filtravimo turinyje](search-filter-index.md).  

- **UnifiedActivity** perdavimas: šiame objekte perdavimo funkcija veikia tik su laukais **ActivityId** ir **CustomerId**.  

- Norėdami gauti daugiau informacijos apie perdavimą, žr. [„Power Apps“ perduodamosios funkcijos ir operacijos](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Galerijos valdiklio pavyzdys

Pavyzdžiui, įtraukiate kliento profilius į [galerijos valdymą](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Įtraukite valdiklį **Galeriją** į kuriamą programą.

> [!div class="mx-imgBorder"]
> ![Galerijos elemento įtraukimas](media/connector-powerapps9.png "Galerijos elemento įtraukimas")

1. Pasirinkite **Klientas** kaip elementų duomenų šaltinį.

    > [!div class="mx-imgBorder"]
    > ![Pasirinkti duomenų šaltinį](media/choose-datasource-powerapps.png "Duomenų šaltinio pasirinkimas")

1. Galite keisti duomenų skydą dešinėje ir pasirinkti, kurį kliento objekto lauką rodyti galerijoje.

1. Jei galerijoje norite parodyti bet kurį pasirinkto kliento lauką, užpildykite žymos teksto ypatybę:  **{Name_of_the_gallery}.Selected.{property_name}**

    Pavyzdys: Gallery1.Selected.address1_city

1. Norėdami, kad būtų rodoma vieninga kliento laiko planavimo juosta, įtraukite galerijos elementą ir įtraukite elementų ypatybę: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Pavyzdys: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]