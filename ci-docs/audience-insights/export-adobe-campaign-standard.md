---
title: „Customer Insights“ duomenų eksportavimas į "Adobe Campaign Standard"
description: Sužinokite, kaip naudoti auditorijų įžvalgų segmentus naudojant "Adobe Campaign Standard".
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d301b4f0cb875303fb3d373b77177acd1c1f5219cd6f23c2a1d29ce67a222eab
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032173"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>„Customer Insights“ segmentų naudojimas „Adobe Campaign Standard“ (peržiūra)

Kaip auditorijos įžvalgų vartotojas, galbūt sukūrėte segmentų, kad rinkodaros kampanijos būtų efektyvesnės „Dynamics 365 Customer Insights“ atsižvelgiant į atitinkamas auditorijas. Norėdami naudoti segmentą iš auditorijos įžvalgų Adobe Experience Platform ir programose kaip "Adobe Campaign Standard", turite atlikti kelis šiame straipsnyje nurodytus veiksmus.

:::image type="content" source="media/ACS-flow.png" alt-text="Apdoroti šiame straipsnyje aprašytų veiksmų diagramą.":::

## <a name="prerequisites"></a>Būtinosios sąlygos

-   „Dynamics 365 Customer Insights“ licencija
-   Adobe Campaign Standard licencija
-   „Azure“ didelių dvejetainių objektų saugyklos abonementas

## <a name="campaign-overview"></a>Kampanijos apžvalga

Norėdami geriau suprasti, kaip galite naudoti segmentus iš auditorijos įžvalgų Adobe Experience Platform, peržiūrėkime išgalvotą kampanijos pavyzdį.

Tarkime, kad jūsų įmonė siūlo mėnesinę, prenumerata pagrįstą paslaugą jūsų klientams Jungtinėse Amerikos Valstijose. Norite nustatyti klientus, kurių prenumeratos turi būti atnaujintos per artimiausias aštuonias dienas, bet jie dar neatnaujino prenumeratos. Norėdami išlaikyti šiuos klientus, el. paštu išsiųskite reklaminį pasiūlymą, naudojantis „Adobe Campaign Standard“.

Šiame pavyzdyje norime reklaminę el. pašto kampaniją įvykdyti vieną kartą. Šiame straipsnyje neaprašomas kampanijos vykdymas daugiau negu vieną kartą. Tačiau auditorijos įžvalgas ir „Adobe Campaign Standard“ galima sukonfigūruoti taip, kad jos veiktų ir naudojant pasikartojantį kampanijos scenarijų.

## <a name="identify-your-target-audience"></a>Atpažinkite savo tikslinę auditoriją

Mūsų scenarijuje darome prielaidą, kad klientų el. pašto adresai yra pasiekiami auditorijos įžvalgose, o jų reklaminės nuostatos buvo analizuojamos siekiant nustatyti segmento narius.

[Segmentas, kurį apibrėžėte auditorijos įžvalgose](segments.md) yra vadinamas **„ChurnProneCustomers”** ir jūs planuojate šiems klientams nusiųsti el. pašto reklamą.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Segmentų puslapio su sukurtu ChurnProneCustomers segmentu ekrano kopija.":::

Pasiūlymo el. laiške, kurį jūs norite išsiųsti, bus vardas, pavardė ir kliento prenumeratos pabaigos data. Jis informuoja klientus apie nuolaidą, kurią jie gaus, jei atnaujins prenumeratą prieš jai pasibaigiant.

## <a name="export-your-target-audience"></a>Eksportuokite savo tikslinę auditoriją

### <a name="configure-a-connection"></a>Ryšio konfigūravimas

Atpažinę mūsų tikslinę auditoriją, galime konfigūruoti eksportavimą iš auditorijos įžvalgų į „Azure“ didelių dvejetainių objektų saugyklos abonementą.

1. Auditorijos įžvalgose eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti jungtis** ir pasirinkite **Adobe Campaign** norint sukonfigūruoti jungtis arba pasirinkite **Sąranką** **Adobe kampanijos** plytelė.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigūracijos plytelė Adobe Campaign Standard.":::

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

1. **Jungtis eksportui** lauke pasirinkite jungtį iš Adobe Campaign skyriaus. Jei šio skyriaus pavadinimo nematote, jums nėra jokių šio tipo ryšių.

1. Pasirinkite segmentą, kurį norite eksportuoti. Šiame pavyzdyje tai yra **„ChurnProneCustomers”**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Segmento pasirinkimo vartotojo sąsajos su pasirinktu ChurnProneCustomers segmentu ekrano kopija.":::

1. Pasirinkite **Toliau**.

1. Dabar išdėstykite **Šaltinių** laukus iš auditorijos įžvalgų segmentų į **Tikslinį** lauko pavadinimą "Adobe Campaign Standard" profilio schemą.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Laukų susiejimas Adobe Campaign Standard jungčiai.":::

   Jeigu norite įtraukti daugiau atributų, pasirinkite **Įtraukti atributą**. Tikslinis pavadinimas gali skirtis nuo šaltinio lauko pavadinimo, kad segmento išvestį nuo auditorijos įžvalgų vis tiek būtų galima susieti su "Adobe Campaign Standard", jei laukai neturi tokio paties pavadinimo abiejose sistemose.

   > [!NOTE]
   > El. pašto adresas naudojamas kaip tapatybės laukas, tačiau galite naudoti bet kurį kitą identifikatorių iš savo auditorijos įžvalgų kliento profilio, kad susiedami duomenis su "Adobe Campaign Standard".

1. Pasirinkite **Įrašyti**.

Išsaugoję eksportavimo paskirties vietą ją rasite pasirinkę **Duomenys** > **Eksportavimai**.

Dabar galite [eksportuoti segmentą pareikalavus](export-destinations.md#run-exports-on-demand). Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md).

> [!NOTE]
> Įsitikinkite, kad eksportuotame segmente įrašų skaičius ribojamas pagal jūsų "Adobe Campaign Standard" licencijos leistiną ribą.

Eksportuoti duomenys saugomi „Azure Blob Storage“ didelių dvejetainių objektų saugyklos talpyklėje, kurią sukonfigūravote aukščiau. Jūsų talpyklėje automatiškai sukuriamas šis aplanko maršrutas:

„*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*”

Pavyzdys: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standard konfigūracija

Kai eksportuojamas segmentas iš auditorijos įžvalgų, jame yra stulpeliai, kuriuos pasirinkote nustatydami eksportavimo paskirties vietą ankstesniame veiksme. Šie duomenys gali būti naudojami [kuriant šablonus Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Kad segmentą būtų galima "Adobe Campaign Standart", reikia išplėsti profilio schemą "Adobe Campaign Standard" ir įtraukti du papildomus laukus. Sužinokite, kaip [išplėsti profilio išteklių](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) naudojant naujus laukus "Adobe Campaign Standard".

Mūsų pavyzdyje šie laukai yra *Segmento pavadinimas ir Segmento data (pasirenkama)*.

Šiuos laukus naudosime nustatyti profilius Adobe Campaign Standard mes siekiame šios kampanijos.

Jei kitų įrašų nėra „Adobe Campaign Standard“, išskyrus tai, ką ketinate importuoti, šį veiksmą galite praleisti.

## <a name="import-data-into-adobe-campaign-standard"></a>Duomenų importavimas į "Adobe Campaign Standard"

Dabar, kai viskas parengta, reikia importuoti paruoštus auditorijos duomenis iš auditorijos įžvalgų į "Adobe Campaign Standard", kad būtų sukurti profiliai. Sužinokite [kaip importuoti profilius į Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) naudojant darbo eigą.

Toliau pateiktame paveikslėlyje importavimo darbo eiga sukonfigūruota taip, kad ji būtų vykdoma kas aštuonias valandas ir ieškoma eksportuotų auditorijos įžvalgų segmentų (.csv failo „Azure Blob Storage"). Darbo eiga išskleidžia .csv failo turinį nustatyta stulpelių tvarka. Ši darbo eiga sukurta siekiant atlikti pagrindinius klaidų apdorojimo veiksmus ir užtikrinti, kad kiekvienas įrašas turi el. pašto adresą prieš įrašant duomenis į "Adobe Campaign Standard". Darbo eiga taip pat iš failo pavadinimo išskleidžia segmento pavadinimą prieš ją perrašant į "Adobe Campaign Standard" profilio duomenis.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Importavimo darbo eigos ekrano kopija Adobe Campaign Standard vartotojo sąsajoje.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Nuskaitykite auditoriją naudodami "Adobe Campaign Standard"

Kai duomenys importuoti į Adobe Campaign Standard, jūs [galite sukurti darbo eigą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ir [užklausą](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) paremtą klientais *Segmento pavadinimas* ir *Segmento data* kad pasirinktumėte profilius, kurie buvo numatyti mūsų pavyzdinei kampanijai.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Kurti ir siųsti el. laišką naudojant "Adobe Campaign Standard"

Sukurkite el. pašto turinį ir tada [išbandykite ir išsiųskite](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) jūsų el. laišką.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="El. laiško su atnaujinimo pasiūlymu iš Adobe Campaign Standard" pavyzdys.":::
