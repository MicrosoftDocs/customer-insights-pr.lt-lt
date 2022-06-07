---
title: Ryšiai su kitomis paslaugomis iš „Customer Insights“.
description: Bendrinkite duomenis su kitomis paslaugomis.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 2a3175737ac95e10d75fad4a69db303b0564c6cc
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800382"
---
# <a name="connections-preview-overview"></a>Ryšių (peržiūros) apžvalga

Ryšiai yra pagrindinis duomenų bendrinimo į „Customer Insights“ ir iš jo raktas. Kiekvienas ryšys sukuria duomenų bendrinimą su konkrečia paslauga. Ryšiai yra [trečiųjų šalių papildymų konfigūravimo](enrichment-hub.md) ir [eksportavimo konfigūravimo](export-destinations.md) pagrindas. Tą patį ryšį galima naudoti kelis kartus. Pavyzdžiui, vienas ryšys su „Dynamics 365 Marketing“ veikia keliems eksportams, o vienas „Leadspace“ ryšys gali būti naudojamas keliems papildymams.

Eikite į **Administravimas** > **Ryšiai** ir kurkite bei peržiūrėkite ryšius.

Skirtuke **Ryšiai** rodomi visi aktyvūs ryšiai. Sąraše rodoma kiekvieno ryšio eilutė.

Greitai peržiūrėkite, gaukite aprašą ir sužinokite, ką galite daryti su kiekviena išplėtimo parinktimi skirtuke **Atrasti**.

## <a name="exports"></a>Eksportavimai

Naujus ryšius gali konfigūruoti tik administratoriai, tačiau jie gali suteikti prieigą prie bendraautorių, kad galėtų naudoti esamus ryšius. Administratoriai valdo, kur gali būti perkeliami duomenys, bendradarbiai apibrėžia jų poreikius pagal apkrovą ir dažnumą. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Papildymai

Naujus ryšius gali konfigūruoti tik administratoriai, bet sukurti ryšiai visada pasiekiami ir administratoriams, ir bendradarbiams. Administratoriai valdo kredencialus ir sutinka, kad duomenys būtų perduoti. Tada administratoriai ir bendradarbiai ryšius gali naudoti papildymams.

## <a name="add-a-new-connection"></a>Pridėti naują ryšį

Norėdami įtraukti ryšius, turite turėti [administratoriaus teises](permissions.md). Jei prisijungsite prie kitų „Microsoft“ paslaugų, manysime, kad abi paslaugos teikiamos toje pačioje organizacijoje.

1. Eikite į **Administravimas** > **Ryšiai (peržiūra)**.

1. Eikite į skirtuką **Ryšiai**.

1. Norėdami sukurti naują ryšį, pasirinkite **Pridėti ryšį**. Išplečiamajame meniu pasirinkite, kokio tipo ryšį norite sukurti.

1. Srityje **Nustatyti ryšį** pateikite reikiamą informaciją.
   1. **Rodomas pavadinimas** ir ryšio tipas apibūdina ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas šio ryšio tikslas ir paskirtis.
   1. Tikslūs laukai priklauso nuo to, prie kokios paslaugos jungiatės. Apie konkretaus ryšio tipo duomenis galite sužinoti straipsnyje apie tikslinę paslaugą.
   1. Jei [naudojate savo „Key Vault“](use-azure-key-vault.md) slaptai saugoti, suaktyvinkite **naudoti Key Vault** ir sąraše pasirinkite slaptą parinktį.

1. Jei norite sukurti ryšį, pasirinkite **Įrašyti**.

Taip pat galite pasirinkti **Nustatyti** plytelėje, esančioje skirtuke **Atrasti**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Leidimas bendradarbiams naudoti ryšį eksportuojant

Nustatę arba redaguodami eksportavimo ryšį pasirenkate, kuriems naudotojams bus leidžiama naudoti šį konkretų ryšį [eksportavimui](export-destinations.md) apibrėžti. Pagal numatytuosius nustatymus ryšys prieinamas naudotojams, kuriems priskirtas administratoriaus vaidmuo. Šį parametrą galite keisti dalyje **Pasirinkite, kas gali naudoti šį ryšį** ir leisti šiuo ryšiu naudotis naudotojams, kuriems priskirtas bendradarbio vaidmuo.

- Bendradarbiai negalės peržiūrėti ar redaguoti ryšio. Jie matys tik rodomą pavadinimą ir jo tipą kurdami eksportavimą.
- Bendrindami ryšį leidžiate bendradarbiams naudoti ryšį. Nustatydami eksportavimą, bendradarbiai matys bendrai naudojamus ryšius. Jie gali valdyti kiekvieną eksportavimą, kuris naudoja šį konkretų ryšį.
- Šį parametrą galima keisti išlaikant eksportavimą, kurį jau yra nustatę bendradarbiai.

## <a name="edit-a-connection"></a>Ryšio redagavimas

1. Eikite į **Administravimas** > **Ryšiai (peržiūra)**.

1. Eikite į skirtuką **Ryšiai**.

1. Pasirinkite norimo redaguoti ryšio vertikalią elipsę (&vellip;) .

1. Pasirinkite **Redaguoti**.

1. Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.

## <a name="remove-a-connection"></a>Ryšio pašalinimas

Jei ryšį, kurį pašalinate, naudoja sodrinimas arba eksportas, pirmiausia turite juos atskirti arba pašalinti. Šalinimo dialogas padės atlikti svarbius papildymus arba eksportavimą.

Atsieti papildymai ir eksportavimai tampa neaktyvūs. Iš naujo suaktyvinate juos prie jų pridėdami kitą ryšį puslapyje [Papildymai](enrichment-hub.md) arba [Eksporavimai](export-destinations.md).

1. Eikite į **Administravimas** > **Ryšiai (peržiūra)**.

1. Eikite į skirtuką **Ryšiai**.

1. Pasirinkite norimo pašalinti ryšio vertikalią elipsę (&vellip;) .

1. Išskleidžiamajame meniu pasirinkite **Pašalinti**. Rodomos patvirtinimo dialogas.

   1. Jei naudojant šį ryšį atliekami papildymai ar eksportavimai, pažymėkite mygtuką, kad pamatytumėte, kas naudoja ryšį.
      - **Eksportavimai:** galite pasirinkti pašalinti arba atjungti eksportavimą, kad galėtumėte pašalinti ryšį. Norėdami atjungti eksportavimą, administratoriai gali naudoti veiksmą **Atjungti**. Šį veiksmą galima naudoti pavieniam arba keliems pasirinktiems eksportavimams. Atjungdami išlaikote eksportavimo konfigūraciją, tačiau ji nebus vykdoma, kol prie jos nebus pridėtas kitas ryšys.
      - **Papildymai:** galite pasirinkti pašalinti arba atjungti papildymus, kad galėtumėte pašalinti ryšį.
   1. Kai ryšys nebeturi priklausomybių, grįžkite į **Administravimas** > **Ryšiai** ir dar kartą pabandykite pašalinti ryšį.

1. Jei norite patvirtinti trynimą, pasirinkite **Šalinti**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Ryšių su slaptais įrašais, kuriuos valdo jūsų „Key Vault“, nustatymas

Kai kuriems ryšiams reikia slaptai pvz., API raktų arba slaptažodžius. Kai kurie ryšiai palaiko slaptas informacijas, saugomas jūsų saugykloje „Key Vault“. Sužinokite daugiau apie palaikomus ryšius ir kaip nustatyti [savo "Key Vault for Customer Insights"](use-azure-key-vault.md).
