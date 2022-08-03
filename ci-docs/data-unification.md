---
title: Duomenų suvienodinimo apžvalga
description: Atlikite duomenų suvienijimo procesą su savo duomenimis, kad sukurtumėte vieną vieningų klientų profilių duomenų rinkinį.
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
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139510"
---
# <a name="data-unification-overview"></a>Duomenų suvienodinimo apžvalga

Po to, kai [nustatysite duomenų šaltinius](data-sources.md), galite suvienodinti duomenis. Duomenų suvienijimas leidžia suvienodinti vieną kartą skirtingus duomenų šaltinius į vieną pagrindinį duomenų rinkinį, kuris pateikia vieningą tų duomenų rodinį. Individualiems vartotojams (nuo B iki C), kur duomenys yra orientuoti į asmenis, suvienijimas suteikia vieningą jūsų klientų vaizdą. Verslo paskyroms (nuo B iki B), kuriose duomenys sutelkti į paskyras, suvienodinimas suteikia vieningą jūsų paskyrų rodinį.

Duomenis galima suvienodinti viename objekte arba keliuose objektuose. Suvienijimas atliekamas tokia tvarka:

1. [Šaltinio laukai](map-entities.md) (anksčiau vadinti žemėlapiu): šaltinio laukų veiksme pasirinkite objektus ir laukus, kuriuos norite įtraukti į suvienodinimo procesą. Susiekite laukus su įprastu semantiniu tipu, kuris apibūdina lauko paskirtį.

1. [Besidubliuojantys įrašai](remove-duplicates.md) (ankstesnė atitikties dalis): besidubliuojančiuose įrašuose pasirinktinai apibrėžkite taisykles, kaip pašalinti pasikartojančius kliento įrašus iš kiekvieno objekto.

1. [Atitikimo sąlygos](match-entities.md) (anksčiau vadintos atitiktimi): derinimo sąlygų veiksme apibrėžkite taisykles, kurios atitinka kliento įrašus tarp objektų. Kai klientas randamas dviejuose ar daugiau objektų, sukuriamas vienas konsoliduotas įrašas su visais stulpeliais ir duomenimis iš kiekvieno objekto.

1. [Vieningieji kliento laukai](merge-entities.md) (anksčiau vadinti sulieti): atlikdami vieningųjų klientų laukų veiksmą nustatykite, kurie šaltinio laukai turi būti įtraukti, neįtraukti arba sulieti į vieningą kliento profilį.  

1. [Peržiūrėkite](review-unification.md) ir sukurkite vieningą profilį.

Baigę duomenų suvienodinimą, galite pasirinktinai:

- [Nustatykite ryšius tarp objektų](relationships.md), kad sukurtumėte sudėtingus segmentus.
- [Praturtinkite savo duomenis](enrichment-hub.md), kad gautumėte daugiau įžvalgų apie klientus.
- [Apibrėžkite veiklą](activities.md) iš kai kurių nurijusių atributų.
- [Kurkite priemones](measures.md), kad geriau suprastumėte klientų elgseną ir verslo našumą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
