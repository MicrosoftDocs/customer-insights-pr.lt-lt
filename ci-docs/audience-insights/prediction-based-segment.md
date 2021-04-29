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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Segmento kūrimas pagal prognozės modelį (peržiūra)

Prognozės rezultatai kartais taikomi tik antriniams jūsų klientų rinkiniams. Padidinkite rekomendacijų suasmeninimą sukurdami segmentus pagal prognozės modelių rezultatus. Pavyzdžiui, galite pateikti konkrečias rekomendacijas klientams, kurie teikia pirmenybę tam tikro tipo aptarnavimui. 

## <a name="prerequisites"></a>Būtinosios sąlygos

- Bent [bendraautoriaus teisės](permissions.md) „Customer Insights“.

- Produkto rekomendacija, sandorio praradimas, prenumeratos praradimas arba kliento nuolatinės vertės modelis, sukonfigūruotas srityje „Customer Insights“. Peržiūrėkite reikalavimus skirtingiems modeliams nustatyti:

  - [Produkto rekomendacijos modelis](predict-product-recommendation.md)
  - [Prenumeratos praradimo modelis](predict-subscription-churn.md)
  - [Operacijos praradimo modelis](predict-transactional-churn.md)
  - [Kliento naudojimo laiko vertės modelis](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Kliento segmento kūrimas pagal prognozes

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pažymėkite vertikalias elipses prie modelio, kurį norite peržiūrėti, ir pasirinkite **Peržiūrėti**.

1. Rezultatų puslapyje pasirinkite **Kurti segmentą**. Daugiau informacijos apie rezultatų puslapį rasite straipsnyje apie modelį.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Prognozės rezultatų puslapio ekrano nuotrauka su pažymėtu segmento kūrimo veiksmu.":::

1. Kurkite naują segmentą pagal pasirinkto modelio rezultato objektą. Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).