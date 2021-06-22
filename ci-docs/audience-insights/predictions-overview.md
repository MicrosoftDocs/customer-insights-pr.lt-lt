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
# <a name="predictions-overview"></a>Prognozių apžvalga

„Dynamics 365 Customer Insights” pateikia daugybę parinkčių, kurios išnaudoja AI ir mašininį mokymą duomenų prognozavimui. 

## <a name="out-of-box-models"></a>Visiškai parengti modeliai

Lengviausias būdas pradėti prognozuoti duomenis yra iš anksto nustatyti modeliai, dažnai vadinami visiškai parengtais modeliais. Jiems reikia tik tam tikrų duomenų ir struktūros, kad jie galėtų greitai sugeneruoti įžvalgas. Šiuo metu galimi šie modeliai: 
- [Klientų ciklo vertė](predict-customer-lifetime-value.md): Prognozuoja potencialias kliento pajamas visos sąveikos su verslu metu. 
- [Produkto rekomendacija](predict-product-recommendation.md): Pasiūlo numatytąsias produktų rekomendacijas pagal pirkimo elgseną ir klientus su panašiais pirkimo modeliais.
- [Prenumeratų praradimas](predict-subscription-churn.md): Prognozuoja, ar yra rizika, kad klientas nebenaudos jūsų įmonės prenumeruojamų produktų ar paslaugų.
- [Operacijų praradimas](predict-transactional-churn.md): Numato, ar klientas nebepirks jūsų produktų ar paslaugų tam tikru skirtuoju laiku.

## <a name="azure-machine-learning-integration"></a>„Azure“ mašininio mokymo integravimas

Jei organizacija jau naudoja mašininio mokymo scenarijus, pagrįstus „Azure” mašininio mokymo eksperimentais, „Customer Insights” pasirinktinių modelių funkcija padeda susieti informaciją. Kurkite darbo eigas, padedančias pasirinkti duomenis, iš kurių norite generuoti įžvalgas, ir susieti rezultatus su jūsų vieningaisiais klientų profiliais. Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).

## <a name="ai-builder-prediction"></a>„AI Builder“ prognozė

Kartais duomenų rinkiniai yra neišsamūs ir trūksta tam tikrų reikšmių. „Customer Insights” gali padėti numatyti trūkstamas Kliento objekto ir segmentų reikšmes. Daugiau informacijos rasite [Užbaikite savo nepilnus duomenis naudodami prognozes](predictions.md).
