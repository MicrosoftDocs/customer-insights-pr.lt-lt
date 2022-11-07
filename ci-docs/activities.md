---
title: Klientų arba verslo kontaktų veikla
description: Apibrėžkite klientų arba verslo kontaktų veiklas ir peržiūrėkite jas klientų profilių laiko planavimo juostoje.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723791"
---
# <a name="customer-or-business-contact-activities"></a>Klientų arba verslo kontaktų veikla

Klientų veikla yra klientų ar verslo kontaktų atliekami veiksmai ar įvykiai. Pavyzdžiui, operacijos, palaikymo skambučio trukmė, svetainės apžvalgos, pirkimai ar grąžinimai. Ši veikla pateikiama viename ar keliuose duomenų šaltiniuose. Naudodami "Customer Insights" sujunkite savo klientų veiklą iš šių [duomenų šaltinių](data-sources.md) ir susiekite ją su klientų profiliais. Šios veiklos rodomos chronologine tvarka kliento profilio laiko planavimo juostoje. Įtraukite laiko planavimo juostą į "Dynamics 365" programas naudodami ["Customer Card" papildinio](customer-card-add-in.md) sprendimą.

## <a name="define-a-customer-activity"></a>Kliento veiklos apibrėžimas

Objektas turi turėti bent vieną atributą, kurio tipas **Date** turi būti įtrauktas į kliento laiko planavimo juostą. Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.

1. Eikite į **Duomenų** > **veikla**.

1. Pasirinkite **Pridėti veiklos**, kad pradėtumėte vadovaujamą patirtį.

1. **Atlikdami veiksmą Veiklos duomenys** įveskite šią informaciją:

   - **Veiklos pavadinimas**: pasirinkite savo veiklos pavadinimą.
   - **Veiklos objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.
   - **Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

     > [!NOTE]
     > Kiekvienos eilutės pirminis raktas turi išlikti nuoseklus visuose duomenų šaltinis atnaujinimuose. Jei eilutės pirminis raktas atnaujinamas duomenų šaltinis atnaujinimo metu, jis sukuria dublikatus išvesties veiklos objekte. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nustatykite veiklos duomenis su pavadinimu, objektu ir pagrindiniu raktu.":::

1. Pasirinkite **Toliau**.

1. **Ryšio** veiksme pasirinkite **Įtraukti ryšį**, kad susietumėte savo veiklos duomenis su atitinkamu kliento įrašu. Šiuo veiksmu vaizduojamas objektų ryšys.  

   - **Užsienio raktas**: jūsų veiklos objekto laukas Užsienis, kuris bus naudojamas ryšiui su kitu subjektu užmegzti.
   - **Į objekto pavadinimą**: atitinkamas šaltinio kliento objektas, su kuriuo bus susijęs jūsų veiklos objektas. Ryšį galite nustatyti tik su tais šaltinio kliento objektais, kurie naudojami duomenų suvienodinimo procese.
   - **Ryšio pavadinimas: jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas** bus tik skaitymo režimu. Jei tokio ryšio nėra, bus sukurtas naujas ryšys tokiu pavadinimu, kurį pateikiate šiame lauke.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Objekto ryšio apibrėžimas.":::

   > [!TIP]
   > B2B aplinkose galite pažymėti kliento objektus ir kitus objektus. Jei pažymėsite kliento objektą, ryšio kelias bus nustatomas automatiškai. Kitiems objektams turite nustatyti ryšio kelią virš vieno ar daugiau objektų, kol pasieksite kliento objektą.

1. Pasirinkite **Taikyti**, kad sukurtumėte ryšį.

1. Pasirinkite **Toliau**.

1. **Veiklos suvienodinimo** žingsnyje pasirinkite veiklos įvykį ir veiklos pradžios laiką.
   - **Būtini laukai**
      - **Įvykio veikla**: laukelis, kuris yra šios veiklos įvykis.
      - **Laiko žyma**: laukelis, nurodantis jūsų veiklos pradžios laiką.

   - **Pasirinktiniai laukai**
      - **Papildoma informacija**: laukelis su svarbia šios veiklos informacija.
      - **Piktograma:** piktograma, geriausiai atspindinti šį veiklos tipą.
      - **Žiniatinklio adresas**: laukelis, kuriame yra URL su informacija apie šią veiklą. Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai. Šis URL gali būti bet kuris laukas iš duomenų šaltinis arba jis gali būti sukurtas kaip naujas laukas naudojant transformaciją Power Query. URL duomenys bus išsaugoti *Unified Activity* objektui, kurį galima naudoti tolesniuose srautuose naudojant [API](apis.md).

   - **Rodyti laiko planavimo juostoje**
      - Pasirinkite, jei norite rodyti šią veiklą jūsų klientų profilių laiko planavimo juostos rodinyje. Pasirinkite **Taip**, jei norite rodyti veiklą laiko planavimo uostoje, arba **Ne**, jei ją norite paslėpti.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Kliento veiklos duomenis nurodykite „Unified Activity“ objekte.":::

1. Pasirinkite **Pirmyn**, kad pasirinktumėte veiklos tipą, arba pasirinkite **Baigti ir peržiūrėti**, kad įrašytumėte veiklą, kurios veiklos tipas nustatytas kaip **Kita**.

1. Žingsnyje **Veiklos tipas** pasirinkite veiklos tipą ir pasirinktinai pažymėkite, ar norite po kelis veiklos tipus susieti ir naudoti kitose „Customer Insights“ srityse. *Šiuo* metu atsiliepimų, lojalumo *,* *"SalesOrder* *", "SalesOrderLine"* ir *prenumeratos* veiklos tipai palaiko semantiką sutikus susieti laukus. Jei veiklos tipas nėra aktualus naujai veiklai, galite pasirinkti *Kita* arba *Kurti naują* pasirinktinio veiklos tipo atveju.

1. Pasirinkite **Toliau**.

1. Žingsnyje **Atsiliepimas** patikrinkite savo pasirinkimus. Grįžkite prie bet kurio iš ankstesnių veiksmų ir prireikus atnaujinkite informaciją.

1. Pasirinkite **Įrašyti veiklą**, kad pritaikytumėte pakeitimus, ir pasirinkite **Atlikta**, kad grįžtumėte prie **Duomenys** > **Veikla**. Rodoma sukurta veikla.

1. Sukūrę visas savo veiklas, pasirinkite **Vykdyti**, kad jas apdorotumėte.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Valdykite esamą klientų veiklą

Eikite į Duomenų veiklos, kad peržiūrėtumėte įrašytas veiklas, jų šaltinio objektą, veiklos **tipą ir tai, ar jos įtrauktos į** > **kliento** laiko planavimo juostą. Galite rūšiuoti veiklų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte norimą tvarkyti veiklą.

Pasirinkite veiklą, kad peržiūrėtumėte galimus veiksmus.

- **Redaguokite** veiklą, kad pakeistumėte jos konfigūraciją. Konfigūracija atidaroma peržiūros veiksme. Pakeitę konfigūraciją, pasirinkite **Įrašyti veiklą**, tada pasirinkite **Vykdyti**, kad būtų apdoroti pakeitimai.
- **Pervardykite** veiklą. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.
- **Ištrinkite** veiklą. Norėdami vienu metu panaikinti daugiau nei vieną veiklą, pasirinkite veiklas, tada – **Naikinti**. Patvirtinkite naikinimą.

## <a name="view-activity-timelines-on-customer-profiles"></a>Veiklos laiko planavimo juostų rodinys klientų profiliuose

1. Jei veiklos konfigūracijoje pasirinkote **Rodyti veiklos laiko planavimo juostoje, eikite į** Klientai **ir pasirinkite kliento profilį, kad peržiūrėtumėte kliento veiklą** skyriuje Veiklos laiko planavimo **juosta**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Peržiūrėkite sukonfigūruotas veiklas klientų profiliuose.":::

1. Norėdami filtruoti veiklą veiklos laiko planavimo juostoje:

   - Pasirinkite vieną ar daugiau veiklos piktogramų, kad patikslintumėte rezultatus ir įtrauktumėte tik pasirinktus tipus.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtruoti veiklas pagal tipą naudojant piktogramas.":::

   - Pasirinkite **Filtras**, kad atidarytumėte filtrų skydelį ir sukonfigūruotumėte laiko planavimo juostos filtrus. Filtruokite pagal *"ActivityType"* ir (arba *) datą*. Pasirinkite **Taikyti**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Naudodami filtrų skydą konfigūruokite filtravimo sąlygas.":::

> [!NOTE]
> Veiklos filtrai pašalinami išeidami iš kliento profilio. Turite juos taikyti kiekvieną kartą, kai atidarote kliento profilį.

## <a name="define-a-contact-activity"></a>Kontaktinės veiklos apibrėžimas

Verslo paskyroms (nuo B iki B) naudokite *objektą ContactProfile*, kad užfiksuotumėte kontaktų veiklą. Paskyros, už kurią kontaktas buvo atsakingas už kiekvieną veiklą, veiklos laiko planavimo juostoje galite matyti. Dauguma veiksmų atliekami pagal klientų veiklos susiejimo konfigūraciją.

   > [!NOTE]
   > Norint apibrėžti kontakto lygio veiklą, *reikia sukurti objektą ContactProfile* kaip vieningą kontakto profilį [arba naudojant](data-unification-contacts.md) semantinį [susiejimą](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Turite turėti ir AccountID, ir **ContactID** **atributus** kiekvienam veiklos duomenų įrašui.
  
1. Eikite į **Duomenų** > **veikla**.

1. Pasirinkite **Pridėti veiklos**.

1. **Atlikdami veiksmą Veiklos duomenys** įveskite šią informaciją:

   - **Veiklos pavadinimas**: pasirinkite savo veiklos pavadinimą.
   - **Veiklos objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.
   - **Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

     > [!NOTE]
     > Kiekvienos eilutės pirminis raktas turi išlikti nuoseklus visuose duomenų šaltinis atnaujinimuose. Jei eilutės pirminis raktas atnaujinamas duomenų šaltinis atnaujinimo metu, jis sukuria dublikatus išvesties veiklos objekte. 


1. **Atlikdami veiksmą Ryšiai** sukurkite netiesioginį ryšį tarp veiklos šaltinio duomenų ir paskyrų, naudodami kontaktinius duomenis kaip tarpinį objektą. Daugiau informacijos ieškokite [tiesioginio ir netiesioginio ryšio keliuose](relationships.md#relationship-paths).
   - Veiklos, vadinamos *Pirkimai,* ryšio pavyzdys:
      - **Pirkimo šaltinio veiklos duomenys Kontaktiniai duomenys** > **atribute** **ContactID**
      - **Kontaktinių duomenų** > **paskyros duomenys**, esantys atribute **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ryšių nustatymo pavyzdys.":::

1. Nustatę ryšius pasirinkite **Pirmyn** ir užbaikite veiklos susiejimo konfigūraciją. Išsamių veiklos kūrimo veiksmų ieškokite [kliento veiklos](#define-a-customer-activity) apibrėžimas.

1. Paleiskite veiklos susiejimus.

1. Jūsų kontaktų lygio veikla dabar bus matoma jūsų klientų laiko planavimo juostoje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Galutinis rezultatas sukonfigūravus kontaktines veiklas":::

## <a name="contact-level-activity-timeline-filtering"></a>Kontaktų lygio veiklos laiko planavimo juostos filtravimas

Sukonfigūravus kontaktų lygio veiklos susiejimą ir jį paleidus, jūsų klientų veiklos laiko planavimo juosta bus atnaujinta. Tai apima jų ID arba vardus, atsižvelgiant į jūsų *"ContactProfile"* konfigūraciją, skirtą veiklai, kurią jie vykdė. Galite filtruoti veiklą pagal kontaktus laiko planavimo juostoje, kad pamatytumėte konkrečius jus dominančius kontaktus. Be to, galite matyti visas veiklas, kurios nėra priskirtos konkrečiam kontaktui, pasirinkdami **Veikla, nesusieta su kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Galimos kontaktų lygio veiklos filtravimo parinktys.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
