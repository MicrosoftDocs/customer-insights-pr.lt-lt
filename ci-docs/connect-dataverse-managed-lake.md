---
title: Prisijungimas prie „Microsoft Dataverse“ valdomo duomenų telkinio
description: Duomenų importavimas iš „Microsoft Dataverse“ valdomo duomenų telkinio.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206963"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Prisijungimas prie „Microsoft Dataverse“ valdomo duomenų telkinio

Microsoft Dataverse vartotojai gali greitai prisijungti prie analitinių objektų valdomame Microsoft Dataverse ežere. Tik vienas aplinkos duomenų šaltinis gali vienu metu naudoti tą patį „Dataverse“sutvarkytą ežerą.

> [!NOTE]
> Turite būti organizacijos administratorius, Dataverse kad galėtumėte tęsti ir peržiūrėti valdomo ežero objektų sąrašą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Duomenys, saugomi internetinėse tarnybose, pavyzdžiui, „Azure Data Lake Storage“, gali būti saugomi kitoje vietoje, kurioje duomenys yra apdorojami ar saugomi „Dynamics 365 Customer Insights“.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse paslaugose, jūs sutinkate, kad duomenys gali būti perduodami ir saugomi su Dynamics 365 Customer Insights. [Sužinokite daugiau "Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).

- Matomi tik Dataverse objektai, kurių [keitimų sekimas](/power-platform/admin/enable-change-tracking-control-data-synchronization) įjungtas. Šiuos objektus galima eksportuoti į valdomų duomenų ežerą Dataverse ir naudoti "Customer Insights". Nebenaudojamose Dataverse lentelėse pagal numatytuosius nustatymus įjungtas pakeitimų sekimas. Turite įjungti pasirinktinių lentelių pakeitimų sekimą. Norėdami patikrinti, Dataverse ar lentelėje įgalintas keitimų sekimas, eikite į [Power Apps](https://make.powerapps.com) > **Duomenų** > **lentelės**. Raskite jus dominančią lentelę ir pasirinkite ją. Eikite į **"Settings Advanced"** > **parinktis** ir peržiūrėkite **nustatymą Sekti keitimus**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Prisijungimas prie „Dataverse” valdomojo telkinio

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pažymėkite **Microsoft Dataverse**.

1. **Įveskite duomenų šaltinis pavadinimą** ir pasirinktinį **aprašą**.

1. Nurodykite „Dataverse” organizacijos **Serverio adresą** ir pasirinkite **Prisijungti**.

1. Iš galimų sąrašų pasirinkite lenteles, kurias norite praryti kaip "Customer Insights" objektus.

   > [!NOTE]
   > Jei kai kurios lentelės jau pažymėtos, jas gali naudoti kitos „Dynamics 365” programos (pavyzdžiui, „Dynamics 365 Sales Insights” arba „Customer Service Insights”). Šio pasirinkimo keisti negalima. Šios lentelės bus prieinamos kaip objektai sukūrus duomenų šaltinį.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogo langas, kuriame rodomas Dataverse aplinkos objektų sąrašas.":::

1. Įrašykite savo pasirinkimą, kad pradėtumėte sinchronizuoti pasirinktas lenteles iš „Dataverse”. Puslapyje **Duomenų šaltiniai** rasite naujai pridėtą ryšį. Jis bus atnaujinimo eilėje ir rodys objektų skaičių kaip 0 iki tol, kol bus susinchronizuotos visos pažymėtos lentelės.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Duomenų įkėlimas gali užtrukti. Sėkmingai atnaujinus, nurijusius duomenis galima peržiūrėti puslapyje [**Objektai**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>„Dataverse” valdomojo telkinio duomenų šaltinio redagavimas

Sukūrus duomenų šaltinį galite redaguoti tik objekto pasirinkimą. Pavyzdžiui, jei į „Dataverse“ buvo įtraukti papildomi objektai ir norite importuoti ir juos.
Norėdami prisijungti prie kito „Dataverse data lake”, [sukurkite naują duomenų šaltinį](#connect-to-a-dataverse-managed-lake).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Šalia duomenų šaltinis, kurį norite atnaujinti, pasirinkite **Redaguoti**.

1. Pasirinkite papildomus objektus iš galimų objektų sąrašo.

1. Spustelėkite **Įrašyti**, kad pritaikytumėte pakeitimus ir grįžtumėte į **puslapį Duomenų šaltiniai**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
