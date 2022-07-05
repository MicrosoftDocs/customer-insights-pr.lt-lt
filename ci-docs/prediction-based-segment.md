---
title: Segmento kūrimas pagal prognozė modelį
description: Kurkite segmentus pagal prognozės modelio rezultato objektą.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: d67594f2467c1a0fde84b1ba0bd1afa4025e7b71
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082432"
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