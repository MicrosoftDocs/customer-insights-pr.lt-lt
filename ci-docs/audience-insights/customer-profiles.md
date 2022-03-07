---
title: Peržiūrėti kliento profilius
description: Gaukite bendrą jūsų suvienodintų kliento duomenų rodinį.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 3a17716508a14020c56640c7d68f300a9d721af4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354891"
---
# <a name="customer-profiles"></a>Klientų profiliai

Klientų **puslapyje** rodomas bendras jūsų vieningų klientų profilių rodinys. Klientų profiliai pasiekiami sukūrus [vieningą kliento objektą](data-unification.md). Puslapyje galima ieškoti klientų ir apibrėžti tos ieškos rodyklę.

Klientai gali būti asmenys arba organizacijos. Kiekvieno kliento profilį vaizduoja plytelė. Norėdami gauti daugiau įrašų, naudokite puslapių ieškos valdiklius. Šioje kortelės lauke rodomi kliento *objekto* laukai, apibrėžti **ieškos ir filtro rodyklėje**. Pasirinkite plytelę, kad specialiame puslapyje, pavadintame Kliento išsami informacija, būtų [peržiūrėti pasirinkto kliento duomenys](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Klientų puslapis, kuriame rodomos rezultatų plytelės](media/customers-page-result-tiles-B2C.png "Klientų puslapis, kuriame rodomos rezultatų plytelės")

> [!NOTE]
> Jei naršymo srityje pažymėdami **Klientai** plytelių nematote, jūsų administratorius turi ieškos ir filtro rodyklėje [apibrėžti bent vieną ieškomą](search-filter-index.md) atributą **Ieškos ir filtro rodyklėje**.

## <a name="search-for-customers"></a>Klientų paieška

Klientų galite ieškoti, į paieškos laukelį įvesdami vardą ar kokį nors kitą atributą. Ieška veikia tik _kliento_ objektui, sukurtame suvienodinimo proceso metu.

Turėdami administratoriaus teises, galite konfigūruoti paieškai pasiekiamus atributus, naudodami puslapį **Ieškos ir filtro rodyklė**. Daugiau informacijos rasite apsilankę [Ieškos ir filtro rodyklės valdymas](search-filter-index.md).

## <a name="filter-customers"></a>Filtruoti klientus

Klientus galite filtruoti pagal objekto laukus _Klientas_. Panašiai kaip ir atliekant iešką, jūsų administratoriui pirmiausia reikės apibrėžti laukus kaip galimus filtruoti, naudojant puslapį **Ieškos ir filtro rodyklė**.

1. Rinkitės **Rodyti filtrus** puslapyje **Klientai**.

1. Pažymėkite laukelius šalia atributų, pagal kuriuos norite filtruoti klientus.

1. Pašalinkite savo filtrus pasirinkę **Pašalinti filtrus** **Klientų** puslapyje.

## <a name="customer-details-page"></a>Kliento informacijos puslapis

Pasirinkite bet kurias kliento plytas tam, kad atvertumėte **Kliento informacijos puslapį**. Šis rodinys apima suvienodintą informaciją pasirinktam klientui. Į išsamią kliento informaciją įtraukiamas šis turinys:

**Kliento profilio plytelė**: šioje plytelėje rodomos kitos reikšmės nei vieningojo _kliento_ objektas. Jei lauke nėra pasirinkto kliento profilio reikšmės, jis nebus rodomas. Plytelę sudaro skyriai:  
  - Pirmajame skyriuje rodomas iš anksto nustatytas laukų rinkinys, po kurio seka visi laukai, kurie yra ieškos &filtro rodyklės dalis. Visi su adresu susiję laukai sujungiami į vieną eilutę, jei profilyje yra tokių laukų. 
  - **Šio kliento kontaktai**: verslo klientų aplinkose kaip antrą skyrių bus rodomi visi susiję šio kliento kontaktai. Kiekvienas kontaktas rodomas su jų laukais. Tušti laukai paslėpti.
  - **Papildomi laukai**: rodomi likę pasirinkto kliento laukai, išskyrus TV. 
  - **ID** : visų ID pateikiamas jų atitinkamo objekto pavadinimo sąrašas. Laukus kaip ID identifikuoja jų semantikos, o šie laukai skirstomi į kategorijas.

**Veiklos laiko planavimo juosta**: rodomi duomenys, jei turite sukonfigūruotų veiklų. Laiko planavimo juostos rodinyje yra chronologiškai rūšiuotos pasirinkto kliento veiklos, pradedant naujausia veikla. Norėdami gauti daugiau informacijos, eikite į [Kliento veiksmai](activities.md).

**įžvalgos**:  
  - **Priemonės**: rodo, ar konfigūravote vieną ar daugiau priemonių, pagal kurias klientas atributų priemones. Jos apima apskaičiuotą KPI pagal jūsų klientus individualiu kliento lygmeniu. Daugiau informacijos rasite straipsnyje [Priemonių apibrėžimas ir valdymas](measures.md).

  - **Potencialūs susidomėjimas, galimi prekių ženklai**: rodo, ar sukonfigūravote prekės ženklą, ar dominamą susidomėjimą. Tai atitinka galimus prekių ženklų, pagrįstų kitais klientais, kurių profilis yra panašus į pasirinktą kliento profilį, interesą ir galimybes. Norėdami gauti daugiau informacijos, eikite į [Klientų profilių pagerinimo naudojant prekės ženklą ir susidomėjimo profilį](enrichment-microsoft.md).

Norėdami grįžti į klientų ieškos puslapį, pasirinkite **Atgal į klientus**.

## <a name="next-steps"></a>Kiti veiksmai

[Įtraukite daugiau duomenų šaltinių](data-sources.md), [praturtinkite vieningus profilius](enrichment-hub.md) arba [kurkite segmentus](segments.md) tam, kad suvienytus klientų profilius būtų galima naudoti kitose taikomosiose programose.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
