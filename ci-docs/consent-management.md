---
title: Naudoti kliento sutikimą
description: Gerbkite klientų sutikimo nuostatas "Customer Insights" importuodami sutikimo duomenis.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947526"
---
# <a name="use-customer-consent"></a>Naudoti kliento sutikimą

Duomenų apsaugos ir privatumo taisyklės suteikia asmenims teisę reglamentuoti, kaip organizacija naudoja savo asmens duomenis. Tokių taisyklių pavyzdžiai yra Bendrasis duomenų apsaugos reglamentas Europos Sąjungoje arba Kalifornijos vartotojų privatumo įstatymas Jungtinėse Amerikos Valstijose. Šios taisyklės leidžia žmonėms atsisakyti, kad jų asmens duomenys būtų renkami, tvarkomi ar bendrinami su trečiosiomis šalimis.  

Klientai gali pasirinkti atšaukti arba atsisakyti savo sutikimo dėl konkrečių kontaktų formų. Jie taip pat gali prašyti, kad neleistumėte jiems rinkti, saugoti, naudoti ar parduoti jų asmens duomenų. Svarbu, kad jūsų organizacija gerbtų visus klientų sutikimus ir privatumo nuostatas.  

Dynamics 365 Customer Insights padeda jums įvykdyti savo klientų užklausas importuodami ir saugodami jų nuostatas kaip vieningų klientų profilių dalį.

Jei sutikimo duomenys saugomi atskirai nuo jūsų klientų profilių, [pridėkite savo sutikimo duomenis kaip naują duomenų šaltinis](#import-and-unify-consent-data). Duomenų šaltinis, kuriame yra sutikimo duomenys, įtraukiamas į duomenų suvienijimo procesą. Sėkmingas sutikimo duomenų ir klientų profilių suvienijimas lemia vieningus klientų profilius, kuriuose yra sutikimo informacija. Klientų profiliuose, kuriuose jau yra sutikimo informacijos, eikite tiesiai į naudojimo sutikimo [duomenų](#use-consent-data) skyrių.

## <a name="prerequisites"></a>Būtinosios sąlygos

Jūsų šaltinio duomenyse turi būti pateikta ši informacija, kad sutikimo duomenys būtų sujungti su kitais klientų profiliais:

- Alternatyvusis raktas susieti sutikimo informaciją su vartotojų profiliais programoje "Customer Insights". Pavyzdžiui, el. pašto adresas arba telefono numeris.
- Sutikimo vertė kliento sutikimo būsenai nustatyti.

Apsvarstykite galimybę įtraukti šią *pasirinktinę* informaciją:

- Pirminis raktas sutikimo būsenai atnaujinti, jei klientas prašo pakeitimo.
- Sutikimo tipas, jei yra daugiau nei vienas būdas apdoroti kliento informaciją.
- Sutikimo data arba bet kokie kiti duomenys, susiję su jūsų sutikimo scenarijais.

Paprastos sutikimo duomenų bazės su keliomis sutikimo parinktimis pavyzdžių lentelė:

|Sutikimo ID (pirminis raktas)   |El. paštas (alternatyvusis raktas)  |Sutikimo parinktis  |Sutikimo reikšmė  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Informacinis biuletenis       |  Klaidinga       |
|2    |  holly@contoso.com       |  Produktų naujinimai       |  Teisinga       |
|3    |  frank@contoso.com       |  Informacinis biuletenis       | Teisinga        |
|4    |  frank@contoso.com       |  Produktų naujinimai       |  Klaidinga       |

## <a name="import-and-unify-consent-data"></a>Sutikimo duomenų importavimas ir suvienodinimas

Sutikimo duomenis galite importuoti taip pat, kaip "Customer Insights" praryjate kitus duomenų šaltinius. Daugiau informacijos apie palaikomus duomenų šaltinius ir kaip juos importuoti ieškokite [Duomenų šaltinių apžvalgoje](data-sources.md).

Daugiau informacijos apie duomenų šaltinių suvienodinimą ieškokite [Duomenų suvienijimo apžvalgoje](data-unification.md).

## <a name="use-consent-data"></a>Naudoti sutikimo duomenis

Kai sutikimo duomenys yra jūsų vieningų klientų profilių dalis, galite juos naudoti "Customer Insights". Pavyzdžiui, sukurkite segmentą su taisykle, kad užtikrintumėte, jog laikotės klientų privatumo ir duomenų apsaugos nuostatų. Taisyklės, palaikančios sutikimo nuostatas, naudojamos siekiant pašalinti naudotojus iš segmento pagal profilio atributus. Taisyklės įtraukimas į segmentą, kuriame neįtraukiami klientų profiliai, kurie nepateikė sutikimo susisiekti.

Kalbant apie aukščiau pateiktą pavyzdinę lentelę, segmente gali būti ši taisyklė:`Consent option=Newsletter & Consent value=True`. Ši konfigūracija sukuria segmentą, kuriame atsižvelgiama į kontaktų nuostatas, kad būtų galima siųsti naujienlaiškį.

Daugiau informacijos apie pastatų segmentus ieškokite [Create segments](segment-builder.md).

Sukūrę segmentą, galite naudoti vieną iš daugelio [eksportavimo parinkčių](export-destinations.md), kad segmentą galėtumėte naudoti kitose programose.

## <a name="ensure-updated-consent-status"></a>Užtikrinti atnaujintą sutikimo būseną

Svarbu nuolat atnaujinti klientų sutikimo būseną. Suplanuotas atnaujinimas "Customer Insights" visada importuoja naujausią jūsų duomenų šaltinių būseną. Tada ši informacija apdorojama suvienijus duomenis ir dėl to atnaujinami klientų profiliai. Tada šie atnaujinti profiliai naudojami segmentams atnaujinti, kad įsitikintumėte, jog dirbate su naujausia informacija.

Kitaip tariant, įsitikinkite, kad šaltinio duomenys, importuojami į "Customer Insights", visada turi naujausią informaciją.

Daugiau informacijos ieškokite [Update segments rankiniu būdu](segments.md#refresh-segments) arba [suplanuoto atnaujinimo](system.md#schedule-tab) konfigūravimas.
