---
title: duomenų šaltinis prijungimas Azure Synapse (peržiūra)
description: Naudokite duomenų bazę Azure Synapse kaip duomenų šaltinis Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738166"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>duomenų šaltinis prijungimas Azure Synapse Analytics (peržiūra)

Azure Synapse Analytics yra įmonės analizės paslauga, kuri pagreitina laiką iki įžvalgų įvairiose duomenų saugyklose ir didžiųjų duomenų sistemose. Azure Synapse Analytics sujungia geriausias SQL technologijas, naudojamas įmonės duomenų saugojimui, "Spark" technologijas, naudojamas dideliems duomenims, "Data Explorer", skirtą žurnalų ir laiko eilučių analizei, duomenų integravimo ir ETL / ELT vamzdynus bei gilią integraciją su kitomis "Azure" paslaugomis, tokiomis kaip Power BI, Cosmos DB ir "AzureML".

Daugiau informacijos rasite [Azure Synapse apžvalgoje](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Būtinosios sąlygos

> [!NOTE]
> "Synapse" darbo sritys, kuriose įjungta [užkarda](/azure/synapse-analytics/security/synapse-workspace-ip-firewall), šiuo metu nepalaikomos.
> [!IMPORTANT]
> Įsitikinkite, kad nustatėte visus **vaidmenų priskyrimus**, kaip aprašyta.  

**Klientų įžvalgose**:

* "Customer Insights" turite **administratoriaus** vaidmenį. Sužinokite daugiau apie [naudotojų teises "Customer Insights](permissions.md#add-users)".

**Žydroje spalva**:

- Aktyvi „Azure“ prenumerata.

- Jei naudojate naują Azure Data Lake Storage "Gen2" paskyrą, "Customer Insights" aptarnavimo vadovui, *kuris yra "Dynamics 365 AI for Customer Insights* ", reikia **didelių dvejetainių objektų saugyklos duomenų bendradarbio** teisių. Sužinokite daugiau apie [prisijungimą prie Azure Data Lake Storage "Customer Insights](connect-service-principal.md)" aptarnavimo pagrindinio teikėjo. „Data Lake Storage Gen2“ **privalo turėti** įjungtą [hierarchinę vardų sritį](/azure/storage/blobs/data-lake-storage-namespace).

- Išteklių grupėje, kurioje Azure Synapse yra darbo sritis, aptarnavimo pagrindiniam klientui *,* kuris yra "Dynamics 365 AI for Customer Insights", ir *"Customer Insights*" vartotojui turi būti priskirtos bent skaitytojo **teisės**. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

- *Vartotojui* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau apie [„Azure” portalo naudojimą „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teises](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[„Azure Synapse” darbo srities valdomajai tapatybei](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* reikia **Didelių dvejetainių objektų duomenų saugyklos bendraautoriaus** teisių „Azure Data Lake Storage Gen2” kliente, kuriame duomenys yra patalpinti ir susieti su „Azure Synapse” darbo sritimi. Sužinokite daugiau [„Azure” portalo naudojimas „Azure” vaidmens priskyrimui, kad būtų galima pasiekti didelį dvejetainį objektą ir duomenų eilę](/azure/storage/common/storage-auth-aad-rbac-portal) ir [Didelių dvejetainių objektų saugyklos bendraautoriaus teisės](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Darbo Azure Synapse srityje "Customer Insights" aptarnavimo vadovui, *kuris yra "Dynamics 365 AI for Customer Insights* ", turi būti priskirtas "Synapse" **administratoriaus** vaidmuo. Vartotojui **reikia** bent "**Synapse Contributor**" vaidmens, priskirto darbo sričiai. Daugiau informacijos rasite [Kaip nustatyti prieigos valdiklį savo „Synapse” darbo sričiai](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Jei jūsų "Customer Insights" aplinka saugo duomenis jūsų [pačių Azure Data Lake Storage](own-data-lake-storage.md), vartotojui, kuris nustato ryšį Azure Synapse Analytics, reikia bent jau įtaisytojo skaitytojo **vaidmens** "Data Lake Storage" paskyroje. Daugiau informacijos rasite [„Azure” vaidmenų priskyrimas naudojant „Azure” portalą](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Prisijunkite prie "data lake" duomenų bazės Azure Synapse Analytics

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Azure Synapse Analytics (peržiūros)** metodą.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialogo langas, skirtas prisijungti prie &quot;Synapse Analytics&quot; duomenų":::
  
1. Įveskite **duomenų šaltinis pavadinimą** ir pasirinktinį **aprašą**.

1. Pasirinkite [galimą ryšį](connections.md) Azure Synapse Analytics arba [sukurkite naują](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Pasirinkite **Duomenų bazę iš darbo srities, prijungtos pasirinktu** ryšiu, ir pasirinkite Azure Synapse Analytics Pirmyn **·**. Šiuo metu palaikome tik duomenų bazės tipo *Lake duomenų bazę*.

1. Pasirinkite objektus, kuriuos norite nuryti iš prijungtos duomenų bazės, ir pasirinkite **Pirmyn**.

1. Pasirinktinai pasirinkite duomenų objektus, kuriuose leidžiamas duomenų profiliavimas.

1. Pasirinkite **Įrašyti, kad pritaikytumėte savo pasirinkimą ir pradėtumėte nuryti** duomenis iš naujai sukurtos duomenų šaltinis, susietos su ežero duomenų bazės lentelėmis Azure Synapse Analytics. Atidaromas **puslapis Duomenų šaltiniai**, rodantis naują duomenų šaltinis dalyje **Atnaujinimo** būsena.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, nurijusius duomenis galima peržiūrėti [**puslapyje Objektai**](entities.md) .

[!INCLUDE [footer-include](includes/footer-banner.md)]
