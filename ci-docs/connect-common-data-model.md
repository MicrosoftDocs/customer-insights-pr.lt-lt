---
title: Sujungti „Common Data Model“ duomenis su „Azure Data Lake“ paskyra
description: Dirbkite su „Common Data Model“ duomenimis naudodami „Azure Data Lake Storage“.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833373"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Jungimasis prie „Common Data Model” aplanko naudojant „Azure Data Lake” klientą

Šiame straipsnyje pateikiama informacija apie tai, kaip įvesti duomenis Dynamics 365 Customer Insights iš "Common Data Model" aplanko naudojant " Azure Data Lake Storage Gen2" paskyrą.

## <a name="important-considerations"></a>Svarbi informacija

- „Azure Data Lake“ duomenys turi atitikti bendrojo duomenų modelio standartą. Kiti formatai šiuo metu nepalaikomi.

- Duomenų suvartojimas palaiko tik „Azure Data Lake“ *Gen2* talpinimo paskyras. Negalite naudoti „Azure Data Lake“ Gen1 talpinimo paskyrų siekiant suvartoti duomenis.

- "Azure Data Lake" saugyklos abonemente turi būti [įgalinta hierarchinė vardų sritis](/azure/storage/blobs/data-lake-storage-namespace).

- Norėdami autentifikuoti su „Azure“ pagrindinėmis paslaugomis, įsitikinkite, kad sukonfigūravote jas savo nuomotojuje. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md)

- „Azure Data Lake“, kurį norite prijungti ir iš kurio suvartoti duomenis turi būti tame pačiame „Azure“ regione kaip ir „Dynamics 365 Customer Insights“ aplinka. Ryšiai su „Common Data Model“ katalogu iš kito „Azure“ regiono duomenų telkinio nėra palaikomi. Norėdami sužinoti "Azure" aplinkos regioną, eikite į **"Customer Insights" administravimo** > **sistema** > **apie**.

- Internetinėse paslaugose saugomi duomenys gali būti saugomi kitoje vietoje nei ten, kur duomenys tvarkomi ar saugomi Dynamics 365 Customer Insights.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse paslaugose, jūs sutinkate, kad duomenys gali būti perduodami ir saugomi su Dynamics 365 Customer Insights. [Sužinokite daugiau "Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Prisijungti prie „Common Data Model“ aplanko

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **"Azure" duomenų ežero saugykla**, įveskite **duomenų šaltinis pavadinimą**, tada pasirinkite **Pirmyn**.

   - Jei būsite paraginti, pasirinkite vieną iš duomenų rinkinių pavyzdžių, susijusių su jūsų pramone, tada pasirinkite **Pirmyn**.

1. Galite pasirinkti tarp naudojimo resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md) Įveskite serverio **adresą**, pasirinkite **prisijungti**, tada pasirinkite **Pirmyn**.
   > [!div class="mx-imgBorder"]
   > ![Dialogo langas, skirtas naujai „Azure Data Lake“.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Norint sukurti duomenų šaltinis, saugyklos abonemente esančiame konteineryje reikia atlikti vieną iš šių vaidmenų:
   >
   >  - "Storage Blob Data Reader" pakanka skaityti iš saugyklos abonemento ir nuryti duomenis "Customer Insights". 
   >  - Saugyklos BLOB duomenų ruošiklis arba savininkas reikalingas, jei deklaracijos failus norite redaguoti tiesiogiai "Customer Insights".

1. Dialogo lange Pasirinkite aplanką **„Įprastas duomenų modelis“**, pasirinkite failą model.json arba manifest.json, iš kurio norite importuoti duomenis, ir pasirinkite **Kitas**.
   > [!NOTE]
   > Sąraše nebus rodomas bet koks failas model.json arba jison duomenų šaltinis su kitu aplinkos sąrašu.

1. Galimų objektų sąrašą matysite pasirinktame model.json arba manifest.json faile. Peržiūrėkite ir pasirinkite iš galimų objektų sąrašo, tada pasirinkite **Įrašyti**. Visi pasirinkti objektai bus vartojami iš naujo duomenų šaltinio.
   > [!div class="mx-imgBorder"]
   > ![Dialogo langas, kuriame pateikiamas sąrašas su objektais iš model.json failo.](media/review-entities.png)

1. Nurodykite, kuriuos duomenų objektus norite įgalinti duomenų profiliavimą, tada pasirinkite **Įrašyti**. Duomenų profiliavimas įgalina analizės ir kitas galimybes. Galite pasirinkti visą objektą, kuris pasirenka visus atributus iš objekto ar pasirinkite tam tikrus jūsų pasirinkimo atributus. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.
   > [!div class="mx-imgBorder"]
   > ![Teksto laukelis rodo duomenų profiliavimą.](media/dataprofiling-entities.png)

1. Įrašius pasirinkimus, atidaromas puslapis **Duomenų šaltiniai**. Dabar turėtumėte matyti „Common Data Model“ aplanko ryšį kaip duomenų šaltinį.

> [!NOTE]
> Model.json failas arba anonsas.json gali būti susiejantis tik su vienu duomenų šaltinis toje pačioje aplinkoje. Tačiau tą patį failą model.json arba manifest.json galima naudoti duomenų šaltiniams keliose aplinkose.

## <a name="edit-a-common-data-model-folder-data-source"></a>Bendrojo duomenų modelio aplanko duomenų šaltinio redagavimas

Galite naujinti prieigos raktą paskyros talpinimui, kurioje yra „Common Data Model“ katalogas. Taip pat galite pakeisti failą model.json arba manifest.jison. Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-a-common-data-model-folder).

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Šalia duomenų šaltinis norite atnaujinti, pasirinkite vertikalią elipsę (&vellip;).

3. Sąraše pasirinkite **Redaguoti**.

4. Taip pat galite atnaujinti **Prieigos raktą** ir pasirinkti **Pirmyn**.

   ![Esamo duomenų šaltinio prieigos rakto redagavimo ir naujinimo dialogo langas.](media/edit-access-key.png)

5. Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursais pagrįstą ar prenumeravimu pagrįstą jungtį. Norėdami gauti daugiau informacijos, žr [.Azure Data Lake Storage](connect-service-principal.md) Negalite keisti **Talpyklos** informacijos naujinant jungtį.
   > [!div class="mx-imgBorder"]

   > ![Dialogo langas, skirtas įvesti informacijai apie „Azure Data Lake” ryšį su esamu saugyklos abonementu įvesti.](media/enter-existing-storage-details.png)

6. Galite pasirinkti kitą model.json arba atskirai.json failą su skirtingu objektų iš konteinerio objektų rinkiniu.

7. Pasirinktinai, galite pasirinkti papildomus vartojamus objektus. Jei nėra priklausomybių, taip pat galite pašalinti jau pažymėtus objektus.

   > [!IMPORTANT]
   > Jei yra esamo modelio.json arba manifest.json failo ir objektų rinkinio priklausomybių, bus rodomas klaidos pranešimas, kuriame negalite pažymėti kito modelio.json arba manifest.json failo. Pašalinkite šias priklausomybes prieš keisdami failą model.json arba manifest.json arba sukurkite naują duomenų šaltinį naudodami failą model.json arba manifest.json, kad išvengtumėte priklausomybių pašalinimo.

8. Pasirinktinai, galite pasirinkti papildomus atributus ar objektus, kuriems bus įjungtas duomenų profiliavimas ar išjungti jau pasirinktus.

[!INCLUDE [footer-include](includes/footer-banner.md)]
