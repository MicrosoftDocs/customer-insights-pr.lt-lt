---
title: Ryšiai su kitomis paslaugomis iš „Customer Insights“.
description: Bendrinkite duomenis su kitomis paslaugomis.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896107"
---
# <a name="connections-preview-overview"></a>Ryšių (peržiūros) apžvalga

Ryšiai yra pagrindinis duomenų bendrinimo į „Customer Insights“ ir iš jo raktas. Kiekvienas ryšys sukuria duomenų bendrinimą su konkrečia paslauga. Ryšiai yra [trečiųjų šalių papildymų konfigūravimo](enrichment-hub.md) ir [eksportavimo konfigūravimo](export-destinations.md) pagrindas. Tą patį ryšį galima naudoti kelis kartus. Pavyzdžiui, vienas ryšys su „Dynamics 365 Marketing“ veikia keliems eksportams, o vienas „Leadspace“ ryšys gali būti naudojamas keliems papildymams.

Eikite į **Administravimas** > **Ryšiai** ir kurkite bei peržiūrėkite ryšius.

Skirtuke **Ryšiai** rodomi visi aktyvūs ryšiai. Sąraše rodoma kiekvieno ryšio eilutė. 

Greitai peržiūrėkite, gaukite aprašą ir sužinokite, ką galite daryti su kiekviena išplėtimo parinktimi skirtuke **Atrasti**.

### <a name="exports"></a>Eksportavimai

Naujus ryšius gali konfigūruoti tik administratoriai, tačiau jie gali suteikti prieigą prie bendraautorių, kad galėtų naudoti esamus ryšius. Administratoriai valdo, kur gali būti perkeliami duomenys, bendradarbiai apibrėžia jų poreikius pagal apkrovą ir dažnumą. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Papildymai

Naujus ryšius gali konfigūruoti tik administratoriai, bet sukurti ryšiai visada pasiekiami ir administratoriams, ir bendradarbiams. Administratoriai valdo kredencialus ir sutinka, kad duomenys būtų perduoti. Tada administratoriai ir bendradarbiai ryšius gali naudoti papildymams.

## <a name="add-a-new-connection"></a>Pridėti naują ryšį

Norėdami įtraukti ryšius, turite turėti [administratoriaus teises](permissions.md). Jei prisijungsite prie kitų „Microsoft“ paslaugų, manysime, kad abi paslaugos teikiamos toje pačioje organizacijoje.

1. Eikite į **Administravimas** > **Ryšiai (peržiūra)**.

1. Eikite į skirtuką **Ryšiai**.

1. Norėdami sukurti naują ryšį, pasirinkite **Pridėti ryšį**. Išplečiamajame meniu pasirinkite, kokio tipo ryšį norite sukurti.

1. Srityje **Nustatyti ryšį** pateikite reikiamą informaciją. 
   1. **Rodomas pavadinimas** ir ryšio tipas apibūdina ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas šio ryšio tikslas ir paskirtis.
   1. Tikslūs laukeliai priklauso nuo to, prie kokios paslaugos jungiatės. Apie konkretaus ryšio tipo duomenis galite sužinoti straipsnyje apie tikslinę paslaugą.

1. Jei norite sukurti ryšį, pasirinkite **Įrašyti**.

Taip pat galite pasirinkti **Nustatyti** plytelėje, esančioje skirtuke **Atrasti**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Leidimas bendradarbiams naudoti ryšį eksportuojant

Nustatę arba redaguodami eksportavimo ryšį pasirenkate, kuriems naudotojams bus leidžiama naudoti šį konkretų ryšį [eksportavimui](export-destinations.md) apibrėžti. Pagal numatytuosius nustatymus ryšys prieinamas naudotojams, kuriems priskirtas administratoriaus vaidmuo. Šį parametrą galite keisti dalyje **Pasirinkite, kas gali naudoti šį ryšį** ir leisti šiuo ryšiu naudotis naudotojams, kuriems priskirtas bendradarbio vaidmuo.

- Bendradarbiai negalės peržiūrėti ar redaguoti ryšio. Rodomas pavadinimas ir jo tipas bus rodomi tik kuriant eksportavimą.
- Bendrindami ryšį leidžiate bendradarbiams naudoti ryšį. Nustatydami eksportavimą, bendradarbiai matys bendrai naudojamus ryšius. Jie gali valdyti kiekvieną eksportavimą, kuris naudoja šį konkretų ryšį.
- Šį parametrą galima keisti išlaikant eksportavimą, kurį jau yra nustatę bendradarbiai.

## <a name="edit-a-connection"></a>Ryšio redagavimas

1. Eikite į **Administravimas** > **Ryšiai (peržiūra)**.

1. Eikite į skirtuką **Ryšiai**.

1. Pažymėkite norimo redaguoti ryšio vertikalią elipsę.

1. Pasirinkite **Redaguoti**.

1. Pakeiskite vertes, kurias norite atnaujinti, ir pasirinkite **Įrašyti**.

## <a name="remove-a-connection"></a>Ryšio pašalinimas

Jei ryšys, kurį šalinate, naudojamas praturtinant ar eksportuojant, pirmiausia turite juos atsieti arba pašalinti. Šalinimo dialogas padės atlikti svarbius papildymus arba eksportavimą. Atsieti papildymai ir eksportavimai tampa neaktyvūs. Iš naujo suaktyvinate juos prie jų pridėdami kitą ryšį puslapyje [Papildymai](enrichment-hub.md) arba [Eksporavimai](export-destinations.md).

1. Eikite į **Administravimas** > **Ryšiai (peržiūra)**.

1. Eikite į skirtuką **Ryšiai**.

1. Pažymėkite norimo pašalinti ryšio vertikalią elipsę.

1. Išskleidžiamajame meniu pasirinkite **Pašalinti**. Rodomos patvirtinimo dialogas.

   1. Jei naudojant šį ryšį atliekami papildymai ar eksportavimai, pažymėkite mygtuką, kad pamatytumėte, kas naudoja ryšį.
      - **Eksportavimai:** galite pasirinkti pašalinti arba atjungti eksportavimą, kad galėtumėte pašalinti ryšį. Norėdami atjungti eksportavimą, administratoriai gali naudoti veiksmą **Atjungti**. Šį veiksmą galima naudoti pavieniam arba keliems pasirinktiems eksportavimams. Atjungdami išlaikote eksportavimo konfigūraciją, tačiau ji nebus vykdoma, kol prie jos nebus pridėtas kitas ryšys.
      - **Papildymai:** galite pasirinkti pašalinti arba atjungti papildymus, kad galėtumėte pašalinti ryšį. 
   1. Kai ryšys nebeturi priklausomybių, grįžkite į **Administravimas** > **Ryšiai** ir dar kartą pabandykite pašalinti ryšį.

1. Jei norite patvirtinti trynimą, pasirinkite **Šalinti**.
