---
title: Segmentų eksportavimas į Facebook "Ads Manager" (peržiūra) (yra vaizdo įrašo)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į Facebook „Ads Manager“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724614"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmentų eksportavimas į Facebook "Ads Manager" (peržiūra)

Eksportuokite sujungtų klientų profilių segmentus į „Facebook“ reklamos tvarkytuvą, kad sukurtumėte kampanijas „Facebook“ ir „Instagram“.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Būtinosios sąlygos

- [Facebook Skelbimų paskyros](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), kurioje yra [Facebook verslo paskyra](https://business.facebook.com/).
- "Ads" paskyros administratoriaus [Facebook teisės](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Pasirinktinės auditorijos sąlygos turi būti priimtinos vartotojui, nustatančiam ryšį programoje "Customer Insights".

## <a name="known-limitations"></a>Žinomi apribojimai

- Iki 10 milijonų klientų profilių vienam eksportavimui į Facebook "Ads Manager", o tai gali užtrukti iki 90 minučių.
- Tik segmentai.
- Facebook Skelbimų integravimas nepalaiko naudotojų, turinčių daugiau nei 25 skelbimų paskyras.
- Facebook *Klientų sąrašo* tipas tik pasirinktinėse [auditorijose](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Kai kuriais atvejais išplečiamajame sąraše galite matyti skirtingų tipų pasirinktines auditorijas. Jei pasirinksite kitą tipą nei *klientų sąrašas*, eksportuoti nepavyks.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Ryšio su Facebook „Ads Manager“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Facebook Skelbimų tvarkytuvė**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. [Leisti bendraautoriams naudoti ryšį eksportui](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentifikuoti naudojant Facebook reklamą:

   1. Pasirinkite **Tęsti su Facebook** kad prisiregistruotumėte prie savo „Facebook Ads" paskyros.

   1. Leiskite **reklamos_valdymu** leidimą po autentifikavimo su „Facebook“.

   1. Pasirinkite **„Facebook“ reklamos klientą**, kurį norite naudoti.

   1. Išplečiamajame **sąraše pažymėkite Esamą** pasirinktinę auditoriją arba sukurkite **naują pasirinktinę auditoriją**.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. **Lauke Ryšys eksportavimui** pasirinkite ryšį iš Facebook skilties "Ads Manager". Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. **Lauke Prijungti duomenis** pasirinkite **El. paštas**, Vardas ir adresas **arba** Telefonas **,** kurį norite siųsti Facebook "Ads Manager".

1. Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.
   > [!TIP]
   > Labiausiai tikėtina, kad bus atitikimų, jei pažymėsite rakto identifikatorių **El. paštas**. Įtraukus papildomų identifikatorių, gali pagerėti atitikimų nustatymas.

1. Pasirinkite **Pridėti atributą**, kad žymėtumėte daugiau atributų siuntimui į Facebook „Ads Manager“. Atributai iš Facebook „Ads Manager“ žymimi šiais naudotojams draugiškais pavadinimais: **FN** = **vardas**, **LN** = **pavardė**, **FI** = **vardo inicialas**, **PHONE** = **telefonas**, **GEN** = **lytis**, **DOB** = **gimimo data**, **ST** = **vastija**, **CT** = **miestas**, **ZIP** = **pašto kodas / indeksas**, **COUNTRY** = **šalis / regionas**

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
