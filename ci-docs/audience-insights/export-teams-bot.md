---
title: Robotas „Microsoft Teams“
description: Ieškokite suvienodintų tinkintų profilių „Microsoft Teams“ su roboto pagalba.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267962"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="d0794-103">Komandų robotas „Dynamics 365 Customer Insights“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="d0794-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="d0794-104">Sujunkite su „Microsoft Teams“ norėdami leisti robotui ieškoti suvienodintų klientų profilių „Teams“ kanaluose.</span><span class="sxs-lookup"><span data-stu-id="d0794-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d0794-105">![„Teams“ roboto rodomas kliento įrašas](media/teams-bot.png "„Teams“ roboto rodomas kliento įrašas")</span><span class="sxs-lookup"><span data-stu-id="d0794-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0794-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="d0794-106">Prerequisites</span></span>

<span data-ttu-id="d0794-107">Norint nustatyti ir sukonfigūruoti robotą, turi būti įvykdytos šios būtinosios sąlygos:</span><span class="sxs-lookup"><span data-stu-id="d0794-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d0794-108">Turi būti [įtrauktas bent vienas duomenų šaltinis](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="d0794-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="d0794-109">[Sujungimo procesas](data-unification.md) yra baigtas.</span><span class="sxs-lookup"><span data-stu-id="d0794-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="d0794-110">Laukai yra įtraukti į [ieškos ir filtravimo rodyklę](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d0794-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="d0794-111">„Customer Insights“ ir „Teams“ yra toje pačioje organizacijoje.</span><span class="sxs-lookup"><span data-stu-id="d0794-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="d0794-112">Roboto konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="d0794-112">Configure the bot</span></span>

1. <span data-ttu-id="d0794-113">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="d0794-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="d0794-114">Plytelėje „Microsoft Teams“ pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="d0794-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="d0794-115">Būsite nukreiptas į „Teams“ sritį **Programos**.</span><span class="sxs-lookup"><span data-stu-id="d0794-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="d0794-116">Taip pat galite atidaryti „Teams“ ir apatiniame kairiajame kampe pasirinkti **Programos** arba [jį atsisiųsti tiesiogiai iš „AppSource“](https://go.microsoft.com/fwlink/?linkid=2124104).</span><span class="sxs-lookup"><span data-stu-id="d0794-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="d0794-117">Ieškokite **„Customer Insights“** ir pasirinkite programą.</span><span class="sxs-lookup"><span data-stu-id="d0794-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="d0794-118">Pasirinkite **Įtraukti**.</span><span class="sxs-lookup"><span data-stu-id="d0794-118">Select **Add**.</span></span>
1. <span data-ttu-id="d0794-119">Programoje „Teams“ prisijungęs prie „Customer Insights“ matysite pasveikinimo pranešimą ir galėsite pradėti.</span><span class="sxs-lookup"><span data-stu-id="d0794-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="d0794-120">Ką galite atlikti naudodami robotą</span><span class="sxs-lookup"><span data-stu-id="d0794-120">Things you can do with the bot</span></span>

<span data-ttu-id="d0794-121">Robotas teikia sujungtų klientų profilių peržvalgos galimybes.</span><span class="sxs-lookup"><span data-stu-id="d0794-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="d0794-122">Įveskite **ieškoti** ir vardą, pavardę, el. pašto adresą arba bet kokį kitą sujungto kliento profilio, kuris yra įtrauktas į ieškos ir filtravimo rodyklę, lauką.</span><span class="sxs-lookup"><span data-stu-id="d0794-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="d0794-123">Matysite kortelę su ne daugiau kaip 15 laukų iš rasto kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="d0794-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="d0794-124">Esant keliems atitikmenims pateikiamas rezultatų sąrašas, kuriame galite pasirinktį profilį.</span><span class="sxs-lookup"><span data-stu-id="d0794-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="d0794-125">Norėdami ieškote tikslaus atitikmens galite įvesti ieškos frazę su dvigubomis kabutėmis.</span><span class="sxs-lookup"><span data-stu-id="d0794-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="d0794-126">Jei jūsų organizacija išlaiko daugelį „Customer Insights“ aplinkų toje pačioje organizacijoje, galite įvesti **perjungti elementą** norėdami pasirinkti, kurią aplinką norite sujungti su robotu.</span><span class="sxs-lookup"><span data-stu-id="d0794-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="d0794-127">Įveskite **žinynas**, kad būtų rodomas galimų roboto komandų sąrašas.</span><span class="sxs-lookup"><span data-stu-id="d0794-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]