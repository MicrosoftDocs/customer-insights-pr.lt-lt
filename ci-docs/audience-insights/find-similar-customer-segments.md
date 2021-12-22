---
title: Raskite panašių klientų naudodami AI (Video)
description: Raskite panašių klientų segmentų, naudodami dirbtinį intelektą.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7999c4964773c3b5c49537027a2ed67f0ad57ec5
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903900"
---
# <a name="similar-customers-preview"></a>Panašūs klientai (peržiūros versija)

Naudodamiesi šia funkcija, klientų bazėje rasite panašių klientų, naudodami dirbtinį intelektą. Norint naudotis šia funkcija, būtina sukurti bent vieną segmentą. Išplėtus esamo segmento kriterijus, bus lengviau rasti klientų, panašių į tą segmentą.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> Naudojant funkciją *Panašių klientų radimas*, taikomos automatinės priemonės duomenims įvertinti ir prognozėms pateikti remiantis minėtais duomenimis, todėl šią funkciją galima naudoti kaip profiliavimo metodą, apibrėžtą Bendrajame duomenų apsaugos reglamente („BDAR“). Jei klientas naudoja šią funkciją apdoroti duomenims, gali būti taikomi BDAR arba kiti įstatymai ir kiti teisės aktai. Esate atsakingas už užtikrinimą, kad naudojate „Dynamics 365 Customer Insights“, įskaitant prognozes, atitikimą su visais taikomais teisės aktais ir reglamentais, įskaitant teisės aktus susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir bendravimo konfidencialumu.

## <a name="finding-similar-customers"></a>Panašių klientų radimas

1. Publikos įžvalgose eikite į **Segmentų** puslapį ir pasirinkite segmentą, kuriuo norite pagrįsti naują savo segmentą. Tai jūsų *šaltinio segmentas*.

1. Veiksmų juostoje pažymėkite **Panašių klientų radimas**.

1. Peržiūrėkite siūlomą naujo segmento pavadinimą ir, jei reikia, jį pakeiskite.

1. Peržiūrėkite laukus, kuriuose apibrėžiamas naujas segmentas. Šiuose laukuose apibrėžiamas pagrindas, pagal kurį sistema bandys rasti į šaltinio segmentą panašių klientų. Sistema pagal numatytuosius nustatymus pasirenka rekomenduojamus laukus.
  Laukai, kurie gali gerokai sumažinti modelio veikimą, automatiškai neįtraukiami.
  
   - Laukai, kurių duomenų tipai yra: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Laukai, kurių svarba (lauko elementų skaičius) yra mažesnis nei 2 arba didesnis nei 30

1. Pasirinkite, ar į naują segmentą turi būti įtraukti **Visi klientai**, ar tik klientai, esantys **Tam tikrame esamame segmente**.

1. Pašalinkite šaltinio segmento klientus, pažymėdami žymės langelį **Neįtraukti šaltinio segmento klientų**.

1. Pagal numatytuosius nustatymus sistema siūlo į išvestį įtraukti tik 20 % tikslinės auditorijos. Jei reikia, redaguokite šią ribinę vertę. Padidinus ribinę vertę, sumažės tikslumas.

1. Pasirinkite **Vykdyti** puslapio apačioje ir paleiskite dvejetainio klasifikavimo užduotį (mašininio mokymo metodą), kuria analizuojamas duomenų rinkinys.

## <a name="view-the-similar-segment"></a>Panašaus segmento peržiūra

Apdoroję panašų segmentą, naują segmentą rasite puslapyje **Segmentai**.

> [!div class="mx-imgBorder"]
> ![Panašių klientų segmentas.](media/expanded-segment.png "Panašių klientų segmentas")

Norėdami atidaryti išsamią informaciją apie segmentą, veiksmų juostoje pasirinkite **Peržiūra**. Šiame rodinyje pateikiama informacija apie rezultatų paskirstymą remiantis [panašumo įverčiais](#about-similarity-scores). Panašumo įverčių reikšmes taip pat rasite pasirinkę **Segmento narių peržiūra**.

## <a name="use-the-output-of-a-similar-segment"></a>Panašaus segmento išvesties naudojimas

Galite [naudoti panašaus segmento išvestį](segments.md) kaip ir kitų segmentų išvestis. Pavyzdžiui, eksportuokite segmentą arba sukurkite priemonę.

## <a name="refresh-and-edit-a-similar-segment"></a>Panašaus segmento atnaujinimas ir redagavimas

Jei norite atnaujinti panašų segmentą, pažymėkite jį puslapyje **Segmentai** ir veiksmų juostoje pasirinkite **Atnaujinti**.

Redaguojant panašų segmentą, duomenys apdorojami iš naujo. Anksčiau sukurtas segmentas atnaujinamas įtraukiant atnaujintus duomenis.    
Jei norite redaguoti panašų segmentą, pažymėkite jį puslapyje **Segmentai** ir veiksmų juostoje pasirinkite **Redaguoti**. Pritaikykite pakeitimus ir pasirinkite **Vykdyti**, kad pradėtumėte apdorojimą.

## <a name="delete-a-similar-segment"></a>Panašaus segmento naikinimas

Pažymėkite segmentą puslapyje **Segmentai** ir veiksmų juostoje pasirinkite **Naikinti**. Paskui patvirtinkite naikinimą.

## <a name="about-similarity-scores"></a>Apie panašumo įverčius

Dvejetainio klasifikavimo mašininio mokymo modelyje panašaus segmento klientams priskiriamas įvertis. Įvertis grindžiamas panašumu į klientus šaltinio segmente.

- Panašumo įverčiai, mažesni nei 0,55, yra klientai, kurie sistemoje klasifikuojami kaip *nepanašūs* į šaltinio segmento klientus
- Panašumo įverčiai nuo 0,55 iki 0,7 klasifikuojami kaip *šiek tiek panašūs*
- Panašumo įverčiai nuo 0,7 iki 0,85 klasifikuojami kaip *panašūs*
- Panašumo įverčiai nuo 0,85 iki 1 yra klientai, kurie sistemoje klasifikuojami kaip *labai panašūs*

Klientai, kurių panašumo įverčiai yra mažesni nei 0,4, į modelio išvestį neįtraukiami. Sistema nelaiko jų pakankamai panašiais į šaltinio segmentą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]