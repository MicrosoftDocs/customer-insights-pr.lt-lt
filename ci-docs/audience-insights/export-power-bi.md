---
title: „Power BI“ jungtis
description: Sužinokite, kaip naudoti „Dynamics 365 Customer Insights connector“ programoje „Power BI“.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596049"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="eabbb-103">„Power BI“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="eabbb-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="eabbb-104">Sukurkite vizualizacija jūsų duomenims su „Power BI Desktop“.</span><span class="sxs-lookup"><span data-stu-id="eabbb-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="eabbb-105">Generuokite papildomas įžvalgas ir kurkite ataskaitas naudodami sujungtus klientų duomenis.</span><span class="sxs-lookup"><span data-stu-id="eabbb-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="eabbb-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="eabbb-106">Prerequisites</span></span>

- <span data-ttu-id="eabbb-107">Turite suvienodintus kliento profilius.</span><span class="sxs-lookup"><span data-stu-id="eabbb-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="eabbb-108">Naujausia [„Microsoft Power BI Desktop”](https://powerbi.microsoft.com/desktop/) versija yra įdiegta jūsų kompiuteryje.</span><span class="sxs-lookup"><span data-stu-id="eabbb-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="eabbb-109">[Sužinokite daugiau apie „Power BI Desktop”](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="eabbb-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="eabbb-110">„Power BI“ jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="eabbb-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="eabbb-111">„Power BI Desktop“ pasirinkite **Failas** > **Gauti duomenis**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="eabbb-112">Pasirinkite **Rodyti daugiau** ir ieškokite **„Dynamics 365 Customer Insights“**</span><span class="sxs-lookup"><span data-stu-id="eabbb-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="eabbb-113">Pasirinkite **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-113">Select **Connect**.</span></span>

1. <span data-ttu-id="eabbb-114">**Prisijunkite** naudodami tą patį organizacijos klientą, kurį naudojate „Customer Insights“, ir pasirinkite **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="eabbb-115">Klientas, kurį nurodėte atlikdami šį veiksmą, naudojamas duomenims iš „Customer Insights“ gauti ir jis neturi sutapti su klientu, kurį pasirinkę prisijungėte prie „Power BI“.</span><span class="sxs-lookup"><span data-stu-id="eabbb-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="eabbb-116">Norėdami paleisti iš naujo paskyrą naudojamą duomenų naudojimui, atverkite „Power BI“ ir eikite į **Failai** > **Parinktys** > **Nustatymai** > **Duomenų šaltinio nustatymai**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="eabbb-117">Duomenų šaltinių sąraše pasirinkite **Dynamics 365 Customer Insights prisijungimas** ir pasirinkite **Aiškios teisės**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="eabbb-118">Dialogo lange **„Navigator“**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="eabbb-119">matysite aplinkų sąrašą, prie kurio turite prieigą.</span><span class="sxs-lookup"><span data-stu-id="eabbb-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="eabbb-120">Išplėskite aplinką ir atverkite bet kurį katalogą (objektų, priemonių, segmentų, praturtinimų).</span><span class="sxs-lookup"><span data-stu-id="eabbb-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="eabbb-121">Pavyzdžiui, atidarykite aplanką **Objektai**, kad pamatytumėte visus objektus, kuriuos galite importuoti.</span><span class="sxs-lookup"><span data-stu-id="eabbb-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="eabbb-122">![Power BI jungčių naršyklė](media/power-bi-navigator.png "„Power BI“ jungčių naršyklė")</span><span class="sxs-lookup"><span data-stu-id="eabbb-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="eabbb-123">Pažymėkite žymės langelius šalia objektų, kuriuos reikia įtraukti, ir **įkelkite**.</span><span class="sxs-lookup"><span data-stu-id="eabbb-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="eabbb-124">Galite pažymėti kelis objektus iš kelių aplinkų.</span><span class="sxs-lookup"><span data-stu-id="eabbb-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="eabbb-125">Kol objektai įkeliami, matysite įkėlimo dialogo langą.</span><span class="sxs-lookup"><span data-stu-id="eabbb-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="eabbb-126">Jums pasirinkus įkeltus objektus, galite naudoti „Power BI“ pajėgumus tam, kad rodytumėte duomenis.</span><span class="sxs-lookup"><span data-stu-id="eabbb-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="eabbb-127">Dideli duomenų rinkiniai</span><span class="sxs-lookup"><span data-stu-id="eabbb-127">Large data sets</span></span>

<span data-ttu-id="eabbb-128">„Customer Insights“ jungtis, skirta „Power BI“, sukurta veikti su duomenų rinkiniais, kuriuose yra iki 1 milijono klientų profilių.</span><span class="sxs-lookup"><span data-stu-id="eabbb-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="eabbb-129">Didesnių duomenų rinkinių importavimas gali pavykti, tačiau reikia daug laiko.</span><span class="sxs-lookup"><span data-stu-id="eabbb-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="eabbb-130">Be to, dėl „Power BI“ apribojimų gali baigti procesui skirtas laikas.</span><span class="sxs-lookup"><span data-stu-id="eabbb-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="eabbb-131">Norėdami gauti daugiau informacijos, žr. [„Power BI“: rekomendacijos dėl didelių duomenų rinkinių](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="eabbb-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="eabbb-132">Darbas su antriniu duomenų rinkiniu</span><span class="sxs-lookup"><span data-stu-id="eabbb-132">Work with a subset of data</span></span>

<span data-ttu-id="eabbb-133">Apgalvokite darbą su jūsų duomenų papildomu rinkiniu.</span><span class="sxs-lookup"><span data-stu-id="eabbb-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="eabbb-134">Pavyzdžiui, galite sukurti [segmentus](segments.md) vietoje visų kliento įrašų eksportavimo į „Power BI“.</span><span class="sxs-lookup"><span data-stu-id="eabbb-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="eabbb-135">Trikčių šalinimas</span><span class="sxs-lookup"><span data-stu-id="eabbb-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="eabbb-136">„Customer Insights” aplinka, kuri nerodoma „Power BI”</span><span class="sxs-lookup"><span data-stu-id="eabbb-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="eabbb-137">Aplinkos, kurios turi daugiau nei vieną ryšį, nustatytą tarp dviejų identiškų objektų auditorijos [įžvalgose](relationships.md), pasiekti Power BI nepavyks.</span><span class="sxs-lookup"><span data-stu-id="eabbb-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="eabbb-138">Galite identifikuoti ir pašalinti dubliuotas ryšius.</span><span class="sxs-lookup"><span data-stu-id="eabbb-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="eabbb-139">Auditorijos įžvalgose eikite **Duomenys** > **Ryšiai** aplinkoje, kurios trūksta Power BI.</span><span class="sxs-lookup"><span data-stu-id="eabbb-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="eabbb-140">Identifikuoti dubliuotus ryšius:</span><span class="sxs-lookup"><span data-stu-id="eabbb-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="eabbb-141">Patikrinkite, ar tarp tų pačių dviejų objektų yra daugiau nei vienas ryšys.</span><span class="sxs-lookup"><span data-stu-id="eabbb-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="eabbb-142">Patikrinkite, ar yra ryšys, sukurtas tarp dviejų objektų, kurie abu įtraukti į suvienodinimo procesą.</span><span class="sxs-lookup"><span data-stu-id="eabbb-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="eabbb-143">Tarp visų į suvienodinimo procesą įtrauktų objektų nustatomas numanomas ryšys.</span><span class="sxs-lookup"><span data-stu-id="eabbb-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="eabbb-144">Pašalinti visus nustatytus dublikatų ryšius.</span><span class="sxs-lookup"><span data-stu-id="eabbb-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="eabbb-145">Pašalę dubliuotų ryšių bandykite dar kartą Power BI programoje sukonfigūruoti jungtį.</span><span class="sxs-lookup"><span data-stu-id="eabbb-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="eabbb-146">Aplinka turėtų būti prieinama dabar.</span><span class="sxs-lookup"><span data-stu-id="eabbb-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]