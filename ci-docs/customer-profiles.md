---
title: Peržiūrėti kliento profilius
description: Suvienodintų klientų duomenų peržiūra, įskaitant ieškos ir filtro naudojimą
ms.date: 06/08/2022
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188103"
---
# <a name="view-customer-profiles"></a>Peržiūrėti kliento profilius

Klientų profiliai pasiekiami sukūrus [vieningą *kliento* objektą](data-unification.md). Bendras jūsų vieningųjų klientų profilių rodinys rodomas **puslapyje Klientai**. Klientai gali būti asmenys arba organizacijos.

Eikite į **puslapį Klientai** ir peržiūrėkite savo klientus ir jų profilius. Kiekvieno kliento profilį vaizduoja plytelė. Norėdami gauti daugiau įrašų, naudokite puslapių ieškos valdiklius. Šioje kortelės lauke rodomi kliento *objekto* laukai, apibrėžti **ieškos ir filtro rodyklėje**. Kiekvienos kortelės laukų tvarką parenka sistema.

> [!NOTE]
> Jei pasirinkdami **Klientai** nematote plytelių, administratorius ieškos ir filtro indekse [turi](search-filter-index.md) apibrėžti bent vieną **atributą**, kuriame galima ieškoti.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Puslapis Klientai, kuriame rodomos rezultatų plytelės.":::

Pasirinkite bet kurį iš šių veiksmų:
- [Peržiūrėkite išsamią kliento informaciją](#view-customer-details)
- [Ieškos ir filtro indekso](search-filter-index.md) tvarkymas (tik administratoriams)
- [Filtruoti klientus](#filter-customers)
- **Išplėskite korteles** arba **sutraukite korteles**, kad išplėstumėte arba sutrauktumėte kliento plytelėje rodomą informaciją
- **Rūšiavimas pagal** konkretų atributą
- [Klientų paieška](#search-for-customers)

  > [!NOTE]
  > Norėdamas naudoti iešką ir filtrą, administratorius turi sukonfigūruoti atributus, kuriuose galima ieškoti, ir apibrėžti filtruojamus laukus naudodamas ieškos ir filtro indeksą.

## <a name="search-for-customers"></a>Klientų paieška

Ieškokite klientų įvesdami vardą ar kitą atributą ieškos **klientuose**. Atributus, kuriuose galima ieškoti, apibrėžia administratorius ir jie gaunami iš vieningo *kliento* objekto.

> [!NOTE]
> **Eilutė** yra vienintelis duomenų tipas, įtrauktas į iešką. Naudokite jį puslapyje Klientai esančiame **lauke Ieškoti klientų**, kad ieškotumėte klientų.

## <a name="filter-customers"></a>Filtruoti klientus

Filtruokite klientus pagal kliento objekto *laukus*. Filtruojamus laukus apibrėžia administratorius.

1. **Puslapyje Klientai** pasirinkite **Rodyti filtrus**. Rodoma sritis Filtras.

1. Pažymėkite laukelius šalia atributų, pagal kuriuos norite filtruoti klientus.

1. Pašalinkite visus filtrus pažymėdami **Valyti filtrus** arba išvalykite žymimąjį laukelį šalia pasirinkto atributo.

1. Pasirinkite **Slėpti filtrus**, kad uždarytumėte filtro sritį.

1. Norėdami įrašyti filtro rezultatus kaip segmentą, pasirinkite [Įrašyti filtrus kaip segmentą.](segments.md)**·**
   1. Įveskite segmento pavadinimą.
   1. Pasirinkite **Išsaugoti**, kad išsaugotumėte segmentą.
   1. Pasirinkite, ar paleisti segmentą dabar, pasirinkdami **Aktyvinti** arba paleiskite jį **vėliau**.

## <a name="view-customer-details"></a>Peržiūrėkite išsamią kliento informaciją

**Puslapyje Klientai** pasirinkite kliento plytelę, kad peržiūrėtumėte pasirinkto kliento informaciją.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Kliento rekvizitų puslapis.":::

Kliento išsami informacija apima:

**Kliento profilio plytelė** rodo skirtingas reikšmes nei vieningasis *kliento* objektas. Jei laukas neturi pasirinkto kliento profilio reikšmės, jis nebus rodomas, išskyrus adreso lauką. Plytelę sudaro skyriai:

- Pirmajame skyriuje rodomas iš anksto nustatytas laukų rinkinys, po kurio seka visi laukai, kurie yra ieškos &filtro rodyklės dalis. Visi su adresu susiję laukai sujungiami į vieną eilutę, kuri rodoma, net jei profilyje nėra adreso informacijos.
- **Šio kliento** kontaktai rodomi verslo paskyrų aplinkose. Kiekvienas kontaktas rodomas su jų laukais. Tušti laukai paslėpti.
- **Papildomuose laukuose** rodomi likę pasirinkto kliento laukai, išskyrus ID.
- **ID išvardijami** visi ID pagal atitinkamą objekto pavadinimą. Laukai identifikuojami kaip ID pagal jų semantiką.

**Veiklos laiko planavimo juostoje** rodomi duomenys, jei sukonfigūravote [veiklą](activities.md). Laiko planavimo juostos rodinyje yra chronologiškai rūšiuotos pasirinkto kliento veiklos, pradedant naujausia veikla.

**įžvalgos**:

- **Priemonės** rodo, ar sukonfigūravote [kliento atributų matus](measures.md). Jos apima apskaičiuotą KPI pagal jūsų klientus individualiu kliento lygmeniu.

- **Galimi interesai, potencialūs prekės ženklai** rodo, jei sukonfigūravote [prekės ženklo ar pomėgių giminingumo praturtinimą](enrichment-microsoft.md). Tai atitinka galimus prekių ženklų, pagrįstų kitais klientais, kurių profilis yra panašus į pasirinktą kliento profilį, interesą ir galimybes.

Norėdami grįžti į **puslapį Klientai**, pasirinkite **Grįžti į klientus**.

## <a name="next-steps"></a>Paskesni veiksmai

[Įtraukite daugiau duomenų šaltinių](data-sources.md), [praturtinkite vieningus profilius](enrichment-hub.md) arba [kurkite segmentus](segments.md) tam, kad suvienytus klientų profilius būtų galima naudoti kitose taikomosiose programose.

[!INCLUDE [footer-include](includes/footer-banner.md)]
