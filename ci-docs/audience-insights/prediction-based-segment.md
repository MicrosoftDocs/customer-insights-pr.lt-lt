---
title: Segmentai, grindžiami prognozės rezultatu
description: Kurkite segmentus pagal prognozės modelio rezultato objektą.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741439"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="487a9-103">Segmento kūrimas pagal prognozės modelį (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="487a9-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="487a9-104">Prognozės rezultatai kartais taikomi tik antriniams jūsų klientų rinkiniams.</span><span class="sxs-lookup"><span data-stu-id="487a9-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="487a9-105">Padidinkite rekomendacijų suasmeninimą sukurdami segmentus pagal prognozės modelių rezultatus.</span><span class="sxs-lookup"><span data-stu-id="487a9-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="487a9-106">Pavyzdžiui, galite pateikti konkrečias rekomendacijas klientams, kurie teikia pirmenybę tam tikro tipo aptarnavimui.</span><span class="sxs-lookup"><span data-stu-id="487a9-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="487a9-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="487a9-107">Prerequisites</span></span>

- <span data-ttu-id="487a9-108">Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="487a9-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="487a9-109">Produkto rekomendacija, sandorio praradimas, prenumeratos praradimas arba kliento nuolatinės vertės modelis, sukonfigūruotas srityje „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="487a9-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="487a9-110">Peržiūrėkite reikalavimus skirtingiems modeliams nustatyti:</span><span class="sxs-lookup"><span data-stu-id="487a9-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="487a9-111">Produkto rekomendacijos modelis</span><span class="sxs-lookup"><span data-stu-id="487a9-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="487a9-112">Prenumeratos praradimo modelis</span><span class="sxs-lookup"><span data-stu-id="487a9-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="487a9-113">Operacijos praradimo modelis</span><span class="sxs-lookup"><span data-stu-id="487a9-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="487a9-114">Kliento naudojimo laiko vertės modelis</span><span class="sxs-lookup"><span data-stu-id="487a9-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="487a9-115">Kliento segmento kūrimas pagal prognozes</span><span class="sxs-lookup"><span data-stu-id="487a9-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="487a9-116">Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.</span><span class="sxs-lookup"><span data-stu-id="487a9-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="487a9-117">Pažymėkite vertikalias elipses prie modelio, kurį norite peržiūrėti, ir pasirinkite **Peržiūrėti**.</span><span class="sxs-lookup"><span data-stu-id="487a9-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="487a9-118">Rezultatų puslapyje pasirinkite **Kurti segmentą**.</span><span class="sxs-lookup"><span data-stu-id="487a9-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="487a9-119">Daugiau informacijos apie rezultatų puslapį rasite straipsnyje apie modelį.</span><span class="sxs-lookup"><span data-stu-id="487a9-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Prognozės rezultatų puslapio ekrano nuotrauka su pažymėtu segmento kūrimo veiksmu.":::

1. <span data-ttu-id="487a9-121">Kurkite naują segmentą pagal pasirinkto modelio rezultato objektą.</span><span class="sxs-lookup"><span data-stu-id="487a9-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="487a9-122">Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="487a9-122">For more information, see [Create and manage segments](segments.md).</span></span>