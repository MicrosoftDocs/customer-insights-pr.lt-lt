---
title: Apžvalga apie palaikomus prognozės scenarijus
description: Prognozės scenarijų ir parinkčių, kuriuos apima „Dynamics 365 Customer Insights” taikomoji programa.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be452e4f1515f637f6edbc3ae3aaf6a3d3471489
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618853"
---
# <a name="predictions-overview"></a>Prognozių apžvalga

„Dynamics 365 Customer Insights” pateikia daugybę parinkčių, kurios išnaudoja AI ir mašininį mokymą duomenų prognozavimui. 

## <a name="out-of-box-models"></a>Visiškai parengti modeliai

Lengviausias būdas pradėti prognozuoti duomenis yra iš anksto nustatyti modeliai, dažnai vadinami visiškai parengtais modeliais. Jiems reikia tik tam tikrų duomenų ir struktūros, kad jie galėtų greitai sugeneruoti įžvalgas. Šiuo metu galimi šie modeliai: 

# <a name="individual-customers-b2c"></a>[Atskirų klientų (B2C)](#tab/b2c)

- [Klientų ciklo vertė](predict-customer-lifetime-value.md): Prognozuoja potencialias kliento pajamas visos sąveikos su verslu metu.
- [Produkto rekomendacija](predict-product-recommendation.md): Pasiūlo numatytąsias produktų rekomendacijas pagal pirkimo elgseną ir klientus su panašiais pirkimo modeliais.
- [Prenumeratų praradimas](predict-subscription-churn.md): Prognozuoja, ar yra rizika, kad klientas nebenaudos jūsų įmonės prenumeruojamų produktų ar paslaugų.
- [Operacijų praradimas](predict-transactional-churn.md): Numato, ar klientas nebepirks jūsų produktų ar paslaugų tam tikru skirtuoju laiku.

# <a name="business-accounts-b2b"></a>[Verslo klientai (B2B)](#tab/b2b)

- [Operacijų praradimas](predict-transactional-churn.md): Numato, ar klientas nebepirks jūsų produktų ar paslaugų tam tikru skirtuoju laiku.

---


## <a name="azure-machine-learning-integration"></a>„Azure“ mašininio mokymo integravimas

Jei organizacija jau naudoja mašininio mokymo scenarijus, pagrįstus „Azure” mašininio mokymo eksperimentais, „Customer Insights” pasirinktinių modelių funkcija padeda susieti informaciją. Kurkite darbo eigas, padedančias pasirinkti duomenis, iš kurių norite generuoti įžvalgas, ir susieti rezultatus su jūsų vieningaisiais klientų profiliais. Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).

## <a name="ai-builder-prediction"></a>„AI Builder“ prognozė

Kartais duomenų rinkiniai yra neišsamūs ir trūksta tam tikrų reikšmių. „Customer Insights” gali padėti numatyti trūkstamas Kliento objekto ir segmentų reikšmes. Daugiau informacijos rasite [Užbaikite savo nepilnus duomenis naudodami prognozes](predictions.md).
