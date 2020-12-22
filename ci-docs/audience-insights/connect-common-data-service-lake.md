---
title: Prisijungti prie objektų „Common Data Service“ valdomame ežere
description: Duomenų importavimas iš „Common Data Service“ valdomo „Data Lake“.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643408"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Prisijungimas prie „Common Data Service“ valdomo „Data Lake“ duomenų

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Šiame straipsnyje pateikiama informacija apie tai, kaip esami „Dynamics 365“ klientai gali greitai prisijungti prie analitinių objektų „Common Data Service“ valdomame „Data Lake“. Norėdami tęsti ir peržiūrėti valdomo „Data Lake“ objektų sąrašą, turite būti „Common Data Service“ organizacijos administratorius.

## <a name="important-considerations"></a>Svarbi informacija

Duomenys, saugomi internetinėse tarnybose, pavyzdžiui, „Azure Data Lake Storage“, gali būti saugomi kitoje vietoje, kurioje duomenys yra apdorojami ar saugomi „Dynamics 365 Customer Insights“.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse tarnybose, sutinkate, kad duomenys gali būti perkeliami ir saugomi „Dynamics 365 Customer Insights“.  [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Prisijungimas prie „Common Data Service” valdomojo telkinio

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Pasirinkite **Įtraukti duomenų šaltinį**.

3. Pasirinkite **Prisijungti prie „Common Data Service”** ir pasirinkite **Pirmyn**.

4. Įveskite duomenų šaltinio **Pavadinimą** ir pasirinkite **Pirmyn**.

5. Nurodykite **Serverio adresas**, skirtą jūsų „Common Data Service” organizacijai, ir pasirinkite **Prisijungti**.

   > [!div class="mx-imgBorder"]
   > ![Dialogo langas įvesti „Common Data Service” serverio adresą](media/enter-CDS-org-details.png)

6. Pasirinkite objektus, kuriuos norite suvartoti iš esančio sąrašo.    

   > [!NOTE]
   > Jei kai kurie objektai jau pažymėti, jie gali būti naudojami kitose „Dynamics 365” programose (pvz., „Dynamics 365 Sales Insights” arba „Customer Service Insights”). Šio pasirinkimo keisti negalima. Šie objektai bus pasiekiami sukūrus duomenų šaltinį.

   > [!div class="mx-imgBorder"]
   > ![Dialogo langas, kuriame yra „Common Data Service” organizacijos objektų sąrašas](media/select-analytical-entities.png)

7. Įrašykite savo pasirinkimą, kad pradėtumėte sinchronizuoti pažymėtus objektus su „Common Data Service” valdomuoju telkiniu. Puslapyje **Duomenų šaltiniai** rasite naujai pridėtą ryšį. Jis bus eilėje atnaujinti ir rodyti objektus, turinčius skaičių 0, kol visi objektai bus susinchronizuoti.

Tik vienas aplinkos duomenų šaltinis gali vienu metu naudoti tą patį „Common Data Service“sutvarkytą ežerą.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>„Common Data Service” valdomojo telkinio duomenų šaltinio redagavimas

Sukūrus duomenų šaltinį galite redaguoti tik objekto pasirinkimą. Pavyzdžiui, jei į „Common Data Service“ buvo įtraukti papildomi objektai ir norite importuoti ir juos.    
Norėdami prisijungti prie kitos „Common Data Service” tarnybos, [sukurkite naują duomenų šaltinį](#connect-to-a-common-data-service-managed-lake).

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.

3. Sąraše pasirinkite **Redaguoti**.

4. Pažymėkite papildomus objektus iš galimų objektų sąrašo ir pasirinkite **Įrašyti**.
