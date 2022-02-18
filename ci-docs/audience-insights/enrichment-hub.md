---
title: Papildykite suvienodintus kliento profilius
description: Naudokite savybes siekiant papildyti jūsų kliento duomenis.
ms.date: 02/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5c3dda3b9bae828857258025ff79958ee22bdb6f
ms.sourcegitcommit: a399bd17523c8d06afd7d78af4fc711f93c0e8be
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/07/2022
ms.locfileid: "8098799"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientų profilių papildymas (peržiūra)

Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis.":::

Publikos įžvalgose eikite į **Duomenys** > **Papildymas** tam, kad dirbtumėte su papildymo parinktimis.  

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

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- [Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft” 
- [Patobulinti įmonės duomenys](enrichment-enhanced-company-data.md), kuriuos pateikė "Microsoft"
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“ 
- [Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP) 
- [„Azure” žemėlapiai](enrichment-azure-maps.md), kuriuos teikia „Microsoft”
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

## <a name="see-the-progress-of-the-enrichment-process"></a>Žiūrėti papildymo proceso eigą

Galite rasti informacijos apie papildymo apdorojimą, įskaitant jo būseną ir galimas problemas jį atnaujinant arba pasibaigus atnaujinimui. Sužinokite, kurie procesai naudojami norint atnaujinti papildymą ir procesų vykdymo trukmes. Papildymo būseną palaiko „Experian”, „Leadspace”, HERE Technologijos, SFTP Importavimas ir „Azure” žemėlapiai.

Norėdami peržiūrėti papildymo būseną

1. Eikite į **Duomenys** > **Papildymas**. 
1. Skirtuke **Mano papildymai** pažymėkite papildymo būseną, kad atidarytumėte šoninę sritį. 
1. Srityje **Išsami eigos informacija** išplėskite **Papildymų** skyrių. 
1. Po papildymu, kurio progresą norite peržiūrėti, pasirinkite **Žiūrėti išsamią informaciją**. 
1. Srityje **Išsami užduoties informacija** pasirinkite **Rodyti išsamią informaciją**, kad peržiūrėtumėte procesus, kurie susiję su papildymų atnaujinimu ir jų būsena. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
