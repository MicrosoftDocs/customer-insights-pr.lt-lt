---
title: Duomenų praryti iš Azure Synapse Analytics
description: Naudokite duomenų bazę Azure Synapse kaip duomenų šaltinis programoje Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011437"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Duomenų šaltinis prijungimas Azure Synapse Analytics (peržiūra)

Azure Synapse Analytics yra įmonės analizės paslauga, kuri pagreitina laiką iki įžvalgų duomenų sandėliuose ir didelių duomenų sistemose. Azure Synapse Analytics sujungia geriausias SQL technologijas, naudojamas įmonių duomenų sandėliavimui, "Spark" technologijas, naudojamas dideliems duomenims, "Data Explorer" žurnalų ir laiko eilučių analizei, duomenų integravimo ir ETL / ELT vamzdynus ir gilią integraciją su kitomis "Azure" paslaugomis, tokiomis kaip Power BI, ir " Cosmos DB AzureML".

Daugiau informacijos rasite [Azure Synapse apžvalgoje](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Būtinosios sąlygos

> [!IMPORTANT]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

**"Customer Insights"**:

* "Customer Insights" atlieka **administratoriaus** vaidmenį. Sužinokite daugiau apie [vartotojo teises "Customer Insights"](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują Azure Data Lake Storage "Gen2" abonementą *, "Customer Insights"* aptarnavimo principui reikia **saugyklos BLOB duomenų teikėjo** teisių. Sužinokite daugiau apie [prisijungimą Azure Data Lake Storage prie "Customer Insights](connect-service-principal.md)" aptarnavimo pagrindinio elemento. „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje Azure Synapse, kurioje yra darbo sritis, *aptarnavimo vadovui* ir *"Customer Insights* " vartotojui turi būti priskirtos bent **skaitytojo** teisės. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- *Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Darbo srityje *"Customer Insights"* aptarnavimo vadovui reikia **priskirti "Synapse" administratoriaus** vaidmenį. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Prisijungimas prie duomenų telkinio duomenų bazės Azure Synapse Analytics

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Azure Synapse Analytics (peržiūros)** metodą.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogo langas prisijungti prie &quot;Synapse Analytics&quot; duomenų":::
  
1. Įveskite **duomenų šaltinis pavadinimą** ir pasirinktinį **aprašą**.

1. [Pasirinkite galimą ryšį arba](connections.md)Azure Synapse Analytics sukurkite naują.

1. **Pasirinkite Duomenų bazę** iš darbo srities, prijungtos pasirinktu Azure Synapse Analytics ryšiu, ir pasirinkite **Pirmyn**.

1. Pasirinkite objektus, kuriuos norite nuryti iš prijungtos duomenų bazės, ir pasirinkite **Pirmyn**.

1. Pasirinktinai pasirinkite duomenų objektus, kuriuose leidžiamas duomenų profiliavimas.

1. Pasirinkite **Įrašyti**, kad pritaikytumėte pasirinkimą ir pradėtumėte nuryti duomenis iš naujai sukurto duomenų šaltinis susieto su ežero duomenų bazės lentelėmis Azure Synapse Analytics. Atsidarys **puslapis Duomenų šaltiniai**, kuriame rodoma nauja duomenų šaltinis atnaujinimo **būsenoje**.
