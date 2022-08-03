---
title: Komandų robotas „Dynamics 365 Customer Insights“ (peržiūra)
description: Ieškokite suvienodintų tinkintų profilių „Microsoft Teams“ su roboto pagalba.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195852"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Komandų robotas „Dynamics 365 Customer Insights“ (peržiūra)

Sujunkite su „Microsoft Teams“ norėdami leisti robotui ieškoti suvienodintų klientų profilių „Teams“ kanaluose.

:::image type="content" source="media/teams-bot.png" alt-text="„Teams“ roboto rodomas kliento įrašas":::

## <a name="prerequisites"></a>Būtinosios sąlygos

- Pridėta bent viena [duomenų šaltinis](data-sources.md).
- [Sujungimo procesas](data-unification.md) yra baigtas.
- Laukai įtraukiami į [ieškos ir filtro indeksą](search-filter-index.md).
- „Customer Insights“ ir „Teams“ yra toje pačioje organizacijoje.
- Jūsų aplinkoje pagrindinė tikslinė auditorija nustatyta atskiriems klientams. Verslo klientai nepalaikomi.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Roboto konfigūravimas

1. Eikite į **Administravimas** > **Ryšiai**.
1. Plytelėje „Microsoft Teams“ pasirinkite **Nustatyti**.
1. Būsite nukreiptas į „Teams“ sritį **Programos**. Taip pat galite atidaryti „Teams“ ir apatiniame kairiajame kampe pasirinkti **Programos** arba [jį atsisiųsti tiesiogiai iš „AppSource“](https://go.microsoft.com/fwlink/?linkid=2124104).
1. Ieškokite **„Customer Insights“** ir pasirinkite programą.
1. Pasirinkite **Įtraukti**.
1. Prisijunkite prie "Customer Insights" programoje "Teams". Rodomas pasveikinimo pranešimas.

## <a name="things-you-can-do-with-the-bot"></a>Ką galite atlikti naudodami robotą

Robotas teikia sujungtų klientų profilių peržvalgos galimybes.

- Įveskite **iešką** ir vardą, el. pašto adresą ar bet kurį kitą vieningojo kliento profilio lauką, kuris įtraukiamas į ieškos filtro indeksą.

  Matysite kortelę su ne daugiau kaip 15 laukų iš rasto kliento profilio. Esant keliems atitikmenims pateikiamas rezultatų sąrašas, kuriame galite pasirinktį profilį. Norėdami ieškoti tikslios atitikties, pridėkite paieškos terminą dvigubose kabutėse.

- Jei jūsų organizacija palaiko kelias "Customer Insights" aplinkas toje pačioje organizacijoje, įveskite **"switchinstance"**, kad pasirinktumėte, prie kurios aplinkos norite prijungti robotą.

- Įveskite **žinynas**, kad būtų rodomas galimų roboto komandų sąrašas.  

[!INCLUDE [footer-include](includes/footer-banner.md)]