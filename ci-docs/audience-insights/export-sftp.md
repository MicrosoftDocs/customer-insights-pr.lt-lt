---
title: Eksportuoti „Customer Insights“ duomenis į SFTP šeimininkus
description: Sužinokite, kaip sukonfigūruoti ryšį su SFTP priegloba.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643513"
---
# <a name="connector-for-sftp-preview"></a>SFTP jungtis (peržiūros versija)

Naudokite savo kliento duomenis trečiosios šalies programose eksportuodami juos į „Secure File Transfer Protocol“ (SFTP) šeimininką.

## <a name="prerequisites"></a>Būtinosios sąlygos

- SFTP prieglobos ir atitinkamų kredencialų pasiekiamumas.

## <a name="connect-to-sftp"></a>Prisijungimas prie SFTP

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Dalyje **SFTP** pažymėkite **Nustatyti**.

1. Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.

1. Pateikite **Vartotojo vardą**, **Slaptažodį** ir **Šemininko pavadinimą** jūsų SFTP paskyrai. Pavyzydys: Jei jūsų SFTP serverio šaknies katalogas yra /root/folder ir norėtumėte duomenis eksportuoti į /root/folder/ci_export_destination_folder, šemininkas turėtų būti sftp://<server_address>/ci_export_destination_folder".

1. Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.

1. Sėkmingai patvirtinę, pasirinkite, ar norite eksportuojamus duomenis **Suglaudinti** arba **Išskleisti**, ir pasirinkite eksportuojamų failų **lauko skyriklį**.

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Norėdami pradėti konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connection"></a>Ryšio konfigūravimas

1. Pasirinkite eksportuotinus **kliento atributus**. Galite eksportuoti vieną ar keletą atributų.

1. Pasirinkite **Toliau**.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskrties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
