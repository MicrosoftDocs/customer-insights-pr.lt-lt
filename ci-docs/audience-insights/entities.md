---
title: Objektai ir duomenų rinkiniai
description: Peržiūrėkite duomenis objektų puslapyje.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596417"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="134a8-103">Objektai publikos įžvalgose</span><span class="sxs-lookup"><span data-stu-id="134a8-103">Entities in audience insights</span></span>

<span data-ttu-id="134a8-104">[Sukonfigūravę duomenų šaltinius](data-sources.md), eikite į puslapį **Objektai**, kad įvertintumėte apdorotų duomenų kokybę.</span><span class="sxs-lookup"><span data-stu-id="134a8-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="134a8-105">Objektai yra laikomi duomenų rinkiniais.</span><span class="sxs-lookup"><span data-stu-id="134a8-105">Entities are considered datasets.</span></span> <span data-ttu-id="134a8-106">Daugelis „Dynamics 365 Customer Insights“ pajėgumų yra sukurti aplink šiuos objektus.</span><span class="sxs-lookup"><span data-stu-id="134a8-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="134a8-107">Jei atidžiai juos peržiūrėsite, lengviau įvertinsite šių galimybių rezultatus.</span><span class="sxs-lookup"><span data-stu-id="134a8-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="134a8-108">Puslapyje **Objektai** išvardyti objektai ir yra keletas stulpelių:</span><span class="sxs-lookup"><span data-stu-id="134a8-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="134a8-109">**Pavadinimas**: duomenų objekto pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="134a8-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="134a8-110">Jei prie objekto pavadinimo rodomas įspėjamasis simbolis, reiškia, kad objekto duomenų nepavyko įkelti.</span><span class="sxs-lookup"><span data-stu-id="134a8-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="134a8-111">**Šaltinis**: duomenų šaltinio, apdorojusio objektą, tipas</span><span class="sxs-lookup"><span data-stu-id="134a8-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="134a8-112">**Sukūrė**: objektą sukūrusio žmogaus vardas, pavardė</span><span class="sxs-lookup"><span data-stu-id="134a8-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="134a8-113">**Sukurta**: objekto sukūrimo data ir laikas</span><span class="sxs-lookup"><span data-stu-id="134a8-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="134a8-114">**Atnaujino**: objektą atnaujinusio žmogaus vardas, pavardė</span><span class="sxs-lookup"><span data-stu-id="134a8-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="134a8-115">**Paskutinį kartą atnaujinta**: data ir laikas, kai objektas buvo atnaujintas paskutinį kartą</span><span class="sxs-lookup"><span data-stu-id="134a8-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="134a8-116">**Paskutinį kartą atnaujinta**: paskutinio atnaujinimo data ir laikas</span><span class="sxs-lookup"><span data-stu-id="134a8-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="134a8-117">Susipažinimas su konkretaus objekto duomenimis</span><span class="sxs-lookup"><span data-stu-id="134a8-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="134a8-118">Pažymėkite objektą, kad susipažintumėte su skirtingais laukais ir įrašais, įtrauktais į šį objektą.</span><span class="sxs-lookup"><span data-stu-id="134a8-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="134a8-119">![Pasirinkite objektą](media/data-manager-entities-data.png "Pasirinkite objektą")</span><span class="sxs-lookup"><span data-stu-id="134a8-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="134a8-120">Skirtukas **Duomenys** yra pasirinktas pagal numatytuosius nustatymus ir jame rodoma lentelė, kurioje išvardyta išsami informacija apie atskirus objekto įrašus.</span><span class="sxs-lookup"><span data-stu-id="134a8-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="134a8-121">![Laukų lentelė](media/data-manager-entities-fields.PNG "Laukų lentelė")</span><span class="sxs-lookup"><span data-stu-id="134a8-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="134a8-122">Skirtuke **Laukai** pateikiama lentelė, kurioje galima peržiūrėti išsamią pasirinkto objekto informaciją, pvz., laukų pavadinimus, duomenų tipus ir tipus.</span><span class="sxs-lookup"><span data-stu-id="134a8-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="134a8-123">Stulpelyje **Tipas** pateikiami su „Common Data Model” susiję tipai, kuriuos sistema nustato automatiškai arba [susieja patys](map-entities.md) vartotojai.</span><span class="sxs-lookup"><span data-stu-id="134a8-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="134a8-124">Šie semantiniai tipai gali skirtis nuo atributų duomenų tipų, pvz., žemiau esančio lauko *El. paštas* duomenų tipas yra *Tekstas*, bet jo (semantinis) „Common Data Model” tipas gali būti *El. paštas* arba *El. pašto adresas*.</span><span class="sxs-lookup"><span data-stu-id="134a8-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="134a8-125">Abiejose lentelėse parodytas tik objekto duomenų pavyzdys.</span><span class="sxs-lookup"><span data-stu-id="134a8-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="134a8-126">Norėdami peržiūrėti visą duomenų rinkinį, eikite į puslapį **Duomenų šaltiniai**, pasirinkite objektą, pasirinkite **Redaguoti** ir peržiūrėkite šio objekto duomenis, naudodami rengyklę „Power Query”, kaip paaiškinta skyriuje [Duomenų šaltiniai](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="134a8-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="134a8-127">Jei norite sužinoti daugiau apie į objektą įtrauktus duomenis, stulpelyje **Suvestinė** pateikiamos kai kurios svarbios duomenų charakteristikos, pvz., neapibrėžtos reikšmės, trūkstamos reikšmės, unikalios reikšmės, skaičiai ir pasiskirstymai, taikomi jūsų duomenims.</span><span class="sxs-lookup"><span data-stu-id="134a8-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="134a8-128">Norėdami peržiūrėti duomenų suvestinę, pažymėkite diagramos piktogramą.</span><span class="sxs-lookup"><span data-stu-id="134a8-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="134a8-129">![Suvestinės simbolis](media/data-manager-entities-summary.png "Duomenų suvestinės lentelė")</span><span class="sxs-lookup"><span data-stu-id="134a8-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="134a8-130">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="134a8-130">Next step</span></span>

<span data-ttu-id="134a8-131">Norėdami sužinoti kaip *susieti*, *sutapdinti* ir *sulieti* apdorotus duomenis, žr. temą [Suvienodinti](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="134a8-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]