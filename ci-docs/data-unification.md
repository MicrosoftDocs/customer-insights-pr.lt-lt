---
title: Vieningo klientų rodinio kūrimas
description: Atlikite duomenų suvienijimo procesą su savo duomenimis, kad sukurtumėte vieną pagrindinį paskyros ar klientų profilių duomenų rinkinį.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304437"
---
# <a name="data-unification-overview"></a>Duomenų suvienodinimo apžvalga

Po to, kai [nustatysite duomenų šaltinius](data-sources.md), galite suvienodinti duomenis. Duomenų suvienijimas leidžia suvienodinti vieną kartą skirtingus duomenų šaltinius į vieną pagrindinį duomenų rinkinį, kuris pateikia vieningą tų duomenų rodinį.

Individualiems vartotojams (nuo B iki C), kur duomenys yra orientuoti į asmenis, suvienijimas suteikia vieningą jūsų klientų vaizdą. Verslo paskyroms (nuo B iki B), kuriose duomenys sutelkti į paskyras, suvienodinimas suteikia vieningą jūsų paskyrų rodinį. [Kontaktų suvienijimas (peržiūra)](data-unification-contacts.md) leidžia tų abonementų kontaktus atskirai suvienodinti ir susieti su abonementais.

Duomenis galima suvienodinti viename objekte arba keliuose objektuose.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Suvienijimo procesas susieja klientų duomenis iš jūsų duomenų šaltinių, pašalina dublikatus, sugretina objektų duomenis ir sukuria vieningą profilį. Suvienijimas atliekamas tokia tvarka:

1. [Šaltinio laukai](map-entities.md) (anksčiau vadinti žemėlapiu): šaltinio laukų veiksme pasirinkite objektus ir laukus, kuriuos norite įtraukti į suvienodinimo procesą. Susiekite laukus su įprastu semantiniu tipu, kuris apibūdina lauko paskirtį.

1. [Besidubliuojantys įrašai](remove-duplicates.md) (ankstesnė atitikties dalis): besidubliuojančiuose įrašuose pasirinktinai apibrėžkite taisykles, kaip pašalinti pasikartojančius kliento įrašus iš kiekvieno objekto.

1. [Atitikimo sąlygos](match-entities.md) (anksčiau vadintos atitiktimi): derinimo sąlygų veiksme apibrėžkite taisykles, kurios atitinka kliento įrašus tarp objektų. Kai klientas randamas dviejuose ar daugiau objektų, sukuriamas vienas konsoliduotas įrašas su visais stulpeliais ir duomenimis iš kiekvieno objekto.

1. [Vieningieji kliento laukai](merge-entities.md) (anksčiau vadinti sulieti): atlikdami vieningųjų klientų laukų veiksmą nustatykite, kurie šaltinio laukai turi būti įtraukti, neįtraukti arba sulieti į vieningą kliento profilį.  

1. [Peržiūrėkite](review-unification.md) ir sukurkite vieningą profilį.

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Suvienijimo procesas susieja paskyros duomenis iš jūsų duomenų šaltinių, pašalina dublikatus, sugretina duomenis visuose objektuose ir sukuria vieningą profilį. Suvienijimas atliekamas tokia tvarka:

1. [Šaltinio laukai](map-entities.md) (anksčiau vadinta Žemėlapiu): šaltinio laukų veiksme pasirinkite objektus ir laukus, kuriuos norite įtraukti į suvienodinimo paskyros procesą. Susiekite laukus su įprastu semantiniu tipu, kuris apibūdina lauko paskirtį.

1. [Besidubliuojantys įrašai](remove-duplicates.md) (ankstesnė atitikties dalis): atlikdami pasikartojančių įrašų veiksmą, pasirinktinai apibrėžkite taisykles, kaip pašalinti pasikartojančius abonemento įrašus iš kiekvieno objekto.

1. [Atitikimo sąlygos](match-entities.md) (anksčiau vadintos atitiktis): derinimo sąlygų veiksme apibrėžkite taisykles, kurios atitinka objektų abonemento įrašus. Kai abonementas randamas dviejuose ar daugiau objektų, sukuriamas vienas konsoliduotas įrašas su visais stulpeliais ir duomenimis iš kiekvieno objekto.

1. [Vieningieji kliento laukai](merge-entities.md) (anksčiau vadinti sulieti): atlikdami vieningųjų klientų laukų veiksmą nustatykite, kurie šaltinio laukai turi būti įtraukti, neįtraukti arba sulieti į vieningą kliento profilį.  

1. [Peržiūrėkite](review-unification.md) ir sukurkite vieningą profilį.

Suvienodinę abonementus, galite pasirinktinai [suvienodinti tų abonementų kontaktus (peržiūra)](data-unification-contacts.md) ir susieti vieningus kontaktus su vieningaisiais abonementais.

---

Baigę duomenų suvienodinimą, galite pasirinktinai:

- [Nustatykite ryšius tarp objektų](relationships.md), kad sukurtumėte sudėtingus segmentus.
- [Praturtinkite savo duomenis](enrichment-hub.md), kad gautumėte daugiau įžvalgų apie klientus.
- [Apibrėžkite veiklą](activities.md) iš kai kurių nurijusių atributų.
- [Kurkite priemones](measures.md), kad geriau suprastumėte klientų elgseną ir verslo našumą.

[!INCLUDE [footer-include](includes/footer-banner.md)]
