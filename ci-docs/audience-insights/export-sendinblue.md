---
title: „Customer Insights“ duomenų eksportavimas į „Sendinblue“
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Sendinblue“.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036065"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentų eksportavimas į „Sendinblue“ (peržiūra)

Eksportuoti vieningųjų kliento profilių segmentus siekiant kurti kampanijas, teikti rinkodaros el. laiškus ir naudoti konkrečias klientų grupes su „Sendinblue“.

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Sendinblue“ abonementą](https://www.sendinblue.com/) ir atitinkamus administratoriaus kredencialus.
-   „Sendinblue“ yra esamų sąrašų ir atitinkamų ID.
-   Turite [konfigūruoti segmentus](segments.md).
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijonai profilių eksportuojant į „Sendinblue“.
- Eksportavimas į „Sendinblue“ ribojamas segmentais.
- Eksportuojant segmentus, kurių bendra 1 milijonai profilių, gali trukti iki 90 minučių. 
- Profilių, kuriuos galite eksportuoti į „Sendinblue", skaičius priklauso nuo sutarties su „Sendinblue" ir yra apribotas.

## <a name="set-up-connection-to-sendinblue"></a>Nustatyti ryšį su „Sendinblue“

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Sendinblue,** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **[SendinBlue API raktą](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Pasirinkite **Sutinku** patvirtinti duomenų privatumą ir susiskirstyti duomenis ir pasirinkite **Prisijungti**, kad būtų **inicijuotas** ryšys su „Sendinblue".

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „Sendinblue“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo **Sendinblue sąrašo ID** 

1. **Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą. 

1. Arba galite eksportuoti **vardas**, **pavardė** ir **telefonas** sukurtumėte labiau personalizuotus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į „Dynamics 365 Customer Insights“ leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis „Sedinblue“, „Dynamics 365 Customer Insights“, įskaitant galimai jautrius, tokius kaip asmens. „Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Sendinblue“ privatumo arba saugos apsauga. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
