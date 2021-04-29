---
title: Eksportuoti „Customer Insights“ duomenis į SFTP šeimininkus
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į SFTP vietą.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760429"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a>Segmentų sąrašų ir kitų duomenų eksportavimas į SFTP (peržiūra)

Savo kliento duomenis trečiųjų šalių programose naudokite eksportuodami juos į saugiųjų failų perkėlimo protokolo (SFTP) vietą.

## <a name="prerequisites-for-connection"></a>Būtinosios ryšio sąlygos

- SFTP pagrindinio kompiuterio ir atitinkamų kredencialų pasiekiamumas.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportavimo trukmė priklauso nuo sistemos efektyvumo. Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties. 
- Objektų, kurių klientų profiliai yra iki 100 milijonų, eksportavimas gali užtrukti 90 minučių naudojant rekomenduojamą minimalią dviejų procesorių IR 1 GB atminties konfigūraciją. 

## <a name="set-up-connection-to-sftp"></a>Ryšio su SFTP nustatymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **SFTP**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.

1. Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.

1. Pasirinkite, ar savo duomenis norite eksportuoti kaip **Gzipped** arba **Unzipped**, ir pasirinkite eksportuotų failų **laukelio skyriklį**.

1. Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje SFTP. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pažymėkite objektus, pvz.: segmentus, kuriuos norite eksportuoti.

   > [!NOTE]
   > Eksportavus, kiekvienas pažymėtas objektas padalijamas į penkis išvesties failus. 

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskirties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
