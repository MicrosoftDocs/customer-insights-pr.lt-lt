---
title: Sujungti „Common Data Model“ duomenis su „Azure Data Lake“ paskyra
description: Dirbkite su „Common Data Model“ duomenimis naudodami „Azure Data Lake Storage“.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643468"
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

1. Pasirinkite **Sujungti su „Common Data Model“ katalogu**, pasirinkite **Pavadinimas** duomenų šaltiniui ir rinkitės **Toliau**.

1. Galite pasirinkti tarp naudojimo resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). Įveskite **Talpyklos** informaciją ir pasirinkite **Toliau**.
   > [!div class="mx-imgBorder"]
   > ![Dialogo lango lauke įveskite prisijungimo prie „Azure Data Lake“ informaciją](media/enter-new-storage-details.png)

1. **Pasirinkite „Common Data Model“ katalogą** teksto laukelyje pasirinkite model.json failą, iš kurio importuosite duomenis ir rinkitės **Kitas**.
   > [!NOTE]
   > Bet kuris model.json failas susietas su kitu duomenų šaltiniu aplinkoje nebus rodoma sąraše.

1. Gausite esamų objektų sąrašą pasirinktame model.json faile. Galite peržiūrėti ir pasirinkti objektus iš galimų objektų sąrašo, o tada pasirinkti **Įrašyti**. Visi pasirinkti objektai bus vartojami iš naujo duomenų šaltinio.
   > [!div class="mx-imgBorder"]
   > ![Dialogo langas, kuriame pateikiamas sąrašas su objektais iš model.json failo](media/review-entities.png)

8. Nurodykite, kuriems duomenų objektams norite įjungti duomenų profiliavimą ir pasirinkite **Įrašyti**. Duomenų profiliavimas įgalina analizės ir kitas galimybes. Galite pasirinkti visą objektą, kuris pasirenka visus atributus iš objekto ar pasirinkite tam tikrus jūsų pasirinkimo atributus. Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.
   > [!div class="mx-imgBorder"]
   > ![Teksto laukelis rodo duomenų profiliavimą](media/dataprofiling-entities.png)

9. Įrašius pasirinkimus, atidaromas puslapis **Duomenų šaltiniai**. Dabar turėtumėte matyti „Common Data Model“ aplanko ryšį kaip duomenų šaltinį.

> [!NOTE]
> Model.josn failas gali būti susietas su vienu duomenų šaltiniu vienoje aplinkoje. Nepaisant to, tas pats model.json failas gali būti naudojamas duomenų šaltiniams keliose aplinkose.

## <a name="edit-a-common-data-model-folder-data-source"></a>Bendrojo duomenų modelio aplanko duomenų šaltinio redagavimas

Galite naujinti prieigos raktą paskyros talpinimui, kurioje yra „Common Data Model“ katalogas. Taip pat galite keisti model.json failą. Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-a-common-data-model-folder).

1. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.

2. Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.

3. Sąraše pasirinkite **Redaguoti**.

4. Taip pat galite atnaujinti **Prieigos raktą** ir pasirinkti **Pirmyn**.

   ![Esamo duomenų šaltinio prieigos rakto redagavimo ir naujinimo dialogo langas](media/edit-access-key.png)

5. Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursu pagrįstą ar prenumeravimu pagrįstą jungtį. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). Negalite keisti **Talpyklos** informacijos naujinant jungtį.
   > [!div class="mx-imgBorder"]
   > ![Dialogo lango lauke įveskite prisijungimo prie „Azure Data Lake“ informaciją](media/enter-existing-storage-details.png)

6. Taip pat galite pasirinkti kitą model.json failą su kitu objektų rinkiniu iš konteinerio.

7. Pasirinktinai, galite pasirinkti papildomus vartojamus objektus. Jei nėra priklausomybių, taip pat galite pašalinti jau pažymėtus objektus.

   > [!IMPORTANT]
   > Jei esamame model.json faile yra priklausomybių ir objektų rinkinys, pasirodys klaidos pranešimas ir jūs negalėsite pasirinkti kito model.json failo. Prieš keisdami model.json failą pašalinkite priklausomybes arba sukurkite naują duomenų šaltinį su model.json failu, kurį norite naudoti, kad nereikėtų šalinti priklausomybių.

8. Pasirinktinai, galite pasirinkti papildomus atributus ar objektus, kuriems bus įjungtas duomenų profiliavimas ar išjungti jau pasirinktus.   
