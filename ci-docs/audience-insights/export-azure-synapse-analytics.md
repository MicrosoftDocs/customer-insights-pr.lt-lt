---
title: "\"Customer Insights\" duomenų eksportavimas į Azure Synapse Analytics"
description: Sužinokite, kaip konfigūruoti ryšį su Azure Synapse Analytics.
ms.date: 01/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 289c8d545f057b3f70679b485cf4350545c0587b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231322"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Duomenų eksportavimas į Azure Synapse Analytics (Peržiūra)

„Azure Synapse” yra analizės tarnyba, kuri paspartina duomenų sandėlių ir didelių duomenų sistemų įžvalgų atlikimo laiką. Galite įtraukti ir naudoti savo „Customer Insights” duomenis [„Azure Synapse](/azure/synapse-analytics/overview-what-is) tarnyboje.

## <a name="prerequisites"></a>Būtinosios sąlygos

Turite atitikti toliau pateiktas būtinąsias sąlygas, kad sukonfigūruotumėte ryšį iš „Customer Insights” į „Azure Synapse”.

> [!NOTE]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

## <a name="prerequisites-in-customer-insights"></a>Būtinosios „Customer Insights“ sąlygos

* Auditorijos įžvalgose turite **Administratoriaus** vaidmenį. Sužinokite daugiau apie [vartotojų teisių nustatymą auditorijos įžvalgose](permissions.md#assign-roles-and-permissions)

„Azure“ tarnyboje: 

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują „Azure Data Lake Storage Gen2” klientą, *pagrindinei auditorijos įžvalgų tarnybai* reikalingos **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisės. Sužinokite daugiau skyriuje [prisijungimas prie „Azure Data Lake Storage Gen2” kliento su pagrindine auditorijos įžvalgų „Azure” tarnyba](connect-service-principal.md). „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje, kurioje yra „Azure Synapse” darbo sritis, *pagrindinei tarnybai* ir *auditorijų įžvalgų vartotojui* turi būti priskirtos bent **Skaitytojo** teisės. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- *Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- „Azure Synapse” darbo srityje *pagrindinei auditorijos įžvalgų tarnybai* reikia priskirti **„Synapse” administratoriaus** vaidmenį. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Ryšio nustatymas ir eksportavimas į „Azure Synapse”

### <a name="configure-a-connection"></a>Ryšio konfigūravimas

Norint sukurti ryšį, "Customer Insights" aptarnavimo vadovui ir vartotojo abonementui reikia **reader** teisių *išteklių grupėje*, kurioje yra "Synapse Analytics" darbo sritis. Be to, paslaugos vadovui ir "Synapse Analytics" darbo srities vartotojui reikia **"Synapse Administrator** " teisių. 

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Azure Synapse Analytics** arba pasirinkite **Nustatyti** plytelėje, **Azure Synapse Analytics** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje Rodyti pavadinimą. Ryšio pavadinimas ir tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkite arba ieškokite prenumeratos, kurioje norite naudoti „Customer Insights” duomenis. Pasirinkę prenumeratą, taip pat galėsite pasirinkti **Darbo sritis**, **Saugyklos klientas** ir **Talpyklė**.

1. Pasirinkite **Įrašyti** ryšio įrašymui.

### <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Norėdami konfigūruoti eksportavimą naudojant bendrai naudojamą ryšį, programoje "Customer Insights" reikia bent jau **bendraautorių** teisių. Daugiau informacijos rasite [eksportavimo konfigūravimui reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. **Lauke Ryšys eksportavimui** pasirinkite ryšį iš sekcijos **Azure Synapse Analytics**. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo [ryšių](connections.md).

1. Savo eksportavimui pateikite atpažįstamą **Rodomą pavadinimą** ir **Duomenų bazės pavadinimą**.

1. Pasirinkite, į kuriuos objektus norite eksportuoti Azure Synapse Analytics.
   > [!NOTE]
   > Duomenų šaltiniai, pagrįsti [„Common Data Model” aplanku](connect-common-data-model.md) nėra palaikomi.

2. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).

Norėdami pateikti užklausą duomenims, kurie buvo eksportuoti į "Synapse Analytics", reikia **saugyklos Blob duomenų skaitytuvo** prieigos prie paskirties saugyklos eksporto darbo srityje. 

### <a name="update-an-export"></a>Eksportavimo naujinimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Redaguoti** norimą atnaujinti redagavimą.

   - **Įtraukite** arba **Pašalinkite** objektus iš pasirinkimo. Jei objektai yra pašalinami iš pasirinkimo, jie nėra panaikinami iš „Synapse Analytics” duomenų bazės. Tačiau būsimi duomenų atnaujinimai nenaujins tos duomenų bazės objektų.

   - **Pakeitus duomenų bazės pavadinimą**, sukuriama nauja „Synapse Analytics” duomenų bazė. Duomenų bazė, kurios pavadinimas buvo sukonfigūruotas prieš tai, ateityje nebus atnaujinta.
