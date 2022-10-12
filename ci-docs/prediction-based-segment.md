---
title: Segmento kūrimas pagal prognozė modelį
description: Kurkite segmentus pagal prognozės modelio rezultato objektą.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610430"
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

1. Pasirinkite modelį, kurį norite peržiūrėti, ir pasirinkite **Peržiūrėti**.

1. Rezultatų puslapyje pasirinkite **Kurti segmentą**. Daugiau informacijos apie rezultatų puslapį rasite straipsnyje apie modelį.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Prognozės rezultatų puslapio ekrano nuotrauka su pažymėtu segmento kūrimo veiksmu.":::

1. Sukurkite naują segmentą naudodami pasirinkto modelio išvesties objekto atributus. Daugiau informacijos rasite [Segmentų kūrimas ir valdymas](segments.md).

> [!TIP]
> Taip pat galite sukurti prognozė modelio **segmentą puslapyje Segmentai**, pasirinkdami Naujas **ir pasirinkdami** **Kurti iš** > **"Intelligence"**. Norėdami gauti daugiau informacijos, žiūrėkite [Naujo segmento su greitais segmentais](segment-quick.md) kūrimas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
