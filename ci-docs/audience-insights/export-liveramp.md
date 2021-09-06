---
title: „LiveRamp“ jungtis
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „LiveRamp“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7940db3efacad62ba16099849b3e3ca00d2a5cc1ed31e15a34209c0797e6ae13
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035655"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentų eksportavimas į „LiveRamp&reg;“ (peržiūra)

Suaktyvinkite duomenis naudodami „LiveRamp“, kad prisijungtumėte prie daugiau nei 500 skaitmeninių, socialinių ir TV platformų. Nukreipkite, sustabdykite ir asmeniškai pritaikykite skelbimų kampanijas dirbdami su duomenimis „LiveRamp“.

## <a name="prerequisites-for-a-connection"></a>Būtinosios ryšio sąlygos

- Norint naudoti šią jungtį reikalinga „LiveRamp“ prenumerata.
- Norėdami gauti prenumeratą, [kreipkitės tiesiogiai į „LiveRamp“](https://liveramp.com/contact/). [Sužinokite daugiau apie „LiveRamp Onboarding“](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Ryšio su „LiveRamp“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„LiveRamp“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo „LiveRamp“ saugaus FTP (SFTP) kliento **vartotojo vardą** ir **slaptažodį**.
Šie kredencialai gali skirtis nuo jūsų „LiveRamp Onboarding“ kredencialų.

1. Pasirinkite **Tikrinti**, kad patikrintumėte ryšį su „LiveRamp“.

1. Sėkmingą patikrinę pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „LiveRamp“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Lauke **Pasirinkite pagrindinį identifikatorių** pasirinkite **El. paštas**, **Vardas, pavardė ir adresas** arba **Telefonas**, kad šie duomenys būtų nusiųsti „LiveRamp“ tapatybei nustatyti.
   > [!div class="mx-imgBorder"]
   > ![„LiveRamp“ jungtis su atributų susiejimu.](media/export-liveramp-segments.png "„LiveRamp“ jungtis su atributų susiejimu")

1. Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.

1. Pasirinkite **Pridėti atribute**, kad žymėtumėte daugiau atributų siuntimui į „LiveRamp“.

   > [!TIP]
   > „LiveRamp“ nusiuntus daugiau pagrindinio identifikatoriaus atributų tikėtina, kad sutapimo dažnis bus aukštesnis.

1. Pasirinkite segmentus, kuriuos norite eksportuoti į „LiveRamp“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Liveramp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Liveramp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
