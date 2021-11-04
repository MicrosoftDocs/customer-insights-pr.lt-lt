---
title: Sistemos konfigūravimas publikos įžvalgose
description: Sužinokite apie sistemos nustatymus „Dynamics 365 Customer Insights“ publikos įžvalgų pajėgumuose.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651850"
---
# <a name="system-configuration"></a>Sistemos konfigūracija

**Sistemos** puslapyje yra šie skirtukai:
- [Būsena](#status-tab)
- [Tvarkaraštis](#schedule-tab)
- [API naudojimas](#api-usage-tab)
- [Apie](#about-tab)
- [Bendroji informacija](#general-tab)
- [Sauga](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Parametrų skirtukai sistemos puslapyje.":::

## <a name="status-tab"></a>Būsenos skirtukas

Skirtukas **Būsena leidžia sekti duomenų** prarijimo, duomenų eksporto eigą ir kelis kitus svarbius produktų procesus. Peržiūrėkite informaciją šiame skirtuke tam, kad užtikrintumėte aktyvių procesų pilnavertiškumą.

Šiame skirtuke yra lentelių su įvairių procesų būsena ir apdorojimo informacija. Kiekvienoje lentelėje sekamas užduoties **Pavadinimas** ir atitinkamas objektas, naujausio vykdymo **Būsena** ir kada ji buvo **Paskutinį kartą atnaujinta**.

Peržiūrėkite paskutinių kelių užduočių vykdymų informaciją pasirinkdami užduoties pavadinimą.

### <a name="status-types"></a>Būsenos tipai

Esama šešių būsenų tipų užduotims. Toliau nurodyti būsenos tipai taip pat rodomi puslapiuose *Gretinimas*, *Suliejimas*, *Duomenų šaltiniai*, *Segmentai*, *Matai*, *Papildymas*, *Veiklos* ir *Prognozės*.

- **Apdorojama:** užduotis vykdoma. Būsena gali pasikeisti į Sėkmingai įvykdyta ar Nepavyko įvykdyti.
- **Sėkmingai įvykdyta:** užduotis sėkmingai įvykdyta.
- **Praleistas:**: užduotis praleista. Vienas ar daugiau procesų, nuo kurių priklauso ši užduotis, nesėkmingi arba buvo praleisti.
- **Nepavyko įvykdyti:** užduoties apdoroti nepavyko.
- **Atšaukta:** vartotojas atšaukė apdorojimą, kol jis nebuvo baigtas.
- **Eilė:** apdorojama į eilę ir pradedama, kai bus užbaigtos visos srauto užduotys. Daugiau informacijos žr. [Atnaujinimo strategijos](#refresh-policies)

### <a name="refresh-policies"></a>Atnaujinimo strategijos

Sąraše rodomos atnaujinimo strategijos kiekvienam iš pagrindinių procesų:

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

Kalbą ir šalies / regiono formatą galite keisti skirtuke **Bendra**.

„Customer Insights“ [palaikoma nemažai kalbų](/dynamics365/get-started/availability). Programa naudoja jūsų kalbos ypatybes tam, kad parodytų tokius elementus kaip meniu, žymos tekstas ir sistemos pranešimai jūsų pasirinkta kalba.

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

   Operacijose, kuriose pateikiami [realiuoju laiku naudojami duomenys](real-time-data-ingestion.md) yra mygtukas su žiūrono simboliu, skirtu peržiūrėti API naudojimą realiuoju laiku. Pasirinkite mygtuką siekiant atidaryti šoninę juostą turinčią suvartojimo informaciją realaus laiko API naudojimui ir esamai aplinkai.   
   Naudokite lauką **Grupuoti** pagal **pateikiamą realiuoju** laiku naudojant API, ir pasirinkite, kaip geriausiai pateikti bendravimą realiuoju laiku. Duomenis galite grupuoti pagal API būdą, objekto apibrėžtą pavadinimą (įtrauktas objektas), kūrėją (įvykio šaltinis), rezultatą (sėkmė arba nesėkmė) arba klaidų kodus. Duomenys prieinami kaip retrospektyvos diagrama ir kaip lentelė.

## <a name="security-tab"></a>Saugos skirtukas

Skirtukas **Sauga** leidžia susieti ir valdyti savo [„Azure" „key vault“](/azure/key-vault/general/basic-concepts) su aplinka.
Skirta raktų saugykla gali būti naudojama organizacijos sienų etapų ir naudojimo slaptai vietai nustatyti. Auditorijos įžvalgos gali naudoti „Azure“ „Key Vault“ [slaptas vietas ryšiams](connections.md) su trečiųjų šalių sistemomis nustatyti.

Daugiau informacijos žr. [„Azure” „key vault“ sukūrimas](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]