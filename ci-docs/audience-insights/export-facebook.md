---
title: Eksportuoti „Customer Insights“ duomenis į „Facebook“ reklamos tvarkytuvą
description: Sužinokite, kaip sukonfigūruoti ryšį su „Facebook“ reklamos tvarkytuvu.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643693"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>„Facebook“ reklamos tvarkytuvo jungtis (peržiūros versija)

Eksportuokite sujungtų klientų profilių segmentus į „Facebook“ reklamos tvarkytuvą, kad sukurtumėte kampanijas „Facebook“ ir „Instagram“.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Jums reikia turėti [**„Facebook“ reklamos paskyrą**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) apimančią [**„Facebook“ verslo paskyrą**](https://business.facebook.com/).
- Jums reikia būti administratoriumi [**„Facebook“ reklamos paskyroje**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Prisijungimas prie „Facebook“ reklamos tvarkytuvo

1. Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.

1. Dalyje **„Facebook“ reklamos tvarkytuvas** pažymėkite **Nustatyti**.

1. Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.

1. Pasirinkite **Tęsti naudojant „Facebook“**, kad prisijungtumėte prie „Facebook“ reklamos kliento.

1. Leiskite **reklamos_valdymu** leidimą po autentifikavimo su „Facebook“.

1. Pasirinkite **„Facebook“ reklamos klientą**, kurį norite naudoti.

1. Išplečiamajame sąraše pasirinkite **Esama pasirinktinė auditorija** arba sukurkite **Nauja pasirinktinė auditorija**. Norėdami gauti daugiau informacijos, žr. [**„Facebook“ reklamos tvarkytuvo auditorijos**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.

1. Norėdami konfigūruoti eksportavimą, pasirinkite **Toliau**.

## <a name="configure-the-connector"></a>Jungties konfigūravimas

1. Lauke **Pasirinkite rakto identifikatorių**, pasirinkite **El. paštas**, **Vardas ir adresas** arba **Telefonas**, siųstiną į „Facebook“ reklamos tvarkytuvą.

1. Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.
   > [PATARIMAS] Labiausiai tikėtina, kad bus atitikimų, jei pažymėsite rakto identifikatorių **El. paštas**. Įtraukus papildomų identifikatorių, gali pagerėti atitikimų nustatymas.

1. Pažymėkite **Įtraukti atributą**, kad susietumėte papildomų atributų, siųstinų į „Facebook“ reklamos tvarkytuvą. „Facebook“ reklamos tvarkytuvo atributai siejami su toliau pateikiamais vartotojui patogiais pavadinimais: **VD** = **Vardas**, **PV** = **Pavardė**, **PR** = **Pirmoji raidė**, **TEL** = **Telefonas**, **LYT** = **Lytis**, **GD** = **Gimimo data**, **VS** = **Valstija**, **MT** = **Miestas**, **IND** = **Pašto indeksas**, **ŠALIS** = **Šalis / regionas**

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

## <a name="export-the-data"></a>Duomenų eksportavimas

Galite [eksportuoti duomenis pareikalavus](export-destinations.md). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ tuomenų perdavimui į „Facebook“ reklamos tvarkytuvą, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights“, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Facebook“ reklamos atitinka visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.
