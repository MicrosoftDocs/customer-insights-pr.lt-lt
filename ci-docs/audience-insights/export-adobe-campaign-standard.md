---
title: „Customer Insights” duomenų eksportavimas į „Adobe Campaign Standard”
description: Sužinokite, kaip naudoti auditorijos įžvalgų segmentus „Adobe Campaign Standard”.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 917ab9559416f3ee0ffd66e471e590e8da3faffc
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305396"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>„Customer Insights” segmentų naudojimas „Adobe Campaign Standard” (peržiūros versija)

Kaip auditorijos įžvalgų vartotojas, galbūt sukūrėte segmentų, kad rinkodaros kampanijos būtų efektyvesnės „Dynamics 365 Customer Insights“ atsižvelgiant į atitinkamas auditorijas. Norėdami naudoti segmentą iš „Adobe” patirties platformos auditorijos įžvalgų ir programų, pavyzdžiui, „Adobe Campaign Standard”, turite atlikti kelis šiame straipsnyje nurodytus veiksmus.

:::image type="content" source="media/ACS-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a>Būtinosios sąlygos

-   „Dynamics 365 Customer Insights“ licencija
-   „Adobe Campaign Standard“ licencija
-   „Azure“ didelių dvejetainių objektų saugyklos abonementas

## <a name="campaign-overview"></a>Kampanijos apžvalga

Norėdami geriau suprasti, kaip galite naudoti auditorijos įžvalgų segmentus „Adobe” patirties platformoje, pažvelkime į fiktyvią pavyzdinę kampaniją.

Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose. Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos. Siekdami išlaikyti šiuos klientus, norite nusiųsti jiems reklaminį pasiūlymą el. paštu naudojant „Adobe Campaign Standard”.

Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą. Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą. Tačiau auditorijos įžvalgas ir „Adobe Campaign Standard” galima sukonfigūruoti taip, kad veiktų ir pasikartojančios kampanijos scenarijuje.

## <a name="identify-your-target-audience"></a>Atpažinkite savo tikslinę auditoriją

Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.

[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data. Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.

## <a name="export-your-target-audience"></a>Eksportuokite savo tikslinę auditoriją

### <a name="configure-a-connection"></a>Ryšio konfigūravimas

Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.

1. Auditorijos įžvalgose eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Adobe Campaign“**, jei norite konfigūruoti ryšį arba pasirinkite **Sąranka** plytelėje **„Adobe Campaign“**

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigūracijos plytelė, skirta Adobe Campaign Standard.":::

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Įveskite **Paskyros pavadinimas**, **Paskyros raktas** ir **Talpykla** paskyroje „Azure Blob Storage“, į kurią norite eksportuoti segmentą.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija."::: 

   - Jei norite sužinoti daugiau apie tai, kaip rasti „Azure Blob Storage“ didelių dvejetainių objektų saugyklos kliento pavadinimą ir kliento raktą, žr. [Saugyklos kliento parametrų valdymas „Azure“ portale](/azure/storage/common/storage-account-manage).

   - Norėdami sužinoti, kaip sukurti talpyklę, žr. [Talpyklės kūrimas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

### <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Adobe Campaign“. Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.

1. Pasirinkite segmentą, kurį norite eksportuoti. Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. Pasirinkite **Toliau**.

1. Dabar mes susiejame **Šaltinio** laukus iš auditorijos įžvalgų segmento su **Paskirties** laukų pavadinimais „Adobe Campaign Standard” profilio schemoje.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Laukų susiejimas, skirtas Adobe Campaign Standard jungčiai.":::

   Jeigu norite įtraukti daugiau atributų, pasirinkite **Įtraukti atributą**. Paskirties pavadinimas gali skirtis nuo šaltinio lauko pavadinimo, todėl vis tiek galite susieti segmento išvestį iš auditorijos įžvalgų į „Adobe Campaign Standard”, jei laukų pavadinimai dvejuose sistemose nėra tokie patys.

   > [!NOTE]
   > El. pašto adresas naudojamas kaip tapatybės laukas, tačiau galite naudoti bet kurį kitą identifikatorių iš jūsų auditorijos įžvalgų kliento profilio, kad susietumėte duomenis su „Adobe Campaign Standard”.

1. Pasirinkite **Įrašyti**.

Išsaugoję eksportavimo paskirties vietą ją rasite pasirinkę **Duomenys** > **Eksportavimai**.

Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#run-exports-on-demand). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).

> [!NOTE]
> Įsitikinkite, kad eksportuoto segmento įrašų skaičius neviršija leistinos „Adobe Campaign Standard” licencijos ribos.

Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau. Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:

„*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*”

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>„Adobe Campaign Standard“ konfigūravimas

Kai eksportuojamas segmentas iš auditorijos įžvalgų, jame yra stulpeliai, kuriuos pasirinkote nustatydami eksportavimo paskirties vietą ankstesniame veiksme. Šiuos duomenis galima naudoti [kuriant profilius „Adobe Campaign Standard” platformoje](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Norėdami naudoti segmentą „Adobe Campaign Standard” platformoje, turime išplėsti profilio schemą „Adobe Campaign Standard”, kad įtrauktume du papildomus laukus. Sužinokite, kaip [išplėsti profilio išteklius](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) su naujais „Adobe Campaign Standard” laukais.

Mūsų pavyzdyje šie laukai yra *Segmento pavadinimas ir Segmento data (pasirenkama)*.

Šiuos laukus naudosime atpažinti „Adobe Campaign Standard” profiliams, kuriems norime taikyti šią kampaniją.

Jei „Adobe Campaign Standard” nėra kitų įrašų, išskyrus tuos, kuriuos ketinate importuoti, galite praleisti šį veiksmą.

## <a name="import-data-into-adobe-campaign-standard"></a>Duomenų importavimas į „Adobe Campaign Standard”

Dabar, kai viskas tvarkoje, turime importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į „Adobe Campaign Standard” profilių kūrimui. Sužinokite, [kaip importuoti „Adobe Campaign Standard” profilius](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) naudojant darbo eigą.

Toliau pateiktame paveikslėlyje importavimo darbo eiga sukonfigūruota taip, kad ji būtų vykdoma kas aštuonias valandas ir ieškoma eksportuotų auditorijos įžvalgų segmentų (.csv failo „Azure Blob Storage"). Darbo eiga išskleidžia .csv failo turinį nustatyta stulpelių tvarka. Ši darbo eiga buvo sukurta atlikti pagrindiniam klaidų tvarkymui ir užtikrinti, kad kiekvienas įrašas turi el. pašto adresą, prieš drėkinant „Adobe Campaign Standard” duomenis. Darbo eiga taip pat iš failo pavadinimo išskleisti segmento pavadinimą prieš ją perrašant į „Adobe Campaign Standard" profilio duomenis.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importavimo darbo eigos Adobe Campaign Standard vartotojo sąsajoje ekrano kopija.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Auditorijos nuskaitymas „Adobe Campaign Standard” platformoje

Kai duomenys bus importuoti į Adobe „Campaign Standard”, jūs [galėsite sukurti darbo eigą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ir [pateikti užklausą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientams pagal *Segmento pavadinimą* ir *Segmento datą* pasirinkti profiliams, kurie buvo identifikuoti mūsų pavyzdinėje kampanijoje.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>El. laiško sukūrimas ir siuntimas naudojant „Adobe Campaign Standard”

Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Pavyzdinis el. laiškas su atnaujinimo pasiūlymu iš Adobe Campaign Standard.":::
