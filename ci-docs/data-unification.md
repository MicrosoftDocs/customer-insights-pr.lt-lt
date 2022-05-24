---
title: Vieningo klientų rodinio kūrimas
description: Eikite per duomenų suvienijimo procesą su savo duomenimis, kad sukurtumėte vieną vieningų klientų profilių duomenų rinkinį.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755744"
---
# <a name="data-unification-overview"></a>Duomenų suvienodinimo apžvalga

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Po to, kai [nustatysite duomenų šaltinius](data-sources.md), galite suvienodinti duomenis. Duomenų suvienijimas leidžia sujungti vieną kartą skirtingus duomenų šaltinius į vieną pagrindinį duomenų rinkinį, kuris suteikia vieningą tų duomenų rodinį. Atskiriems vartotojams (nuo B iki C), kai duomenys yra orientuoti į asmenis, suvienijimas suteikia vieningą jūsų klientų vaizdą. Verslo paskyrose (nuo B iki B), kuriose duomenys yra orientuoti į sąskaitas, suvienijimas suteikia vieningą jūsų paskyrų vaizdą.

Duomenys gali būti suvienodinti viename objekte arba keliuose objektuose. Suvienijimas atliekamas tokia tvarka:

1. [Šaltinio laukai](map-entities.md) (anksčiau vadinami Žemėlapiu): Šaltinio laukų žingsnyje pasirinkite objektus ir laukus, kuriuos norite įtraukti į susivienijimo procesą. Susieti laukus su bendru semantiniu tipu, apibūdinančiu lauko paskirtį.

1. [Įrašų dublikatai](remove-duplicates.md) (ankstesnė gretinimo dalis): atlikdami įrašų dublikatų veiksmą, pasirinktinai apibrėžkite taisykles, kaip pašalinti pasikartojančius kliento įrašus iš kiekvieno objekto.

1. [Gretinimo sąlygos](match-entities.md) (anksčiau vadintos Gretinti): derinimo sąlygų žingsnyje apibrėžkite taisykles, atitinkančias klientų įrašus tarp objektų. Kai klientas randamas dviejuose ar daugiau objektų, sukuriamas vienas konsoliduotas įrašas su visais kiekvieno objekto stulpeliais ir duomenimis.

1. [Vieningi kliento laukai](merge-entities.md) (anksčiau vadinti suliejimu): vieningų klientų laukų žingsnyje nustatykite, kurie šaltinio laukai turėtų būti įtraukti, neįtraukti arba sulieti į vieningą kliento profilį.  

1. [Peržiūrėkite](review-unification.md) ir sukurkite vieningą profilį.

Baigę duomenų suvienijimą, galite pasirinktinai:

- [Nustatyti ryšius tarp objektų](relationships.md), kad būtų sukurti sudėtingi segmentai.
- [Praturtinkite savo duomenis](enrichment-hub.md), kad gautumėte daugiau įžvalgų apie savo klientus.
- [Apibrėžkite veiklas](activities.md) iš kai kurių prarytų atributų.
- [Sukurkite priemones](measures.md), kad geriau suprastumėte klientų elgesį ir verslo rezultatus.

[!INCLUDE [footer-include](includes/footer-banner.md)]
