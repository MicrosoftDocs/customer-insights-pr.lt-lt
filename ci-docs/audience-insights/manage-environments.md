---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270122"
---
# <a name="manage-environments"></a>Aplinkų valdymas

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Šis straipsnis paaiškina, kaip sukurti naują organizaciją ir kaip aprūpinti aplinką.

## <a name="sign-up-and-create-an-organization"></a>Prisijunkite ir sukurkite organizaciją

1. Atidarykite svetainę [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Pasirinkite **Darbo pradžia**.

3. pasirinkite pageidaujamą prisijungimo scenarijų ir pasirinkite atitinkamą nuorodą.

4. Sutikite su sąlygomis ir pasirinkite **Tęsti**, kad pradėtumėte kurti organizaciją.

5. Sukūrus aplinką jus nukreips į [Customer Insights](https://home.ci.ai.dynamics.com).

6. Norėdami ištirti programą, naudokite demonstracinę aplinką arba galite sukurti naują aplinką atlikdami kitame skyriuje nurodytus veiksmus.

7. Nurodę aplinkos parametrus, pasirinkite **Kurti**.

8. Būsite prijungti po to, kai aplinka bus sėkmingai sukurta.

## <a name="create-an-environment-in-an-existing-organization"></a>Aplinkos kūrimas esamoje organizacijoje

Yra du naujos aplinkos kūrimo būdai. Galite nurodyti visiškai naują konfigūraciją arba galite kopijuoti tam tikrus konfigūracijos parametrus iš esamos aplinkos.

Norėdami sukurti aplinką:

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Naujas**.

   > [!div class="mx-imgBorder"]
   > ![Aplinkų parametrai](media/environment-settings-dialog.png)

1. Dialogo lange **Naujos aplinkos kūrimas** pasirinkite **Nauja aplinka**.

   Jei norite [kopijuoti duomenis iš esamos aplinkos](#additional-considerations-for-copy-configuration-preview), pasirinkite **Kopijuoti iš esamos aplinkos**. Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.

1. Nurodykite toliau pateiktą informaciją.
   - **Pavadinimas**: Šios aplinkos pavadinimas. Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.
   - **Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga.
   - **Tipas**: pasirinkite, ar norite kurti gamybos ar smėlio dėžės aplinką.

2. Pasirinktinai galite spustelėti **Išplėstiniai parametrai**.

   - **Įrašyti visus duomenis į**: nurodo, kur norite saugoti išvesties duomenis, sugeneruotus iš „Customer Insights“. Galimos dvi parinktys: **„Customer Insights“ saugykla** („Azure Data Lake“ valdomas „Customer Insights“ komandos) ir **Azure Data Lake Storage Gen2** (jūsų nuosava „Azure Data Lake Storage“). Pagal numatytuosius parametrus, pasirenkama „Customer Insights“ saugykla.

   > [!NOTE]
   > Įrašydami duomenis į „Azure Data Lake Storage, sutinkate, kad jūsų duomenys būtų perkelti ir saugomi konkrečiai „Azure“ paskyrai paskirtoje geografinėje vietovėje , kuri gali skirtis nuo vietovės, kurioje saugomi „Dynamics 365 Customer Insights“ duomenys. [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)
   >
   > Šiuo metu surinkti objektai visada saugomi „Customer Insights“ valdomame „Data Lake“.
   > Palaikomte tik „Azure Data Lake Gen2“ talpinimo paskyras iš to paties „Azure“ regiono, kurį pasirinkote kurdami aplinką.
   > Palaikome tik „Azure Data Lake Gen2“ saugyklų paskyras, kurioms įgalinta hierarchinio pavadinimo (HNS) funkcija.

   - „Azure Data Lake Storage Gen2“ parinkčiai galite pasirinkti tarp resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). **Talpykla** pavadinimas negali būti keičiamas ir bus „klientoįžvalgos“.
   
   - Jei norite naudoti [prognozes](predictions.md) arba konfigūruoti duomenų bendrinimą su programomis ir sprendimais, pagrįstais Microsoft Dataverse, Microsoft Dataverse dalyje **Konfigūruoti duomenų bendrinimą su papildomomis galimybėmis Microsoft Dataverse** pateikite aplinkos URL. Pasirinkite Įjungti **duomenų bendrinimą** ir bendrinkite Customer Insights išvedimo duomenis su Microsoft Dataverse valdomu Data Lake.

     > [!NOTE]
     > - Duomenų bendrinimas Microsoft Dataverse su valdomasis duomenų telkiniais šiuo metu nepalaikomas, kai įrašote visus duomenis savo Azure Data Lake Storage.
     > - [Prognozės šiuo metu nepalaikomos](predictions.md) trūkstamų objekto reikšmių reikšmės, kai leidžiate bendrinti duomenis su Microsoft Dataverse valdomojo Data Lake duomenimis.

     > [!div class="mx-imgBorder"]
     > ![Konfigūravimo parinktys norint įjungti duomenų bendrinimą naudojant Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Jums vykdant procesus, tokius kaip duomenų suvartojimas ar segmento sukūrimas, atitinkantys katalogai bus sukuriami talpinimo paskyroje, kurią nurodėte prieš tai. Duomenų failai ir model.json failai bus sukurti ir įtraukti į atitinkamus poaplankius pagal jūsų vykdytą procesą.

   Jei sukuriate keletą „Customer Insights“ aplinkų ir pasirenkate įrašyti išvesties objektus iš tų aplinkų į jūsų talpinimo paskyrą, atskiri katalogai bus sukurti kiekvienai aplinka su ci_<environmentid> talpykloje.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Papildomos pastabos dėl kopijavimo konfigūracijos (peržiūros versija)

Kopijuojami šie konfigūracijos parametrai:

- Funkcijų konfigūracijos
- Įtrauktas / importuotas duomenų šaltinis
- Duomenų sujungimo (susiejimo, atitikimo, suliejimo) konfigūracija
- Segmentai
- Matavimai
- Ryšiai
- Veiklos
- Paieškos ir filtravimo rodyklė
- Eksportavimo paskirties vietos
- Suplanuotas atnaujinimas
- Duomenų papildymai
- Modelio valdymas
- Vaidmenų priskyrimai

Šie konfigūracijos parametrai *nėra* kopijuojami:

- Klientų profiliai.
- Duomenų šaltinio kredencialai. Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.
- Duomenų šaltiniai iš „Common Data Model” aplanko ir „Common Data Service” valdomojo telkinio. Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.

Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka. Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.

Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**. Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.

> [!div class="mx-imgBorder"]
> ![Nukopijuoti suomenų šaltiniai](media/data-sources-copied.png)

Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Vienyti**. Čia rasite parametrus iš šaltinio aplinkos. Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.

Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Galite redaguoti kai kurią esamos aplinkos informaciją.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pasirinkite **Redagavimo** piktogramą.

3. Lauke **Redaguoti aplinką** galite atnaujinti aplinkos rodomą **Pavadinimą**, tačiau negalite keisti  **Regiono** arba **Tipo**.

4. Jei aplinka sukonfigūruojama saugoti duomenis „Azure Data Lake Storage Gen2“, galite atnaujinti **Paskyros raktą**. Tačiau negalite keisti **Paskyros pavadinimo** arba **Konteinerio** pavadinimo.

5. Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursu pagrįstą ar prenumeravimu pagrįstą jungtį. Jums atnaujinus negalėsite grįžti prie pagrindinės paskyros po naujinimo. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). Negalite keisti **Talpyklos** informacijos naujinant jungtį.

## <a name="reset-an-existing-environment"></a>Paleiskite iš naujo esamą aplinką

Kaip administratorius galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti prarytus duomenis.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją. 

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį **...**. 

3. Pasirinkite parinktį **Nustatyti iš naujo**. 

4.  Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Esamos aplinkos naikinimas (galima tik administratoriams)

Kaip administratorius galite panaikinti jūsų administruojamą aplinką.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį **...**. 

3. Pasirinkite parinktį **Naikinti**. 

4.  Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]