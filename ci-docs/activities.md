---
title: Klientų arba verslo kontaktinė veikla
description: Apibrėžkite klientų arba verslo kontaktų veiklą ir peržiūrėkite jas klientų profilių laiko juostoje.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
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
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304115"
---
# <a name="customer-or-business-contact-activities"></a>Klientų arba verslo kontaktinė veikla

Klientų veikla yra veiksmai ar įvykiai, kuriuos atlieka klientai arba verslo kontaktai. Pavyzdžiui, operacijos, palaikymo skambučio trukmė, svetainių apžvalgos, pirkiniai ar grąžinimai. Ši veikla pateikiama viename ar keliuose duomenų šaltiniuose. Naudodami "Customer Insights" suaktyvinkite savo klientų veiklą iš šių [duomenų šaltinių](data-sources.md) ir susiekite jas su klientų profiliais. Šios veiklos rodomos chronologiškai kliento profilio laiko juostoje. Įtraukite laiko planavimo juostą į "Dynamics 365" programas naudodami ["Customer Card" papildinio](customer-card-add-in.md) sprendimą.

## <a name="define-a-customer-activity"></a>Kliento veiklos apibrėžimas

Objektas turi turėti bent vieną tipo **datos** atributą, kad būtų įtrauktas į kliento laiko planavimo juostą. Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.

1. Eikite į **Duomenų** > **veikla**.

1. Pasirinkite **Įtraukti veiklos**, kad pradėtumėte vadovaujamą patirtį.

1. Atlikdami veiksmą **Veiklos duomenys** įveskite šią informaciją:

   - **Veiklos pavadinimas**: pasirinkite savo veiklos pavadinimą.
   - **Veiklos objektas**: pasirinkite objektą, į kurį įtraukti operacijų arba veiklos duomenys.
   - **Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nustatykite veiklos duomenis su pavadinimu, objektu ir pagrindiniu raktu.":::

1. Pasirinkite **Toliau**.

1. Atlikdami ryšio **veiksmą** pasirinkite Įtraukti ryšį **,** kad prijungtumėte savo veiklos duomenis prie atitinkamo kliento įrašo. Šiuo veiksmu vaizduojamas objektų ryšys.  

   - **Užsienio raktas**: užsienio laukas jūsų veiklos objekte, kuris bus naudojamas ryšiui su kitu objektu užmegzti.
   - **Objekto pavadinimas**: atitinkamas šaltinio kliento objektas, su kuriuo bus susijęs jūsų veiklos objektas. Ryšį galite nustatyti tik su tais šaltinio kliento objektais, kurie naudojami duomenų suvienodinimo procese.
   - **Ryšio pavadinimas**: jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau egzistuoja, ryšio pavadinimas veiks tik skaitymo režimu. Jei tokio ryšio nėra, bus sukurtas naujas ryšys tokiu pavadinimu, kurį pateikiate šiame lauke.

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
      - **Žiniatinklio adresas**: laukelis, kuriame yra URL su informacija apie šią veiklą. Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai. Šis URL gali būti bet kuris laukas iš duomenų šaltinis arba jis gali būti konstruojamas kaip naujas laukas naudojant transformaciją Power Query. URL duomenys bus išsaugoti *Unified Activity* objektui, kurį galima naudoti tolesniuose srautuose naudojant [API](apis.md).

   - **Rodyti laiko planavimo juostoje**
      - Pasirinkite, jei norite rodyti šią veiklą jūsų klientų profilių laiko planavimo juostos rodinyje. Pasirinkite **Taip**, jei norite rodyti veiklą laiko planavimo uostoje, arba **Ne**, jei ją norite paslėpti.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Kliento veiklos duomenis nurodykite „Unified Activity“ objekte.":::

1. Pasirinkite **Pirmyn**, kad pasirinktumėte veiklos tipą, arba pasirinkite **Baigti ir peržiūrėti**, kad įrašytumėte veiklą, kai veiklos tipas nustatytas kaip **Kita**.

1. Žingsnyje **Veiklos tipas** pasirinkite veiklos tipą ir pasirinktinai pažymėkite, ar norite po kelis veiklos tipus susieti ir naudoti kitose „Customer Insights“ srityse. Šiuo metu atsiliepimų *,* *lojalumo*, *pardavimo užsakymo*, *"SalesOrderLine"* ir *prenumeratos* veiklos tipai palaiko semantiką, sutikus susieti laukus. Jei veiklos tipas nėra aktualus naujai veiklai, galite pasirinkti *Kita* arba *Kurti naują* pasirinktinio veiklos tipo atveju.

1. Pasirinkite **Toliau**.

1. Žingsnyje **Atsiliepimas** patikrinkite savo pasirinkimus. Grįžkite prie bet kurio iš ankstesnių veiksmų ir prireikus atnaujinkite informaciją.

1. Pasirinkite **Įrašyti veiklą**, kad pritaikytumėte pakeitimus, ir pasirinkite **Atlikta**, kad grįžtumėte prie **Duomenys** > **Veikla**. Rodoma sukurta veikla.

1. Sukūrę visą savo veiklą, pasirinkite **Vykdyti**, kad ją apdorotumėte.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Esamos klientų veiklos valdymas

Eikite į **Duomenų** > **veiklas**, kad peržiūrėtumėte įrašytą veiklą, šaltinio objektą, veiklos tipą ir, jei jos įtrauktos į kliento laiko planavimo juostą. Galite rūšiuoti veiklų sąrašą pagal bet kurį stulpelį arba naudoti ieškos lauką, kad rastumėte norimą valdyti veiklą.

Pasirinkite veiklą, kad peržiūrėtumėte galimus veiksmus.

- **Redaguokite** veiklą, kad pakeistumėte jos konfigūraciją. Konfigūracija atidaroma atliekant peržiūros veiksmą. Pakeitę konfigūraciją, pasirinkite **Įrašyti veiklą**, tada pasirinkite **Vykdyti**, kad būtų apdoroti pakeitimai.
- **Pervardykite** veiklą. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.
- **Ištrinkite** veiklą. Norėdami panaikinti daugiau nei vieną veiklą vienu metu, pasirinkite veiklą, tada – **Naikinti**. Patvirtinkite naikinimą.

## <a name="view-activity-timelines-on-customer-profiles"></a>Veiklos laiko planavimo juostų rodinys klientų profiliuose

1. Jei veiklos konfigūracijoje pasirinkote **Rodyti veiklos laiko planavimo juostoje**, eikite į **Klientai** ir pasirinkite kliento profilį, kad peržiūrėtumėte kliento veiklą **skyriuje Veiklos laiko planavimo juosta**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Peržiūrėkite sukonfigūruotas veiklas klientų profiliuose.":::

1. Norėdami filtruoti veiklą veiklos laiko planavimo juostoje:

   - Pasirinkite vieną ar daugiau veiklos piktogramų, kad patikslintumėte rezultatus, kad įtrauktumėte tik pasirinktus tipus.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtruoti veiklas pagal tipą naudojant piktogramas.":::

   - Pasirinkite **Filtras**, kad atidarytumėte filtro skydelį, kad sukonfigūruotumėte laiko planavimo juostos filtrus. Filtruokite pagal *"ActivityType" ir (* arba) *datą*. Pasirinkite **Taikyti**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Naudodami filtrų skydą konfigūruokite filtravimo sąlygas.":::

> [!NOTE]
> Veiklos filtrai pašalinami išeidami iš kliento profilio. Turite juos taikyti kiekvieną kartą, kai atidarote kliento profilį.

## <a name="define-a-contact-activity"></a>Kontakto veiklos apibrėžimas

Jei naudojate verslo paskyras (nuo B iki B), naudokite "ContactProfile *" objektą*, kad užfiksuotumėte kontaktų veiklą. Paskyros veiklos laiko juostoje galite matyti, kuris kontaktas buvo atsakingas už kiekvieną veiklą. Dauguma veiksmų atliekami pagal klientų veiklos susiejimo konfigūraciją.

   > [!NOTE]
   > Norint apibrėžti kontakto lygio veiklą, *"ContactProfile* " objektas turi būti sukurtas kaip vieningas [kontakto profilis](data-unification-contacts.md) arba per [semantinį susiejimą](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Kiekvienam įrašui savo veiklos duomenyse turite turėti **ir kliento ID**, ir **contactID** atributus.
  
1. Eikite į **Duomenų** > **veikla**.

1. Pasirinkite **Pridėti veiklos**.

1. Pavadinkite veiklą, pasirinkite šaltinio veiklos objektą ir pasirinkite pirminį veiklos objekto raktą.

1. Atlikdami veiksmą **Ryšiai** sukurkite netiesioginį ryšį tarp savo veiklos šaltinio duomenų su klientais, naudodami savo kontaktinius duomenis kaip tarpinį objektą. Norėdami gauti daugiau informacijos, žiūrėkite [tiesioginių ir netiesioginių ryšių kelius](relationships.md#relationship-paths).
   - Veiklos, vadinamos *Pirkimais*, ryšio pavyzdys:
      - **Pirkimai Šaltinio veiklos duomenys** > **Kontaktiniai duomenys** atribute **ContactID**
      - **Kontaktiniai duomenų** > **paskyros duomenys** atribute **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ryšio sąrankos pavyzdys.":::

1. Nustatę ryšius, pasirinkite **Pirmyn** ir užbaikite veiklos susiejimo konfigūraciją. Išsamių veiklos kūrimo veiksmų ieškokite [kliento veiklos](#define-a-customer-activity) apibrėžime.

1. Paleiskite veiklos susiejimas.

1. Jūsų kontakto lygio veikla dabar bus matoma kliento laiko juostoje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Galutinis rezultatas sukonfigūravus kontaktinę veiklą":::

## <a name="contact-level-activity-timeline-filtering"></a>Kontakto lygio veiklos laiko planavimo juostos filtravimas

Sukonfigūravus kontakto lygio veiklos susiejimą ir jį paleidus, jūsų klientų veiklos laiko juosta bus atnaujinta. Tai apima jų ID arba pavadinimus, atsižvelgiant į jūsų *"ContactProfile* " konfigūraciją, skirtą veiklai, kurią jie veikė. Laiko planavimo juostoje galite filtruoti veiklą pagal kontaktus, kad pamatytumėte konkrečius jus dominančius kontaktus. Be to, galite matyti visas veiklas, kurios nepriskirtos konkrečiam kontaktui, pasirinkdami **Veikla, nesusieta su kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Galimos kontakto lygio veiklos filtravimo parinktys.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
