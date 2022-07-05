---
title: Priemonių apžvalga
description: Sužinokite, kaip priemonės padeda analizuoti ir atspindėti jūsų įmonės našumą.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083125"
---
# <a name="measures-overview"></a>Priemonių apžvalga

Šios priemonės padeda jums geriau suprasti klientų elgesį ir įmonės efektyvumą. Jos peržvelgia atitinkamas vertes iš [vieningųjų profilių](data-unification.md). Pavyzdžiui, įmonė nori, kad *bendras vienam klientui* skirtas išlaidas būtų galima pamatyti norint suprasti kliento pirkimo retrospektyvą arba įvertinti *bendrą įmonės pardavimą* tam, kad būtų galima suprasti agregavimo lygio pajamas visoje įmonėje.  

Priemonės kuriamos [naudojant matų kūrimo priemonę](measure-builder.md), duomenų užklausų platformą su įvairiais operatoriais ir paprastas susiejimo parinktis. Ji leidžia filtruoti duomenis, grupuoti rezultatus, aptikti [objekto ryšio maršrutus](relationships.md), ir peržiūrėti išvestį. Galite [naudoti iš anksto nustatytus šablonus](measure-templates.md), kad efektyviai sukonfigūruotumėte dažniausiai naudojamas priemones.

Naudodami matą, galite planuoti verslo veiklas užklausdami klientų duomenis ir išskleisti įžvalgas. Pavyzdžiui, sukūrus *bendrą vienam klientui išleidus sumą* ir *bendrą grąžą klientui* galima nustatyti klientų grupę, kurios išlaidos yra didelės, bet didelė ir grąža. Galite [sukurti segmentą](segments.md) pagal šias priemones, kad paskatintumėte kitus geriausius veiksmus.

## <a name="manage-your-measures"></a>Matų valdymas

Priemonių sąrašą galima rasti puslapyje **Priemonės**.

Rasite informacijos apie matavimo tipą, kūrėją, kūrimo datą, būseną ir būseną. Kai sąraše pažymite priemonę, galite peržiūrėti išvestį ir atsisiųsti CSV failą.

:::image type="content" source="media/measures-actions.png" alt-text="Atskirų matų valdymo veiksmai."lightbox="media/measures-actions.png":::

Pasirinkus matą, galimi šie veiksmai:

- **Redaguokite** mato konfigūraciją.
- **Dubliuokite** matą. Galite iš karto pasirinkti redaguoti jo ypatybes arba tiesiog įrašyti dublikatą.
- **Atnaujinkite** priemonę pagal naujausius duomenis. Norėdami atnaujinti visas priemones vienu metu, pasirinkite visas priemones ir **atnaujinkite**.
- **Pervardykite** matą.
- **Aktyvuokite** arba **Deaktyvuokite**. Suplanuoto atnaujinimo metu neaktyvūs duomenys nebus [atnaujinti](system.md#schedule-tab).
- **Žymė**, skirta [segmento žymoms](work-with-tags-columns.md#manage-tags) tvarkyti.
- **Panaikinkite** matą.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Tolesnis veiksmas

Galite naudoti esamus priemones klientų [segmentui kurti](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
