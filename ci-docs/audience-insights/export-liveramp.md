---
title: „LiveRamp“ jungtis
description: Sužinokite kaip eksportuoti duomenis į „LiveRamp“.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597567"
---
# <a name="liverampreg-connector-preview"></a>„LiveRamp&reg;“ jungtis (peržiūra)

Aktyvinkite savo duomenis „LiveRamp“, kad prisijungtumėte prie daugiau nei 500 platformų skaitmeninėse, socialinėse ir TV ekosistemose. Nukreipkite, sustabdykite ir asmeniškai pritaikykite skelbimų kampanijas dirbdami su duomenimis „LiveRamp“.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Norint naudoti šią jungtį reikalinga „LiveRamp“ prenumerata.
- Norėdami gauti prenumeratą, [kreipkitės tiesiogiai į „LiveRamp“](https://liveramp.com/contact/). [Sužinokite daugiau apie „LiveRamp Onboarding“](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Prisijungimas prie „LiveRamp“

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.

1. **„LiveRamp“** plytoje pasirinkite **Nustatyti**.

1. Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.

1. Įveskite savo „LiveRamp“ saugaus FTP (SFTP) kliento **vartotojo vardą** ir **slaptažodį**.
Šie kredencialai gali skirtis nuo jūsų „LiveRamp Onboarding“ kredencialų.

1. Pasirinkite **Tikrinti**, kad patikrintumėte ryšį su „LiveRamp“.

1. Sėkmingą patikrinę pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.

1. Pasirinkite **Toliau**, kad nustatytumėte „LiveRamp“ jungtį.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. Lauke **Pasirinkite pagrindinį identifikatorių** pasirinkite **El. paštas**, **Vardas, pavardė ir adresas** arba **Telefonas**, kad šie duomenys būtų nusiųsti „LiveRamp“ tapatybei nustatyti.

1. Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.

1. Pasirinkite **Įtraukti atributą**, kad susietumėte papildomus atributus, kurie bus siunčiami „LiveRamp“.

   > [!TIP]
   > „LiveRamp“ nusiuntus daugiau pagrindinio identifikatoriaus atributų tikėtina, kad sutapimo dažnis bus aukštesnis.

1. Pasirinkite segmentus, kuriuos norite eksportuoti į „LiveRamp“.

1. Pasirinkite **Įrašyti**.

> [!div class="mx-imgBorder"]
> ![„LiveRamp“ jungtis su atributų susiejimu](media/export-liveramp-segments.png "„LiveRamp“ jungtis su atributų susiejimu")

## <a name="export-the-data"></a>Duomenų eksportavimas

Jei įvykdytos visos būtinosios eksportavimo sąlygos, eksportavimas netrukus bus pradėtas. Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).
Kai eksportavimas sėkmingai baigtas, galite prisijungti prie „LiveRamp Onboarding“, kad suaktyvintumėte savo duomenis ir juos paskirstytumėte.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Liveramp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Liveramp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

[!INCLUDE[footer-include](../includes/footer-banner.md)]