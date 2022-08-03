---
title: Segmentų eksportavimas į Facebook skelbimų tvarkytuvę (peržiūra) (yra vaizdo įrašų)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Facebook „Ads Manager“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195024"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmentų eksportavimas į Facebook skelbimų tvarkytuvę (peržiūra)

Eksportuokite sujungtų klientų profilių segmentus į „Facebook“ reklamos tvarkytuvą, kad sukurtumėte kampanijas „Facebook“ ir „Instagram“.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Būtinosios sąlygos

- Skelbimų [Facebook paskyra](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kurioje yra [Facebook verslo paskyra](https://business.facebook.com/).
- Administratoriaus privilegijos skelbimų [Facebook paskyroje](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 10 milijonų klientų profilių vienam eksportavimui į Facebook "Ads Manager", o tai gali užtrukti iki 90 minučių.
- Tik segmentai.
- Facebook *klientų sąrašas* įveskite [tik pasirinktines auditorijas](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Kai kuriais atvejais išplečiamajame sąraše galite matyti skirtingų tipų tinkintas auditorijas. Jei pasirinksite kitą tipą nei *klientų sąrašas*, eksportuoti nepavyks.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Ryšio su Facebook „Ads Manager“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Facebook Skelbimų tvarkytuvė**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. [Leiskite bendraautoriams naudoti ryšį eksportui](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentifikuoti naudojant Facebook reklamą:

   1. Pasirinkite **Tęsti su Facebook** kad prisiregistruotumėte prie savo „Facebook Ads" paskyros.

   1. Leiskite **reklamos_valdymu** leidimą po autentifikavimo su „Facebook“.

   1. Pasirinkite **„Facebook“ reklamos klientą**, kurį norite naudoti.

   1. Išplečiamajame **sąraše pažymėkite Esamą** pasirinktinę auditoriją arba sukurkite **naują pasirinktinę auditoriją**.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. **Lauke Ryšys eksportui** pasirinkite ryšį iš skyriaus "Skelbimų Facebook tvarkytuvė". Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. **Lauke Susieti duomenis** pasirinkite **El. paštas**, **Vardas ir adresas** arba **Telefonas**, kurį norite siųsti skelbimų tvarkytuvei Facebook.

1. Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.
   > [!TIP]
   > Labiausiai tikėtina, kad bus atitikimų, jei pažymėsite rakto identifikatorių **El. paštas**. Įtraukus papildomų identifikatorių, gali pagerėti atitikimų nustatymas.

1. Pasirinkite **Pridėti atributą**, kad žymėtumėte daugiau atributų siuntimui į Facebook „Ads Manager“. Atributai iš Facebook „Ads Manager“ žymimi šiais naudotojams draugiškais pavadinimais: **FN** = **vardas**, **LN** = **pavardė**, **FI** = **vardo inicialas**, **PHONE** = **telefonas**, **GEN** = **lytis**, **DOB** = **gimimo data**, **ST** = **vastija**, **CT** = **miestas**, **ZIP** = **pašto kodas / indeksas**, **COUNTRY** = **šalis / regionas**

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
