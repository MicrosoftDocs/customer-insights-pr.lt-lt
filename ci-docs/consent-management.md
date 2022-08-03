---
title: Kliento sutikimo naudojimas
description: Gerbkite klientų sutikimo nuostatas "Customer Insights" importuodami sutikimo duomenis.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188058"
---
# <a name="use-customer-consent"></a>Kliento sutikimo naudojimas

Duomenų apsaugos ir privatumo taisyklės suteikia asmenims teisę valdyti, kaip organizacija naudoja jų asmens duomenis. Tokių reglamentų pavyzdžiai yra Bendrasis duomenų apsaugos reglamentas Europos Sąjungoje arba Kalifornijos vartotojų privatumo aktas Jungtinėse Amerikos Valstijose. Šios taisyklės leidžia žmonėms atsisakyti, kad jų asmens duomenys būtų renkami, tvarkomi ar bendrinami su trečiosiomis šalimis.  

Klientai gali nuspręsti atšaukti arba atsisakyti duoti sutikimą dėl konkrečių formų kontaktų. Jie taip pat gali paprašyti, kad atsisakytumėte jų asmens duomenų rinkimo, saugojimo, naudojimo ar pardavimo. Svarbu, kad jūsų organizacija gerbtų visų klientų sutikimą ir privatumo nuostatas.  

Dynamics 365 Customer Insights padeda jums patenkinti klientų užklausas importuojant ir saugant jų nuostatas kaip vieningų klientų profilių dalį.

Jei sutikimo duomenys saugomi atskirai nuo jūsų klientų profilių, [pridėkite savo sutikimo duomenis kaip naują duomenų šaltinis](#import-and-unify-consent-data). Duomenų šaltinis, kuriame yra sutikimo duomenys, įtraukiamas į duomenų suvienijimo procesą. Sėkmingas sutikimo duomenų ir klientų profilių suvienodinimas nukreipia į vieningus klientų profilius, kuriuose yra sutikimo informacija. Jei tai yra klientų profiliai, kuriuose jau yra sutikimo informacija, eikite tiesiai į [skyrių Naudojimo sutikimo duomenys](#use-consent-data).

## <a name="prerequisites"></a>Būtinosios sąlygos

Šaltinio duomenyse turi būti pateikta toliau nurodyta informacija, kad sutikimo duomenys būtų suvienodinti su kitų klientų profiliais:

- Alternatyvusis raktas susieti sutikimo informaciją su naudotojų profiliais programoje "Customer Insights". Pavyzdžiui, el. pašto adresas arba telefono numeris.
- Sutikimo vertė kliento sutikimo būsenai nustatyti.

Apsvarstykite galimybę pridėti šią *neprivalomą* informaciją:

- Pirminis raktas, skirtas atnaujinti sutikimo būseną, jei klientas pateikia pakeitimo užklausą.
- Sutikimo tipas, jei yra daugiau nei vienas būdas apdoroti kliento informaciją.
- Sutikimo data arba bet kokio kito tipo duomenys, susiję su jūsų sutikimo scenarijais.

Paprastos sutikimo duomenų bazės su keliomis sutikimo parinktimis lentelės pavyzdys:

|Sutikimo ID (pirminis raktas)   |El. paštas (alternatyvusis raktas)  |Sutikimo parinktis  |Sutikimo reikšmė  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Informacinis biuletenis       |  Klaidinga       |
|2    |  holly@contoso.com       |  Produktų naujinimai       |  Teisinga       |
|3    |  frank@contoso.com       |  Informacinis biuletenis       | Teisinga        |
|4    |  frank@contoso.com       |  Produktų naujinimai       |  Klaidinga       |

## <a name="import-and-unify-consent-data"></a>Sutikimo duomenų importavimas ir suvienodinimas

Importuokite sutikimo duomenis taip pat, kaip prarydami kitus duomenų šaltinius į "Customer Insights". Daugiau informacijos apie palaikomus duomenų šaltinius ir kaip juos importuoti ieškokite [Duomenų šaltinių apžvalga](data-sources.md).

Daugiau informacijos apie duomenų šaltinių suvienodinimą ieškokite [Duomenų suvienijimo apžvalga](data-unification.md).

## <a name="use-consent-data"></a>Sutikimo duomenų naudojimas

Kai jūsų sutikimo duomenys yra jūsų suvienodintų klientų profilių dalis, galite juos naudoti programoje "Customer Insights". Pavyzdžiui, sukurkite segmentą su taisykle, kad užtikrintumėte, jog gerbiate klientų privatumo ir duomenų apsaugos nuostatas. Taisyklės, palaikančios sutikimo nuostatas, naudojamos norint išskirti naudotojus iš segmento pagal profilio atributus. Įtraukite taisyklę į segmentą, kuris neįtraukia klientų profilių, kurie nedavė sutikimo susisiekti.

Remiantis aukščiau pateikta pavyzdine lentele, segmente gali būti ši taisyklė:`Consent option=Newsletter & Consent value=True`. Dėl šios konfigūracijos gaunamas segmentas, kuriame pagerbiamos kontaktų nuostatos siunčiant informacinį biuletenį.

Daugiau informacijos apie pastatų segmentus rasite [Segmentų](segment-builder.md) kūrimas.

Sukūrę segmentą, galite naudoti vieną iš daugelio [eksportavimo parinkčių](export-destinations.md), kad galėtumėte naudoti segmentą kitose programose.

## <a name="ensure-updated-consent-status"></a>Užtikrinkite atnaujintą sutikimo būseną

Svarbu nuolat atnaujinti klientų sutikimo būseną. Suplanuotas atnaujinimas programoje "Customer Insights" visada importuoja naujausią duomenų šaltinių būseną. Tada ši informacija apdorojama suvienodinant duomenis ir gaunami atnaujinti klientų profiliai. Tada šie atnaujinti profiliai naudojami segmentams atnaujinti, kad įsitikintumėte, jog dirbate su naujausia informacija.

Kitaip tariant, įsitikinkite, kad šaltinio duomenys, importuojami į "Customer Insights", visada turi naujausią informaciją.

Daugiau informacijos ieškokite [Segmentų atnaujinimas rankiniu būdu](segments.md#refresh-segments) arba [suplanuoto atnaujinimo](system.md#schedule-tab) konfigūravimas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
