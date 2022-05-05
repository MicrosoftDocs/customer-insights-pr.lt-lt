---
title: Papildykite suvienodintus kliento profilius
description: Naudokite savybes siekiant papildyti jūsų kliento duomenis.
ms.date: 03/29/2022
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
ms.openlocfilehash: 5c14e6c96d2f907ba161331b6f92277191cbdbef
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653533"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientų profilių papildymas (peržiūra)

Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis.":::

Eikite į **"DataEnrichment** > **·**", kad dirbtumėte su sodrinimo galimybėmis.  

Norėdami kurti arba redaguoti papildymus, turite turėti dalyvio arba administratoriaus teises. Daugiau informacijos žr. [Teisės](permissions.md).

Skirtuke **Atrasti** rasite visas palaikomas gerinimo parinktis.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- [Rūšys](enrichment-microsoft.md), kurias teikia „Microsoft“
- [Pomėgiai](enrichment-microsoft.md), kuriuos teikia „Microsoft“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft” 
- [Demografiniai](enrichment-experian.md) duomenys pateikti „Experian“
- [Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP) 
- [„Azure” žemėlapiai](enrichment-azure-maps.md), kuriuos teikia „Microsoft”
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“ 
- [Tapatybę](enrichment-liveramp.md) pateikė LiveRamp AbiliTec

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- [Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft” 
- [Patobulinti "Microsoft" pateikti įmonės duomenys](enrichment-enhanced-company-data.md)
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“ 
- [Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP) 
- [„Azure” žemėlapiai](enrichment-azure-maps.md), kuriuos teikia „Microsoft”
- [Įmonės duomenys](enrichment-dnb.md), kuriuos pateikė Dun & Bradstreet
- ["Microsoft" pateikti abonemento įtraukimo duomenys](enrichment-office.md)

---

Skirtuke **Mano papildymai** galite matyti sukonfigūruotus papildymus ir redaguoti jų ypatybes.

## <a name="manage-existing-enrichments"></a>Esamų papildymų tvarkymas

Eikite į skirtuką **Mano papildymai**, kad pamatytumėte visus sukonfigūruotus papildymus. Kiekvienas papildymas atvaizduotas kaip eilutė su papildoma informacija apie papildymą.

Norėdami peržiūrėti galimas parinktis, pažymėkite papildymą. Taip pat galite pažymėti elipsę (...) sąrašo elemente ir peržiūrėti parinktis. Jei sukonfigūravote kelis papildymus, galite naudoti ieškos lauką, kad greitai juos rastumėte.

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

Objektas, kurį reikia papildyti, nurodomas papildymo konfigūracijoje, o tai jums leidžia papildyti tik antrinį jūsų profilių rinkinį. Pavyzdžiui, duomenis papildyti galima tik konkrečiame segmente. Galite konfigūruoti kelis to paties tipo papildymus ir pakartotinai naudoti tą patį ryšį. Kai kuriems papildymams bus ribojamas to paties tipo sukuriamų papildymų skaičius. Apribojimus ir dabartinį naudojima galima peržiūrėti puslapyje **Papildymas**.

## <a name="enrich-data-sources-before-unification"></a>Duomenų šaltinių praturtinimas prieš suvienijimą

Galite praturtinti savo klientų duomenis prieš duomenų suvienijimą, kad padėtumėte pagerinti duomenų atitikties kokybę. Daugiau informacijos rasite [duomenų šaltinis sodrinimą](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>Žiūrėti papildymo proceso eigą

Galite rasti informacijos apie papildymo apdorojimą, įskaitant jo būseną ir galimas problemas jį atnaujinant arba pasibaigus atnaujinimui. Sužinokite, kurie procesai naudojami norint atnaujinti papildymą ir procesų vykdymo trukmes. Papildymo būseną palaiko „Experian”, „Leadspace”, HERE Technologijos, SFTP Importavimas ir „Azure” žemėlapiai.

Norėdami peržiūrėti papildymo būseną

1. Eikite į **Duomenys** > **Papildymas**. 
1. Skirtuke **Mano papildymai** pažymėkite papildymo būseną, kad atidarytumėte šoninę sritį. 
1. Srityje **Išsami eigos informacija** išplėskite **Papildymų** skyrių. 
1. Po papildymu, kurio progresą norite peržiūrėti, pasirinkite **Žiūrėti išsamią informaciją**. 
1. Srityje **Išsami užduoties informacija** pasirinkite **Rodyti išsamią informaciją**, kad peržiūrėtumėte procesus, kurie susiję su papildymų atnaujinimu ir jų būsena. 

## <a name="enrichment-results"></a>Papildymo rezultatai

Baigę sodrinimo bėgimą, galite peržiūrėti sodrinimo rezultatus.

1. Eikite į **Duomenys** > **Papildymas**. 
1. Pasirinkite sodrinimą, apie kurį norite gauti informacijos.

Visuose sodrinimo įrenginiuose pateikiama pagrindinė informacija, pvz., praturtintų profilių skaičius, sukurto sodrinimo subjekto peržiūra ir praturtintų profilių skaičius laikui bėgant. Jei įmanoma, **lauke** praturtintų klientų skaičius suteikia išsamią informaciją apie kiekvieno praturtinto lauko aprėptį.

:::image type="content" source="media/enrichments-results.png" alt-text="Sodrinimo rezultatų puslapis.":::

Kai kurie sodrinimas taip pat rodo informaciją, būdingą sodrinimo tipui. Daugiau informacijos rasite atitinkamo sodrinimo dokumentuose.


[!INCLUDE [footer-include](includes/footer-banner.md)]
