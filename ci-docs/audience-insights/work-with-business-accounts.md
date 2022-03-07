---
title: Darbo su verslo klientais kaip pagrindinę tikslinę auditoriją pradžia
description: Darbo su verslo klientais kaip pagrindinę tikslinę auditoriją pradžia „Dynamics 365 Customer Insights“.
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
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353553"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Darbas su verslo klientais naudojant auditorijos įžvalgas

Naudodami auditorijos įžvalgų galimybę galite konfigūruoti aplinką skirtingoms pirminėms tikslinėms auditorijoms: atskiriems klientams „Dynamics 365 Customer Insights“ (B2C) ir verslo klientams (B2B). B2C scenarijuose duomenys centruojami į individus. Pagrindinė B2B tikslinė auditorija yra klientai – organizacijos ar įmonės – ir kontaktai. Šis straipsnis padeda pradėti dirbti su verslo paskyrų aplinka. Joje išvardyti auditorijos įžvalgų funkcijų sričių skirtumai, atsižvelgiant į jūsų aplinkos įvesties vietą. Norėdami gauti daugiau informacijos apie skirtumus, peržiūrėkite funkcijų sričių dokumentus. 

## <a name="create-an-environment-for-business-accounts"></a>Kurti aplinkos verslo paskyras

Administratoriai [gali kurti aplinką esamoje organizacijoje](create-environment.md). Naujos aplinkos kūrimo proceso žingsnis prašo administratorių nurodyti pagrindinę tikslinę aplinkos auditoriją. Jei įsigijus licenciją bus iš pradžių sukonfigūruotos auditorijos įžvalgos, interaktyvioji aplinka padeda kurti pirmąją aplinką.

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

