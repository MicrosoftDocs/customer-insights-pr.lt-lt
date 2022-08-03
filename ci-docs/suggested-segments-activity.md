---
title: Siūlomi segmentai pagal veiklą (peržiūra)
description: Leiskite mašininiam mokymui padėti jums surasti naujus ir įdomius segmentus, pagrįstus klientų veikla.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170599"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Siūlomi segmentai pagal veiklą (peržiūra)

Atraskite jūsų klientų įdomius segmentus pagal klientų veiklos duomenis, įtrauktus į „Customer Insights”. Veiklos duomenų pavyzdžiai yra operacijos, palaikymo skambučio trukmė, pirkimai ar grąžinimai. Siekiant pasiūlyti segmentus, veiklos duomenys yra analizuojami pagal naujumą, dažnumą ir piniginę vertę (arba trukmę). Taip pat galite sugeneruoti [siūlomus segmentus, kad pagerintumėte priemonę, ar geriau suprastumėte, kas sąlygoja atributą](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Siūlomų segmentų skirtukas, kuriame rodomi segmentų pasiūlymai pagal veiklą ir atributais pagrįsti segmentai.":::

## <a name="categorize-customers-by-activity"></a>Klientų skirstymas į kategorijas pagal veiklą

Naudodami [veiklos duomenis](activities.md), pasiekiamus „Customer Insights”, galime sugeneruoti pasiūlymus, kurie atitinka klientų grupes:

- aktyviausi klientai 
- klientai, kurie atliko daugiausia pirkimų 
- klientai, kurie sugeneravo daugiausia pajamų 
- klientai, kurie pastaruoju metu nebuvo aktyvūs 
- klientai, kurie dažnai sąveikauja su jūsų verslu  

Jei turite mažmeninės prekybos įmonę, galite sužinoti, kurie klientai sugeneruoja daugiausia pajamų ir apdovanoti juos kuponu. Taip pat, galite identifikuoti nenuolatinius klientus ir pasiūlyti jiems prisijungti prie apdovanojimų programos, kad jie dažniau lankytų jūsų įmonę.
Jei teikiate viešąsias sveikatos priežiūros paslaugas ir jūsų tikslas yra sumažinti atskirų pacientų išlaidas, galite pabandyti sumažinti pasikartojančių apsilankymų skaičių teikdami geriausią įmanomą priežiūrą per kuo mažiau apsilankymų. Tokiu atveju jūsų tikslas yra išlaikyti žemą vizitų dažnumą ir sumažinti pasikartojančias pacientų išlaidas. Taip pat galite nustatyti pacientų, turinčių dažnus vizitus ir dideles pasikartojančias išlaidas, segmentus bei išanalizuoti tuos atvejus, kad patobulintumėte asmeninį gydymą.

## <a name="required-data"></a>Būtini duomenys

Pasiūlymai yra generuojami pagal pasirinktus įvesties duomenis.

- Klientų profiliai: Visi klientai arba konkretaus segmento nariai.

- Laikotarpis: Pastarasis mėnuo, Pastarieji metai arba bet kuris kitas pasirinktinis skirtasis laikas.

- Veiklos tipas: Pirkimai, mažmeninės prekybos operacijos, internetinės operacijos, klientų palaikymo atvejai, prenumeratos ir kita.  

- „Customer Insights” objektas, kuriame yra veiklos duomenys: Suvienodintos arba konkrečios veiklos objektas.

- Įtrauktinos dimensijos: Naujumo, dažnumo arba piniginė dimensija, priklausomai nuo jūsų veiklos reikalavimų.

## <a name="generate-suggested-segments"></a>Kurti siūlomus segmentus

1. Eikite į **Segmentai** ir pasirinkite skirtuką **Pasiūlymai (peržiūra).**

1. Pažymėkite **Rasti naujus pasiūlymus** ir pasirinkite **Peržiūrėti arba numatyti klientų elgesį**. Pasirinkite **Pradėti**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Pirmasis veikla pagrįsto segmento konfigūravimo vedlio veiksmas.":::

1. Pateikite reikiamus įvesties duomenis ir pasirinkite **Pirmyn**.

   - Klientų pasirinkimas: Įtraukite visus klientus arba konkretų segmentą.
   - Veiklos pasirinkimas: Pažymėkite veiklos tipą ir veiklą apibūdinančius objektus.
   - Nuostatos: Nustatykite į kurį laikotarpį reikia atsižvelgti ir pasiūlymų veiksnius, bei susiekite atributus.

1. Peržiūrėkite savo įvestį ir pasirinkite **Vykdyti**, kad paleistumėte modelį ir sugeneruotumėte pasiūlymus.

Priklausomai nuo klientų profilių ir pasirinktų veiklų skaičiaus, tai gali užtrukti kelias minutes.

Sugeneravę pasiūlymus, galite juos filtruoti pagal labiausiai dominantį aspektą arba reikšmę.

## <a name="manage-suggested-segments"></a>Siūlomų segmentų tvarkymas

Eikite į **Segmentai** ir pasirinkite skirtuką **Pasiūlymai (peržiūra).** **Skiltyje Veikla pagrįsti pasiūlymai** pasirinkite siūlomą segmentą, kad peržiūrėtumėte galimus veiksmus.

- **Peržiūrėkite pasiūlymą** peržiūrėti išsamią to segmento informaciją, pvz., kiekvieno aspekto mastą, palyginti su tiksline grupe. Be to, joje akcentuojamas potencialių segmento narių skaičius ir atitinkama visų klientų procentinė dalis.
- **Sukurkite segmentą**, kad išsaugotumėte siūlomą kaip segmentą. Jis rodomas skirtuke **Visi segmentai** ir gali būti [atnaujintas arba ištrintas](segments.md). Jūs negalite redaguoti segmento išsamios informacijos. Tačiau galite pakeisti pasiūlymų įvesties kriterijus ir sugeneruoti skirtingus pasiūlymus.
- **Redaguokite pasiūlymus** modifikuoti sukonfigūruotus atributus, kurie pakeis dabartinius pasiūlymus.
- **Atnaujinkite pasiūlymus**, kad atnaujintumėte pasiūlymus, išlaikydami sukonfigūruotus atributus.

[!INCLUDE [footer-include](includes/footer-banner.md)]
