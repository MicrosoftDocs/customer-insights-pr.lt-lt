---
title: Panašių klientų radimas naudojant AI (peržiūra) (yra vaizdo įrašas)
description: Raskite panašių klientų segmentų, naudodami dirbtinį intelektą.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170737"
---
# <a name="find-similar-customers-with-ai-preview"></a>Panašių klientų radimas naudojant AI (peržiūra)

Raskite panašių klientų savo klientų bazėje naudodami dirbtinį intelektą. Norint naudoti šią funkciją, jums reikia bent vieno sukurto segmento. Esamo segmento kriterijų išplėtimas padeda rasti klientų, panašių į tą segmentą.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Rasti panašius klientus* naudoja automatizuotas priemones duomenims įvertinti ir pagal tuos duomenis prognozuoti. Todėl jis gali būti naudojamas kaip profiliavimo metodas, nes šis terminas apibrėžtas Bendrajame duomenų apsaugos reglamente (toliau – BDAR). Jei klientas naudoja šią funkciją apdoroti duomenims, gali būti taikomi BDAR arba kiti įstatymai ir kiti teisės aktai. Esate atsakingas už užtikrinimą, kad naudojate „Dynamics 365 Customer Insights“, įskaitant prognozes, atitikimą su visais taikomais teisės aktais ir reglamentais, įskaitant teisės aktus susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir bendravimo konfidencialumu.

## <a name="find-similar-customers"></a>Rasti panašių klientų

1. Eikite į **Segmentai** ir pasirinkite segmentą, kuriuo norite pagrįsti naują segmentą. Tai jūsų *šaltinio segmentas*.

1. Pasirinkite **Rasti panašių klientų**.

1. Peržiūrėkite siūlomą naujo segmento pavadinimą ir, jei reikia, jį pakeiskite.

1. Pasirinktinai pridėkite [žymų](work-with-tags-columns.md#manage-tags) prie naujo segmento.

1. Peržiūrėkite laukus, kuriuose apibrėžiamas naujas segmentas. Šiuose laukuose apibrėžiamas pagrindas, pagal kurį sistema bandys rasti į šaltinio segmentą panašių klientų. Sistema pagal numatytuosius nustatymus pasirenka rekomenduojamus laukus. Jei reikia, pridėkite daugiau laukų.
  Laukai, kurie gali gerokai sumažinti modelio veikimą, automatiškai neįtraukiami.
  
   - Laukai, kurių duomenų tipai yra: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Laukai, kurių svarba (lauko elementų skaičius) yra mažesnis nei 2 arba didesnis nei 30

1. Pasirinkite, ar norite įtraukti **visus klientus**, išskyrus šaltinio segmentą, ar tik klientus **kitame** segmente į naują segmentą.

1. Pagal numatytuosius nustatymus sistema siūlo į išvestį įtraukti tik 20 % tikslinės auditorijos. Jei reikia, redaguokite šią ribinę vertę. Padidinus ribinę vertę, sumažės tikslumas.

1. Įtraukite klientus į šaltinio segmentą pažymėdami žymimąjį laukelį **Įtraukti narius iš šaltinio segmento, be klientų su panašiais atributais**.

1. Puslapio apačioje pasirinkite **Vykdyti**, kad pradėtumėte dvejetainę [klasifikavimo užduotį](#about-similarity-scores) (mašininis mokymas metodą), kuri analizuoja duomenų rinkinį.

## <a name="view-the-similar-segment"></a>Panašaus segmento peržiūra

Apdoroję panašų segmentą, puslapyje Segmentai rasite naują segmentą **su plėtinio tipu** **.**

Pasirinkite **Peržiūrėti**, kad segmento narių peržiūroje pamatytumėte rezultatų pasiskirstymą panašumo [baluose](#about-similarity-scores) ir panašumo balo **reikšmes**.

:::image type="content" source="media/expanded-segment.png" alt-text="Panašių klientų segmentas.":::

## <a name="manage-a-similar-segment"></a>Panašaus segmento valdymas

[Dirbkite su panašiu segmentu](segments.md#manage-existing-segments) ir jį valdykite kaip ir su kitais segmentais. Pavyzdžiui, eksportuokite segmentą arba sukurkite priemonę.

Redaguokite, atnaujinkite, pervardykite, atsisiųskite ir panaikinkite panašų segmentą. Redaguojant panašų segmentą iš naujo apdorojami jūsų duomenys. Anksčiau sukurtas segmentas atnaujinamas įtraukiant atnaujintus duomenis.

## <a name="about-similarity-scores"></a>Apie panašumo įverčius

Dvejetainio klasifikavimo mašininio mokymo modelyje panašaus segmento klientams priskiriamas įvertis. Įvertis grindžiamas panašumu į klientus šaltinio segmente.

- Panašumo įverčiai, mažesni nei 0,55, yra klientai, kurie sistemoje klasifikuojami kaip *nepanašūs* į šaltinio segmento klientus
- Panašumo įverčiai nuo 0,55 iki 0,7 klasifikuojami kaip *šiek tiek panašūs*
- Panašumo įverčiai nuo 0,7 iki 0,85 klasifikuojami kaip *panašūs*
- Panašumo įverčiai nuo 0,85 iki 1 yra klientai, kurie sistemoje klasifikuojami kaip *labai panašūs*

Klientai, kurių panašumo įverčiai yra mažesni nei 0,4, į modelio išvestį neįtraukiami. Sistema nelaiko jų pakankamai panašiais į šaltinio segmentą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
