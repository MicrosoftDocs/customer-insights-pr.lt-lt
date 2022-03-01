---
title: Robotas „Microsoft Teams“
description: Ieškokite suvienodintų tinkintų profilių „Microsoft Teams“ su roboto pagalba.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406410"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Komandų robotas „Dynamics 365 Customer Insights“ (peržiūra)

Sujunkite su „Microsoft Teams“ norėdami leisti robotui ieškoti suvienodintų klientų profilių „Teams“ kanaluose.

> [!div class="mx-imgBorder"]
> ![„Teams“ roboto rodomas kliento įrašas](media/teams-bot.png "„Teams“ roboto rodomas kliento įrašas")

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint nustatyti ir sukonfigūruoti robotą, turi būti įvykdytos šios būtinosios sąlygos:

- Turi būti [įtrauktas bent vienas duomenų šaltinis](data-sources.md).
- [Sujungimo procesas](data-unification.md) yra baigtas.
- Laukai yra įtraukti į [ieškos ir filtravimo rodyklę](search-filter-index.md).
- „Customer Insights“ ir „Teams“ yra toje pačioje organizacijoje.

## <a name="configure-the-bot"></a>Roboto konfigūravimas

1. Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.
1. Plytelėje „Microsoft Teams“ pasirinkite **Nustatyti**.
1. Būsite nukreiptas į „Teams“ sritį **Programos**. Taip pat galite atidaryti „Teams“ ir apatiniame kairiajame kampe pasirinkti **Programos** arba [jį atsisiųsti tiesiogiai iš „AppSource“](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Ieškokite **„Customer Insights“** ir pasirinkite programą.
1. Pasirinkite **Įtraukti**.
1. Programoje „Teams“ prisijungęs prie „Customer Insights“ matysite pasveikinimo pranešimą ir galėsite pradėti.

## <a name="things-you-can-do-with-the-bot"></a>Ką galite atlikti naudodami robotą

Robotas teikia sujungtų klientų profilių peržvalgos galimybes.

- Įveskite **ieškoti** ir vardą, pavardę, el. pašto adresą arba bet kokį kitą sujungto kliento profilio, kuris yra įtrauktas į ieškos ir filtravimo rodyklę, lauką.

  Matysite kortelę su ne daugiau kaip 15 laukų iš rasto kliento profilio. Esant keliems atitikmenims pateikiamas rezultatų sąrašas, kuriame galite pasirinktį profilį. Norėdami ieškote tikslaus atitikmens galite įvesti ieškos frazę su dvigubomis kabutėmis.

- Jei jūsų organizacija išlaiko daugelį „Customer Insights“ aplinkų toje pačioje organizacijoje, galite įvesti **perjungti elementą** norėdami pasirinkti, kurią aplinką norite sujungti su robotu.

- Įveskite **žinynas**, kad būtų rodomas galimų roboto komandų sąrašas.  
