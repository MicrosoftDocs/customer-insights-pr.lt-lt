---
title: "\"Customer Insights\" segmentų eksportavimas į Adobe \"Campaign Standard\" (peržiūra)"
description: Sužinokite, kaip naudoti "Customer Insights" segmentus " Adobe Campaign Standard".
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195530"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>"Customer Insights" segmentų eksportavimas į Adobe "Campaign Standard" (peržiūra)

Eksportuokite segmentus, taikomus pagal atitinkamas auditorijas, į Adobe "Campaign Standard".

:::image type="content" source="media/ACS-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a>Būtinosios sąlygos

- " Adobe Campaign Standard" licencija.
- " [Azure Blob" saugyklos paskyros](/azure/storage/blobs/create-data-lake-storage-account) pavadinimas ir paskyros raktas. Norėdami rasti pavadinimą ir raktą, žiūrėkite ["Azure" portalo saugyklos abonemento parametrų valdymas](/azure/storage/common/storage-account-manage).
- Azure [Blob saugyklos konteineris](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampanijos apžvalga

Jei norite geriau suprasti, kaip galite naudoti segmentus iš "Customer Insights Adobe Experience Platform", pažvelkime į fiktyvią pavyzdinę kampaniją.

Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose. Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos. Norėdami išlaikyti šiuos klientus, el. paštu išsiųskite reklaminį pasiūlymą, naudojantis „Adobe Campaign Standard“.

Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą. Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą. Tačiau "Customer Insights" ir Adobe "Campaign Standard" galima sukonfigūruoti taip, kad veiktų ir pagal pasikartojantį kampanijos scenarijų.

## <a name="identify-your-target-audience"></a>Atpažinkite savo tikslinę auditoriją

Pagal mūsų scenarijų darome prielaidą, kad klientų el. pašto adresai pasiekiami "Customer Insights" ir jų reklaminės nuostatos buvo išanalizuotos siekiant identifikuoti segmento narius.

Segmentas, [kurį apibrėžėte "Customer Insights",](segments.md) vadinamas **"ChurnProneCustomers"** ir planuojate siųsti šiems klientams el. pašto reklamą.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data. Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.

## <a name="export-your-target-audience"></a>Eksportuokite savo tikslinę auditoriją

### <a name="set-up-connection-to-adobe-campaign"></a>Ryšio su Adobe kampanija nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Adobe Kampanija**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Įveskite "Blob Storage" paskyros paskyros pavadinimą**, **abonemento raktą** ir **konteinerį**.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Saugyklos abonemento konfigūracijos ekrano kopija.":::

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

### <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. **Jungtis eksportui** lauke pasirinkite jungtį iš Adobe Campaign skyriaus. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Pasirinkite segmentą, kurį norite eksportuoti. Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. Pasirinkite **Toliau**.

1. Susiekite šaltinio **laukus** iš segmento "Customer Insights" su **paskirties** laukų pavadinimais kampanijų Adobe standartinio profilio schemoje.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Laukų susiejimas Adobe Campaign Standard jungčiai.":::

   Jeigu norite įtraukti daugiau atributų, pasirinkite **Įtraukti atributą**. Paskirties pavadinimas gali skirtis nuo šaltinio lauko pavadinimo, kad vis tiek galėtumėte susieti segmento išvestį iš "Customer Insights" į "Campaign Standard", Adobe jei laukuose dviejose sistemose nėra to paties pavadinimo.

   > [!NOTE]
   > El. pašto adresas naudojamas kaip tapatybės laukas, tačiau galite naudoti bet kurį kitą identifikatorių iš kliento profilio, kad susietumėte duomenis su Adobe "Campaign Standard".

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Įsitikinkite, kad eksportuotame segmente įrašų skaičius ribojamas pagal jūsų "Adobe Campaign Standard" licencijos leistiną ribą.

Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau. Jūsų konteineryje automatiškai sukuriamas šis aplanko kelias: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard konfigūracija

Eksportuotuose segmentuose yra stulpeliai, kuriuos pasirinkote konfigūruodami eksportavimą. Šie duomenys gali būti naudojami [kuriant šablonus Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Jei norite naudoti segmentą "Adobe Campaign Standard", išplėskite "Campaign Standard" profilio [schemą](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing), Adobe kad įtrauktumėte du papildomus laukus.

Mūsų pavyzdyje šie laukai yra segmento pavadinimas ir segmento data. Šiuos laukus naudosime nustatyti profilius Adobe Campaign Standard mes siekiame šios kampanijos.

Jei "Campaign Standard" nėra kitų įrašų Adobe, išskyrus tai, ką ketinate importuoti, praleiskite šį veiksmą.

## <a name="import-data-into-adobe-campaign-standard"></a>Duomenų importavimas į "Adobe Campaign Standard"

Importuokite paruoštus auditorijos duomenis iš "Customer Insights" į Adobe "Campaign Standard", kad sukurtumėte [profilius naudodami darbo eigą](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Importavimo darbo eiga toliau pateiktame paveikslėlyje buvo sukonfigūruota vykdyti kas aštuonias valandas ir ieškoti eksportuotų "Customer Insights" segmentų (.csv failo "Azure Blob" saugykloje). Darbo eiga išskleidžia .csv failo turinį nustatyta stulpelių tvarka. Ši darbo eiga sukurta siekiant atlikti pagrindinius klaidų apdorojimo veiksmus ir užtikrinti, kad kiekvienas įrašas turi el. pašto adresą prieš įrašant duomenis į "Adobe Campaign Standard". Darbo eiga taip pat iš failo pavadinimo išskleidžia segmento pavadinimą prieš ją perrašant į "Adobe Campaign Standard" profilio duomenis.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importavimo darbo eigos ekrano kopija Adobe Campaign Standard vartotojo sąsajoje.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Nuskaitykite auditoriją naudodami "Adobe Campaign Standard"

Importavę duomenis į Adobe "Campaign Standard", [sukurkite darbo eigą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ir [pateikite užklausą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientams pagal segmento pavadinimą ir segmento datą, kad pasirinktumėte profilius, kurie buvo identifikuoti mūsų pavyzdinei kampanijai.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kurti ir siųsti el. laišką naudojant "Adobe Campaign Standard"

Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="El. laiško su atnaujinimo pasiūlymu iš Adobe Campaign Standard&quot; pavyzdys.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
