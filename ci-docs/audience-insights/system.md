---
title: Sistemos konfigūravimas publikos įžvalgose
description: Sužinokite apie sistemos nustatymus „Dynamics 365 Customer Insights“ publikos įžvalgų pajėgumuose.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406421"
---
# <a name="system-configuration"></a>Sistemos konfigūracija

**Sistemos** puslapis apima keturis skirtukus: **Būsena**, **Tvarkaraštis**, **Apie** ir **Bendri**.

> [!div class="mx-imgBorder"]
> ![Sistemos puslapis](media/system-tabs.png "Sistemos puslapis")

## <a name="status-tab"></a>Būsenos skirtukas

**Būsenos skirtukas** leidžia sekti duomenų įtraukimo eigą, duomenų eksportavimą ir kelis svarbius produktų procesus. Peržiūrėkite informaciją šiame skirtuke tam, kad užtikrintumėte aktyvių procesų pilnavertiškumą.

Šiame skirtuke pateikiamos **Duomenų šaltiniai**, **Sistemos procesai** ir **Duomenų puošimas** būsenos lentelės. Kiekvienoje lentelėje sekamas užduoties **Pavadinimas** ir atitinkamas objektas, naujausio vykdymo **Būsena** ir kada ji buvo **Paskutinį kartą atnaujinta**.

Peržiūrėkite paskutinių kelių užduočių vykdymų informaciją pasirinkdami užduoties pavadinimą.

### <a name="status-types"></a>Būsenos tipai

Esama šešių būsenų tipų užduotims. Toliau nurodyti būsenos tipai taip pat rodomi puslapiuose *Gretinimas*, *Suliejimas*, *Duomenų šaltiniai*, *Segmentai*, *Matai*, *Papildymas*, *Veiklos* ir *Prognozės*.

- **Apdorojama:** užduotis vykdoma. Būsena gali pasikeisti į Sėkmingai įvykdyta ar Nepavyko įvykdyti.
- **Sėkmingai įvykdyta:** užduotis sėkmingai įvykdyta.
- **Praleistas:**: užduotis praleista. Vienas ar daugiau procesų, nuo kurių priklauso ši užduotis, nesėkmingi arba buvo praleisti.
- **Nepavyko įvykdyti:** užduoties apdoroti nepavyko.
- **Atšaukta:** vartotojas atšaukė apdorojimą, kol jis nebuvo baigtas.
- **Įtraukta į eilę:** apdorojimas yra įtrauktas į eilę ir bus pradėtas užbaigus visas proceso pabaigos užduotis. Daugiau informacijos žr. [Atnaujinimo strategijos](#refresh-policies)

### <a name="refresh-policies"></a>Atnaujinimo strategijos

Sąraša rodomos atnaujinimo politikoms kiekvienam iš pagrindinių procesų:

- **Duomenų šaltiniai:** vykdoma pagal [sukonfigūruotą grafiką](#schedule-tab). Nepriklauso nuo jokio kito proceso. Gretinimas priklauso nuo, ar šis procesas buvo sėkmingai baigtas.
- **Gretinimas:** vykdoma pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo duomenų šaltinių, naudojamų gretinimo apraše, apdorojimo. Suliejimas priklauso nuo, ar šis procesas buvo sėkmingai baigtas.
- **Suliejimas**: vykdoma pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.
- **Segmentai**: vykdoma neautomatiškai (vienkartinis atnaujinimas) ir pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Suliejimas. Nuo jo apdorojimo priklauso įžvalgos.
- **Matai**: vykdoma neautomatiškai (vienkartinis atnaujinimas) ir pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Suliejimas.
- **Veiklos**: vykdoma neautomatiškai (vienkartinis atnaujinimas) ir pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Suliejimas.
- **Papildymas**: vykdoma neautomatiškai (vienkartinis atnaujinimas) ir pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Suliejimas.
- **Ieška**: vykdoma neautomatiškai (vienkartinis atnaujinimas) ir pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Suliejimas.
- **Duomenų paruošimas:** vykdoma pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Suliejimas.
- **Įžvalgos**: vykdoma neautomatiškai (vienkartinis atnaujinimas) ir pagal [sukonfigūruotą grafiką](#schedule-tab). Priklauso nuo proceso Segmentai.

Spustelėkite užduoties būseną, kad matytumėte visos užduoties, kurioje buvo ta užduotis, vykdymo eigos išsamią informaciją. Aukščiau pateiktos atnaujinimo strategijos gali padėti suprasti, kokių veiksmų galite imtis dėl **Praleistos** arba į **Įtrauktos į eilę** užduoties.

## <a name="schedule-tab"></a>Grafiko skirtukas

Naudokite **Tvarkaraščio** skirtuką tam, kad nustatytumėte automatinius visų jūsų [vartojamų duomenų šaltinių](data-sources.md) naujinimus. Automatinis atnaujinimas padeda užtikrinti, kad jūsų duomenų šaltinių naujinimai atsispindės jūsų vieninguose klientų profiliuose.

1. Publikos įžvalgose eikite į **Administratorius** > **Sistema** ir pasirinkite  **Tvarkaraštis** skirtuką.

2. Numatytoji suplanuoto atnaujinimo būsena yra **Išjungta**. Norėdami įjungti suplanuotus atnaujinimus, pakeiskite perjungimą ekrano viršuje į **Įjungta**.

3. Pasirinkite tarp **Savaitinis** (numatytasis) arba **Kasdienis** atnaujinimų. Jei planuojate savaitinį atnaujinimą, pasirinkite vieną ar kelias dienas, kada norite vykdyti atnaujinimą.

4. Nustatykite **Laiko juostą**, tada naudokite išplečiamąjį meniu **Laikas**, kad nustatytumėte atnaujinimo laiką. Baigę, pasirinkite **Nustatyti**. Jei norite suplanuoti kelis naujinimus per vieną dieną, pasirinkite **Įtraukti kitą laiką**.

5. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

## <a name="about-tab"></a>Skirtukas „Apie“

Skirtuke **Apie** rodomas organizacijos **Rodomas pavadinimas**, aktyvus **Aplinkos ID**, **Sritis** ir **Seanso ID**. Jei turite daugiau nei vieną aplinką, turėtumėte suteikti kiekvieną paprastai atpažįstamą rodinio pavadinimą.

## <a name="general-tab"></a>Bendros informacijos skirtukas

Skirtuke **Bendra** yra dvi parinktys – **Kalba** ir **Šalies / regiono formatas**.

Programa [palaiko daugelį kalbų](supported-languages.md). Norėdami pakeisti pageidaujamą kalbą, išplečiamajame sąraše pasirinkite **Kalba**.

Norėdami keisti pageidaujamą datų, laiko ir skaičių formatavimą, naudokite išplečiamąjį sąrašą **Šalies / regiono formatas**. Po šiuo lauku rodoma formatavimo peržiūra. Sistema automatiškai siūlys pasirinkimą jums pasirinkus naują kalbą.

Pasirinkite **išsaugoti**, norėdami patvirtinti savo pasirinkimus.

## <a name="api-usage-tab"></a>API naudojimo skirtukas

Sužinokite informaciją apie realaus laiko API naudojimą ir kokie įvykiai įvyko nurodytu laikotarpiu. Daugiau informacijos žr. [Duomenų įtraukimas realiuoju laiku](real-time-data-ingestion.md).
