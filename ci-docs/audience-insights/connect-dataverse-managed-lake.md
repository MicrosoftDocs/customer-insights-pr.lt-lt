---
title: Jungtis prie lentelių „Microsoft Dataverse“
description: Duomenų importavimas iš „Microsoft Dataverse“ valdomo duomenų telkinio.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692584"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Prisijungimas prie „Microsoft Dataverse“ valdomo duomenų telkinio

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Šiame straipsnyje pateikiama informacija apie tai, kaip „Dataverse” vartotojai gali greitai prisijungti prie savo analizės objektų „Dataverse” valdomame telkinyje. Norėdami tęsti ir peržiūrėti valdomo duomenų telkinio objektų sąrašą, turite būti „Dataverse“ organizacijos administratorius.

## <a name="important-considerations"></a>Svarbi informacija

Duomenys, saugomi internetinėse tarnybose, pavyzdžiui, „Azure Data Lake Storage“, gali būti saugomi kitoje vietoje, kurioje duomenys yra apdorojami ar saugomi „Dynamics 365 Customer Insights“. Importuodami arba prisijungdami prie duomenų, saugomų internetinėse tarnybose, sutinkate, kad duomenys gali būti perkeliami ir saugomi „Dynamics 365 Customer Insights“.  [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Prisijungimas prie „Dataverse” valdomojo telkinio

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite **Įtraukti duomenų šaltinį**.

3. Pasirinkite **Prisijungti prie „Microsoft Dataverse” valdomo telkinio** ir **Kitas**.

4. Įveskite duomenų šaltinio **Pavadinimą** ir pasirinkite **Pirmyn**. Pavadinimų rekomendacijos: 
   - Pradėti nuo raidės.
   - Naudokite tik raides ir skaičius. Specialiųjų simbolių ir tarpų neleidžiama įvesti.
   - Naudokite nuo 3 iki 64 simbolių.

5. Nurodykite „Dataverse” organizacijos **Serverio adresą** ir pasirinkite **Prisijungti**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Duomenų įtraukimo veiksmo ekranas, kuriame vartotojas gali įvesti Dataverse aplinkos URL.":::

6. Iš galimo sąrašo pasirinkite lenteles, kurias norite įtraukti į auditorijos įžvalgas kaip objektus.    

   > [!NOTE]
   > Jei kai kurios lentelės jau pažymėtos, jas gali naudoti kitos „Dynamics 365” programos (pavyzdžiui, „Dynamics 365 Sales Insights” arba „Customer Service Insights”). Šio pasirinkimo keisti negalima. Šios lentelės bus prieinamos kaip objektai sukūrus duomenų šaltinį.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialogo langas, kuriame rodomas Dataverse aplinkos objektų sąrašas.":::

7. Įrašykite savo pasirinkimą, kad pradėtumėte sinchronizuoti pasirinktas lenteles iš „Dataverse”. Puslapyje **Duomenų šaltiniai** rasite naujai pridėtą ryšį. Jis bus atnaujinimo eilėje ir rodys objektų skaičių kaip 0 iki tol, kol bus susinchronizuotos visos pažymėtos lentelės.

Tik vienas aplinkos duomenų šaltinis gali vienu metu naudoti tą patį „Dataverse“sutvarkytą ežerą.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>„Dataverse” valdomojo telkinio duomenų šaltinio redagavimas

Sukūrus duomenų šaltinį galite redaguoti tik objekto pasirinkimą. Pavyzdžiui, jei į „Dataverse“ buvo įtraukti papildomi objektai ir norite importuoti ir juos.    
Norėdami prisijungti prie kito „Dataverse data lake”, [sukurkite naują duomenų šaltinį](#connect-to-a-dataverse-managed-lake).

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.

3. Sąraše pasirinkite **Redaguoti**.

4. Pažymėkite papildomus objektus iš galimų objektų sąrašo ir pasirinkite **Įrašyti**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]