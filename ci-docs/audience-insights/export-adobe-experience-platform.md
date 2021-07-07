---
title: „Customer Insights” duomenų eksportavimas į „Adobe” patirties platformą
description: Sužinokite, kaip naudoti auditorijų įžvalgų segmentus „Adobe Experience Platform".
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305534"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>„Customer Insights” segmentų naudojimas „Adobe” patirties platformoje (peržiūros versija)

Kaip auditorijos įžvalgų vartotojas, galbūt sukūrėte segmentų, kad rinkodaros kampanijos būtų efektyvesnės „Dynamics 365 Customer Insights“ atsižvelgiant į atitinkamas auditorijas. Norėdami naudoti segmentą iš „Adobe” patirties platformos auditorijos įžvalgų ir programų, pavyzdžiui, „Adobe Campaign Standard”, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.

:::image type="content" source="media/AEP-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a>Būtinosios sąlygos

-   „Dynamics 365 Customer Insights“ licencija
-   „Adobe” patirties platformos licencija
-   „Adobe Campaign Standard“ licencija
-   „Azure“ didelių dvejetainių objektų saugyklos abonementas

## <a name="campaign-overview"></a>Kampanijos apžvalga

Norėdami geriau suprasti, kaip galite naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje, pažvelkime į fiktyvią pavyzdinę kampaniją.

Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose. Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos. Siekdami išlaikyti šiuos klientus, norite nusiųsti jiems reklaminį pasiūlymą el. paštu naudojant „Adobe” patirties platformą.

Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą. Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą.

## <a name="identify-your-target-audience"></a>Atpažinkite savo tikslinę auditoriją

Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.

[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data. Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.

## <a name="export-your-target-audience"></a>Eksportuokite savo tikslinę auditoriją

Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.

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
> Įsitikinkite, kad eksportuoto segmento įrašų skaičius neviršija leistinos „Adobe Campaign Standard” licencijos ribos.

Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau. Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:

„*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*”

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Eksportuotų objektų *„model.json”* išlieka *„%ExportDestinationName%”* lygiu.

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Patirties duomenų modelio (XDM) apibrėžimas „Adobe” patirties platformoje

Prieš naudojant iš auditorijos įžvalgų eksportuotus duomenis „Adobe” patirties platformoje, turime apibrėžti patirties duomenų modelio schemą ir [konfigūruoti kliento profilio duomenis realiuoju laiku](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Sužinokite, [kas yra XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ir supraskite [schemos struktūros pagrindus](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Duomenų importavimas į „Adobe” patirties platformą

Dabar, kai viskas tvarkoje, turime importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į „Adobe” patirties platformą.

Pirma, [sukurkite „Azure” didelių dvejetainių objektų saugyklos ryšį](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Nustatę šaltinio ryšį, [sukonfigūruokite duomenų srautą](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) debesies saugyklos paketinio ryšiui tam, kad importuotumėte segmento išvestį iš auditorijos įžvalgų į „Adobe” patirties platformą.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Auditorijos kūrimas „Adobe Campaign Standard” platformoje

Jei norite siųsti šios kampanijos el. laišką, naudosime „Adobe Campaign Standard". Importavę duomenis į „Adobe” patirties platformą, turime [sukurti auditoriją](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) „Adobe Campaign Standard” platformoje naudodami duomenis iš „Adobe” patirties platformos.


Sužinokite, kaip [naudoti segmentų daryklę](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) „Adobe Campaign Standard” platformoje, kad apibrėžtumėte auditoriją pagal „Adobe” patirties platformos duomenis.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>El. laiško sukūrimas ir siuntimas naudojant „Adobe Campaign Standard”

Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Pavyzdinis el. laiškas su atnaujinimo pasiūlymu iš Adobe Campaign Standard.":::
