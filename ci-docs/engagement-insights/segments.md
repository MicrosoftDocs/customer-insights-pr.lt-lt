---
title: Peržiūrėti ir kurti segmentus
description: Kaip kurti, redaguoti ir naikinti segmentus, bei kur juos naudoti.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225386"
---
# <a name="view-and-create-segments"></a>Peržiūrėti ir kurti segmentus

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmentai leidžia jums identifikuoti lankytojų antrinius rinkinius pagal charakteristikas arba sąveiką su žiniatinklio svetaine. Segmentai leidžia jums taikyti filtrus ir analizuoti šiuos antrinius rinkinius. Analizė gali padėti išnagrinėti ir reaguoti į jūsų verslo tendencijas. 

:::image type="content" source="media/segments-page.png" alt-text="Įtraukimo įžvalgų programos ekrano kopija, rodanti esamų segmentų sąrašą darbo srityje.":::

## <a name="view-segments"></a>Peržiūrėti segmentus

1. Eikite į **Duomenys** kairiojoje naršymo srityje. 

1. Pasirinkite **Segmentų** skirtuką, kad pamatytumėte visų segmentų sąrašą darbo srityje. 

## <a name="create-a-segment"></a>Kurti segmentą

Segmentus sudaro taisyklės ir sąlygos, susijusios su loginiais operatoriais. Sąlygos taiko filtrus pažymėtai dimensijai. Kiekvienas segmentas gali naudoti ne daugiau nei penkias dimensijas.

Toliau pateiktame pavyzdyje rodomas segmentas, kurio vienoje taisyklėje yra dvi sąlygos. Jis filtruoja visus svetainės įvykius, kai naršyklė yra „Chrome”, o operacinė sistema yra „iOS” arba „Android”.

:::image type="content" source="media/segment-sample.png" alt-text="Pavyzdiniai segmentai, turinčių dvi sąlygas vienoje taisyklėje, skirtoje žiniatinklio įvykiams filtruoti.":::

Šiame skyriuje aprašoma, kaip sukurti *tuščią segmentą* nuo nulio.

1. Eikite į **Duomenys** > **Segmentai**.

1. Pasirinkite **Naujas segmentas**.

1. Išteklių **bibliotekoje pažymėkite** (+) šalia atributo, pagal kurį norite filtruoti. Šiuo metu galite kurti tik segmentus pagal dimensijas.

   :::image type="content" source="media/create-new-segment.png" alt-text="Sukurkite naują segmentą.":::

1. Taisyklės **skyriuje** pasirinkite operatorių ir pažymėto atributo reikšmę. Palaikomos toliau pateiktos operacijos.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Pasirinkite naujo segmento operatorių.":::

   - **yra**: būtinas tikslus atitikmuo, kad reikšmės būtų įtrauktos. Naudoja **lygus** vienai reikšmei arba **bet kuris iš** kelių reikšmių įtraukimui.
   - **nėra**: būtinas tikslus atitikmuo, kad reikšmės nebūtų įtrauktos. Naudoja **lygus** vienai reikšmei arba **bet kuris iš** kelių reikšmių įtraukimui.
   - **prasideda**: eilutė, kuria prasideda sutampančios reikšmės.
   - **pasibaigia**: eilutė, kuria pasibaigia sutampančios reikšmės.
   - **apima**: eilutė, esanti sutampančiose reikšmėse.

1. Norėdami į grupę įtraukti daugiau sąlygų, galite naudoti loginius operatorius. Suplanuoti atributai yra įtraukiami naudojant rinkinio operatorius.
   - Operatorius **IR**: abi sąlygos turi būti įvykdytos kaip segmentavimo proceso dalis. Ši parinktis labiausiai naudinga nustatant sąlygas skirtingiems objektams.
   - Operatorius **ARBA**: viena iš sąlygų turi būti įvykdyta kaip segmentavimo proceso dalis. Ši parinktis labiausiai naudinga nustatant kelias sąlygas tam pačiam objektui.

1. Pasirinkite **Įrašyti** ir pavadinkite segmentą. 

Segmentas bus pateiktas **Segmentų** puslapyje ir jį galėsite taikyti visoms darbo srities ataskaitoms ir piltuvėliams.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Segmento naudojimas ataskaitoje arba piltuvėlyje

Galite taikyti segmentus ataskaitai arba piltuvėliui, kad filtruotumėte juos pagal segmento sąlygas. Tačiau negalite taikyti segmentų naudojimo realiuoju laiku ataskaitai.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Puslapių rodinių ataskaita su išplėstiniu išplečiamajame sąraše, kad būtų galima pasirinkti, kuriuos segmentus taikyti.":::

Norėdami taikyti segmentą, atidarykite ataskaitą arba piltuvėlį. Pasirinkite **+ Įtraukti sąlygą** ir **Filtruoti pagal segmentą**. Iš sąrašo pasirinkite segmentą, kurį norite taikyti. Segmentas bus pritaikytas ataskaitai. Jeigu diagrama nepalaiko segmento, joje rodoma klaida. Daugiau informacijos žr. [Piltuvėlio ataskaitų kūrimas ir valdymas](funnel-reports.md).
 
Galite taikyti *iki trijų segmentų* ataskaitai arba piltuvėliui.

## <a name="edit-a-segment"></a>Redaguoti segmentą

1. Eikite į **Duomenys** > **Segmentai**.
1. Sąraše pasirinkite segmentą, kad jį atidarytumėte. 
1. Prireikus pakeiskite arba įtraukite reikšmes.
1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

## <a name="change-the-name-of-a-segment"></a>Segmento pavadinimo keitimas

1. Eikite į **Duomenys** > **Segmentai**.
1. Segmentų sąraše pasirinkite **Daugiau [...]**. 
1. Iš iškrentančiojo meniu rinkitės **Redaguoti pavadinimą**.
1. Įveskite naują pavadinimą ir pasirinkite **Pervadinti**.

## <a name="delete-a-segment"></a>Segmento naikinimas

1. Eikite į **Duomenys** > **Segmentai**.
1. Segmentų sąraše pasirinkite **Daugiau [...]**. 
1. Iš iškrentančiojo sąrašo rinkitės **Naikinti**.
1. Pasirinkite **Naikinti** patvirtinimui.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
