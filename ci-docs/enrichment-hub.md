---
title: Duomenų papildymo (peržiūros) apžvalga
description: Naudokite "Microsoft" ir kitų trečiųjų šalių tarnybų galimybes, kad praturtintumėte savo klientų duomenis.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053890"
---
# <a name="data-enrichment-preview-overview"></a>Duomenų papildymo (peržiūros) apžvalga

Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis. Trečiosios šalies papildymai konfigūruojami naudojant [ryšius](connections.md), kuriuos administratorius nustato su kredencialais ir pateikia sutikimą duomenims perduoti. Ryšiai gali būti naudojami administratorių ir prie konfigūracijos papildinių prisidedančių subjektų.  

## <a name="multiple-enrichments-of-the-same-type"></a>Keli to paties tipo papildymai

Objektas, kurį reikia papildyti, nurodomas papildymo konfigūracijoje, o tai jums leidžia papildyti tik antrinį jūsų profilių rinkinį. Pavyzdžiui, duomenis papildyti galima tik konkrečiame segmente. Galite konfigūruoti kelis to paties tipo papildymus ir pakartotinai naudoti tą patį ryšį. Kai kuriems papildymams bus ribojamas to paties tipo sukuriamų papildymų skaičius. Apribojimus ir dabartinį naudojimą galima pamatyti kiekvienoje plytelėje, esančioje **papildymo** **puslapio skirtuke Atrasti**.

## <a name="enrich-data-sources-before-unification"></a>Praturtinkite duomenų šaltinius prieš suvienijimą

Galite papildyti savo klientų duomenis prieš suvienodindami duomenis, kad pagerintumėte duomenų atitikties kokybę. Daugiau informacijos rasite [duomenų šaltinis sodrinimas](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Kurti papildymą

Turite turėti bendraautorio arba administratoriaus [teises](permissions.md), kad galėtumėte kurti arba redaguoti papildymus.

Eikite į **Duomenys** > **Papildymas**. Skirtuke Atrasti **rodomos** visos palaikomos papildymo parinktys.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis.":::

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- ["AbiliTec" tapatybę](enrichment-liveramp.md) teikia "LiveRamp AbiliTec"
- [Rūšys](enrichment-microsoft.md), kurias teikia „Microsoft“
- [Demografiniai](enrichment-experian.md) duomenys pateikti „Experian“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft”
- [Pomėgiai](enrichment-microsoft.md), kuriuos teikia „Microsoft“
- [Žemėlapių teikiami](enrichment-azure-maps.md) vietos duomenys Microsoft Azure
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“
- [SFTP pasirinktiniai duomenys](enrichment-SFTP-custom-import.md) per saugaus failų perdavimo protokolą (SFTP)

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- ["Microsoft" pateikti įtraukimo į paskyrą duomenys](enrichment-office.md)
- [Įmonės duomenis](enrichment-dnb.md) pateikė Dun & Bradstreet
- [Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft”
- [Patobulinti įmonės duomenys](enrichment-enhanced-company-data.md), kuriuos teikia "Microsoft"
- [Žemėlapių teikiami](enrichment-azure-maps.md) vietos duomenys Microsoft Azure
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“
- [SFTP pasirinktiniai duomenys](enrichment-SFTP-custom-import.md) per saugaus failų perdavimo protokolą (SFTP)

---

## <a name="manage-existing-enrichments"></a>Esamų papildymų tvarkymas

Eikite į **Duomenys** > **Papildymas**. Skirtuke **Mano papildymai** peržiūrėkite sukonfigūruotus papildymus, jų būseną, papildytų klientų skaičių ir paskutinį kartą, kai duomenys buvo atnaujinti. Galite rūšiuoti papildymų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte norimą tvarkyti papildymą.

Pasirinkite papildymą, kad peržiūrėtumėte galimus veiksmus.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Papildymų tvarkymo parinktys papildymų sąraše.":::

- **Peržiūrėkite** papildymo informaciją su papildytų klientų profilių skaičiumi.
- **Redaguokite** papildymo konfigūraciją.
- [**Vykdykite**](#run-or-refresh-enrichments) papildymą, kad atnaujintumėte klientų profilius naujausiais duomenimis. Vykdykite kelis papildymus vienu metu, pasirinkdami juos sąraše.
- **Suaktyvinkite** arba **išjunkite** papildymą. Neaktyvus papildymas nebus atnaujintas per suplanuotą [atnaujinimą](system.md#schedule-tab).
- **Panaikinkite** papildymą.

Taip pat galite kurti [segmentus arba](segments.md) matus [iš](measures.md) sodrinimo.

## <a name="run-or-refresh-enrichments"></a>Papildymų vykdymas arba atnaujinimas

Paleidus papildymus, juos galima atnaujinti automatiniu grafiku arba atnaujinti rankiniu būdu pagal poreikį.

1. Norėdami rankiniu būdu atnaujinti vieną ar daugiau papildymų, pažymėkite juos ir pasirinkite **Vykdyti**. Norėdami [suplanuoti automatinį atnaujinimą](system.md#schedule-tab), eikite į **Administratoriaus** > **sistemos** > **tvarkaraštis**. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.

1. Pasirinktinai [žiūrėkite sodrinimo proceso eigą](#see-the-progress-of-the-enrichment-process).

1. Kai papildymo procesas bus baigtas, eikite į **Mano papildymai** ir peržiūrėkite naujai papildytų klientų profilių duomenis, paskutinio atnaujinimo laiką ir papildytų profilių skaičių.

1. Pasirinkite papildymą, kad pamatytumėte [papildymo rezultatus](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Žiūrėti papildymo proceso eigą

Galite rasti informacijos apie papildymo apdorojimą, įskaitant jo būseną ir galimas problemas jį atnaujinant arba pasibaigus atnaujinimui. Sužinokite, kurie procesai naudojami norint atnaujinti papildymą ir procesų vykdymo trukmes. Papildymo būseną palaiko „Experian”, „Leadspace”, HERE Technologijos, SFTP Importavimas ir „Azure” žemėlapiai.

1. Eikite į **Duomenys** > **Papildymas**.
1. Skirtuke **Mano papildymai** pasirinkite papildymo būseną, kad atidarytumėte šoninę sritį.
1. Srityje **Išsami eigos informacija** išplėskite **Papildymų** skyrių.
1. Po papildymu, kurio progresą norite peržiūrėti, pasirinkite **Žiūrėti išsamią informaciją**.
1. Srityje **Išsami užduoties informacija** pasirinkite **Rodyti išsamią informaciją**, kad peržiūrėtumėte procesus, kurie susiję su papildymų atnaujinimu ir jų būsena.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

Baigę papildymo eigą, peržiūrėkite papildymo rezultatus.

1. Eikite į **Duomenys** > **Papildymas**.
1. Skirtuke **Mano papildymai** pasirinkite papildymą, kurį norite peržiūrėti.

Visuose papildymuose pateikiama pagrindinė informacija, pvz., praturtintų profilių skaičius ir papildytų profilių skaičius laikui bėgant. Papildytų **klientų peržiūros** plytelėje rodomas sugeneruoto papildymo objekto pavyzdys. Norėdami peržiūrėti išsamų rodinį, pasirinkite **Peržiūrėti daugiau** ir pasirinkite skirtuką **Duomenys**.

:::image type="content" source="media/enrichments-results.png" alt-text="Papildymo rezultatų puslapis.":::

Jei įmanoma, pagal lauką **praturtintų** klientų skaičius leidžia detalizuoti kiekvieno praturtinto lauko aprėptį.

Kai kurie sodrinimo būdai taip pat rodo informaciją, būdingą sodrinimo tipui. Daugiau informacijos ieškokite susijusioje dokumentacijoje.

[!INCLUDE [footer-include](includes/footer-banner.md)]
