---
title: Apžvalga apie palaikomus prognozės scenarijus
description: Prognozės scenarijų ir parinkčių, kuriuos apima „Dynamics 365 Customer Insights” taikomoji programa.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095731"
---
# <a name="predictions-overview"></a><span data-ttu-id="e3654-103">Prognozių apžvalga</span><span class="sxs-lookup"><span data-stu-id="e3654-103">Predictions overview</span></span>

<span data-ttu-id="e3654-104">„Dynamics 365 Customer Insights” pateikia daugybę parinkčių, kurios išnaudoja AI ir mašininį mokymą duomenų prognozavimui.</span><span class="sxs-lookup"><span data-stu-id="e3654-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="e3654-105">Visiškai parengti modeliai</span><span class="sxs-lookup"><span data-stu-id="e3654-105">Out-of-box models</span></span>

<span data-ttu-id="e3654-106">Lengviausias būdas pradėti prognozuoti duomenis yra iš anksto nustatyti modeliai, dažnai vadinami visiškai parengtais modeliais.</span><span class="sxs-lookup"><span data-stu-id="e3654-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="e3654-107">Jiems reikia tik tam tikrų duomenų ir struktūros, kad jie galėtų greitai sugeneruoti įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="e3654-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="e3654-108">Šiuo metu galimi šie modeliai:</span><span class="sxs-lookup"><span data-stu-id="e3654-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="e3654-109">[Klientų ciklo vertė](predict-customer-lifetime-value.md): Prognozuoja potencialias kliento pajamas visos sąveikos su verslu metu.</span><span class="sxs-lookup"><span data-stu-id="e3654-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="e3654-110">[Produkto rekomendacija](predict-product-recommendation.md): Pasiūlo numatytąsias produktų rekomendacijas pagal pirkimo elgseną ir klientus su panašiais pirkimo modeliais.</span><span class="sxs-lookup"><span data-stu-id="e3654-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="e3654-111">[Prenumeratų praradimas](predict-subscription-churn.md): Prognozuoja, ar yra rizika, kad klientas nebenaudos jūsų įmonės prenumeruojamų produktų ar paslaugų.</span><span class="sxs-lookup"><span data-stu-id="e3654-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="e3654-112">[Operacijų praradimas](predict-transactional-churn.md): Numato, ar klientas nebepirks jūsų produktų ar paslaugų tam tikru skirtuoju laiku.</span><span class="sxs-lookup"><span data-stu-id="e3654-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="e3654-113">„Azure“ mašininio mokymo integravimas</span><span class="sxs-lookup"><span data-stu-id="e3654-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="e3654-114">Jei organizacija jau naudoja mašininio mokymo scenarijus, pagrįstus „Azure” mašininio mokymo eksperimentais, „Customer Insights” pasirinktinių modelių funkcija padeda susieti informaciją.</span><span class="sxs-lookup"><span data-stu-id="e3654-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="e3654-115">Kurkite darbo eigas, padedančias pasirinkti duomenis, iš kurių norite generuoti įžvalgas, ir susieti rezultatus su jūsų vieningaisiais klientų profiliais.</span><span class="sxs-lookup"><span data-stu-id="e3654-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="e3654-116">Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="e3654-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="e3654-117">„AI Builder“ prognozė</span><span class="sxs-lookup"><span data-stu-id="e3654-117">AI Builder prediction</span></span>

<span data-ttu-id="e3654-118">Kartais duomenų rinkiniai yra neišsamūs ir trūksta tam tikrų reikšmių.</span><span class="sxs-lookup"><span data-stu-id="e3654-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="e3654-119">„Customer Insights” gali padėti numatyti trūkstamas Kliento objekto ir segmentų reikšmes.</span><span class="sxs-lookup"><span data-stu-id="e3654-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="e3654-120">Daugiau informacijos rasite [Užbaikite savo nepilnus duomenis naudodami prognozes](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="e3654-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
