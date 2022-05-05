---
title: Jungtis prie lentelių „Microsoft Dataverse“
description: Duomenų importavimas iš „Microsoft Dataverse“ valdomo duomenų telkinio.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: e8a294a4bad1581539b5905160cddcd625699d90
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643111"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Prisijungimas prie „Microsoft Dataverse“ valdomo duomenų telkinio

Šiame straipsnyje pateikiama informacija apie tai, kaip Dataverse vartotojai gali greitai prisijungti prie analitinių subjektų valdomame Microsoft Dataverse ežere. 

> [!NOTE]
> Turite būti organizacijos administratorius, Dataverse kad galėtumėte tęsti ir peržiūrėti valdomo ežero objektų sąrašą.

## <a name="important-considerations"></a>Svarbi informacija

1. Duomenys, saugomi internetinėse tarnybose, pavyzdžiui, „Azure Data Lake Storage“, gali būti saugomi kitoje vietoje, kurioje duomenys yra apdorojami ar saugomi „Dynamics 365 Customer Insights“.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse paslaugose, jūs sutinkate, kad duomenys gali būti perduodami ir saugomi su Dynamics 365 Customer Insights. [Sužinokite daugiau "Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).
2. Matomi tik Dataverse objektai, kuriuose [įgalintas keitimų stebėjimas](/power-platform/admin/enable-change-tracking-control-data-synchronization). Šiuos objektus galima eksportuoti į valdomų duomenų ežerą Dataverse ir naudoti "Customer Insights". Pagal numatytuosius nustatymus lentelėse Dataverse yra įgalintas keitimų stebėjimas. Turite įjungti pasirinktinių lentelių keitimų sekimą. Norėdami patikrinti, Dataverse ar lentelė įgalinta keitimų stebėjimui, eikite į [Power Apps](https://make.powerapps.com) > **DataTables** > **·**. Raskite jus dominančią lentelę ir pasirinkite ją. Eikite į **"SettingsAdvanced** > **" parinktis** ir peržiūrėkite parametrą **Sekti keitimus**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Prisijungimas prie „Dataverse” valdomojo telkinio

1. „Customer Insights“ eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite **Įtraukti duomenų šaltinį**.

3. Pasirinkite **Microsoft Dataverse** ir pasirinkite **Pirmyn**.

4. Įveskite duomenų šaltinio **Pavadinimą** ir pasirinkite **Pirmyn**. 

5. Nurodykite „Dataverse” organizacijos **Serverio adresą** ir pasirinkite **Prisijungti**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Duomenų įtraukimo veiksmo ekranas, kuriame vartotojas gali įvesti Dataverse aplinkos URL.":::

6. Iš galimo sąrašo pasirinkite lenteles, kurias norite praryti kaip objektus į "Customer Insights".    

   > [!NOTE]
   > Jei kai kurios lentelės jau pažymėtos, jas gali naudoti kitos „Dynamics 365” programos (pavyzdžiui, „Dynamics 365 Sales Insights” arba „Customer Service Insights”). Šio pasirinkimo keisti negalima. Šios lentelės bus prieinamos kaip objektai sukūrus duomenų šaltinį.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogo langas, kuriame rodomas Dataverse aplinkos objektų sąrašas.":::

7. Įrašykite savo pasirinkimą, kad pradėtumėte sinchronizuoti pasirinktas lenteles iš „Dataverse”. Puslapyje **Duomenų šaltiniai** rasite naujai pridėtą ryšį. Jis bus atnaujinimo eilėje ir rodys objektų skaičių kaip 0 iki tol, kol bus susinchronizuotos visos pažymėtos lentelės.

Tik vienas aplinkos duomenų šaltinis gali vienu metu naudoti tą patį „Dataverse“sutvarkytą ežerą.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>„Dataverse” valdomojo telkinio duomenų šaltinio redagavimas

Sukūrus duomenų šaltinį galite redaguoti tik objekto pasirinkimą. Pavyzdžiui, jei į „Dataverse“ buvo įtraukti papildomi objektai ir norite importuoti ir juos.    
Norėdami prisijungti prie kito „Dataverse data lake”, [sukurkite naują duomenų šaltinį](#connect-to-a-dataverse-managed-lake).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.

3. Sąraše pasirinkite **Redaguoti**.

4. Pažymėkite papildomus objektus iš galimų objektų sąrašo ir pasirinkite **Įrašyti**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
