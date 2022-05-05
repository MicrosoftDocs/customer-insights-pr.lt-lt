---
title: "\"Customer Insights\" duomenų eksportavimas į Adobe Experience Platform"
description: Sužinokite, kaip naudoti "Customer Insights" segmentus programoje Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 42a4e0c6bce67a63b449a541299620ef2f4a3259
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643733"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>„Customer Insights“ segmentų naudojimas Adobe Experience Platform (peržiūra)

Kaip, galbūt Dynamics 365 Customer Insights sukūrėte segmentus, kad jūsų rinkodaros kampanijos būtų efektyvesnės taikant atitinkamas auditorijas. Norėdami naudoti segmentą iš "Customer Insights" Adobe Experience Platform ir taikomąsias programas, pvz.Adobe, kampanijos standartą, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.

:::image type="content" source="media/AEP-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a>Būtinosios sąlygos

-   „Dynamics 365 Customer Insights“ licencija
-   „Adobe Experience Platform“ licencija
-   Adobe Campaign Standard licencija
-   „Azure“ didelių dvejetainių objektų saugyklos abonementas

## <a name="campaign-overview"></a>Kampanijos apžvalga

Norėdami geriau suprasti, kaip galite naudoti segmentus iš "Customer Insights", pažvelkime Adobe Experience Platform į fiktyvią pavyzdinę kampaniją.

Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose. Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos. Norėdami išlaikyti šiuos klientus, el. paštu išsiųskite reklaminį pasiūlymą, naudojantis Adobe Experience Platform.

Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą. Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.

## <a name="identify-your-target-audience"></a>Atpažinkite savo tikslinę auditoriją

Pagal mūsų scenarijų darome prielaidą, kad klientų el. pašto adresai yra prieinami "Customer Insights", o jų reklaminės nuostatos buvo išanalizuotos siekiant nustatyti segmento narius.

Segmentas [, kurį apibrėžėte "Customer Insights"](segments.md), vadinamas " **ChurnProneCustomers"**, ir jūs planuojate siųsti šiems klientams el. pašto reklamą.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data. Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.

## <a name="export-your-target-audience"></a>Eksportuokite savo tikslinę auditoriją

Identifikavus tikslinę auditoriją, galime konfigūruoti eksportą iš "Customer Insights" į "Azure Blob Storage" paskyrą.

### <a name="configure-a-connection"></a>Ryšio konfigūravimas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Azure Blob Storage“**, jei norite konfigūruoti ryšį arba pasirinkite **Nustatyti** plytelėje **„Azure Blob Storage“**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Konfigūracijos plytelė, skirta „Azure“ didelių dvejetainių objektų saugyklai."::: 

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite **Paskyros pavadinimas**, **Paskyros raktas** ir **Talpykla** savo „Blob Storage“ laikymo paskyroje, į kurią norite eksportuoti segmentą.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija."::: 
   
    - Jei norite sužinoti daugiau apie didelių dvejetainių objektų „Storage“ paskyros pavadinimą ir paskyros raktą, žr. [Talpyklos paskyros nuostatų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).
    - Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

### <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Azure” didelių dvejetainių objektų saugykla. Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.

1. Pasirinkite segmentą, kurį norite eksportuoti. Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. Pasirinkite **Įrašyti**.

Išsaugoję eksportavimo paskirties vietą ją rasite pasirinkę **Duomenys** > **Eksportavimai**.

Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#run-exports-on-demand). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).

> [!NOTE]
> Įsitikinkite, kad eksportuotame segmente įrašų skaičius ribojamas pagal jūsų "Adobe Campaign Standard" licencijos leistiną ribą.

Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau. Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:

„*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*”

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Eksportuotų objektų *„model.json”* išlieka *„%ExportDestinationName%”* lygiu.

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Patirties duomenų modelio (XDM) apibrėžimas Adobe Experience Platform

Prieš naudodami Adobe Experience Platform eksportuotus duomenis iš "Customer Insights", turime apibrėžti patirties duomenų modelio schemą ir [sukonfigūruoti kliento profilio realiuoju laiku duomenis](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Sužinokite, [kas yra XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ir supraskite [schemos struktūros pagrindus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Duomenų importavimas į „Adobe Experience Platform“

Dabar, kai viskas yra vietoje, turime importuoti paruoštus auditorijos duomenis iš "Customer Insights" į Adobe Experience Platform.

Pirma, [sukurkite „Azure” didelių dvejetainių objektų saugyklos ryšį](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Apibrėžę šaltinio ryšį, konfigūruokite debesies saugyklos paketo ryšio duomenų srautą [,](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) kad importuotumėte segmento išvestį iš "Customer Insights" į Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Sukurkite auditoriją "Adobe Campaign Standard"

Jei norite siųsti šios kampanijos el. laišką, naudosime „Adobe Campaign Standard". Importavus duomenis į Adobe Experience Platform, turime [sukurti auditoriją](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) "Adobe Campaign Standard", naudodami duomenis Adobe Experience Platform.


Sužinokite, kaip [naudoti segmento kurimo įrankį](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) "Adobe Campaign Standard", kad apibrėžtume auditoriją, pagrįstą Adobe Experience Platform duomenimis.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kurti ir siųsti el. laišką naudojant "Adobe Campaign Standard"

Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="El. laiško su atnaujinimo pasiūlymu iš Adobe Campaign Standard&quot; pavyzdys.":::
