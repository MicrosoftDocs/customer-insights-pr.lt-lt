---
title: Segmentų eksportavimas į „Mailchimp“ (peržiūros versija)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Mailchimp“.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a19c517eeca71a19649e3d07cf47e5d25df6a68
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082474"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmentų eksportavimas į „Mailchimp“ (peržiūros versija)

Eksportuoti suvienodintų kliento profilių segmentus į „Mailchimp“ siekiant sukurti naujienlaiškius ir el. pašto kampanijas.

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

-   Turite [„Mailchimp“ paskyrą](https://mailchimp.com/) ir atitinkančius administratoriaus prisijungimo duomenis.
-   Yra esančių publikų „Mailchimp“ ar atitinkamų ID. Dėl daugiau informacijos, žr. [„Mailchimp“ publikos](https://mailchimp.com/help/create-audience/).
-   Turite [konfigūruoti segmentus](segments.md)
-   Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 1 milijono klientų profilių viename eksportavime į „Mailchimp".
- Eksportavimas į „Mailchimp“ yra apribotas segmentais.
- 1 milijono klientų profilių segmentų eksportavimas gali trukti iki trijų valandų. 
- Klientų profilių, kuriuos galite eksportuoti į „Mailchimp“, skaičius priklauso ir yra apribotas pagal sutartį su „Mailchimp“.

## <a name="set-up-connection-to-mailchimp"></a>Ryšio su „Mailchimp“ nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **„MailChimp“,** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Prisijungti** ir inicijuokite ryšį su „Mailchimp“.

1. Pasirinkite **Autentifikuoti su „Mailchimp“** ir pateikti savo „Mailchimp“ prisijungimo duomenis.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-the-connector"></a>Jungties konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys**> **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Mailchimp“. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Įveskite savo **[„Mailchimp“ auditorijos ID](https://mailchimp.com/help/find-audience-id/)**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. 

1. Taip pat galite eksportuoti **vardą** ir **pavardę**, jei norite sukurti labiau personalizuotus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti. Galite eksportuoti iki 1 milijono kliento profilių bendrai į „Mailchimp“.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Mailchimp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Mailchimp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
