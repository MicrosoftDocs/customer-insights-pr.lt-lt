---
title: Papildykite suvienodintus kliento profilius
description: Naudokite savybes siekiant papildyti jūsų kliento duomenis.
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
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954051"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientų profilių papildymas (peržiūra)

Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis.":::

Eikite į **"Data** > **Enrichment** ", kad dirbtumėte su sodrinimo galimybėmis.  

Norėdami kurti arba redaguoti papildymus, turite turėti dalyvio arba administratoriaus teises. Daugiau informacijos žr. [Teisės](permissions.md).

Skirtuke **Atrasti** rasite visas palaikomas gerinimo parinktis.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- [AbiliTec identity](enrichment-liveramp.md) pateikė LiveRamp AbiliTec
- [Rūšys](enrichment-microsoft.md), kurias teikia „Microsoft“
- [Demografiniai](enrichment-experian.md) duomenys pateikti „Experian“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft”
- [Pomėgiai](enrichment-microsoft.md), kuriuos teikia „Microsoft“
- [Žemėlapių pateikti](enrichment-azure-maps.md) vietos nustatymo duomenys Microsoft Azure
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“
- [SFTP pasirinktiniai duomenys](enrichment-SFTP-custom-import.md) per saugaus failų perdavimo protokolą (SFTP)

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- ["Microsoft" pateikti abonemento įtraukimo duomenys](enrichment-office.md)
- [Įmonės duomenys](enrichment-dnb.md), kuriuos pateikė Dun & Bradstreet
- [Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft”
- [Patobulinti "Microsoft" pateikti įmonės duomenys](enrichment-enhanced-company-data.md)
- [Žemėlapių pateikti](enrichment-azure-maps.md) vietos nustatymo duomenys Microsoft Azure
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“
- [SFTP pasirinktiniai duomenys](enrichment-SFTP-custom-import.md) per saugaus failų perdavimo protokolą (SFTP)

---

Skirtuke **Mano papildymai** galite matyti sukonfigūruotus papildymus ir redaguoti jų ypatybes. Taip pat galite sukurti [segmentus](segments.md) ar [priemones](measures.md) iš sodrinimo.

## <a name="manage-existing-enrichments"></a>Esamų papildymų tvarkymas

Eikite į skirtuką **Mano papildymai**, kad pamatytumėte visus sukonfigūruotus papildymus. Kiekvienas papildymas atvaizduotas kaip eilutė su papildoma informacija apie papildymą.

Norėdami peržiūrėti galimas parinktis, pažymėkite papildymą. Taip pat galite pasirinkti vertikalią elipsę (&vellip;) sąrašo elemente, kad pamatytumėte parinktis. Jei sukonfigūravote kelis papildymus, galite naudoti ieškos lauką, kad greitai juos rastumėte.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Papildymų tvarkymo parinktys papildymų sąraše.":::

- **Peržiūrėkite** papildymo informaciją su papildytų klientų profilių skaičiumi.
- **Redaguokite** papildymo konfigūraciją.
- **Vykdykite** papildymą ir atnaujinkite klientų profilius naujausiais duomenimis.
- **Išjunkite** esamą papildymą, kad jis nebebūtų automatiškai atnaujinamas per kiekvieną suplanuotą atnaujinimą. Paskutinio sėkmingo atnaujinimo duomenys išliks prieinami. **Aktyvinkite** neaktyvų papildymą, jei norite iš naujo paleisti automatinį atnaujinimą su kiekvienu suplanuotu atnaujinimu.
- **Panaikinkite** papildymą.

Vienu metu paleiskite arba išjunkite kelis papildymus pažymėdami juos sąraše. Peržiūros ir redagavimo parinktys negalimos kaip masinis veiksmas. Jos veikia tik vienam papildymui vienu metu.

## <a name="enrichments-and-connections"></a>Papildymai ir ryšiai

Trečiosios šalies papildymai konfigūruojami naudojant [ryšius](connections.md), kuriuos administratorius nustato su kredencialais ir pateikia sutikimą duomenims perduoti. Ryšiai gali būti naudojami administratorių ir prie konfigūracijos papildinių prisidedančių subjektų.  

## <a name="multiple-enrichments-of-the-same-type"></a>Keli to paties tipo papildymai

Objektas, kurį reikia papildyti, nurodomas papildymo konfigūracijoje, o tai jums leidžia papildyti tik antrinį jūsų profilių rinkinį. Pavyzdžiui, duomenis papildyti galima tik konkrečiame segmente. Galite konfigūruoti kelis to paties tipo papildymus ir pakartotinai naudoti tą patį ryšį. Kai kuriems papildymams bus ribojamas to paties tipo sukuriamų papildymų skaičius. Apribojimus ir dabartinį naudojimą galima pamatyti kiekvienoje plytelėje **puslapio Sodrinimas skirtuke** Atrasti **·**.

## <a name="enrich-data-sources-before-unification"></a>Duomenų šaltinių praturtinimas prieš suvienijimą

Galite praturtinti savo klientų duomenis prieš duomenų suvienijimą, kad padėtumėte pagerinti duomenų atitikties kokybę. Daugiau informacijos rasite [duomenų šaltinis sodrinimą](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Vykdyti arba atnaujinti sodrinimą

1. Norėdami pradėti sodrinimo procesą, pasirinkite **Vykdyti**. Arba leiskite sistemai automatiškai paleisti sodrinimą kaip suplanuoto [atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio.

1. Pasirinktinai [žiūrėkite sodrinimo proceso](#see-the-progress-of-the-enrichment-process) eigą.

1. Pasibaigus sodrinimo procesui, eikite į **"My enrichments"**, kad peržiūrėtumėte naujai praturtintus klientų profilių duomenis, paskutinio atnaujinimo laiką ir praturtintų profilių skaičių.

1. Pasirinkite sodrinimą, kad pamatytumėte [sodrinimo rezultatus](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Žiūrėti papildymo proceso eigą

Galite rasti informacijos apie papildymo apdorojimą, įskaitant jo būseną ir galimas problemas jį atnaujinant arba pasibaigus atnaujinimui. Sužinokite, kurie procesai naudojami norint atnaujinti papildymą ir procesų vykdymo trukmes. Papildymo būseną palaiko „Experian”, „Leadspace”, HERE Technologijos, SFTP Importavimas ir „Azure” žemėlapiai.

1. Eikite į **Duomenys** > **Papildymas**.
1. Skirtuke **Mano sodrinimas** pasirinkite sodrinimo būseną, kad atidarytumėte šoninę sritį.
1. Srityje **Išsami eigos informacija** išplėskite **Papildymų** skyrių.
1. Po papildymu, kurio progresą norite peržiūrėti, pasirinkite **Žiūrėti išsamią informaciją**.
1. Srityje **Išsami užduoties informacija** pasirinkite **Rodyti išsamią informaciją**, kad peržiūrėtumėte procesus, kurie susiję su papildymų atnaujinimu ir jų būsena.

## <a name="enrichment-results"></a>Papildymo rezultatai

Baigę sodrinimo ciklą, peržiūrėkite sodrinimo rezultatus.

1. Eikite į **Duomenys** > **Papildymas**.
1. Skirtuke **Mano praturtinimai** pasirinkite praturtinimą, apie kurį norite gauti informacijos.

Visi praturtinimai rodo pagrindinę informaciją, pvz., Praturtintų profilių skaičių ir praturtintų profilių skaičių laikui bėgant. Plytelėje Praturtinti **klientai rodomi** sugeneruoto sodrinimo objekto pavyzdys. Norėdami pamatyti išsamų rodinį, pasirinkite **Peržiūrėti daugiau** ir pasirinkite skirtuką **Duomenys**.

:::image type="content" source="media/enrichments-results.png" alt-text="Sodrinimo rezultatų puslapis.":::

Jei įmanoma, **lauke** praturtintų klientų skaičius suteikia išsamią informaciją apie kiekvieno praturtinto lauko aprėptį.

Kai kurie sodrinimas taip pat rodo informaciją, būdingą sodrinimo tipui. Daugiau informacijos rasite susijusiuose dokumentuose.

[!INCLUDE [footer-include](includes/footer-banner.md)]
