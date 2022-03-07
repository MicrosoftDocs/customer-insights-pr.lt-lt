---
title: Visos duomenų dalys naudojančios prognozes
description: Naudokite prognozes tam, kad užpildytumėte nepilnus kliento duomenis.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-predictions
- ci-custom-models
- customerInsights
ms.openlocfilehash: 9634523f61e27a0ed183186a788ab0cef3c0491b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354013"
---
# <a name="complete-your-partial-data-with-predictions-deprecated"></a>Užpildykite dalinius duomenis prognozėmis (nebenaudojami)

> [!IMPORTANT]
> Ši funkcija bus **nebenaudojama** nuo **2021 m. lapkričio 5 d**. Dabartiniai diegimai veiks tol, kol funkcija bus pašalinta, tačiau negalėsite kurti naujų integracijų naudodami toliau pateiktas instrukcijas.

Prognozės leidžia lengvai kurti numatomas reikšmes, kurios gali pagerinti jūsų nusimanymą apie klientą. **Protingumas** > **Prognozės** puslapyje galite pasirinkti **Mano prognozės** tam, kad matytumėte prognozes, kurias sukonfigūravote kitose publikos įžvalgų dalyse ir leistumėte sau toliau jas tinkinti.

> [!NOTE]
> Šios funkcijos naudoti negalima, jei jūsų aplinka naudoja „Azure Data Lake Gen 2“ saugyklą.
>
> Prognozių funkcija naudoja automatizuotas priemones, kad įvertintų duomenis ir pateiktų tais duomenimis pagrįstas prognozes, todėl šią funkciją galima naudoti kaip profiliavimo, kaip ši sąvoka apibrėžta Bendrajame duomenų apsaugos reglamente (BDAR), būdą. Klientui naudojant šią funkciją duomenims tvarkyti gali būti taikomi BDAR arba kiti įstatymai ar kiti teisės aktai. Esate atsakingas už užtikrinimą, kad naudojate „Dynamics 365 Customer Insights“, įskaitant prognozes, atitikimą su visais taikomais teisės aktais ir reglamentais, įskaitant teisės aktus susijusius su privatumu, asmens duomenimis, biometriniais duomenimis, duomenų apsauga ir bendravimo konfidencialumu.

## <a name="prerequisites"></a>Būtinosios sąlygos

Tam, kad jūsų organizacija galėtų naudoti prognozių funkciją, įsitikinkite, kad tenkinamos šios būtinosios sąlygos:

1. Jūsų organizacijoje yra egzempliorius, kuris [nustatytas „Microsoft Dataverse”](/ai-builder/build-model#prerequisites) ir esantis toje pačioje organizacijoje kaip ir „Customer Insights”.

2. Jūsų auditorijos įžvalgų aplinka pridedama prie jūsų „Dataverse” egzemplioriaus.

Daugiau informacijos žiūrėkite [Naujos aplinkos kūrimas](create-environment.md).

## <a name="create-a-prediction-in-the-customer-entity"></a>Sukurkite prognozę kliento objekte

1. Publikos įžvalgose, eikite į **Duomenys** > **Objektai**.

2. Pasirinkite objektą **Klientas**.

3. Objekte **Klientas: „Customer Insights“** pažymėkite skirtuką **Laukai**.

4. Raskite atributo pavadinimą, kuriam norite prognozuoti reikšmės, tada stulpelyje **Suvestinė** pasirinkite piktogramą **Apžvalga**.
   > [!div class="mx-imgBorder"]
   > ![Apžvalgos piktograma.](media/intelligence-overviewicon.png "Apžvalgos piktograma")

5. Jei jūsų atributui priskiriamas didelis kiekis trūkstamų reikšmių, pasirinkite **Numatyti trūkstamas reikšmes**, kad tęstumėte prognozę.
   > [!div class="mx-imgBorder"]
   > ![Apžvalgos būsena su rodomu numatomų trūkstamų reikšmių mygtuku.](media/intelligence-overviewpredictmissingvalues.png "Apžvalgos būsena su rodomu numatomų trūkstamų reikšmių mygtuku")

6. Įrašykite **rodomą pavadinimą** ir **išvesties objekto pavadinimą**, kad peržiūrėtumėte prognozės rezultatus.

7. Iš anksto paruoštame parinkčių sąraše matysite, kur galite susieti reikšmes su numatoma kategorija. Tokiu atveju jūsų vienintelės kategorijos parinktys bus 0 arba 1, nes šios reikšmės susietos su „teisinga“ / „klaidinga“ arba dvejetainiu prognozės pobūdžiu. Kategorijos stulpelyje lauko reikšmes, kurios galutinėje prognozėje turėtų būti klasifikuojamos kaip „0“, susiekite su „0“, o elementus, kurie galutinėje prognozėje turėtų būti klasifikuojami kaip „1“, susiekite su „1“.
   > [!div class="mx-imgBorder"]
   > ![Lauko reikšmių, susietų į kategorijas, pavyzdys.](media/intelligence-categorymapping.png "Lauko reikšmių, susietų į kategorijas, pavyzdys")

8. Pažymėkite **Atlikta** ir prognozė bus apdorota. Atsižvelgiant į duomenų dydį ir sudėtingumą, apdorojimas užtruks šiek tiek laiko. Rezultatai bus prieinami naujame objekte pagal sukurtos prognozės **išvesties objekto pavadinimą**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="create-a-prediction-while-creating-a-segment"></a>Prognozės kūrimas kuriant segmentą

Kuriant segmentą taip pat galima prognozuoti trūkstamas konkretaus pasirinkto atributo reikšmes. Tiksliau sakant, kai sparčiai kuriate segmentą, pagrįstą jūsų vieningu kliento objektu arba „Customer_Measure“ objektu.

Vykdydami šią procedūrą, jūs pasirinksite konkretų atributą, kuris bus segmento pagrindas, pvz., kliento pasitenkinimą arba pirkinio sumą. Sukūrus segmentą, sistema pasiūlys trūkstamų šio atributo reikšmių prognozavimo metodą.

1. Publikos įžvalgose eikite į  **Segmentai** ir pasirinkite **Profiliai** plytą.

2. Pasirinkite **lauką**, kad sukurtumėte segmentą, pasirinkite **operatorių**, tada – **Peržiūra**.

3. Nurodykite segmento **pavadinimą** ir **rodomą pavadinimą**.

4. Pasirinkite **Įrašyti**.

5. Jei jūsų sukurtas segmentas turi neišsamius duomenis šaltinio lauke, galite pasirinkti prognozuoti trūkstamas reikšmes.
   > [!div class="mx-imgBorder"]
   > ![Prognozės mygtukas.](media/segments-predictoption.png "Prognozės mygtukas")

6. Įrašykite **rodomą pavadinimą** ir **išvesties objekto pavadinimą**, kad peržiūrėtumėte prognozės rezultatus.

7. Pasirinkite **Atlikta**. Jūsų prognozė bus netrukus sugeneruota ir prieinama naujame objekte pavadinimu, kurį nurodėte kaip **išvesties objekto pavadinimą**.

## <a name="view-a-prediction"></a>Prognozės peržiūra

1. Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.

2. Pasirinkite prognozę, kurią norite peržiūrėti.

3. Pažymėkite elipsę stulpelyje **Veiksmai** ir pasirinkite **Peržiūrėti**.

4. Peržiūrint prognozę matysite duomenų taškų skaičių.
   > [!div class="mx-imgBorder"]
   > ![Prognozių puslapis.](media/intelligence-predictionsviewpage.png "Prognozių puslapis")

   - **Numatomos reikšmės** rodo susiejimą, kurį sukūrėte lauko reikšmės susiejimo į kategoriją fazėje. Tai yra jūsų duomenų rinkinio reikšmės, susietos su konkrečia kategorija.
   -**Labiausiai įtakojantys veiksniai** yra jūsų duomenų rinkinio veiksniai, kurie galėjo turėti daugiausiai įtakos prognozės patikimumui, kai jūsų lauko reikšmė buvo susiejama su konkrečia kategorija.
   - **Efektyvumas** nurodo, kaip veikia prognozės. Norėdami sužinoti daugiau, pažymėkite nuorodą.
   - **Peržiūroje** rodomi išvesties duomenų rinkinio pavyzdžiai jūsų prognozėje ir numatomos reikšmės, kai „0“ yra neapibrėžtas, o „1“ yra apibrėžtas, tikėtinumas arba patikimumas.

## <a name="update-a-prediction"></a>Prognozės naujinimas

1. Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.

2. Pažymėkite norimą naujinti prognozę ir pasirinkite piktogramą **Naujinti**.

3. Prognozė bus planuojama apdoroti. Galite peržiūrėti paskutinio atnaujinimo datą puslapio **Prognozės** stulpelyje **Atnaujinta**.

## <a name="edit-a-prediction"></a>Prognozės redagavimas

Sukūrę prognozė, galite tinkinti modelį, AI Builder kad padidintumėte modelio efektyvumą.  

1. Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.

2. Pažymėkite prognozę, kurią norite redaguoti.

3. Pažymėkite elipsę stulpelyje **Veiksmai** ir pasirinkite **Peržiūrėti**.

4. Pasirinkite **Tinkinti AI Builder**.

5. Atnaujinkite savo modelį AI Builder. [Sužinokite daugiau apie modelių valdymą programoje „AI Builder“](/ai-builder/manage-model#retrain-and-republish-existing-models).

Kitame jūsų prognozės vykdyme bus naudojamas jūsų sukurtas atnaujintas modelis.

> [!NOTE]
> Nauji modeliai, sukurti naudojant AI Builder, nebus rodomi auditorijos įžvalgose, nebent modelis buvo sukurtas iš pirmiau išvardytų funkcijų.

## <a name="remove-a-prediction"></a>Prognozės pašalinimas

1. Publikos įžvalgose, eikite į **Protingumas** > **Prognozės** > **Mano prognozės**.

2. Pažymėkite norimą naikinti prognozę.

3. Pažymėkite elipsę stulpelyje **Veiksmai** ir pasirinkite **Naikinti**.

4. Patvirtinkite naikinimą.

## <a name="troubleshooting"></a>Trikčių šalinimas

Jei dėl klaidos negalite baigti „Dataverse“ pridėjimo proceso, procesą galite bandyti užbaigti rankiniu būdu. Yra dvi žinomos problemos, kurios gali kilti pridėjimo procese.

- Kliento kortelės papildinio sprendimas nėra įdiegtas.
    1. Vadovaukitės instrukcijomis, kad [įdiegtumėte ir sukonfigūruotumėte sprendimą](customer-card-add-in.md).

- Programos leidimai nėra suteikti.
    1. Eikite į [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Pasirinkti **Aplinkos**.
    1. Pažymėkite elipsę šalia aplinkos, į kurią norite įtraukti leidimą, ir pasirinkite **Parametrai**.
    1. Išplėskite **Vartotojai ir teisės** ir pasirinkite **Vartotojai**.
    1. Pasirinkite **+ Naujas**, tada – **Vartotojas**.
    1. Pasirinkite **Programos vartotojas**, jei programos vartotojas dar nepasirinktas, ir įveskite toliau nurodytą informaciją.
        - **Vartotojo vardas:** cihelp@microsoft.com
        - **Programos ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Vardas**: Kliento
        - **Pavardė:** įžvalgos
        - **Pagrindinis el. paštas:** cihelp@microsoft.com
    1. Pasirinkite **Įrašyti ir uždaryti**.
    1. Pasirinkite vartotoją, kurį ką tik sukūrėte.
    1. Viršutinio meniu juostoje pasirinkite **Tvarkyti vaidmenis**.
    1. Pasirinkite **Sistemos administratorius**, tada pasirinkite **Gerai**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
