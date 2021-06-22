---
title: Bendrai naudojamos prognozės scenarijų užduotys
description: Sužinokite, kaip valdyti, šalinti triktis ir tikslinti prognozes.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095732"
---
# <a name="manage-predictions"></a><span data-ttu-id="4150f-103">Prognozių valdymas</span><span class="sxs-lookup"><span data-stu-id="4150f-103">Manage predictions</span></span>

<span data-ttu-id="4150f-104">Šiame straipsnyje aptariama keletas užduočių, kurios yra bendros daugumai prognozės scenarijų.</span><span class="sxs-lookup"><span data-stu-id="4150f-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="4150f-105">Nepavykusios prognozės trikčių šalinimas</span><span class="sxs-lookup"><span data-stu-id="4150f-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="4150f-106">Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="4150f-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4150f-107">Pasirinkite vertikalias elipses šalia prognozės, kuriose norite peržiūrėti klaidų žurnalus.</span><span class="sxs-lookup"><span data-stu-id="4150f-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="4150f-108">Pasirinkite **Žurnalai**.</span><span class="sxs-lookup"><span data-stu-id="4150f-108">Select **Logs**.</span></span>

1. <span data-ttu-id="4150f-109">Peržiūrėkite visas klaidas.</span><span class="sxs-lookup"><span data-stu-id="4150f-109">Review all the errors.</span></span> <span data-ttu-id="4150f-110">Galimos kelių tipų klaidos, kurios aprašo, kokia būsena sukėlė klaidą.</span><span class="sxs-lookup"><span data-stu-id="4150f-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="4150f-111">Pavyzdžiui, klaida, kuri įvyko, nes nepakanka duomenų tiksliai prognozei, įprastai yra išsprendžiama įkeliant papildomų duomenų į „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="4150f-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="4150f-112">Įvesties duomenų naudojimo ataskaita</span><span class="sxs-lookup"><span data-stu-id="4150f-112">Input data usability report</span></span>

<span data-ttu-id="4150f-113">Įvesties duomenų naudojimo ataskaita pateikia klaidų ir įspėjimų, kuriuos gali sugeneruoti jūsų visiškai parengtos prognozės, apibendrintą rodinį.</span><span class="sxs-lookup"><span data-stu-id="4150f-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="4150f-114">Joje taip pat pateikiama rekomendacijų, kaip pagerinti modelio efektyvumą.</span><span class="sxs-lookup"><span data-stu-id="4150f-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="4150f-115">Ataskaita yra pasiekiama atlikus modelio mokymo procesą.</span><span class="sxs-lookup"><span data-stu-id="4150f-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="4150f-116">Ji sukuriama kiekvienam modeliui atskirai, neatsižvelgiant į tai, ar jis užbaigtas sėkmingai.</span><span class="sxs-lookup"><span data-stu-id="4150f-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="4150f-117">Šiuo metu ši funkcija veikia tik su Operacijų praradimo modeliu.</span><span class="sxs-lookup"><span data-stu-id="4150f-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="4150f-118">Peržiūrėti įvesties duomenų naudojimo ataskaitą</span><span class="sxs-lookup"><span data-stu-id="4150f-118">View the input data usability report</span></span>

<span data-ttu-id="4150f-119">Užbaigę mokymo veiksmą visiškai parengtam modeliui, peržiūrėkite ataskaitą:</span><span class="sxs-lookup"><span data-stu-id="4150f-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="4150f-120">Pasirinkite elipses prie modelio pavadinimo ir pasirinkite **Įvesties duomenų naudojimo ataskaita**.</span><span class="sxs-lookup"><span data-stu-id="4150f-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="4150f-121">Pasirinkite modelio būseną ir **Peržiūrėti įvesties duomenų naudojimo ataskaitą** šoninėje srityje.</span><span class="sxs-lookup"><span data-stu-id="4150f-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="4150f-122">Pasirinkite vieną modelį iš sąrašo ir **Įvesties duomenų naudojimo ataskaita** komandų juostoje.</span><span class="sxs-lookup"><span data-stu-id="4150f-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="4150f-123">Atidarykite modelio rezultatų puslapį ir pasirinkite **Įvesties duomenų naudojimo ataskaita** komandų juostoje.</span><span class="sxs-lookup"><span data-stu-id="4150f-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="4150f-124">Informacija įvesties duomenų naudojimo ataskaitoje</span><span class="sxs-lookup"><span data-stu-id="4150f-124">Information in the input data usability report</span></span>

<span data-ttu-id="4150f-125">Toliau pateiktuose ataskaitos stulpeliuose yra naudingos informacijos apie tai, kaip patobulinti modelio duomenis.</span><span class="sxs-lookup"><span data-stu-id="4150f-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Įvesties duomenų naudojimo ataskaitos, rodančios lentelę su klaidomis, įspėjimais ir rekomendacijomis, pavyzdys.":::

- <span data-ttu-id="4150f-127">Pavadinimas: Aprašomasis klaidos, įspėjimo arba rekomendacijos pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="4150f-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="4150f-128">Veiksmas: Modelio etapas, mokymas ar įvertinimas, nurodoma informacija.</span><span class="sxs-lookup"><span data-stu-id="4150f-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="4150f-129">Būsena: Informacijos svarba (klaida, įspėjimas, rekomendacija).</span><span class="sxs-lookup"><span data-stu-id="4150f-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="4150f-130">Stulpelio pavadinimas: Objekto, kurį reikia modifikuoti, kad būtų pagerintas modelio efektyvumas, stulpelis.</span><span class="sxs-lookup"><span data-stu-id="4150f-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="4150f-131">Objekto pavadinimas: Objekto, kurį reikia modifikuoti, kad būtų pagerintas modelio efektyvumas, pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="4150f-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="4150f-132">Išsami informacija: Išsami informacija apie klaidą, įspėjimą arba rekomendaciją.</span><span class="sxs-lookup"><span data-stu-id="4150f-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="4150f-133">Prognozės atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="4150f-133">Refresh a prediction</span></span>

<span data-ttu-id="4150f-134">Prognozės automatiškai atsinaujins tuo pačiu parametruose sukonfigūruotu [grafiku, kuriuo atnaujinami jūsų duomenys](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4150f-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="4150f-135">Galite juos paleisti iš naujo ir rankiniu būdu.</span><span class="sxs-lookup"><span data-stu-id="4150f-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="4150f-136">Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="4150f-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4150f-137">Pasirinkite vertikalius daugtaškius šalia norimos atnaujinti prognozės.</span><span class="sxs-lookup"><span data-stu-id="4150f-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="4150f-138">Pasirinkite **Atnaujinti**.</span><span class="sxs-lookup"><span data-stu-id="4150f-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="4150f-139">Prognozės šalinimas</span><span class="sxs-lookup"><span data-stu-id="4150f-139">Delete a prediction</span></span>

<span data-ttu-id="4150f-140">Prognozės panaikinimas taip pat pašalina jos išvesties objektą.</span><span class="sxs-lookup"><span data-stu-id="4150f-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="4150f-141">Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="4150f-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="4150f-142">Pasirinkite vertikalius daugtaškius šalia norimos pašalinti prognozės.</span><span class="sxs-lookup"><span data-stu-id="4150f-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="4150f-143">Pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="4150f-143">Select **Delete**.</span></span>
