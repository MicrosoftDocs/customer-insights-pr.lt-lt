---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8251cac9f95455b61eb0300b6c72cd4ab2969591
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046343"
---
# <a name="manage-environments"></a>Aplinkų valdymas



## <a name="switch-environments"></a>Perjungti aplinką

Norėdami keisti aplinkas, viršutiniame dešiniajame puslapio kampe pasirinkite valdiklį **Aplinka**.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Aplinkų perjungimo valdiklio ekrano kopija.":::

Administratoriai gali [kurti](create-environment.md) ir valdyti aplinkas.

## <a name="edit-an-existing-environment"></a>Esamos aplinkos redagavimas

Galite redaguoti kai kurią esamos aplinkos informaciją.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pasirinkite **Redagavimo** piktogramą.

3. Lauke **Redaguoti aplinką** galite atnaujinti aplinkos parametrus.

Daugiau informacijos apie aplinkos parametrus žr. [Naujos aplinkos kūrimas](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Prisijungti prie „Microsoft Dataverse“
   
Šis **Microsoft Dataverse** veiksmas leidžia „Customer Insights“ susieti su „Dataverse“ aplinka.

Jei norite [naudoti iš anksto anksto prognozė modelius](predictions-overview.md#out-of-box-models) konfigūruokite duomenų bendrinimą su „Dataverse“. Arba galite įjungti duomenų nurijimas iš vietinis šaltinių, pateikdami jūsų „Microsoft Dataverse“ organizacijos administruojami aplinkos URL. Pasirinkite **Įjungti duomenų bendrinimą**, jei „Customer Insights“ išvesties duomenis norite bendrinti su „Dataverse“ valdomu „Data Lake“.

> [!IMPORTANT]
> "Customer Insights" ir Dataverse turi būti tame pačiame regione, kad būtų galima bendrinti duomenis.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::

> [!NOTE]
> Jūsų „Customer Insights“ aplinkos konfigūracija nepalaiko šių duomenų bendrinimo scenarijų:
> - Jei visus duomenis įrašysite savo, negalėsite įjungti bendro duomenų bendrinimo su valdomojo „Azure Data Lake Storage“ duomenų „Dataverse“ sutvarkytas „Data Lake“.
> - Įjungę duomenų bendrinimą su „Dataverse“, negalėsite kurti prognozuojamų [arba trūkstamų objekto reikšmių](predictions.md).

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

- Duomenų šaltiniai iš bendrojo duomenų modelio aplanko ir „Dataverse“ valdomo „data lake“. Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.

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
