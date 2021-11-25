---
title: Sistemos konfigūravimas publikos įžvalgose
description: Sužinokite apie sistemos parametrus Dynamics 365 Customer Insights auditorijos įžvalgų galimybėse.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732380"
---
# <a name="system-configuration"></a>Sistemos konfigūracija

Norėdami pasiekti sistemos konfigūracijas auditorijos įžvalgose, kairiojoje naršymo juostoje pasirinkite **Administravimo** > **·** sistema, kad peržiūrėtumėte sistemos užduočių ir procesų sąrašą.

**Sistemos** puslapyje yra šie skirtukai:
- [Būsena](#status-tab)
- [Tvarkaraštis](#schedule-tab)
- [API naudojimas](#api-usage-tab)
- [Apie](#about-tab)
- [Bendroji informacija](#general-tab)
- [Sauga](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Parametrų skirtukai sistemos puslapyje.":::

## <a name="status-tab"></a>Būsenos skirtukas

**Skirtuke Būsena galite sekti užduočių** eigą, duomenų nurijimą, duomenų eksportavimą ir kelis kitus svarbius produkto procesus. Peržiūrėkite šiame skirtuke esantį informaciją, kad užtikrintumėte aktyvių užduočių ir procesų išsamumą.

Šiame skirtuke yra lentelių su įvairių procesų būsena ir apdorojimo informacija. Kiekvienoje lentelėje sekamas užduoties **Pavadinimas** ir atitinkamas objektas, naujausio vykdymo **Būsena** ir kada ji buvo **Paskutinį kartą atnaujinta**. Galite peržiūrėti paskutinių kelių važiavimų informaciją pasirinkdami užduoties arba proceso pavadinimą. 

Stulpelyje Būsena pasirinkite būseną šalia užduoties arba **·** proceso, kad atidarytumėte **sritį Išsami eigos** informacija.

   :::image type="content" source="media/system-progress-details.png" alt-text="Sistemos eigos išsamios informacijos sritis":::

### <a name="status-definitions"></a>Būsenos apibrėžimai

Uždaviniams ir procesams sistema naudoja šias būsenas:

|Būsena  |Apibrėžtis  |
|---------|---------|
|Atšauktos |Vartotojas atšaukė apdorojimą prieš jį baigiant.   |
|Atlikta nesėkmingai   |Apdorojant duomenis įvyko klaidų.         |
|Triktis  |Apdoroti nepavyko.  |
|Nepradėta   |Duomenų šaltinis dar neturi jokių suvartotų duomenų arba jie dar yra šablono režime.         |
|Apdorojimas  |Užduotis arba procesas vyksta.  |
|Atnaujinama    |Vyksta duomenų apdorojimas. Galite atšaukti šią operaciją, stulpelyje **Veiksmai** pasirinkdami **Sustabdyti naujinimą**. Sustabdžius duomenų šaltinio naujinimą, jis bus grąžintas į paskutinio naujinimo būseną.       |
|Praleista  |Užduotis arba procesas praleistas. Vienas ar daugiau procesų, nuo kurių priklauso ši užduotis, nesėkmingi arba buvo praleisti.|
|Pavyko  |Užduotis arba procesas sėkmingai baigtas. Duomenų šaltinių atveju nurodo, kad duomenys buvo sėkmingai nuryti, jei **stulpelyje Atnaujinta paminėtas** laikas.|
|Įtraukta į eilę | Apdorojimas yra eilėje ir prasidės, kai bus baigtos visos tiekėjų užduotys ir procesai. Daugiau informacijos ieškokite [Refresh processes](#refresh-processes).|

### <a name="refresh-processes"></a>Atnaujinti procesus

Užduočių ir procesų atnaujinimas vykdomas pagal [sukonfigūruotą tvarkaraštį](#schedule-tab). 

|Proceso  |Aprašymas  |
|---------|---------|
|Veikla  |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo suliejimo proceso. Nuo jo apdorojimo priklauso įžvalgos.|
|Analizės susiejimas |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo segmentų.  |
|Analizės parengimas |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo segmentų.  |
|Duomenų paruošimas   |Priklauso nuo suliejimo.   |
|Duomenų šaltiniai   |Nepriklauso nuo jokio kito proceso. Gretinimas priklauso nuo, ar šis procesas buvo sėkmingai baigtas.  |
|Papildymai   |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo suliejimo proceso. |
|Eksporto paskirties vietos |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo segmentų.  |
|Įžvalgos |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo segmentų.  |
|Duomenų rinkimas   |Priklauso nuo suliejimo.   |
|Sugretinti |Priklauso nuo duomenų šaltinių, naudojamų gretinimo apraše, apdorojimo.      |
|Matavimai  |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo suliejimo proceso.  |
|Sulieti   |Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.   |
|Profiliai   |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo suliejimo proceso. |
|Paieška   |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo suliejimo proceso. |
|Segmentai  |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo suliejimo proceso. Nuo jo apdorojimo priklauso įžvalgos.|
|Sistema   |Priklauso nuo, ar gretinimo procesas buvo sėkmingai baigtas. Segmentai, matai, papildymas, ieška, veiklos, prognozės ir duomenų paruošimas priklauso nuo to, ar šis procesas buvo sėkmingai baigtas.   |
|Vartotojas  |Veikia rankiniu būdu (vienkartinis atnaujinimas). Priklauso nuo objektų.  |

Pasirinkti proceso būseną, kad būtų galima peržiūrėti visos užduoties, kurioje jis buvo, eigos informaciją. Aukščiau pateikti atnaujinimo procesai gali padėti suprasti, ką galite padaryti, kad išspręstumėte **praleistą arba į eilę įrašytą** **užduotį ar** procesą.

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

Kalbą ir šalies / regiono formatą galite keisti skirtuke **Bendra**.

"Customer Insights" [palaiko daug kalbų](/dynamics365/get-started/availability). Programa naudoja jūsų kalbos ypatybes tam, kad parodytų tokius elementus kaip meniu, žymos tekstas ir sistemos pranešimai jūsų pasirinkta kalba.

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

-  **Operacijos** – lentelė su kiekvienos galimos API operacijos eilutėmis ir išsami informacija apie operacijų naudojimą. Galite pažymėti operacijos pavadinimą, kurį [į norite eiti API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operacijose, kurios naudoja [duomenų nurijimą realiuoju](real-time-data-ingestion.md) laiku, yra mygtukas su žiūroniniu simboliu, kad būtų galima peržiūrėti api naudojimą realiuoju laiku. Pasirinkite mygtuką siekiant atidaryti šoninę juostą turinčią suvartojimo informaciją realaus laiko API naudojimui ir esamai aplinkai.   
   Naudokite lauką **Grupuoti** pagal **pateikiamą realiuoju** laiku naudojant API, ir pasirinkite, kaip geriausiai pateikti bendravimą realiuoju laiku. Duomenis galite grupuoti pagal API būdą, objekto apibrėžtą pavadinimą (įtrauktas objektas), kūrėją (įvykio šaltinis), rezultatą (sėkmė arba nesėkmė) arba klaidų kodus. Duomenys prieinami kaip retrospektyvos diagrama ir kaip lentelė.

## <a name="security-tab"></a>Saugos skirtukas

Skirtukas **Sauga** leidžia susieti ir valdyti savo [„Azure" „key vault“](/azure/key-vault/general/basic-concepts) su aplinka.
Skirta raktų saugykla gali būti naudojama organizacijos sienų etapų ir naudojimo slaptai vietai nustatyti. Auditorijos įžvalgos gali naudoti „Azure“ „Key Vault“ [slaptas vietas ryšiams](connections.md) su trečiųjų šalių sistemomis nustatyti.

Daugiau informacijos žr. [„Azure” „key vault“ sukūrimas](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
