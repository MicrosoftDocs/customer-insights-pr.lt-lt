---
title: Segmentų eksportavimas į Adobe Experience Platform (peržiūra)
description: Sužinokite, kaip naudoti "Customer Insights" segmentus Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195300"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmentų eksportavimas į Adobe Experience Platform (peržiūra)

Segmentų, taikomų pagal atitinkamas auditorijas, eksportavimas į Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a>Būtinosios sąlygos

- Licencija Adobe Experience Platform.
- " Adobe Campaign Standard" licencija.
- " [Azure Blob" saugyklos paskyros](/azure/storage/blobs/create-data-lake-storage-account) pavadinimas ir paskyros raktas. Norėdami rasti pavadinimą ir raktą, žiūrėkite ["Azure" portalo saugyklos abonemento parametrų valdymas](/azure/storage/common/storage-account-manage).
- Azure [Blob saugyklos konteineris](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampanijos apžvalga

Jei norite geriau suprasti, kaip galite naudoti segmentus iš "Customer Insights Adobe Experience Platform", pažvelkime į fiktyvią pavyzdinę kampaniją.

Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose. Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos. Norėdami išlaikyti šiuos klientus, el. paštu išsiųskite reklaminį pasiūlymą, naudojantis Adobe Experience Platform.

Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą. Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.

## <a name="identify-your-target-audience"></a>Atpažinkite savo tikslinę auditoriją

Pagal mūsų scenarijų darome prielaidą, kad klientų el. pašto adresai pasiekiami "Customer Insights" ir jų reklaminės nuostatos buvo išanalizuotos siekiant identifikuoti segmento narius.

Segmentas, [kurį apibrėžėte "Customer Insights",](segments.md) vadinamas **"ChurnProneCustomers"** ir planuojate siųsti šiems klientams el. pašto reklamą.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data. Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.

## <a name="export-your-target-audience"></a>Eksportuokite savo tikslinę auditoriją

Eksportui iš "Customer Insights" sukonfigūruosime į "Azure" didelių dvejetainių objektų saugyklos paskyrą.

### <a name="set-up-connection-to-azure-blob-storage"></a>Ryšio su "Azure Blob Storage" nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **"Azure" didelių dvejetainių objektų saugykla**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite **Paskyros pavadinimas**, **Paskyros raktas** ir **Talpykla** savo „Blob Storage“ laikymo paskyroje, į kurią norite eksportuoti segmentą.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija.":::

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

### <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite segmentą, kurį norite eksportuoti. Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Įsitikinkite, kad eksportuotame segmente įrašų skaičius ribojamas pagal jūsų "Adobe Campaign Standard" licencijos leistiną ribą.

Eksportuoti duomenys saugomi jūsų sukonfigūruotame "Azure" didelių dvejetainių objektų saugyklos konteineryje. Šie aplanko maršrutai automatiškai sukuriami jūsų konteineryje:

- Šaltinio objektams ir objektams sukurtiems sistemos: 

  „*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*”

  Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Eksportuotų objektų *„model.json”* išlieka *„%ExportDestinationName%”* lygiu.

  Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Patirties duomenų modelio (XDM) apibrėžimas Adobe Experience Platform

Prieš eksportuodami duomenis iš "Customer Insights" galite naudoti, Adobe Experience Platform apibrėžkite "Experience Data Model" schemą ir [sukonfigūruokite kliento profilio](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) realiuoju laiku duomenis.

Sužinokite, [kas yra XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ir supraskite [schemos struktūros pagrindus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Duomenų importavimas į „Adobe Experience Platform“

Importuokite paruoštus auditorijos duomenis iš "Customer Insights" į Adobe Experience Platform.

1. [Sukurkite "Azure" didelių dvejetainių objektų saugyklos šaltinio ryšį](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigūruokite debesies saugyklos paketinio ryšio duomenų srautą](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials), kad segmento išvestis iš "Customer Insights" būtų importuota į Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Sukurkite auditoriją "Adobe Campaign Standard"

Jei norite siųsti šios kampanijos el. laišką, naudosime „Adobe Campaign Standard".

1. [Sukurkite auditoriją](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) " Adobe Campaign Standard" naudodami duomenis Adobe Experience Platform.

1. [Naudokite segmentų kūrimo priemonę](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) " Adobe Campaign Standard", kad apibrėžtumėte auditoriją pagal duomenis Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kurti ir siųsti el. laišką naudojant "Adobe Campaign Standard"

Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="El. laiško su atnaujinimo pasiūlymu iš Adobe Campaign Standard&quot; pavyzdys.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
