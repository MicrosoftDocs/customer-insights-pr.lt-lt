---
title: Robotas „Microsoft Teams“
description: Ieškokite suvienodintų tinkintų profilių „Microsoft Teams“ su roboto pagalba.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 6a9575de922bc2ff9c9d2212b99b4c0c8b61ab0e
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967829"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Komandų robotas „Dynamics 365 Customer Insights“ (peržiūra)

Sujunkite su „Microsoft Teams“ norėdami leisti robotui ieškoti suvienodintų klientų profilių „Teams“ kanaluose.

> [!div class="mx-imgBorder"]
> ![„Teams“ roboto rodomas kliento įrašas.](media/teams-bot.png "„Teams“ roboto rodomas kliento įrašas")

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint nustatyti ir sukonfigūruoti robotą, turi būti įvykdytos šios būtinosios sąlygos:

- Turi būti [įtrauktas bent vienas duomenų šaltinis](data-sources.md).
- [Sujungimo procesas](data-unification.md) yra baigtas.
- Laukai yra įtraukti į [ieškos ir filtravimo rodyklę](search-filter-index.md).
- „Customer Insights“ ir „Teams“ yra toje pačioje organizacijoje.
- Jūsų aplinkoje pagrindinė tikslinė auditorija nustatyta atskiriems klientams. Verslo klientai nepalaikomi.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]