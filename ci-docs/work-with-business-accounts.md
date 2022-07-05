---
title: Darbas su veiklos paskyros
description: Sužinokite apie verslo paskyras kaip pagrindinę tikslinę auditoriją Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053123"
---
# <a name="work-with-business-accounts"></a>Darbas su veiklos paskyros

Tai Dynamics 365 Customer Insights leidžia konfigūruoti aplinką skirtingoms pagrindinėms tikslinėms auditorijoms: atskiriems vartotojams (nuo B iki C) ir verslo paskyroms (nuo B iki B). B2C scenarijuose duomenys centruojami į individus. Pagrindinė B2B tikslinė auditorija yra klientai – organizacijos ar įmonės – ir kontaktai. Šis straipsnis padeda pradėti dirbti su verslo paskyrų aplinka. Jame pateikiami "Customer Insights" funkcijų sričių skirtumai, atsižvelgiant į jūsų aplinkos aspektą. Norėdami gauti daugiau informacijos apie skirtumus, peržiūrėkite funkcijų sričių dokumentus. 

## <a name="create-an-environment-for-business-accounts"></a>Kurti aplinkos verslo paskyras

Administratoriai [gali kurti aplinką esamoje organizacijoje](create-environment.md). Naujos aplinkos kūrimo proceso žingsnis prašo administratorių nurodyti pagrindinę tikslinę aplinkos auditoriją. Jei tai yra pradinė sąranka įsigijus licenciją, vadovaujama patirtis padeda sukurti pirmąją aplinką.

Tada galite [permesti verslo](data-sources.md) abonementų ir susijusių kontaktų duomenis kaip duomenų šaltinius iš visų palaikomų šaltinių.

Suvienodinę [duomenis, nurodykite abonementų hierarchijas](relationships.md#set-up-account-hierarchies) kaip ryšių konfigūravimo dalį. Taip pat galite [sukonfigūruoti semaninius](semantic-mappings.md) susiejimus, kad prijungtumėte kontaktų ir klientų objektus. 

## <a name="switch-between-primary-target-audience"></a>Perjungti pagrindinę tikslinę auditoriją

Jei jūsų organizacija išlaiko atskirų klientų ir verslo klientų aplinkas, kairiojoje srityje naudodami jungiklį galite pasirinkti pagrindinę tikslinę auditoriją.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Perjungėjas pakeičia pagrindinę tikslinę auditoriją tarp atskirų klientų ir verslo klientų.":::

## <a name="supported-feature-areas"></a>Palaikomų funkcijų sritys

- [Veiklos](activities.md): abonementų ir susijusių kontaktų palaikymas norint kurti veiklas ir rodyti jas laiko planavimo juostoje.
- [Ryšiai](relationships.md): veiklos vedlys padeda kurti ryšius tarp objektų, kad kliento rodinyje būtų galima rodyti visas veiklas iš kontaktų. Kontaktai gali detalizuoti ir matyti kontaktų rodinį, o hierarchijas galima naudoti klientų veiklos agregavimui.
- [Priemonės](measures.md): palaiko matus, sukurtus naudojant matą kūrimo įtaiso su vienu skaičiavimu. Pasirinktinis parametras leidžia kurti priemones antriniams abonementams.
- [Segmentai](segments.md): palaiko segmentus, sukurtus naudojant nuo nulio su segmentų kūrimo įtaisą. Kurdami segmentus, nauji operatoriai leidžia naudoti tam tikrą sąskaitų hierarchiją.
- [Duomenų nurijimas](data-sources.md): visos šios srities funkcijos verslo klientams ir individualiems klientams yra tos pačios.
- [Duomenų susiejimas](data-unification.md): visos šios srities funkcijos verslo klientams ir individualiems klientams yra tos pačios.
- [Papildymas](enrichment-hub.md): kai kuriuos papildymo tipus galima naudoti tik atskiriems klientų scenarijams, o kiti – tik verslo klientams.
- [Prognozės ir iš anksto nustatyti modeliai](predictions-overview.md): transakcijos tipo prognozė yra papildomų veiksmų verslo klientams. Kitos prognozės prieinamos tik individualiems klientams.
- [Aktyvinimas ir eksportavimas](export-destinations.md): galima eksportuoti verslo klientus ir atskirus klientus. Kai kuriems eksportuojamams klientams reikia papildomos konfigūravimo ir kontaktinės informacijos, o pagrindiniai segmentai sukurti taip, kad jie tiktų verslo klientams.
- [Sistemos nustatymai](system.md) ir [vartotojo valdymas](permissions.md): visos šios srities funkcijos verslo klientams ir individualiems klientams yra tos pačios.

