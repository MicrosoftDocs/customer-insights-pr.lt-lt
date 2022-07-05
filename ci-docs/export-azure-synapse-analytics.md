---
title: Duomenų eksportavimas į Azure Synapse Analytics (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį su Azure Synapse Analytics.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082873"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Duomenų eksportavimas į Azure Synapse Analytics (peržiūra)

„Azure Synapse” yra analizės tarnyba, kuri paspartina duomenų sandėlių ir didelių duomenų sistemų įžvalgų atlikimo laiką. Galite įtraukti ir naudoti savo „Customer Insights” duomenis [„Azure Synapse](/azure/synapse-analytics/overview-what-is) tarnyboje.

## <a name="prerequisites"></a>Būtinosios sąlygos

Turite atitikti toliau pateiktas būtinąsias sąlygas, kad sukonfigūruotumėte ryšį iš „Customer Insights” į „Azure Synapse”.

> [!NOTE]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

## <a name="prerequisites-in-customer-insights"></a>Būtinosios „Customer Insights“ sąlygos

* Jūsų Azure Active Directory (AD) vartotojo paskyroje yra **administratoriaus** vaidmuo programoje "Customer Insights". Sužinokite daugiau apie [naudotojų teisių nustatymą](permissions.md#assign-roles-and-permissions).

„Azure“ tarnyboje: 

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują Azure Data Lake Storage Gen2 paskyrą, *"Customer Insights* " paslaugų teikėjui reikia **"Blob Data Contributor** " saugyklos teisių. Sužinokite daugiau apie [prisijungimą Azure Data Lake Storage prie Gen2 paskyros naudojant "Azure" paslaugų teikėjo paslaugą, skirtą "Customer Insights](connect-service-principal.md)". „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje, kurioje Azure Synapse yra darbo sritis, tarnybos vykdytojui *ir* *Azure AD vartotojui, turinčiam administratoriaus teises "Customer Insights", turi būti priskirtos bent skaitytojo* **teisės**. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- Vartotojui, *Azure AD turinčiam administratoriaus teises "Customer Insights",* reikia **saugyklos "Blob Data Contributor"** teisių Gen2 paskyroje Azure Data Lake Storage, kurioje yra duomenys ir kuri Azure Synapse yra susieta su darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Darbo srityje *"Customer Insights*" aptarnavimo vadovui reikia **priskirti sinapsės administratoriaus** vaidmenį. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Ryšio nustatymas ir eksportavimas į „Azure Synapse”

### <a name="configure-a-connection"></a>Ryšio konfigūravimas

Norint sukurti ryšį, paslaugų vykdytojui ir "Customer Insights" naudotojo paskyrai reikia **skaitytuvo** teisių *išteklių grupėje*, kurioje yra "Synapse Analytics" darbo sritis. Be to, paslaugos vykdytojui ir "Synapse Analytics" darbo srities naudotojui reikia **"Synapse" administratoriaus** teisių. 

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **Azure Synapse Analytics** arba pasirinkite **Nustatyti** plytelėje, **Azure Synapse Analytics** kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje Rodyti pavadinimą. Ryšio pavadinimas ir tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkite arba ieškokite prenumeratos, kurioje norite naudoti „Customer Insights” duomenis. Pasirinkę prenumeratą, taip pat galėsite pasirinkti **Darbo sritis**, **Saugyklos klientas** ir **Talpyklė**.

1. Pasirinkite **Įrašyti** ryšio įrašymui.

### <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Norėdami konfigūruoti eksportavimą naudodami bendrinamą ryšį, jums reikia bent bendraautorių **teisių** "Customer Insights". Daugiau informacijos rasite [eksportavimo konfigūravimui reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš sekcijos **Azure Synapse Analytics**. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo [ryšių](connections.md).

1. Savo eksportavimui pateikite atpažįstamą **Rodomą pavadinimą** ir **Duomenų bazės pavadinimą**. Eksportas sukurs naują [Azure Synapse ežero duomenų bazę](/azure/synapse-analytics/database-designer/concepts-lake-database) darbo vietoje, apibrėžtoje ryšyje.

1. Pasirinkite, į kuriuos objektus norite eksportuoti Azure Synapse Analytics.
   > [!NOTE]
   > Duomenų šaltiniai, pagrįsti [„Common Data Model” aplanku](connect-common-data-model.md) nėra palaikomi.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).

Jei norite užklausti duomenų, kurie buvo eksportuoti į "Synapse Analytics", jums reikia **"Storage Blob Data Reader"** prieigos prie paskirties saugyklos eksportavimo darbo srityje. 

### <a name="update-an-export"></a>Eksportavimo naujinimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Redaguoti** norimą atnaujinti redagavimą.

   - **Įtraukite** arba **Pašalinkite** objektus iš pasirinkimo. Jei objektai yra pašalinami iš pasirinkimo, jie nėra panaikinami iš „Synapse Analytics” duomenų bazės. Tačiau būsimi duomenų atnaujinimai nenaujins tos duomenų bazės objektų.

   - **Pakeitus duomenų bazės pavadinimą**, sukuriama nauja „Synapse Analytics” duomenų bazė. Duomenų bazė, kurios pavadinimas buvo sukonfigūruotas prieš tai, ateityje nebus atnaujinta.
