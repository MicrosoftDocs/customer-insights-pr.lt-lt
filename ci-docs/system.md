---
title: Peržiūrėti sistemos konfigūraciją
description: Sužinokite apie sistemos parametrus programoje „Dynamics 365 Customer Insights“.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246257"
---
# <a name="view-system-configuration"></a>Peržiūrėti sistemos konfigūraciją

Peržiūrėkite sistemos informaciją, sistemos būseną ir API naudojimą.

## <a name="view-api-usage"></a>Peržiūrėkite API naudojimą

Peržiūrėkite išsamią informaciją apie API naudojimą realiuoju laiku ir sužinokite, kurie įvykiai įvyko per tam tikrą laikotarpį.

1. Eikite į **"Admin** > **System"** ir pasirinkite skirtuką **API naudojimas**.

1. **Pasirinkite laiko tarpą**, kurį norite peržiūrėti.

   **API naudojimo** puslapyje yra trys skyriai:

   - **API skambučiai** – diagrama, vaizduojama per pažymėtą laiko tarpą vizualizuojamas į API ėjusių skambučių agreguotas skaičius.
   - **Duomenų perdavimas** – diagrama, kurioje rodomas per API per pasirinktą laiko tarpą perduotų duomenų kiekis.
   - **Operacijos** – lentelė su kiekvienos galimos API operacijos eilutėmis ir išsami informacija apie operacijų naudojimą. Pasirinkite operacijos pavadinimą, kad pereitumėte į [API nuorodą](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacijose, kuriose naudojamas [duomenų įsisavinimas](real-time-data-ingestion.md) realiuoju laiku, yra žiūrono simbolis, leidžiantis peržiūrėti API naudojimą realiuoju laiku.

   1. Pasirinkite žiūroną, kad atidarytumėte realaus **laiko API naudojimo** sritį, kurioje pateikiama išsami operacijos naudojimo informacija.
   1. **Pasirinkite laiko tarpą**, kurį norite peržiūrėti.
   1. Naudokite laukelį **Grupuoti pagal**, kad pasirinktumėte, kaip geriausiai pristatyti sąveiką realiuoju laiku. Grupuokite duomenis pagal API **metodą**, **objekto sąlyginį pavadinimą** (nurijusį objektą), **sukurtą pagal** (įvykio šaltinį), **rezultatą** (sėkmę arba nesėkmę) arba **klaidų kodus**. Duomenys prieinami kaip retrospektyvos diagrama ir kaip lentelė.

## <a name="view-system-information"></a>Peržiūrėkite sistemos informaciją

Peržiūrėkite aplinkos rodomą pavadinimą, ID, regioną, tipą ir seanso ID.

1. Eikite į **Administravimo** > **sistema** ir pasirinkite skirtuką **Apie**.

1. Norėdami peržiūrėti kalbą ir šalį / regioną, pasirinkite skirtuką **Bendra**.

### <a name="update-preferred-language-or-countryregion"></a>Pageidaujamos kalbos arba šalies / regiono naujinimas

"Customer Insights" [palaiko daugelį kalbų](/dynamics365/get-started/availability). Programa naudoja jūsų kalbos ypatybes tam, kad parodytų tokius elementus kaip meniu, žymos tekstas ir sistemos pranešimai jūsų pasirinkta kalba.

Importuoti duomenys ir informacija, kurią įvedėte rankiniu būdu, nėra išversti.

1. Eikite į **Administravimo** > **sistema** ir pasirinkite skirtuką **Bendra**.

1. Norėdami pakeisti pageidaujamą kalbą, išplečiamajame sąraše pasirinkite **Kalba**.

1. Norėdami keisti pageidaujamą datų, laiko ir skaičių formatavimą, naudokite išplečiamąjį sąrašą **Šalies / regiono formatas**. Rodoma formatavimo peržiūra. Sistema automatiškai siūlo pasirinkimą, kai pasirenkate naują kalbą.

1. Pasirinkite **Įrašyti**.

## <a name="view-system-status"></a>Peržiūrėti sistemos būseną

Stebėkite užduočių eigą, duomenų įsisavinimą, duomenų eksportavimą ir keletą kitų svarbių produktų procesų. Peržiūrėkite informaciją, kad užtikrintumėte aktyvių užduočių ir procesų išsamumą.

1. Eikite į **Administravimo** > **sistema** ir pasirinkite skirtuką **Būsena**.

   Įvairių procesų rodymo būsenos ir apdorojimo informacija. Peržiūrėkite **užduoties pavadinimą**, naujausio jos paleidimo būseną **ir** kada ji buvo **paskutinį kartą atnaujinta**.

1. Norėdami peržiūrėti kelių paskutinių paleidimų informaciją, pasirinkite užduoties arba proceso pavadinimą.

1. Norėdami peržiūrėti užduoties eigos informaciją, pasirinkite būseną. Rodoma sritis Išsami **eigos informacija**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistemos eigos išsamios informacijos sritis":::

1. Norėdami peržiūrėti išsamią visų užduočių eigos informaciją, pasirinkite **Visa darbo eiga**.

### <a name="status-definitions"></a>Būsenos apibrėžimai

Sistema užduotims ir procesams naudoja šias būsenas:

|Būsena  |Apibrėžtis  |
|---------|---------|
|Atšauktos |Užduotį ar procesą vartotojas atšaukė dar nebaigęs.   |
|Atlikta nesėkmingai   |Užduotis ar procesas susidūrė su klaidomis.         |
|Triktis  |Užduotis ar procesas nepavyko.  |
|Nepradėta   |Duomenų šaltinis dar nepraryti jokie duomenys arba užduotis vis dar veikia juodraščio režimu.         |
|Apdorojimas  |Vyksta užduotis arba procesas.  |
|Atnaujinama    |Vyksta užduotis arba procesas. Norėdami atšaukti šią operaciją, pasirinkite **Atnaujinti** ir **Atšaukti užduotį**. Sustabdžius užduoties ar proceso atnaujinimą, jis bus grąžintas į paskutinę atnaujinimo būseną.       |
|Praleista  |Užduotis ar procesas buvo praleistas. Vienas ar daugiau procesų, nuo kurių priklauso ši užduotis, nesėkmingi arba buvo praleisti.|
|Sėkminga  |Užduotis arba procesas sėkmingai baigtas. Duomenų šaltinių atveju nurodo, kad duomenys buvo sėkmingai praryti, jei stulpelyje **Atnaujinta** paminėtas laikas.|
|Įtraukta į eilę | Apdorojimas yra eilėje ir prasidės, kai bus baigtos visos pradinės užduotys ir procesai. Daugiau informacijos ieškokite [Procesų](#refresh-processes) atnaujinimas.|

### <a name="refresh-processes"></a>Atnaujinimo procesai

Užduočių ir procesų atnaujinimas vykdomas pagal [sukonfigūruotą tvarkaraštį](schedule-refresh.md).

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
