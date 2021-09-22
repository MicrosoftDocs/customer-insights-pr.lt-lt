---
title: Piltuvėlio ataskaitos
description: Kaip naudoti piltuvėlio ataskaitas norint suprasti, kaip auditorija priima sprendimus.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032265"
---
# <a name="create-and-manage-funnel-reports"></a>Piltuvėlio ataskaitų kūrimas ir valdymas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Piltuvėlio ataskaita renka informaciją apie veiksmus, kuriuos reikia atlikti klientų veiklos ciklas per žiniatinklio svetainę arba mobiliąją programą. Ji padeda jums suprasti, kaip proceso metu progresuoja auditorija ir nustato išskleidžiamus taškus. Pavyzdžiui, galite naudoti piltuvėlio ataskaitą, jei norite nustatyti jūsų klientų maršrutus prieš įsigijimą. Piltuvėlio ataskaitoje pateikiami duomenys, skirti sprendimams pateikti ir optimizavimo bei procesų patobulinimų sritims nustatyti.

## <a name="create-a-funnel-report"></a>Piltuvėlio ataskaitos kūrimas

Norėdami sukurti piltuvėlio ataskaitą, nurodykite veiksmus, kuriuos norite įtraukti, ir kiekvieno veiksmo veiklą. Veikla yra [įvykis](glossary.md), vaizduojantis vartotojo elgesį. Piltuvėlio ataskaitoje rodomas vartotojų, kurie baigė kiekvieną apibrėžtą žingsnį, skaičius. 

1. Eikite į **piltuvėlio** lauką ir pasirinkite **+Naujas piltuvėlis,** kad būtų galima pradėti piltuvėlio ataskaitą.

1. Skyriuje **Piltuvėlio rengyklė**, rinkitės **Veiksmai** ir **+Įtraukti veiksmą.** 

1. Žingsnio pavadinime  **įveskite pavadinimą**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Nauja piltuvėlio ataskaita.":::

1. Rinkitės **Veiklos**. Veiklos įrašai, kai vartotojas peržiūri puslapį (**Peržiūros** veikla) ar sąveikauja su turiniu (**Veiksmų** veikla).

1. Naudokite **žingsnio kriterijus** veiklos susiejimei nurodyti. [Dimensijos](dimensions.md) yra atributai, galintys apibūdinti, filtruoti ar grupuoti duomenis.

1. Pasirinktinai galite konfigūruoti kelių sąlygų piltuvėlio veiksmus. Pasirinkite **Įtraukti sąlygą**, kad nurodytumėte daugiau dimensijų veiksmui. Papildomi kriterijai turi naudoti tą patį veiklos tipą. Galite pasirinkti, ar kelios sąlygos yra susietos su IR, ar su AR operatoriumi.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Piltuvėlio rengyklė, rodanti veiksmo konfigūraciją kelių sąlygų veiksmams.":::

1. Pažymėkite **Įtraukti veiksmą**, kol baigsite visus norimus ataskaitos žingsnius.

1. Pažymėkite **Įrašyti**, pavadinkite ataskaitą ir **Įrašyti dar** kartą. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Pavyzdys: „Fourth Coffee“ įmonės piltuvėlio ataskaita

Toliau pateikiamas scenarijus patvirtina, kad vienas būdas naudoti piltuvėlio ataskaitą. „Fourth Coffee" įmonės analitikas nori suprasti naujausios reklaminės kampanijos įtaką prenumeratos tarifams. Analitikas sukuria piltuvėlio ataskaitą kliento veiklai identifikuoti. Jis pradedamas, kai klientai į įmonės pagrindinį puslapį ateina tol, kol naudoja prenumeratos reklamos kodą. Analyst sukuria piltuvėlio ataskaitą su šiais veiksmais:

1 žingsnis: klientai, kurie nusileido pagrindiniame puslapyje   
2 žingsnis: perkantys klientai   
3 žingsnis: klientai, naudojantys reklamos kodą nuolaidai prenumeratai gauti   
4 žingsnis: prenumeratos registracija   

:::image type="content" source="media/funnel-report-example.png" alt-text="piltuvėlio ataskaitos pavyzdys.":::
  
Šis piltuvėlis leidžia matyti vartotojų, kurie naudojo reklamos kodą vieną kartą įsigę prenumeratos programai prisiregistruoti, skaičių.

### <a name="configure-advanced-settings"></a>Išplėstinių parametrų konfigūravimas 

Piltuvėlio ataskaitos leidžia jums apibrėžti laiko, reikalingo piltuvėliui užbaigti, limitą. Pavyzdžiui, galite nustatyti, kad piltuvėlio užbaigimo trukmė būtų keturios dienos. Šis parametras skaičiuos tik tuos sėkmingus prenumeratos prisijungimus, kurie įvyko per keturias dienas nuo tos dienos, kai vartotojas lankėsi pagrindiniame puslapyje.

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką.

1. Pažymėkite pavadinimą, kurį norite atidaryti. 

1. Srityje **Piltuvėlio rengyklė** pasirinkite **Išplėstiniai parametrai**. 

1. Nustatykite Riboti piltuvėlio užbaigimo laiką į **Įjungta**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Piltuvėlio rengyklė, rodanti išplėstinius parametrus ir parinktis, skirtus piltuvėlio užbaigimo laiko apribojimui.":::

1. Pasirinkite laiką, kada piltuvėlis turi būti užbaigtas **išplečiamajame sąraše** Nustatyti limitą.

1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.


## <a name="cross-channel-funnel-reports"></a>Kelių kanalų piltuvėlio ataskaitos 

Įsitraukimo įžvalgos taip pat gali rinkti elgsenos klientų duomenis mobiliojo įrenginio programoje. Kai naudodami įtraukimo įžvalgų naudojate šią mobiliąją programą, galite kurti kelių [Android SDK](get-started-android.md) ar [iOS SDK](get-started-ios.md) kanalų piltuvėlio ataskaitas. 

### <a name="create-a-cross-channel-funnel-report"></a>Kurti kryžminio kanalo piltuvėlio ataskaitą 

1. Norėdami sukurti [piltuvėlio ataskaitą, atlikite veiksmus](#create-a-funnel-report).    

1. Norėdami sekti, kaip klientai sąveikauja su jūsų prekės ženklu tiek svetainėje, tiek mobiliųjų įrenginių programėlėje arba keliose srityse, naudodami darbo srities perjungiklį sukurkite piltuvėlio žingsnius su duomenimis iš kitų darbo sričių. Skyriuje **Piltuvėlio rengyklė**, dalyje **Veiksmai** pažymi, iš kurios darbo srities turi būti atiteks piltuvėlio žingsnio duomenys.

## <a name="manage-funnel-reports"></a>Tvarkyti piltuvėlio ataskaitas

Galite peržiūrėti piltuvėlio ataskaitas, analizuoti duomenis, sekti efektyvumą ir rinkti įžvalgas.

> [!NOTE]
> - Įtraukimo įžvalgų piltuvėlio ataskaitos šiuo metu palaiko scenarijus, kai visi piltuvėlio vartotojai yra anoniminiai arba autentifikuojami visi vartotojai. 
> - Piltuvėlio ataskaitų istoriniai duomenys pasiekiami per paskutines 30 dienų.

### <a name="view-funnel-reports"></a>Peržiūrėti piltuvėlio ataskaitas

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką.
1. Pažymėkite pavadinimą, kurį norite atidaryti.    

### <a name="see-the-data-collected-for-a-report"></a>Peržiūrėkite surinktus ataskaitos duomenis   

Norėdami peržiūrėti informaciją apie etapą

- Nukreipkite žymiklį į ataskaitos žingsnį.

:::image type="content" source="media/funnel-step-data.png" alt-text="piltuvėlio duomenys.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Piltuvėlio ataskaitos datų diapazono keitimas

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką.

1. Pažymėkite pavadinimą, kurį norite atidaryti.

1. Atidarykite **laiko intervalą** ir sąraše arba Fiksuotos datos intervale pasirinkite naują laiko **periodą ir nurodykite** datų intervalą.

## <a name="edit-or-delete-funnel-reports"></a>Piltuvėlio ataskaitų redagavimas arba naikinimas

Piltuvėlio ataskaitos pavadinimą galite keisti, panaikinti arba modifikuoti ataskaitos veiksmus.

### <a name="rename-or-delete-a-funnel-report"></a>Piltuvėlio ataskaitos pervardijimas arba naikinimas

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką. 

1. Šalia **ataskaitos**, kurią norite keisti, pasirinkite Daugiau ir pasirinkite **Redaguoti pavadinimą** arba **Naikinti**.

### <a name="edit-a-funnel-step"></a>Piltuvėlio žingsnio redagavimas  

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką. 

1. Pažymėkite pavadinimą, kurį norite atidaryti.

1. Pasirinkite redaguotiną veiksmą.

1. Pasirinkite **Redaguoti**.

1. **Piltuvėlio rengyklėje** atnaujinkite norimą keisti informaciją.  

1. Pasirinkite **Įrašyti**.

### <a name="reorder-a-funnel-step"></a>Piltuvėlio žingsnio naujas redagavimas

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką. 

1. Pažymėkite pavadinimą, kurį norite atidaryti.

1. Pasirinkite naujai redaguotiną veiksmą.

1. Rinkitės **Perkelti** ir tada **Aukštyn**, **Žemyn**, **Į viršų** ar **Į apačią**, kad perkeltumėte žingsnį.

### <a name="delete-a-funnel-step"></a>Naikinti piltuvėlio veiksmą

1. Norėdami atidaryti **piltuvėlio** biblioteką, **eikite į piltuvėlio** biblioteką. 

1. Pažymėkite pavadinimą, kurį norite atidaryti.

1. Pažymėkite norimus šalinti veiksmus, tada pašalinkite ir pasirinkite **Naikinti**.

