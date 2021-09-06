---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e3f99f8f151aea5f120084382babd5e46e109545a4f63aafc51c3ecb1400cc33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034187"
---
# <a name="manage-environments"></a>Aplinkų valdymas

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Perjungti aplinką

Norėdami keisti aplinkas, viršutiniame dešiniajame puslapio kampe pasirinkite valdiklį **Aplinka**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Aplinkų perjungimo valdiklio ekrano kopija.":::

Administratoriai gali [kurti](get-started-paid.md) ir valdyti aplinkas.

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Galite redaguoti kai kurią esamos aplinkos informaciją.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pasirinkite **Redagavimo** piktogramą.

3. Lauke **Redaguoti aplinką** galite atnaujinti aplinkos rodomą **Pavadinimą**, tačiau negalite keisti  **Regiono** arba **Tipo**.

4. Jei aplinka sukonfigūruota duomenims saugoti „Azure Data Lake Storage“, galite atnaujinti **kliento raktą**. Tačiau negalite keisti **Paskyros pavadinimo** arba **Konteinerio** pavadinimo.

5. Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursais pagrįstą arba prenumeravimu pagrįstą jungtį. Jums atnaujinus negalėsite grįžti prie pagrindinės paskyros po naujinimo. Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md). Negalite keisti **Talpyklos** informacijos naujinant jungtį.

6. Taip pat galite nurodytų Microsoft Dataverse aplinkos URL skiltyje **Duomenų bendrinimo su Microsoft Dataverse konfigūravimas ir papildomų galimybių įjungimas**. Į šias galimybes įeina duomenų bendrinimas su „Microsoft Dataverse” pagrįstomis programomis ir sprendimais, duomenų paėmimas iš vietinių duomenų šaltinių arba [prognozių](predictions.md) naudojimas. Pasirinkite **Įjungti duomenų bendrinimą**, jei „Customer Insights“ išvesties duomenis norite bendrinti su Microsoft Dataverse valdomu „Data Lake“.

   > [!NOTE]
   > - Duomenų bendrinimas Microsoft Dataverse su valdomasis duomenų telkiniais šiuo metu nepalaikomas, kai įrašote visus duomenis savo Azure Data Lake Storage.
   > - [Trūkstamų objekto reikšmių prognozė](predictions.md) ir „PowerBI” įdėtosios ataskaitos auditorijos įžvalgose (jei įgalinta jūsų aplinkoje) šiuo metu nepalaikomos, kai įgalinate duomenų bendrinimą su „Microsoft Dataverse” valdomu „data lake”.

   Įgalinus duomenų bendrinimą su „Microsoft Dataverse”, prasideda visiškas jūsų duomenų šaltinių atnaujinimas ir kiti procesai. Jei šiuo metu vykdomi procesai, nematysite duomenų bendrinimo su „Microsoft Dataverse” įjungimo parinkties. Palaukite, kol šie procesai bus užbaigti arba atšaukite juos, kad įgalintumėte duomenų bendrinimą. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::
   
   Jums vykdant procesus, tokius kaip duomenų suvartojimas ar segmento sukūrimas, atitinkantys katalogai bus sukuriami talpinimo paskyroje, kurią nurodėte prieš tai. Atsižvelgiant į jūsų vykdomą procesą, duomenų failai ir model.json failai kuriami ir įtraukiami į atitinkamus antrinius aplankus.

## <a name="copy-the-environment-configuration"></a>Aplinkos konfigūracijos kopijavimas

Kurdami naują aplinką galite pasirinkti kopijuoti konfigūraciją iš esamos aplinkos. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Aplinkos parametrų parinkčių ekrano kopija.":::

Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.

Kopijuojami šie konfigūracijos parametrai:

- Įtrauktas / importuotas duomenų šaltinis
- Duomenų sujungimo (susiejimo, atitikimo, suliejimo) konfigūracija
- Segmentai
- Matavimai
- Ryšiai
- Veiklos
- Paieškos ir filtravimo rodyklė
- Eksportavimo paskirties vietos
- Suplanuotas atnaujinimas
- Papildymai
- Modelio valdymas
- Vaidmenų priskyrimai

Šie duomenys *nėra* kopijuojami:

- Klientų profiliai.
- Duomenų šaltinio kredencialai. Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.
- Duomenų šaltiniai iš „Common Data Model“ aplanko ir „Dataverse“ valdomojo duomenų „Data Lake". Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.

Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka. Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.

Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**. Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.

:::image type="content" source="media/data-sources-copied.png" alt-text="Duomenų šaltinių, kurie buvo nukopijuoti ir kuriems reikalingas autentifikavimas, sąrašas.":::

Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**. Čia rasite parametrus iš šaltinio aplinkos. Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.

Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.

## <a name="reset-an-existing-environment"></a>Paleiskite iš naujo esamą aplinką

Kaip administratorius galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti prarytus duomenis.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją. 

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Nustatyti iš naujo**. 

4.  Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip administratorius galite panaikinti jūsų administruojamą aplinką.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Naikinti**. 

4.  Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
