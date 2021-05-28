---
title: Papildykite suvienodintus kliento profilius
description: Naudokite savybes siekiant papildyti jūsų kliento duomenis.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954497"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Klientų profilių papildymas (peržiūra)

Naudokite duomenis iš tolių šaltinių kaip „Microsoft“ ar kiti partneriai, kad papildytumėte kliento duomenis.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Papildymo telkinio puslapis":::

Publikos įžvalgose eikite į **Duomenys** > **Papildymas** tam, kad dirbtumėte su papildymo parinktimis.    
Norėdami kurti arba redaguoti papildymus, turite turėti dalyvio arba administratoriaus teises. Daugiau informacijos žr. [Teisės](permissions.md).

Skirtuke **Atrasti** rasite šiuos papildymus:

- [Rūšys](enrichment-microsoft.md), kurias teikia „Microsoft“
- [Pomėgiai](enrichment-microsoft.md), kuriuos teikia „Microsoft“
- [Išplėstiniai adresai](enrichment-enhanced-addresses.md), kuriuos teikia „Microsoft”
- [Bendrovės duomenys](enrichment-leadspace.md) pateikti „Leadspace“
- [Demografiniai duomenys](enrichment-experian.md), pateikti „Experian“
- [Vietos duomenys](enrichment-here.md) pateikti „HERE Technologies“
- [Tinkinti duomenys](enrichment-SFTP-custom-import.md) per „Secure File Transfer Protocol“ (SFTP)

Skirtuke **Mano papildymai** galite matyti sukonfigūruotus papildymus ir redaguoti jų ypatybes.

## <a name="manage-existing-enrichments"></a>Esamų papildymų tvarkymas

Eikite į **Mano papildymai**, kad peržiūrėtumėte visus sukonfigūruotus papildymus. Kiekvienas papildymas atvaizduotas kaip eilutė su papildoma informacija apie papildymą.

Pasirinkite papildymą, kad pamatytumėte galimas parinktis. Taip pat galite pažymėti elipsę (...) sąrašo elemente ir peržiūrėti parinktis.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Papildymų tvarkymo parinktys papildymų sąraše":::

- **Peržiūrėkite** papildymo informaciją su papildytų klientų profilių skaičiumi.
- **Redaguokite** papildymo konfigūraciją.
- **Vykdykite** papildymą ir atnaujinkite klientų profilius naujausiais duomenimis.
- **Išjunkite** esamą papildymą, kad jis nebebūtų automatiškai atnaujinamas per kiekvieną suplanuotą atnaujinimą. Paskutinio sėkmingo atnaujinimo duomenys išliks prieinami. **Aktyvinkite** neaktyvų papildymą, jei norite iš naujo paleisti automatinį atnaujinimą su kiekvienu suplanuotu atnaujinimu.
- **Panaikinti** papildymą.

Vienu metu galite vykdyti arba išjungti kelis papildymus pažymėdami juos sąraše. Peržiūros ir redagavimo parinktys nepasiekiamos kaip masiniai veiksmai ir vienu metu veikia tik viename papildyme.

## <a name="enrichments-and-connections"></a>Papildymai ir ryšiai

Trečiosios šalies papildymai konfigūruojami naudojant [ryšius](connections.md), kuriuos administratorius nustato su kredencialais ir pateikia sutikimą duomenims perduoti. Tada administratoriai ir bendradarbiai ryšį gali naudoti papildymams konfigūruoti.  

## <a name="multiple-enrichments-of-the-same-type"></a>Keli to paties tipo papildymai

Objektas, kurį reikia papildyti, nurodomas papildymo konfigūracijoje, o tai jums leidžia papildyti tik antrinį jūsų profilių rinkinį. Pavyzdžiui, duomenų papildymas tik konkrečiam segmentui. Galite konfigūruoti kelis to paties tipo papildymus ir pakartotinai naudoti tą patį ryšį. Kai kuriems papildymams bus ribojamas to paties tipo sukuriamų papildymų skaičius. Apribojimus ir dabartinį naudojima galima peržiūrėti puslapyje **Papildymas**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
