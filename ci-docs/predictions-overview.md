---
title: Prognozių apžvalga
description: Prognozės scenarijų ir parinkčių, kuriuos apima „Dynamics 365 Customer Insights” taikomoji programa.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083104"
---
# <a name="predictions-overview"></a>Prognozių apžvalga

„Dynamics 365 Customer Insights” pateikia daugybę parinkčių, kurios išnaudoja AI ir mašininį mokymą duomenų prognozavimui. 

## <a name="out-of-box-models"></a>Visiškai parengti modeliai

Lengviausias būdas pradėti prognozuoti duomenis yra iš anksto nustatyti modeliai, dažnai vadinami visiškai parengtais modeliais. Jiems reikia tik tam tikrų duomenų ir struktūros, kad jie galėtų greitai sugeneruoti įžvalgas. Šiuo metu galimi šie modeliai: 

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- [Klientų ciklo vertė](predict-customer-lifetime-value.md): Prognozuoja potencialias kliento pajamas visos sąveikos su verslu metu.
- [Produkto rekomendacija](predict-product-recommendation.md): Pasiūlo numatytąsias produktų rekomendacijas pagal pirkimo elgseną ir klientus su panašiais pirkimo modeliais.
- [Prenumeratų praradimas](predict-subscription-churn.md): Prognozuoja, ar yra rizika, kad klientas nebenaudos jūsų įmonės prenumeruojamų produktų ar paslaugų.
- [Operacijų praradimas](predict-transactional-churn.md): Numato, ar klientas nebepirks jūsų produktų ar paslaugų tam tikru skirtuoju laiku.
- [Nuotaikų analizė](sentiment-analysis.md): analizuokite klientų atsiliepimų nuotaikas ir nustatykite dažnai minimus verslo aspektus.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- [Operacijų praradimas](predict-transactional-churn.md): Numato, ar klientas nebepirks jūsų produktų ar paslaugų tam tikru skirtuoju laiku.

---

> [!TIP]
> Rekomenduojame reguliariai atnaujinti parengtus naudoti modelius su atnaujintais duomenimis, kad įsitikintumėte, jog jie tiksliai informuoja jūsų verslo naudojimo atvejį. Duomenys atnaujinami ad hoc, kai sistema praryja naujus arba atnaujintus duomenų šaltinius. Tačiau modeliai tik šiuo atveju bus atšaukti ir toliau naudos esamus mokymo duomenis.
> 
> Galite konfigūruoti **naujinimo tvarkaraštį** nustatydami modelio perkvalifikavimo tvarkaraštį konfigūravimo funkcijose. Modelis persikvalifikuos ir pakeis šį tvarkaraštį, kurį galėsite bet kada pakeisti.


## <a name="azure-machine-learning-integration"></a>„Azure“ mašininio mokymo integravimas

Jei organizacija jau naudoja mašininio mokymo scenarijus, pagrįstus „Azure” mašininio mokymo eksperimentais, „Customer Insights” pasirinktinių modelių funkcija padeda susieti informaciją. Kurkite darbo eigas, padedančias pasirinkti duomenis, iš kurių norite generuoti įžvalgas, ir susieti rezultatus su jūsų vieningaisiais klientų profiliais. Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder prognozė

Kartais duomenų rinkiniai yra neišsamūs ir trūksta tam tikrų reikšmių. „Customer Insights” gali padėti numatyti trūkstamas Kliento objekto ir segmentų reikšmes. Daugiau informacijos rasite [Užbaikite savo nepilnus duomenis naudodami prognozes](predictions.md).
