---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376886"
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

Jei norite [naudoti iš anksto anksto prognozė modelius](predictions-overview.md#out-of-box-models) konfigūruokite duomenų bendrinimą su „Dataverse“. Arba galite įjungti duomenų nurijimas iš vietinis šaltinių, pateikdami jūsų „Microsoft Dataverse“ organizacijos administruojami aplinkos URL.

> [!IMPORTANT]
> Klientų įžvalgos ir Dataverse turi būti tame pačiame regione, kad būtų galima dalytis duomenimis.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::

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

## <a name="change-the-owner-of-an-environment"></a>Aplinkos savininko keitimas

Nors keli vartotojai gali turėti administratoriaus teises "Customer Insights", tik vienas vartotojas yra aplinkos savininkas. Pagal numatytuosius nustatymus administratorius iš pradžių sukuria aplinką. Kaip aplinkos administratorius, galite priskirti nuosavybę kitam vartotojui, turinčiam administratoriaus teises.

1. Programos antraštėje pasirinkite **Aplinkos** parinkėją.

1. Pasirinkite **Redagavimo** piktogramą.

1. Lauke Aplinkos redagavimas **eikite** **į veiksmą Pagrindinė informacija**.

1. **Lauke Aplinkos savininko** keitimas pasirinkite naują aplinkos savininką.  

1. Pasirinkite **Peržiūra ir pabaiga**, tada **Naujinti**, kad pritaikytumėte keitimus. 

## <a name="claim-ownership-of-an-environment"></a>Reikalauti nuosavybės teisės į aplinką

Jei aplinkos savininkas palieka organizaciją arba jo vartotojo abonementas panaikinamas, aplinka neturės savininko. Vartotojas, turintis administratoriaus teises, gali reikalauti nuosavybės teisių ir tapti nauju savininku. Jie gali ir toliau valdyti aplinką arba [pakeisti nuosavybę į kitą administratorių](#change-the-owner-of-an-environment). 

Norėdami reikalauti nuosavybės, pasirinkite mygtuką **Paimti nuosavybę**, kuris rodomas kiekvieno "Customer Insights" puslapio viršuje, kai pradinis savininkas paliko organizaciją.

## <a name="reset-an-existing-environment"></a>Paleiskite iš naujo esamą aplinką

Kaip aplinkos savininkas, galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti nurytus duomenis.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją. 

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Nustatyti iš naujo**. 

4.  Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.

## <a name="delete-an-existing-environment"></a>Esamos aplinkos naikinimas

Kaip aplinkos savininkas, galite panaikinti savo administruojamą aplinką.

1.  Programos antraštėje pasirinkite **Aplinkos** parinkėją.

2.  Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**). 

3. Pasirinkite parinktį **Naikinti**. 

4.  Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
