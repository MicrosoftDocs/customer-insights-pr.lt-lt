---
title: Duomenų eksportavimas į Azure Synapse Analytics (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį su Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259854"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Duomenų eksportavimas į Azure Synapse Analytics (peržiūra)

„Azure Synapse” yra analizės tarnyba, kuri paspartina duomenų sandėlių ir didelių duomenų sistemų įžvalgų atlikimo laiką. Galite įtraukti ir naudoti savo „Customer Insights” duomenis [„Azure Synapse](/azure/synapse-analytics/overview-what-is) tarnyboje.

## <a name="prerequisites"></a>Būtinosios sąlygos

> [!NOTE]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.

- Programoje "Customer Insights" jūsų Azure Active Directory (AD) vartotojo paskyra turi turėti [administratoriaus vaidmenį](permissions.md#add-users).

„Azure“ tarnyboje:

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują Azure Data Lake Storage Gen2 paskyrą, ["Customer Insights" aptarnavimo vykdytojas](connect-service-principal.md) turi **saugyklos "Blob Data Contributor** " teises. „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje, kurioje Azure Synapse yra darbo sritis, tarnybos vykdytojui *ir* *Azure AD vartotojui, turinčiam administratoriaus teises "Customer Insights", turi būti priskirtos bent skaitytojo* **·**[teisės.](/azure/role-based-access-control/role-assignments-portal)

- Vartotojas, *Azure AD turintis administratoriaus teises "Customer Insights",* turi **"Blob Data Contributor** " saugyklos teises "Gen2" paskyroje Azure Data Lake Storage, kurioje yra duomenys ir kuri Azure Synapse yra susieta su darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbo *[Azure Synapse srities valdoma tapatybė](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* turi **saugyklos "Blob Data Contributor"** teises Gen2 paskyroje Azure Data Lake Storage, kurioje yra duomenys ir kuri Azure Synapse yra susieta su darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbo srityje Azure Synapse"Customer Insights" aptarnavimo vykdytojas *turi priskirtą* **"Synapse" administratoriaus**[vaidmenį.](/azure/synapse-analytics/security/how-to-set-up-access-control)

- Jei jūsų "Customer Insights" aplinka saugo duomenis jūsų [Azure Data Lake Storage](own-data-lake-storage.md) pačių, vartotojui, kuris nustato ryšį, Azure Synapse Analytics reikia bent jau įtaisytojo **Skaitytuvo** vaidmens duomenų ežero saugyklos paskyroje. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>Ryšio su Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Azure Synapse Analytics**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Ryšio pavadinimas ir tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pasirinkite arba ieškokite prenumeratos, kurioje norite naudoti „Customer Insights” duomenis. Pasirinkę prenumeratą, taip pat galėsite pasirinkti **Darbo sritis**, **Saugyklos klientas** ir **Talpyklė**.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)] Norėdami konfigūruoti eksportavimą naudodami bendrinamą ryšį, jums reikia bent bendraautorių **teisių** "Customer Insights".

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš sekcijos Azure Synapse Analytics. Jei ryšio nėra, kreipkitės į administratorių.

1. Savo eksportavimui pateikite atpažįstamą **Rodomą pavadinimą** ir **Duomenų bazės pavadinimą**. Eksportas sukurs naują [Azure Synapse ežerų duomenų bazę](/azure/synapse-analytics/database-designer/concepts-lake-database) ryšio apibrėžtoje darbo vietoje.

1. Pasirinkite, į kuriuos objektus norite eksportuoti Azure Synapse Analytics.
   > [!NOTE]
   > Duomenų šaltiniai, pagrįsti [„Common Data Model” aplanku](connect-common-data-model.md) nėra palaikomi.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Jei norite užklausti duomenų, kurie buvo eksportuoti į "Synapse Analytics", jums reikia **"Storage Blob Data Reader"** prieigos prie paskirties saugyklos eksportavimo darbo srityje.

## <a name="update-an-export"></a>Eksportavimo naujinimas

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Redaguoti** norimą atnaujinti redagavimą.

   - **Įtraukite** arba **Pašalinkite** objektus iš pasirinkimo. Jei objektai yra pašalinami iš pasirinkimo, jie nėra panaikinami iš „Synapse Analytics” duomenų bazės. Tačiau būsimi duomenų atnaujinimai nenaujins tos duomenų bazės objektų.

   - **Pakeitus duomenų bazės pavadinimą**, sukuriama nauja „Synapse Analytics” duomenų bazė. Duomenų bazė, kurios pavadinimas buvo sukonfigūruotas prieš tai, ateityje nebus atnaujinta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
