---
title: „Power BI“ jungtis
description: Sužinokite, kaip naudoti „Dynamics 365 Customer Insights“ jungtį programoje „Power BI“.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406382"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="038bf-103">„Power BI“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="038bf-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="038bf-104">Sukurkite vizualizacija jūsų duomenims su „Power BI Desktop“.</span><span class="sxs-lookup"><span data-stu-id="038bf-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="038bf-105">Generuokite papildomas įžvalgas ir kurkite ataskaitas naudodami sujungtus klientų duomenis.</span><span class="sxs-lookup"><span data-stu-id="038bf-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="038bf-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="038bf-106">Prerequisites</span></span>

- <span data-ttu-id="038bf-107">Turite suvienodintus kliento profilius.</span><span class="sxs-lookup"><span data-stu-id="038bf-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="038bf-108">Jūsų kompiuteryje įdiegta naujausia [„Microsoft Power BI Desktop“](https://powerbi.microsoft.com/desktop/) versija.</span><span class="sxs-lookup"><span data-stu-id="038bf-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="038bf-109">[Sužinokite daugiau apie „Power BI Desktop”](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="038bf-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="038bf-110">„Power BI“ jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="038bf-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="038bf-111">„Power BI Desktop“ pasirinkite **Failas** > **Gauti duomenis**.</span><span class="sxs-lookup"><span data-stu-id="038bf-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="038bf-112">Pasirinkite **Rodyti daugiau** ir ieškokite **„Dynamics 365 Customer Insights“**</span><span class="sxs-lookup"><span data-stu-id="038bf-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="038bf-113">Pasirinkite rezultatą ir spustelėkite **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="038bf-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="038bf-114">**Prisijunkite** naudodami tą patį organizacijos klientą, kurį naudojate „Customer Insights“, ir pasirinkite **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="038bf-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="038bf-115">Klientas, kurį nurodėte atlikdami šį veiksmą, naudojamas duomenims iš „Customer Insights“ gauti ir jis neturi sutapti su klientu, kurį pasirinkę prisijungėte prie „Power BI“.</span><span class="sxs-lookup"><span data-stu-id="038bf-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="038bf-116">Norėdami paleisti iš naujo paskyrą naudojamą duomenų naudojimui, atverkite „Power BI“ ir eiktie į **Failai** > **Parinktys** > **Nustatymai** > **Duomenų šaltinio nustatymai**.</span><span class="sxs-lookup"><span data-stu-id="038bf-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="038bf-117">Duomenų šaltinių sąraše pasirinkite **Dynamics 365 Customer Insights prisijungimas** ir pasirinkite **Aiškios teisės**.</span><span class="sxs-lookup"><span data-stu-id="038bf-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="038bf-118">Dialogo lange **„Navigator“**.</span><span class="sxs-lookup"><span data-stu-id="038bf-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="038bf-119">matysite aplinkų sąrašą, prie kurio turite prieigą.</span><span class="sxs-lookup"><span data-stu-id="038bf-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="038bf-120">Išplėskite aplinką ir atverkite bet kurį katalogą (objektų, priemonių, segmentų, praturtinimų).</span><span class="sxs-lookup"><span data-stu-id="038bf-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="038bf-121">Pavyzdžiui, atidarykite aplanką **Objektai**, kad pamatytumėte visus objektus, kuriuos galite importuoti.</span><span class="sxs-lookup"><span data-stu-id="038bf-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="038bf-122">![Power BI jungčių naršyklė](media/power-bi-navigator.png "„Power BI“ jungčių naršyklė")</span><span class="sxs-lookup"><span data-stu-id="038bf-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="038bf-123">Pažymėkite žymės langelius šalia objektų, kuriuos reikia įtraukti, ir **įkelkite**.</span><span class="sxs-lookup"><span data-stu-id="038bf-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="038bf-124">Galite pažymėti kelis objektus iš kelių aplinkų.</span><span class="sxs-lookup"><span data-stu-id="038bf-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="038bf-125">Kol objektai įkeliami, matysite įkėlimo dialogo langą.</span><span class="sxs-lookup"><span data-stu-id="038bf-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="038bf-126">Jums pasirinkus įkeltus objektus, galite naudoti „Power BI“ pajėgumus tam, kad rodytumėte duomenis.</span><span class="sxs-lookup"><span data-stu-id="038bf-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="038bf-127">Dideli duomenų rinkiniai</span><span class="sxs-lookup"><span data-stu-id="038bf-127">Large data sets</span></span>

<span data-ttu-id="038bf-128">„Customer Insights“ jungtis, skirta „Power BI“, sukurta veikti su duomenų rinkiniais, kuriuose yra iki 1 milijono klientų profilių.</span><span class="sxs-lookup"><span data-stu-id="038bf-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="038bf-129">Didesnių duomenų rinkinių importavimas gali pavykti, tačiau reikia daug laiko.</span><span class="sxs-lookup"><span data-stu-id="038bf-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="038bf-130">Be to, dėl „Power BI“ apribojimų gali baigti procesui skirtas laikas.</span><span class="sxs-lookup"><span data-stu-id="038bf-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="038bf-131">Norėdami gauti daugiau informacijos, žr. [„Power BI“: rekomendacijos dėl didelių duomenų rinkinių](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="038bf-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="038bf-132">Darbas su antriniu duomenų rinkiniu</span><span class="sxs-lookup"><span data-stu-id="038bf-132">Work with a subset of data</span></span>

<span data-ttu-id="038bf-133">Apgalvokite darbą su jūsų duomenų papildomu rinkiniu.</span><span class="sxs-lookup"><span data-stu-id="038bf-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="038bf-134">Pavyzdžiui, galite sukurti [segmentus](segments.md) vietoje visų kliento įrašų eksportavimo į „Power BI“.</span><span class="sxs-lookup"><span data-stu-id="038bf-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
