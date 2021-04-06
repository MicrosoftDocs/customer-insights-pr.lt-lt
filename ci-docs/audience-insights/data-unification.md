---
title: Duomenų susijungimas
description: Sužinokite, kaip suvienodinti suvartotus duomenis.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 73d8006c670268420f8cd6a2b37cb214ba1bbd6c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597889"
---
# <a name="data-unification-overview"></a><span data-ttu-id="85d61-103">Duomenų suvienodinimo apžvalga</span><span class="sxs-lookup"><span data-stu-id="85d61-103">Data unification overview</span></span>

<span data-ttu-id="85d61-104">Po to, kai [nustatysite duomenų šaltinius](data-sources.md), galite suvienodinti duomenis.</span><span class="sxs-lookup"><span data-stu-id="85d61-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="85d61-105">Duomenys sujungiami trimis etapais: **susiejimas**, **gretinimas** ir **suliejimas**.</span><span class="sxs-lookup"><span data-stu-id="85d61-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="85d61-106">Duomenų sujungimas leidžia sujungti skirtingus duomenų šaltinius į vieną pagrindinį duomenų rinkinį, kuriame pateikiamas vieningasis jūsų klientų rodinys.</span><span class="sxs-lookup"><span data-stu-id="85d61-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="85d61-107">Sujungimo etapai yra privalomi ir atliekami toliau pateikiama tvarka:</span><span class="sxs-lookup"><span data-stu-id="85d61-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="85d61-108">Susiejimas</span><span class="sxs-lookup"><span data-stu-id="85d61-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="85d61-109">Match</span><span class="sxs-lookup"><span data-stu-id="85d61-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="85d61-110">Suliejimas</span><span class="sxs-lookup"><span data-stu-id="85d61-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="85d61-111">Užbaigę duomenų sujungimą, pasirinktinai galite</span><span class="sxs-lookup"><span data-stu-id="85d61-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="85d61-112">[nustatykite ryšius tarp objektų](relationships.md) tam, kad sukurtumėte sudėtingus segmentus</span><span class="sxs-lookup"><span data-stu-id="85d61-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="85d61-113">[praturtinkite savo duomenis](enrichment-hub.md) tam, kad gautumėte platesnį įžvalgų intervalą apie savo klientus</span><span class="sxs-lookup"><span data-stu-id="85d61-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="85d61-114">[nustatykite veiklas](activities.md) iš keleto suvartotų savybių</span><span class="sxs-lookup"><span data-stu-id="85d61-114">[define activities](activities.md) from some of the ingested attributes</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]