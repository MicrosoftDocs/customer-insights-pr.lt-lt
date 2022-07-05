---
title: Duomenų šaltinis prijungimas Azure Synapse (peržiūra)
description: Naudokite duomenų bazę Azure Synapse kaip duomenų šaltinis Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052709"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Duomenų šaltinis prijungimas Azure Synapse Analytics (peržiūra)

Azure Synapse Analytics yra įmonės analizės paslauga, kuri pagreitina laiką iki įžvalgų visose duomenų saugyklose ir didžiųjų duomenų sistemose. Azure Synapse Analytics sujungia geriausias SQL technologijas, naudojamas įmonės duomenų saugykloje, "Spark" technologijas, naudojamas dideliems duomenims, "Data Explorer", skirtą žurnalų ir laiko eilučių analizei, duomenų integravimo vamzdynus ir ETL / ELT bei gilią integraciją su kitomis "Azure" paslaugomis, tokiomis kaip Power BI, Cosmos DB, ir "AzureML".

Daugiau informacijos rasite [Azure Synapse apžvalgoje](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Būtinosios sąlygos

> [!IMPORTANT]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

**Programoje "Customer Insights"**:

* "Customer Insights" turite **administratoriaus** vaidmenį. Sužinokite daugiau apie [vartotojų teises "Customer Insights](permissions.md#assign-roles-and-permissions)".

**Žydroje indų kalba**:

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują Azure Data Lake Storage Gen2 paskyrą, *"Customer Insights* " paslaugų teikėjui reikia **"Blob Data Contributor** " saugyklos teisių. Sužinokite daugiau apie [prisijungimą Azure Data Lake Storage prie "Customer Insights](connect-service-principal.md)" paslaugų teikėjo. „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje, Azure Synapse kurioje yra darbo sritis, *aptarnavimo direktoriui* ir *"Customer Insights" vartotojui turi būti priskirtos bent skaitytojo* **teisės**. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- *Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Darbo srityje *"Customer Insights*" aptarnavimo vadovui reikia **priskirti sinapsės administratoriaus** vaidmenį. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Prisijunkite prie duomenų ežero duomenų bazės Azure Synapse Analytics

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. **Azure Synapse Analytics Pasirinkite (peržiūros)** metodą.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogo langas, skirtas prisijungti prie &quot;Synapse Analytics&quot; duomenų":::
  
1. **Įveskite duomenų šaltinis pavadinimą** ir pasirinktinį **aprašą**.

1. [Pasirinkite galimą ryšį arba](connections.md)Azure Synapse Analytics sukurkite naują.

1. Pasirinkite duomenų bazę **iš** darbo srities, prijungtos pasirinktu Azure Synapse Analytics ryšiu, ir pasirinkite **Pirmyn**. Šiuo metu mes palaikome tik duomenų bazės tipą *Lake duomenų bazė*.

1. Pasirinkite objektus, kuriuos norite nuryti iš prijungtos duomenų bazės, ir pasirinkite **Pirmyn**.

1. Pasirinktinai pasirinkite duomenų objektus, kuriuose leidžiama naudoti duomenų profiliavimą.

1. Pasirinkite **Įrašyti**, kad pritaikytumėte savo pasirinkimą ir pradėtumėte duomenų įsisavinimą iš naujai sukurtų duomenų šaltinis susietų su ežero duomenų bazės lentelėmis Azure Synapse Analytics. Atidaromas **puslapis Duomenų šaltiniai**, kuriame rodoma nauja atnaujinimo būsenos duomenų **šaltinis**.
