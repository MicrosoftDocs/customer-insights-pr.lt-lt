---
title: Padidėjimo paleidimas iš naujo „Power Query“ pagrįstiems duomenų šaltiniams
description: Atnaujinkite naujus ir atnaujintus „Power Query“ pagrįstų didelių duomenų šaltinių duomenis.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268558"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="7e2a6-103">„Power Query“ pagrįstų duomenų šaltinių papildantysis naujinimas</span><span class="sxs-lookup"><span data-stu-id="7e2a6-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="7e2a6-104">Papildantysis duomenų šaltinių naujinimas teikia toliau nurodytus privalumus.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="7e2a6-105">**Greitesnis naujinimas** – atnaujinami tik pakeisti duomenys.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="7e2a6-106">Pavyzdžiui, galite atnaujinti tik pastarąsias penkias istorinio duomenų rinkinio dienas.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="7e2a6-107">**Didesnis patikimumas** – vykdant smulkesnius atnaujinimus, nereikia ilgai palaikyti ryšių su nepastoviomis šaltinių sistemomis, taip sumažinant ryšio problemų pavojų.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="7e2a6-108">**Sumažintas išteklių suvartojimas** – atnaujinant tik dalį visų duomenų, skaičiavimo ištekliai naudojami efektyviau ir sumažinamas poveikis aplinkai.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="7e2a6-109">Konfigūruoti papildantįjį naujinimą</span><span class="sxs-lookup"><span data-stu-id="7e2a6-109">Configure incremental refresh</span></span>

<span data-ttu-id="7e2a6-110">Publikos įžvalgos leidžia padidinti paleidimą iš naujo duomenų šaltiniams importuotiems per „Power Query“, kurie palaiko padidinimo suvartojimą.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="7e2a6-111">Pavyzdžiui, „Azure“ SQL duomenų bazių, kurių datos ir laiko laukuose nurodoma, kada paskutinį kartą buvo atnaujinti duomenų įrašai.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="7e2a6-112">[Kurkite „Power Query“ pagrįstą naują duomenų šaltinį](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="7e2a6-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="7e2a6-113">Įveskite duomenų šaltinio pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="7e2a6-114">Pažymėkite duomenų šaltinį, palaikantį papildantįjį naujinimą, pvz., „Azure“ SQL duomenų bazę.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="7e2a6-115">Pažymėkite rinktinus objektus arba lenteles.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="7e2a6-116">Atlikite transformavimo veiksmus ir pasirinkite **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="7e2a6-117">Dialogo lange **Nustatyti papildantįjį naujinimą** pasirinkite **Nustatyti**, kad atidarytumėte **Papildančiojo naujinimo parametrai**.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="7e2a6-118">Jei pasirinksite **Praleisti**, duomenų šaltinis atnaujins visą duomenų rinkinį.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="7e2a6-119">Taip pat galite taikyti papildantįjį atnaujinimą vėliau, redaguodami esamą duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="7e2a6-120">Pasirinkę **Papildančiojo naujinimo parametrai**, sukonfigūruojate papildantįjį naujinimą visiems objektams, kuriuos pasirinkote kurdami duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7e2a6-121">![Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį naujinimą](media/incremental-refresh-settings.png "Objektų konfigūravimas duomenų šaltinyje norint atlikti papildantįjį naujinimą")</span><span class="sxs-lookup"><span data-stu-id="7e2a6-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="7e2a6-122">Pažymėkite objektą ir nurodykite toliau pateikiamą informaciją.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="7e2a6-123">**Pasirinkite pirminį raktą**: pažymėkite objekto arba lentelės pirminį raktą.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="7e2a6-124">**Apibrėžkite lauką „paskutinį kartą atnaujinta“**: šiame lauke rodomi tik datos arba laiko tipų atributai.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="7e2a6-125">Pasirinkite atributą, nurodantį, kada įrašai buvo paskutinį kartą atnaujinti.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="7e2a6-126">Jis bus naudojamas įrašams, patenkantiems į papildančiojo naujinimo skirtąjį laiką, identifikuoti.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="7e2a6-127">**Tikrinti, ar yra naujinimų, kas**: nurodykite papildančiojo atnaujinimo laikotarpio trukmę.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="7e2a6-128">Pasirinkite **Įrašyti**, kad užbaigtumėte duomenų šaltinio kūrimą.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="7e2a6-129">Pradinio duomenų naujinimo metu bus atnaujinti visi duomenys.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="7e2a6-130">Paskui papildantysis duomenų naujinimas vykdomas pagal ankstesnio veiksmo metu nustatytus parametrus.</span><span class="sxs-lookup"><span data-stu-id="7e2a6-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]