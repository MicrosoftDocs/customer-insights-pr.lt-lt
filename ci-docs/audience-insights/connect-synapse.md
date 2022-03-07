---
title: 3. išskųsti duomenys iš Azure Synapse Analytics
description: Naudokite duomenų bazę Azure Synapse kaip duomenų šaltinis Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356050"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Duomenų šaltinis prijungimas Azure Synapse (peržiūra)

Azure Synapse Analytics tai įmonės analizės paslauga, kuri pagreitina laiką įžvalgoms duomenų sandėliuose ir didelių duomenų sistemose. Azure Synapse Analytics sujungia geriausias SQL technologijas, naudojamas įmonių duomenų sandėliavimui, "Spark" technologijas, naudojamas dideliems duomenims, "Data Explorer" žurnalų ir laiko sekų analizei, duomenų integravimo vamzdynus ir ETL / ELT bei gilią integraciją su kitomis "Azure" paslaugomis, pvz Power BI., Cosmos DB ir "AzureML".

Daugiau informacijos ieškokite [Azure Synapse overview](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Būtinosios sąlygos

Turite atitikti toliau pateiktas būtinąsias sąlygas, kad sukonfigūruotumėte ryšį iš „Customer Insights” į „Azure Synapse”.

> [!IMPORTANT]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

## <a name="prerequisites-in-customer-insights"></a>Būtinosios „Customer Insights“ sąlygos

* "Customer Insights **" turite administratoriaus** vaidmenį. Sužinokite daugiau apie [vartotojų teises auditorijos įžvalgose](permissions.md#assign-roles-and-permissions).

„Azure“ tarnyboje: 

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują „Azure Data Lake Storage Gen2” klientą, *pagrindinei auditorijos įžvalgų tarnybai* reikalingos **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisės. Sužinokite daugiau apie [prisijungimą Azure Data Lake Storage prie paslaugos vadovo auditorijos įžvalgoms](connect-service-principal.md). „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje, kurioje yra „Azure Synapse” darbo sritis, *pagrindinei tarnybai* ir *auditorijų įžvalgų vartotojui* turi būti priskirtos bent **Skaitytojo** teisės. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- *Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- „Azure Synapse” darbo srityje *pagrindinei auditorijos įžvalgų tarnybai* reikia priskirti **„Synapse” administratoriaus** vaidmenį. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Prisijungimas prie duomenų ežerų duomenų bazių Azure Synapse Analytics

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Azure Synapse Analytics (peržiūros)** metodą.

1. Nurodykite duomenų šaltinio **Pavadinimas** ir pasirinkite **Toliau**, kad sukurtumėte duomenų šaltinį. 

1. Pasirinkite galimas [ryšys](connections.md)Azure Synapse Analytics arba sukurti naują.

1. **Pasirinkite ežero duomenų bazę** iš pasirinkto ryšio darbo srities ir pasirinkite Azure Synapse Analytics **Pirmyn**.

1. Pasirinkite objektus, kurie bus nuryti iš prijungtos duomenų bazės. 

1. Pasirinktinai pasirinkite duomenų objektus, kad būtų galima profiliuoti duomenis. 

1. Pasirinkite **Įrašyti**, kad pritaikytumėte savo pasirinkimą ir pradėtumėte duomenų nurijimas iš naujai sukurtų duomenų šaltinis susietų su ežero duomenų bazės lentelėmis .Azure Synapse Analytics
