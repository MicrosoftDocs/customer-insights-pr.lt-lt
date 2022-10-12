---
title: Prognozių apžvalga
description: Prognozės scenarijų ir parinkčių, kuriuos apima „Dynamics 365 Customer Insights” taikomoji programa.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610200"
---
# <a name="predictions-overview"></a>Prognozių apžvalga

„Dynamics 365 Customer Insights” pateikia daugybę parinkčių, kurios išnaudoja AI ir mašininį mokymą duomenų prognozavimui.

## <a name="out-of-box-models"></a>Visiškai parengti modeliai

Lengviausias būdas pradėti prognozuoti duomenis yra iš anksto nustatyti modeliai, dažnai vadinami visiškai parengtais modeliais. Jiems reikia tik tam tikrų duomenų ir struktūros, kad jie galėtų greitai sugeneruoti įžvalgas. Galimi šie modeliai:

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- [Klientų ciklo vertė](predict-customer-lifetime-value.md): Prognozuoja potencialias kliento pajamas visos sąveikos su verslu metu.
- [Produkto rekomendacija](predict-product-recommendation.md): Pasiūlo numatytąsias produktų rekomendacijas pagal pirkimo elgseną ir klientus su panašiais pirkimo modeliais.
- [Prenumeratų praradimas](predict-subscription-churn.md): Prognozuoja, ar yra rizika, kad klientas nebenaudos jūsų įmonės prenumeruojamų produktų ar paslaugų.
- [Operacijų nutraukimas](predict-transactional-churn.md): prognozuojama, ar atskiras klientas nebepirks jūsų produktų ar paslaugų per tam tikrą laikotarpį.
- [Nuotaikų analizė](sentiment-analysis.md): analizuoja klientų atsiliepimų nuotaikas ir nustato dažnai minimus verslo aspektus.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- [Operacijų nutraukimas](predict-transactional-churn.md): prognozuojama, ar kliento paskyra nebepirks jūsų produktų ar paslaugų per tam tikrą laikotarpį.

---

> [!TIP]
> Rekomenduojame reguliariai atnaujinti parengtus naudoti modelius su atnaujintais duomenimis, kad įsitikintumėte, jog jie tiksliai informuoja jūsų verslo naudojimo atvejį. Duomenys atnaujinami ad hoc, kai sistema praryja naujus arba atnaujintus duomenų šaltinius. Tačiau modeliai tik šiuo atveju bus atšaukti ir toliau naudos esamus mokymo duomenis.
>
> **Konfigūruokite naujinimo tvarkaraštį** nustatydami modelio perkvalifikavimo tvarkaraštį konfigūravimo metu. Modelis persikvalifikuos ir pakeis šį tvarkaraštį, kurį galėsite bet kada pakeisti.

## <a name="azure-machine-learning-integration"></a>„Azure“ mašininio mokymo integravimas

Jei organizacija jau naudoja mašininio mokymo scenarijus, pagrįstus „Azure” mašininio mokymo eksperimentais, „Customer Insights” pasirinktinių modelių funkcija padeda susieti informaciją. Kurkite darbo eigas, padedančias pasirinkti duomenis, iš kurių norite generuoti įžvalgas, ir susieti rezultatus su jūsų vieningaisiais klientų profiliais. Daugiau informacijos rasite [Pasirinktiniai mašininio mokymo modeliai](custom-models.md).

## <a name="manage-existing-predictions"></a>Esamų prognozių valdymas

Eikite į **puslapį Žvalgybos** > **prognozės**. Skirtuke **Mano numatymai** peržiūrėkite savo sukurtas prognozes, jų prognozė tipą, išvesties objekto pavadinimą, būseną, paskutinį kartą, kai prognozė buvo redaguotas, ir paskutinį kartą, kai duomenys buvo atnaujinti. Prognozių sąrašą galite rūšiuoti pagal bet kurį stulpelį.

Pasirinkite prognozė, kad peržiūrėtumėte galimus veiksmus.

:::image type="content" source="media/predictions.png" alt-text="Mano prognozių puslapis.":::

- **Redaguokite** prognozė, kad pakeistumėte jo ypatybes.
- [**Atnaujinkite**](#refresh-a-prediction) prognozė, kad įtrauktumėte naujausius duomenis.
- **Peržiūrėkite** išsamią prognozė informaciją.
- [**Įvesties duomenų naudojimo ataskaitą**](#view-the-input-data-usability-report), kad galėtumėte peržiūrėti klaidas, įspėjimus ir rekomendacijas.
- **Ištrinkite** prognozė.

### <a name="refresh-a-prediction"></a>Prognozės atnaujinimas

Numatymai gali būti atnaujinami automatiniu grafiku arba atnaujinami rankiniu būdu pagal poreikį. Norėdami rankiniu būdu atnaujinti visus numatymus, pasirinkite **Atnaujinti viską**. Norėdami rankiniu būdu atnaujinti prognozė, pasirinkite jį ir pasirinkite **Atnaujinti**. Norėdami [suplanuoti automatinį atnaujinimą](schedule-refresh.md), eikite į **Administratoriaus** > **sistemos** > **tvarkaraštis**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Peržiūrėti įvesties duomenų naudojimo ataskaitą

Įvesties duomenų naudojimo ataskaita pateikia klaidų ir įspėjimų, kuriuos gali sugeneruoti jūsų visiškai parengtos prognozės, apibendrintą rodinį. Jame taip pat pateikiamos rekomendacijos, kaip pagerinti modelio našumą.

Ataskaita yra pasiekiama atlikus modelio mokymo procesą. Jis sukurtas kiekvienam modeliui atskirai, neatsižvelgiant į tai, ar jis sėkmingai baigė mokymus, ar ne.

Skirtuke **Mano numatymai** pasirinkite prognozė ir pasirinkite **Įvesties duomenų naudojimo ataskaitą**. Arba prognozė išsamios informacijos rodinyje pasirinkite **Įvesties duomenų naudojimo ataskaita**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Įvesties duomenų naudojimo ataskaitos, rodančios lentelę su klaidomis, įspėjimais ir rekomendacijomis, pavyzdys.":::

Ataskaitoje pateikiama:

- **Pavadinimas:** aprašomasis klaidos, įspėjimo arba rekomendacijos pavadinimas.
- **Žingsnis:** Modelio fazė, traukinys ar balas, informacija nurodo.
- **Būsena:** informacijos rimtumas (klaida, įspėjimas, rekomendacija).
- **Stulpelio pavadinimas:** stulpelis objekte, kurį reikia modifikuoti, kad būtų pagerintas modelio našumas.
- **Objekto pavadinimas:** objekto, kurį reikia modifikuoti, kad būtų pagerintas modelio našumas, pavadinimas.
- **Išsami informacija:** išsami informacija apie klaidą, įspėjimą arba rekomendaciją.

[!INCLUDE [footer-include](includes/footer-banner.md)]
