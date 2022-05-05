---
title: Sistemos konfigūracija "Customer Insights"
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
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653626"
---
# <a name="system-configuration"></a>Sistemos konfigūracija

Norėdami pasiekti sistemos konfigūracijas, eikite į **AdminSystem** > **ir** peržiūrėkite sistemos užduočių ir procesų sąrašą.

**Sistemos** puslapyje yra šie skirtukai:
- [Būsena](#status-tab)
- [Tvarkaraštis](#schedule-tab)
- [API naudojimas](#api-usage-tab)
- [Apie](#about-tab)
- [Bendroji informacija](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Parametrų skirtukai sistemos puslapyje.":::

## <a name="status-tab"></a>Būsenos skirtukas

Skirtuke **Būsena** galite stebėti užduočių eigą, duomenų nurijimą, duomenų eksportavimą ir kelis kitus svarbius produkto procesus. Peržiūrėkite šiame skirtuke esančią informaciją, kad užtikrintumėte aktyvių užduočių ir procesų išsamumą.

Šiame skirtuke yra lentelių su įvairių procesų būsena ir apdorojimo informacija. Kiekvienoje lentelėje sekamas užduoties **Pavadinimas** ir atitinkamas objektas, naujausio vykdymo **Būsena** ir kada ji buvo **Paskutinį kartą atnaujinta**. Išsamią informaciją apie paskutinius kelis važiavimus galite peržiūrėti pasirinkdami užduoties arba proceso pavadinimą. 

Pasirinkite būseną šalia užduoties arba proceso stulpelyje **Būsena**, kad atidarytumėte išsamios informacijos apie **eigą** sritį.

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistemos eigos išsamios informacijos sritis":::

### <a name="status-definitions"></a>Būsenos apibrėžimai

Sistemai užduotims ir procesams naudojamos šios būsenos:

|Būsena  |Apibrėžtis  |
|---------|---------|
|Atšauktos |Prieš užbaigdamas apdorojimą vartotojas atšaukė.   |
|Atlikta nesėkmingai   |Apdorojant duomenis įvyko klaidų.         |
|Triktis  |Apdoroti nepavyko.  |
|Nepradėta   |Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.         |
|Apdorojimas  |Vyksta užduotis arba procesas.  |
|Atnaujinama    |Vyksta duomenų apdorojimas. Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**. Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.       |
|Praleista  |Užduotis ar procesas praleistas. Vienas ar daugiau procesų, nuo kurių priklauso ši užduotis, nesėkmingi arba buvo praleisti.|
|Sėkminga  |Užduotis arba procesas sėkmingai atlikti. Duomenų šaltinių atveju nurodoma, kad duomenys buvo sėkmingai praryti, jei stulpelyje **Atnaujintas** paminėtas laikas.|
|Įtraukta į eilę | Apdorojimas yra eilėje ir bus pradėtas, kai bus atliktos visos pirminės užduotys ir procesai. Daugiau informacijos ieškokite [Refresh processes](#refresh-processes).|

### <a name="refresh-processes"></a>Atnaujinti procesus

Užduočių ir procesų atnaujinimas vykdomas pagal [sukonfigūruotą tvarkaraštį](#schedule-tab). 

|Proceso  |Aprašą  |
|---------|---------|
|Veikla  |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo suliejimo proceso. Nuo jo apdorojimo priklauso įžvalgos.|
|Analizės susiejimas |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo segmentų.  |
|Analizės parengimas |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo segmentų.  |
|Duomenų paruošimas   |Reikia objekto, kuriame būtų galima veikti. Duomenų šaltinis subjektai priklauso nuo nurijimo. Praturtinti subjektai priklauso nuo sodrinimo. Kliento objektas priklauso nuo suliejimo.  |
|Duomenų šaltiniai   |Nepriklauso nuo jokio kito proceso. Gretinimas priklauso nuo, ar šis procesas buvo sėkmingai baigtas.  |
|Papildymai   |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo suliejimo proceso. |
|Eksporto paskirties vietos |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo segmentų.  |
|Įžvalgos |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo segmentų.  |
|Duomenų rinkimas   |Priklauso nuo suliejimo.   |
|Sugretinti |Priklauso nuo duomenų šaltinių, naudojamų gretinimo apraše, apdorojimo.      |
|Matavimai  |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo suliejimo proceso.  |
|Sulieti   |Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.   |
|Profiliai   |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo suliejimo proceso. |
|Paieška   |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo suliejimo proceso. |
|Segmentai  |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo suliejimo proceso. Nuo jo apdorojimo priklauso įžvalgos.|
|Sistema   |Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.   |
|User  |Veikia neautomatiniu būdu (atnaujinama vieną kartą). Tai priklauso nuo subjektų.  |

Pasirinkite proceso būseną, kad pamatytumėte visos užduoties, kurioje jis buvo, eigos informaciją. Aukščiau pateikti atnaujinimo procesai gali padėti suprasti, ką galite padaryti, kad išspręstumėte praleistą **arba** eilėje laukiančią **užduotį** ar procesą.

## <a name="schedule-tab"></a>Grafiko skirtukas

Naudokite **Tvarkaraščio** skirtuką tam, kad nustatytumėte automatinius visų jūsų [vartojamų duomenų šaltinių](data-sources.md) naujinimus. Automatinis atnaujinimas padeda užtikrinti, kad jūsų duomenų šaltinių naujinimai atsispindės jūsų vieninguose klientų profiliuose.

> [!NOTE]
> Jūsų valdomi duomenų šaltiniai atnaujinami pagal savo tvarkaraščius. Norėdami suplanuoti jūsų valdomų duomenų šaltinių atnaujinimą, konfigūruokite atnaujinimo parametrus toje konkrečioje duomenų šaltinis puslapyje **Duomenų šaltiniai**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Duomenų srauto atnaujinimo parametrai.":::

1. Eikite į **AdminSystem** > **ir** pasirinkite skirtuką **Tvarkaraštis**.

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

   Operacijose, kuriose naudojamas [duomenų nurijimas](real-time-data-ingestion.md) realiuoju laiku, yra mygtukas su binokuliniu simboliu, kad būtų galima peržiūrėti API naudojimą realiuoju laiku. Pasirinkite mygtuką siekiant atidaryti šoninę juostą turinčią suvartojimo informaciją realaus laiko API naudojimui ir esamai aplinkai.   
   Naudokite lauką **Grupuoti** pagal **pateikiamą realiuoju** laiku naudojant API, ir pasirinkite, kaip geriausiai pateikti bendravimą realiuoju laiku. Duomenis galite grupuoti pagal API būdą, objekto apibrėžtą pavadinimą (įtrauktas objektas), kūrėją (įvykio šaltinis), rezultatą (sėkmė arba nesėkmė) arba klaidų kodus. Duomenys prieinami kaip retrospektyvos diagrama ir kaip lentelė.


[!INCLUDE [footer-include](includes/footer-banner.md)]
