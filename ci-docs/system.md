---
title: Sistemos konfigūracija
description: Sužinokite apie sistemos parametrus programoje „Dynamics 365 Customer Insights“.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050681"
---
# <a name="system-configuration"></a>Sistemos konfigūracija

Norėdami pasiekti sistemos konfigūracijas, eikite į **Administravimo** > **sistema** ir peržiūrėkite sistemos užduočių ir procesų sąrašą.

**Sistemos** puslapyje yra šie skirtukai:
- [Būsena](#status-tab)
- [Tvarkaraštis](#schedule-tab)
- [API naudojimas](#api-usage-tab)
- [Apie](#about-tab)
- [Bendroji informacija](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Parametrų skirtukai sistemos puslapyje.":::

## <a name="status-tab"></a>Būsenos skirtukas

Skirtuke **Būsena** galite sekti užduočių eigą, duomenų įsisavinimą, duomenų eksportavimą ir kelis kitus svarbius produkto procesus. Peržiūrėkite šiame skirtuke pateiktą informaciją, kad įsitikintumėte aktyvių užduočių ir procesų išsamumu.

Šiame skirtuke yra lentelių su įvairių procesų būsena ir apdorojimo informacija. Kiekvienoje lentelėje sekamas užduoties **Pavadinimas** ir atitinkamas objektas, naujausio vykdymo **Būsena** ir kada ji buvo **Paskutinį kartą atnaujinta**. Galite peržiūrėti kelių paskutinių bėgimų informaciją pasirinkdami užduoties arba proceso pavadinimą. 

Pasirinkite būseną šalia užduoties arba proceso stulpelyje Būsena, **kad atidarytumėte** sritį Išsami eigos informacija **.**

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistemos eigos išsamios informacijos sritis":::

### <a name="status-definitions"></a>Būsenos apibrėžimai

Sistema užduotims ir procesams naudoja šias būsenas:

|Būsena  |Apibrėžtis  |
|---------|---------|
|Atšauktos |Vartotojas atšaukė apdorojimą prieš jį užbaigdamas.   |
|Atlikta nesėkmingai   |Apdorojant duomenis įvyko klaidų.         |
|Triktis  |Apdorojimas nepavyko.  |
|Nepradėta   |Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.         |
|Apdorojimas  |Vyksta užduotis arba procesas.  |
|Atnaujinama    |Vyksta duomenų apdorojimas. Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**. Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.       |
|Praleista  |Užduotis ar procesas buvo praleistas. Vienas ar daugiau procesų, nuo kurių priklauso ši užduotis, nesėkmingi arba buvo praleisti.|
|Sėkminga  |Užduotis arba procesas sėkmingai baigtas. Duomenų šaltinių atveju nurodo, kad duomenys buvo sėkmingai praryti, jei stulpelyje **Atnaujinta** paminėtas laikas.|
|Įtraukta į eilę | Apdorojimas yra eilėje ir prasidės, kai bus baigtos visos pradinės užduotys ir procesai. Daugiau informacijos ieškokite [Procesų](#refresh-processes) atnaujinimas.|

### <a name="refresh-processes"></a>Atnaujinimo procesai

Užduočių ir procesų atnaujinimas vykdomas pagal [sukonfigūruotą tvarkaraštį](#schedule-tab). 

|Proceso  |Aprašą  |
|---------|---------|
|Veikla  |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo suliejimo proceso. Nuo jo apdorojimo priklauso įžvalgos.|
|Analizės susiejimas |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo segmentų.  |
|Analizės parengimas |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo segmentų.  |
|Duomenų paruošimas   |Reikia objekto, kad galėtų veikti. Duomenų šaltinis subjektai priklauso nuo nurijimo. Praturtinti subjektai priklauso nuo praturtėjimo. Objektas Klientas priklauso nuo suliejimo.  |
|Duomenų šaltiniai   |Nepriklauso nuo jokio kito proceso. Gretinimas priklauso nuo, ar šis procesas buvo sėkmingai baigtas.  |
|Papildymai   |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo suliejimo proceso. |
|Eksporto paskirties vietos |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo segmentų.  |
|Įžvalgos |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo segmentų.  |
|Duomenų rinkimas   |Priklauso nuo suliejimo.   |
|Sugretinti |Priklauso nuo duomenų šaltinių, naudojamų gretinimo apraše, apdorojimo.      |
|Matavimai  |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo suliejimo proceso.  |
|Sulieti   |Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.   |
|Profiliai   |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo suliejimo proceso. |
|Paieška   |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo suliejimo proceso. |
|Segmentai  |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo suliejimo proceso. Nuo jo apdorojimo priklauso įžvalgos.|
|Sistema   |Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.   |
|User  |Vykdoma rankiniu būdu (atnaujinimas vieną kartą). Priklauso nuo objektų.  |

Pasirinkite proceso būseną, kad pamatytumėte išsamią viso darbo, kuriame jis buvo, eigos informaciją. Anksčiau pateikti atnaujinimo procesai gali padėti suprasti, ką galite padaryti, kad išspręstumėte praleistą **arba** eilę nukreiptą **užduotį** ar procesą.

## <a name="schedule-tab"></a>Grafiko skirtukas

Naudokite **Tvarkaraščio** skirtuką tam, kad nustatytumėte automatinius visų jūsų [vartojamų duomenų šaltinių](data-sources.md) naujinimus. Automatinis atnaujinimas padeda užtikrinti, kad jūsų duomenų šaltinių naujinimai atsispindės jūsų vieninguose klientų profiliuose.

> [!NOTE]
> Jūsų valdomi duomenų šaltiniai atnaujinami pagal jų pačių tvarkaraščius. Norėdami suplanuoti jūsų valdomų duomenų šaltinių atnaujinimą, sukonfigūruokite tos konkrečios duomenų šaltinis atnaujinimo **parametrus puslapyje Duomenų šaltiniai**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Duomenų srauto atnaujinimo nustatymai.":::

1. Eikite į **Administravimo** > **sistema** ir pasirinkite skirtuką **Tvarkaraštis**.

2. Numatytoji suplanuoto atnaujinimo būsena yra **Išjungta**. Norėdami įjungti suplanuotus atnaujinimus, pakeiskite perjungimą ekrano viršuje į **Įjungta**.

3. Pasirinkite tarp **Savaitinis** (numatytasis) arba **Kasdienis** atnaujinimų. Jei planuojate savaitinį atnaujinimą, pasirinkite vieną ar kelias dienas, kada norite vykdyti atnaujinimą.

4. Nustatykite **Laiko juostą**, tada naudokite išplečiamąjį meniu **Laikas**, kad nustatytumėte atnaujinimo laiką. Baigę, pasirinkite **Nustatyti**. Jei norite suplanuoti kelis naujinimus per vieną dieną, pasirinkite **Įtraukti kitą laiką**.

5. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

## <a name="about-tab"></a>Skirtukas „Apie“

Skirtuke **Apie** rodomas organizacijos **Rodomas pavadinimas**, aktyvus **Aplinkos ID**, **Sritis** ir **Seanso ID**. Jei turite daugiau nei vieną aplinką, turėtumėte suteikti kiekvieną paprastai atpažįstamą rodinio pavadinimą.

## <a name="general-tab"></a>Bendros informacijos skirtukas

Kalbą ir šalies / regiono formatą galite keisti skirtuke **Bendra**.

"Customer Insights" [palaiko daugelį kalbų](/dynamics365/get-started/availability). Programa naudoja jūsų kalbos ypatybes tam, kad parodytų tokius elementus kaip meniu, žymos tekstas ir sistemos pranešimai jūsų pasirinkta kalba.

Importuoti duomenys ir informacija, kurią įvedėte rankiniu būdu, nėra išversti.

### <a name="update-the-settings"></a>Naujinti parametrus

Norėdami pakeisti pageidaujamą kalbą, išplečiamajame sąraše pasirinkite **Kalba**.

Norėdami keisti pageidaujamą datų, laiko ir skaičių formatavimą, naudokite išplečiamąjį sąrašą **Šalies / regiono formatas**. Po šiuo lauku rodoma formatavimo peržiūra. Sistema automatiškai siūlys pasirinkimą jums pasirinkus naują kalbą.

Pasirinkite **išsaugoti**, norėdami patvirtinti savo pasirinkimus.

## <a name="api-usage-tab"></a>API naudojimo skirtukas

Raskite informacijos apie realiojo laiko API naudojimą ir sužinokite, kurie įvykiai įvyko per nurodytą laiką. Išskleidžiamajame meniu Pažymėkite **laiko tarpą pasirinkite** laiko tarpą. 

**API naudojimas** apima tris skyrius: 
- **API skambučiai** – diagrama, vaizduojama per pažymėtą laiko tarpą vizualizuojamas į API ėjusių skambučių agreguotas skaičius.

- **Duomenų perdavimas** – diagrama, kurioje rodomas per API per pasirinktą laiko tarpą perduotų duomenų kiekis.

-  **Operacijos** – lentelė su kiekvienos galimos API operacijos eilutėmis ir išsami informacija apie operacijų naudojimą. Galite pažymėti operacijos pavadinimą, kurį [į norite eiti API ](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacijose, kuriose naudojamas [duomenų įsisavinimas](real-time-data-ingestion.md) realiuoju laiku, yra mygtukas su žiūrono simboliu, leidžiantis peržiūrėti API naudojimą realiuoju laiku. Pasirinkite mygtuką siekiant atidaryti šoninę juostą turinčią suvartojimo informaciją realaus laiko API naudojimui ir esamai aplinkai.   
   Naudokite lauką **Grupuoti** pagal **pateikiamą realiuoju** laiku naudojant API, ir pasirinkite, kaip geriausiai pateikti bendravimą realiuoju laiku. Duomenis galite grupuoti pagal API būdą, objekto apibrėžtą pavadinimą (įtrauktas objektas), kūrėją (įvykio šaltinis), rezultatą (sėkmė arba nesėkmė) arba klaidų kodus. Duomenys prieinami kaip retrospektyvos diagrama ir kaip lentelė.


[!INCLUDE [footer-include](includes/footer-banner.md)]
