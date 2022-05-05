---
title: Duomenų praryti iš Azure Synapse Analytics
description: Naudokite duomenų bazę Azure Synapse kaip duomenų šaltinis programoje Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643345"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Duomenų šaltinis prijungimas Azure Synapse (peržiūra)

Azure Synapse Analytics yra įmonės analizės paslauga, kuri pagreitina laiką iki įžvalgų duomenų sandėliuose ir didelių duomenų sistemose. Azure Synapse Analytics sujungia geriausias SQL technologijas, naudojamas įmonių duomenų sandėliavimui, "Spark" technologijas, naudojamas dideliems duomenims, "Data Explorer" žurnalų ir laiko eilučių analizei, duomenų integravimo ir ETL / ELT vamzdynus ir gilią integraciją su kitomis "Azure" paslaugomis, tokiomis kaip Power BI, ir " Cosmos DB AzureML".

Daugiau informacijos rasite [Azure Synapse apžvalgoje](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti ryšį iš Dynamics 365 Customer Insights Azure Synapse.

> [!IMPORTANT]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

## <a name="prerequisites-in-customer-insights"></a>Būtinosios „Customer Insights“ sąlygos

* "Customer Insights" atlieka **administratoriaus** vaidmenį. Sužinokite daugiau apie [vartotojo teises "Customer Insights"](permissions.md#assign-roles-and-permissions).

„Azure“ tarnyboje: 

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują Azure Data Lake Storage "Gen2" abonementą *, "Customer Insights"* aptarnavimo principui reikia **saugyklos BLOB duomenų teikėjo** teisių. Sužinokite daugiau apie [prisijungimą Azure Data Lake Storage prie "Customer Insights](connect-service-principal.md)" aptarnavimo pagrindinio elemento. „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje Azure Synapse, kurioje yra darbo sritis, *aptarnavimo vadovui* ir *"Customer Insights* " vartotojui turi būti priskirtos bent **skaitytojo** teisės. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- *Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Darbo srityje *"Customer Insights"* aptarnavimo vadovui reikia **priskirti "Synapse" administratoriaus** vaidmenį. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Prisijungimas prie duomenų telkinių duomenų bazių Azure Synapse Analytics

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Azure Synapse Analytics (peržiūros)** metodą.

1. Nurodykite duomenų šaltinio **Pavadinimas** ir pasirinkite **Toliau**, kad sukurtumėte duomenų šaltinį. 

1. [Pasirinkite galimą ryšį arba](connections.md)Azure Synapse Analytics sukurkite naują.

1. **Pasirinkite ežero duomenų bazę** iš darbo srities, prijungtos pasirinktu Azure Synapse Analytics ryšiu, ir pasirinkite **Pirmyn**.

1. Pasirinkite objektus, kuriuos norite nuryti iš prijungtos duomenų bazės. 

1. Pasirinktinai pasirinkite duomenų objektus, kuriuose leidžiamas duomenų profiliavimas. 

1. Pasirinkite **Įrašyti**, kad pritaikytumėte pasirinkimą ir pradėtumėte nuryti duomenis iš naujai sukurto duomenų šaltinis susieto su ežero duomenų bazės lentelėmis Azure Synapse Analytics.
