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
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170831"
---
# <a name="measures-overview"></a>Priemonių apžvalga

Šios priemonės padeda jums geriau suprasti klientų elgesį ir įmonės efektyvumą. Jos peržvelgia atitinkamas vertes iš [vieningųjų profilių](data-unification.md). Pavyzdžiui, įmonė nori, kad *bendras vienam klientui* skirtas išlaidas būtų galima pamatyti norint suprasti kliento pirkimo retrospektyvą arba įvertinti *bendrą įmonės pardavimą* tam, kad būtų galima suprasti agregavimo lygio pajamas visoje įmonėje.

Kurkite priemones, kaip planuoti verslo veiklą, pateikdami užklausas klientų duomenims ir gaudami įžvalgas. Pavyzdžiui, sukurkite bendrų išlaidų vienam klientui ir *bendros grąžos vienam klientui* *matą*, kad padėtumėte nustatyti grupę klientų, kurių išlaidos yra didelės, tačiau didelė grąža. Tada sukurkite segmentą [pagal šias priemones,](segments.md) kad paskatintumėte kitus geriausius veiksmus.

## <a name="create-a-measure"></a>Sukurti matą

Pasirinkite, kaip sukurti priemonę pagal tikslinę auditoriją.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- Nuo nulio su matų kūrimo priemone: [sukurkite savo](measure-builder.md).
- Iš dažniausiai naudojamų matų: [naudokite iš anksto nustatytus šablonus](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Nuo nulio su matų kūrimo priemone: [sukurkite savo](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Valdykite esamas priemones

Eikite **į puslapį Priemonės**, kad peržiūrėtumėte sukurtas priemones, jų būseną, priemonės tipą ir paskutinį kartą, kai duomenys buvo atnaujinti. Galite rūšiuoti priemonių sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte norimą tvarkyti priemonę.

Pasirinkite šalia priemonės, kad peržiūrėtumėte galimus veiksmus. Pasirinkite priemonės pavadinimą, kad peržiūrėtumėte išvestį ir atsisiųstumėte CSV failą.

:::image type="content" source="media/measures-actions.png" alt-text="Atskirų matų valdymo veiksmai."lightbox="media/measures-actions.png":::

- **Redaguokite** priemonę, kad pakeistumėte jos ypatybes.
- **Atnaujinkite** priemonę, kad įtrauktumėte naujausius duomenis.
- **Pervardykite** matą.
- **Suaktyvinkite** arba **išjunkite** priemonę. Neaktyvios priemonės nebus atnaujintos per suplanuotą [atnaujinimą](system.md#schedule-tab), o **būsena** bus nurodyta kaip **Praleista**, o tai reiškia, kad atnaujinti net nebuvo bandyta.
- **Pažymėkite**, kad [galėtumėte tvarkyti priemonės žymas](work-with-tags-columns.md#manage-tags).
- **Panaikinkite** matą.
- **Stulpeliai**, skirti [tinkinti rodomus stulpelius](work-with-tags-columns.md#customize-columns).
- **Filtruokite**, kad filtruotumėte [žymes](work-with-tags-columns.md#filter-on-tags).
- **Ieškokite vardo**, kad galėtumėte ieškoti pagal matinį pavadinimą.

## <a name="refresh-measures"></a>Atnaujinkite priemones

Priemonės gali būti atnaujinamos automatiniu grafiku arba atnaujinamos rankiniu būdu pagal poreikį. Norėdami rankiniu būdu atnaujinti vieną ar daugiau priemonių, pažymėkite jas ir pasirinkite **Atnaujinti**. Norėdami [suplanuoti automatinį atnaujinimą](system.md#schedule-tab), eikite į **Administratoriaus** > **sistemos** > **tvarkaraštis**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
