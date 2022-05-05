---
title: Siūlomi segmentai, pagrįsti veikla.
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
ms.openlocfilehash: 85c3cef3a8d531b31b64a7e5decbdc122c4383fc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643513"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Siūlomi segmentai, pagrįsti veiklos duomenimis (peržiūros versija)

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
Jei jūs esate sveikatos priežiūros versle ir suteikiate visuomenės sveikatos priežiūrą, o jūsų tikslas yra sumažinti atskirų pacientų išlaidas. Būdas tai padaryti galėtų būti sumažinti vizitų dažnumą suteikiant geriausią įmanomą priežiūrą per kiek įmanoma mažiau vizitų. Tokiu atveju jūsų tikslas yra išlaikyti žemą vizitų dažnumą ir sumažinti pasikartojančias pacientų išlaidas. Taip pat galite nustatyti pacientų, turinčių dažnus vizitus ir dideles pasikartojančias išlaidas, segmentus bei išanalizuoti tuos atvejus, kad patobulintumėte asmeninį gydymą. 

## <a name="required-data"></a>Būtini duomenys

Pasiūlymai yra generuojami pagal pasirinktus įvesties duomenis. 

- Klientų profiliai: Visi klientai arba konkretaus segmento nariai. 

- Laikotarpis: Pastarasis mėnuo, Pastarieji metai arba bet kuris kitas pasirinktinis skirtasis laikas.

- Veiklos tipas: Pirkimai, mažmeninės prekybos operacijos, internetinės operacijos, klientų palaikymo atvejai, prenumeratos ir kita.  

- „Customer Insights” objektas, kuriame yra veiklos duomenys: Suvienodintos arba konkrečios veiklos objektas. 

- Įtrauktinos dimensijos: Naujumo, dažnumo arba piniginė dimensija, priklausomai nuo jūsų veiklos reikalavimų.

## <a name="generate-suggested-segments"></a>Kurti siūlomus segmentus

1. Eikite į **Segmentai**.

1. Pažymėkite skirtuką **Pasiūlymai**.

1. Pažymėkite **Rasti naujus pasiūlymus** ir pasirinkite **Peržiūrėti arba numatyti klientų elgesį**. Pažymėkite **Pradėti**, kad būtų vykdoma interaktyvioji patirtis.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Pirmasis veikla pagrįsto segmento konfigūravimo vedlio veiksmas.":::

1. Pateikite reikiamus įvesties duomenis ir pažymėkite **Toliau**, kad tęstumėte.

   - Klientų pasirinkimas: Įtraukite visus klientus arba konkretų segmentą.
   - Veiklos pasirinkimas: Pažymėkite veiklos tipą ir veiklą apibūdinančius objektus.
   - Nuostatos: Nustatykite į kurį laikotarpį reikia atsižvelgti ir pasiūlymų veiksnius, bei susiekite atributus.

1. Peržiūrėkite savo įvestį ir pasirinkite **Vykdyti**, kad paleistumėte modelį ir sugeneruotumėte pasiūlymus.

1. Priklausomai nuo klientų profilių ir pasirinktų veiklų skaičiaus, tai gali užtrukti kelias minutes. 

Sugeneravę pasiūlymus, galite juos filtruoti pagal labiausiai dominantį aspektą arba reikšmę. 

## <a name="view-details-of-a-suggested-segment"></a>Peržiūrėkite siūlomo segmento informaciją

Sugeneruoti pasiūlymai bus pateikti parinktyse **Segmentai** > **Pasiūlymai (peržiūros versija)**, esančiose **Veikla pagrįsti pasiūlymai** skyriuje.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Išplėstinė šoninė sritis, rodanti išsamius siūlomo segmento duomenis.":::

Siūlomam segmentui pasirinkite **Peržiūrėti pasiūlymą**, kad peržiūrėtumėte to segmento išsamią informaciją. Šoninėje srityje pateikiama išsami informacija, pavyzdžiui, kiekvienos dimensijos apimtis, palyginus su tiksline grupe. Be to, joje akcentuojamas potencialių segmento narių skaičius ir atitinkama visų klientų procentinė dalis. Jei pasiūlymą norite išsaugoti kaip segmentą, pažymėkite **Kurti segmentą**.    

## <a name="save-a-suggestion-as-a-segment"></a>Įrašykite siūlymą kaip segmentą

1. Eikite į **Segmentai** > **Pasiūlymai (peržiūra)**.

1. Pasirinkite norimą įrašyti segmentą. 

1. Šoninėje srityje pasirinkite **Kurti segmentą**. 

1. Įrašius segmentą, jis bus rodomas segmentų sąraše, esančiame **Visų segmentų** skirtuke ir dabar jį galima [atnaujinti arba panaikinti kaip ir bet kurį kitą segmentą](segments.md). Jūs negalite redaguoti segmento išsamios informacijos. Tačiau galite pakeisti pasiūlymų įvesties kriterijus ir sugeneruoti skirtingus pasiūlymus.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Pasiūlymų rinkinio atnaujinimas arba redagavimas

1. Eikite į **Segmentai** > **Pasiūlymai (peržiūros versija)** ir ieškokite segmento skyriuje **Veikla pagrįsti pasiūlymai**.

1. Pasirinkite **Atnaujinti pasiūlymus,** kad išlikdami sukonfigūruoti atributai būtų atnaujinti pasiūlymus. Taip pat galite pasirinkti **Redaguoti pasiūlymus**, jei norite modifikuoti sukonfigūruotus atributus. Sistema iš naujo paleis procesą, sugeneruos segmentų pasiūlymus pagal naujausius duomenis, ir pakeis dabartinius pasiūlymus.

[!INCLUDE [footer-include](includes/footer-banner.md)]
