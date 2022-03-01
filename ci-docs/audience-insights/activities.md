---
title: Kliento veiklos
description: Nustatykite kliento vieklas ir peržiūrėkite jas kliento laiko juostoje.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667239"
---
# <a name="customer-activities"></a>Kliento veiklos

Derinkite kliento veiklas per [įvairius duomenų šaltinius](data-sources.md) „Dynamics 365 Customer Insights“ norėdami sukurti kliento laiko juostą, kurioje pateiktos veiklos chronologine tvarka. Galite įtraukti laiko planavimo juostą į klientų įtraukimo programas, esančias „Dynamics 365”, per [Kliento kortelės papildinį](customer-card-add-in.md) arba „Power BI” ataskaitų sritį.

## <a name="define-an-activity"></a>Veiklos apibrėžimas

Jūsų duomenų šaltiniuose yra objektų su operacijų ir veiklos duomenimis iš kelių duomenų šaltinių. Identifikuokite šiuos objektus ir pasirinkite veiklas, kurias norite peržiūrėti kliento laiko planavimo juostoje. Pasirinkite objektą, kuriame yra jūsų tikslinė veikla arba veiklos.

1. Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.

1. Pasirinkti **Įtraukti veiklą**.

   > [!NOTE]
   > Objekte turi būti bent vienas **Data** tipo atributas, kurį reikia įtraukti į kliento planavimo juostą; negalite įtraukti objektų be **Data** laukų. Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.

1. Srityje **įtraukti veiklą** nustatykite šių laukų reikšmes:

   - **Objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.
   - **Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.
   - **Laiko žyma**: pasirinkite lauką, kuris nurodo veiklos pradžios laiką.
   - **Įvykis**: pasirinkite lauką, kuris yra veiklos įvykis.
   - **Žiniatinklio adresas**: pažymėkite lauką, kuris nurodo URL, skirtą papildomai informacijai apie šią veiklą. Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai. Šis URL gali būti bet kuris laukas iš duomenų šaltinio arba jį galima sukurti kaip naują lauką naudojant „Power Query“ transformaciją. Šie URL duomenys bus saugomi vieningosios veiklos objekte, kurį galima pasiekti naudojant API.
   - **Išsami informacija**: (pasirinktinai) pasirinkite lauką, įtrauktą į papildomą išsamią informaciją.
   - **Piktograma**: (pasirinktinai) pasirinkite piktogramą, vaizduojančią šią veiklą.
   - **Veiklos tipas**: nustatykite veiklos tipo nuorodą į „Common Data Model“, kuris geriausiai atitinka veiklos semantinį apibrėžimą.

1. Skyriuje **Nustatyti ryšį** konfigūruokite išsamią informaciją, kad savo veiklos duomenis prijungtumėte prie atitinkamo kliento.

   > [!div class="mx-imgBorder"]
   > ![Objekto ryšio apibrėžimas](media/activities-entities-define.png "Objekto ryšio apibrėžimas")

    - **Veiklos objekto laukas**: pasirinkite veiklos objekto lauką, kuris bus naudojamas ryšiui su kitu objektu nustatyti.
    - **Kliento objektas**: pasirinkite atitinkamą šaltinio kliento objektą, su kuriuo bus nustatytas jūsų veiklos objekto ryšys. Galite susieti tik su tais šaltinio kliento objektais, kurie naudojami duomenų sujungimo procese.
    - **Kliento objekto laukas**: šiame lauke rodomas šaltinio kliento objekto, pasirinkto susiejimo procese, pagrindinis raktas. Šis šaltinio kliento objekto pagrindinio rakto laukas naudojamas ryšiui su veiklos objektu nustatyti.
    - **Pavadinimas**: jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas bus rodomas skaitymo režimu. Jei tokio ryšio nėra, bus sukurtas naujas ryšys su pateiktu pavadinimu.

1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

1. Puslapyje **Veiklos** pasirinkite **Vykdyti**.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="edit-an-activity"></a>Veiklos redagavimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.

2. Pasirinkite veiklos objektą, kurį norite redaguoti, ir spustelėkite **Redaguoti**. Arba galite užvesti žymiklį virš objekto eilutės ir spustelėti piktogramą **Redaguoti**.

3. Spustelėkite piktogramą **Redaguoti**.

4. Srityje **Redaguoti veiklą** atnaujinkite reikšmes ir pasirinkite **Įrašyti**.

5. Puslapyje **Veiklos** pasirinkite **Vykdyti**.

## <a name="delete-an-activity"></a>Veiklos panaikinimas

1. Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.

2. Pasirinkite veiklos objektą, kurį norite pašalinti, ir spustelėkite **Naikinti**. Arba galite užvesti žymiklį virš objekto eilutės ir spustelėti piktogramą **Naikinti**. Be to, galite pažymėti kelis veiklos objektus, kuriuos norite panaikinti vienu metu.
   > [!div class="mx-imgBorder"]
   > ![Objekto ryšio redagavimas arba naikinimas](media/activities-entities-edit-delete.png "Objekto ryšio redagavimas arba naikinimas")

3. Spustelėkite piktogramą **Naikinti**.

4. Patvirtinkite šį naikinimą.
