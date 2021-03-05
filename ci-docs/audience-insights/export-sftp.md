---
title: Eksportuoti „Customer Insights“ duomenis į SFTP šeimininkus
description: Sužinokite, kaip sukonfigūruoti ryšį su SFTP priegloba.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268008"
---
# <a name="connector-for-sftp-preview"></a>SFTP jungtis (peržiūros versija)

Naudokite savo kliento duomenis trečiosios šalies programose eksportuodami juos į „Secure File Transfer Protocol“ (SFTP) šeimininką.

## <a name="prerequisites"></a>Būtinosios sąlygos

- SFTP pagrindinio kompiuterio ir atitinkamų kredencialų pasiekiamumas.

## <a name="connect-to-sftp"></a>Prisijungti prie SFTP

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Dalyje **SFTP** pažymėkite **Nustatyti**.

1. Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.

1. Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.

1. Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.

1. Po sekmingos patikros pasirinkite, ar norite eksportuoti duomenis **"Gzipped"** ar **"Unzipped"** ir pažymėkite eksportuotų failų laukų **skyriklį**.

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Norėdami pradėti konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-export"></a>Sprendimo konfigūravimas

1. Pažymėkite objektus, pvz.: segmentus, kuriuos norite eksportuoti.

   > [!NOTE]
   > Eksportuojant kiekvienas pažymėtas objektas bus iki penkių išvesties failų. 

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportavimo trukmė priklauso nuo sistemos efektyvumo. Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties. 
- Objektų, kurių klientų profiliai yra iki 100 000, eksportavimas gali užtrukti 90 minučių naudojant rekomenduojamą minimalią dviejų procesorių IR 1 GB atminties konfigūraciją. 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskrties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]