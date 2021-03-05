---
title: Sujungti „Common Data Model“ duomenis su „Azure Data Lake“ paskyra
description: Dirbkite su „Common Data Model“ duomenimis naudodami „Azure Data Lake Storage“.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 247e4d9c47ff2373065ebf3c6d554323e45a120b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267870"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Jungimasis prie „Common Data Model” aplanko naudojant „Azure Data Lake” klientą

Šis straipsnis pateikia informaciją, kaip vartoti duomenis iš „Common Data Model“ katalogo naudojant jūsų „Azure Data Lake Storage Gen2“ paskyrą.

## <a name="important-considerations"></a>Svarbi informacija

- „Azure Data Lake“ duomenys turi atitikti bendrojo duomenų modelio standartą. Kiti formatai šiuo metu nepalaikomi.

- Duomenų suvartojimas palaiko tik „Azure Data Lake“ *Gen2* talpinimo paskyras. Negalite naudoti „Azure Data Lake“ Gen1 talpinimo paskyrų siekiant suvartoti duomenis.

- Norėdami autentifikuoti su „Azure“ pagrindinėmis paslaugomis, įsitikinkite, kad sukonfigūravote jas savo nuomotojuje. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).

- „Azure Data Lake“, kurį norite prijungti ir iš kurio suvartoti duomenis turi būti tame pačiame „Azure“ regione kaip ir „Dynamics 365 Customer Insights“ aplinka. Ryšiai su „Common Data Model“ katalogu iš „Data Lake“ kitame „Azure“ regione nėra palaikomi. Norėdami sužinoti „Azure“ aplinkos regioną, eikite į **Administravimas** > **Sistema** > **Apie** publikos įžvalgose.

- Duomenys laikomi interneto paslaugose gali būti laikomi kitoje vietoje, o ne ten, kur duomenys apdorojami ar laikomi „Dynamics 365 Customer Insights“.Importuodami arba prisijungdami prie duomenų, saugomų internetinėse tarnybose, sutinkate, kad duomenys gali būti perkeliami ir saugomi „Dynamics 365 Customer Insights“.  [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Prisijungti prie „Common Data Model“ aplanko

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Pasirinkite **Įtraukti duomenų šaltinį**.

1. Pasirinkite **Sujungti su „Common Data Model“ katalogu**, pasirinkite **Pavadinimas** duomenų šaltiniui ir rinkitės **Toliau**. Pavadinimų rekomendacijos: 
   - Pradėti nuo raidės.
   - Naudokite tik raides ir skaičius. Specialiųjų simbolių ir tarpų neleidžiama įvesti.
   - Naudokite nuo 3 iki 64 simbolių.

1. Galite pasirinkti tarp naudojimo resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). Įveskite **Talpyklos** informaciją ir pasirinkite **Toliau**.
   > [!div class="mx-imgBorder"]
   > ![Dialogo langas, skirtas naujai „Azure Data Lake“](media/enter-new-storage-details.png)
   > [!NOTE]
   > Kad galėtumėte prisijungti ir kurti abonementą, jums reikalingas vienas iš šių vaidmenų : konteinerio arba anksčiau nurodytas saugyklos duomenų šaltinis:
   >  - „Storage Blob Data“ skaitytojas
   >  - „Storage Blob Data“ savininkas
   >  - „Storage Blob Data“ pildytojas

1. Dialogo lange Pasirinkite aplanką **„Įprastas duomenų modelis“**, pasirinkite failą model.json arba manifest.json, iš kurio norite importuoti duomenis, ir pasirinkite **Kitas**.
   > [!NOTE]
   > Sąraše nebus rodomas bet koks failas model.json arba jison duomenų šaltinis su kitu aplinkos sąrašu.

1. Gausite galimų objektų sąrašą pasirinktame model.json arba sertifikato.json faile. Galite peržiūrėti ir pasirinkti objektus iš galimų objektų sąrašo, o tada pasirinkti **Įrašyti**. Visi pasirinkti objektai bus vartojami iš naujo duomenų šaltinio.
   > [!div class="mx-imgBorder"]
   > ![Dialogo langas, kuriame pateikiamas sąrašas su objektais iš model.json failo](media/review-entities.png)

8. Nurodykite, kuriems duomenų objektams norite įjungti duomenų profiliavimą ir pasirinkite **Įrašyti**. Duomenų profiliavimas įgalina analizės ir kitas galimybes. Galite pasirinkti visą objektą, kuris pasirenka visus atributus iš objekto ar pasirinkite tam tikrus jūsų pasirinkimo atributus. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.
   > [!div class="mx-imgBorder"]
   > ![Teksto laukelis rodo duomenų profiliavimą](media/dataprofiling-entities.png)

9. Įrašius pasirinkimus, atidaromas puslapis **Duomenų šaltiniai**. Dabar turėtumėte matyti „Common Data Model“ aplanko ryšį kaip duomenų šaltinį.

> [!NOTE]
> Model.json failas arba anonsas.json gali būti susiejantis tik su vienu duomenų šaltinis toje pačioje aplinkoje. Tačiau tą patį failą model.json arba manifest.json galima naudoti duomenų šaltiniams keliose aplinkose.

## <a name="edit-a-common-data-model-folder-data-source"></a>Bendrojo duomenų modelio aplanko duomenų šaltinio redagavimas

Galite naujinti prieigos raktą paskyros talpinimui, kurioje yra „Common Data Model“ katalogas. Taip pat galite pakeisti failą model.json arba manifest.jison. Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-a-common-data-model-folder).

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.

3. Sąraše pasirinkite **Redaguoti**.

4. Taip pat galite atnaujinti **Prieigos raktą** ir pasirinkti **Pirmyn**.

   ![Esamo duomenų šaltinio prieigos rakto redagavimo ir naujinimo dialogo langas](media/edit-access-key.png)

5. Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursu pagrįstą ar prenumeravimu pagrįstą jungtį. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). Negalite keisti **Talpyklos** informacijos naujinant jungtį.
   > [!div class="mx-imgBorder"]

   > ![Dialogo langas, skirtas "Azure Data Lake" duomenų telkinio ryšiui su esamu saugyklos abonementu įvesti](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Kad galėtumėte prisijungti ir kurti abonementą, jums reikalingas vienas iš šių vaidmenų : konteinerio arba anksčiau nurodytas saugyklos duomenų šaltinis:
   >  - „Storage Blob Data“ skaitytojas
   >  - „Storage Blob Data“ savininkas
   >  - „Storage Blob Data“ pildytojas


6. Galite pasirinkti kitą model.json arba atskirai.json failą su skirtingu objektų iš konteinerio objektų rinkiniu.

7. Pasirinktinai, galite pasirinkti papildomus vartojamus objektus. Jei nėra priklausomybių, taip pat galite pašalinti jau pažymėtus objektus.

   > [!IMPORTANT]
   > Jei yra esamo modelio.json arba manifest.json failo ir objektų rinkinio priklausomybių, bus rodomas klaidos pranešimas, kuriame negalite pažymėti kito modelio.json arba manifest.json failo. Pašalinkite šias priklausomybes prieš keisdami failą model.json arba manifest.json arba sukurkite naują duomenų šaltinį naudodami failą model.json arba manifest.json, kad išvengtumėte priklausomybių pašalinimo.

8. Pasirinktinai, galite pasirinkti papildomus atributus ar objektus, kuriems bus įjungtas duomenų profiliavimas ar išjungti jau pasirinktus.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]