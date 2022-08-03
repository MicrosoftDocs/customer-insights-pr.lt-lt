---
title: Kliento veiklos
description: Apibrėžkite klientų veiklas ir peržiūrėkite jas klientų profilių laiko planavimo juostose.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
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
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188149"
---
# <a name="customer-activities"></a>Kliento veiklos

Klientų veikla yra klientų atliekami veiksmai ar įvykiai. Pavyzdžiui, operacijos, palaikymo skambučio trukmė, svetainių apžvalgos, pirkiniai ar grąžinimai. Ši veikla pateikiama viename ar keliuose duomenų šaltiniuose. Naudodami "Customer Insights" suaktyvinkite savo klientų veiklą iš šių [duomenų šaltinių](data-sources.md) ir susiekite jas su klientų profiliais. Šios veiklos rodomos chronologiškai kliento profilio laiko juostoje. Įtraukite laiko planavimo juostą į "Dynamics 365" programas naudodami ["Customer Card" papildinio](customer-card-add-in.md) sprendimą.

## <a name="define-an-activity"></a>Veiklos apibrėžimas

Objektas turi turėti bent vieną tipo **datos** atributą, kad būtų įtrauktas į kliento laiko planavimo juostą. Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.

1. Eikite į **Duomenų** > **veikla**.

1. Pasirinkite **Įtraukti veiklos**, kad pradėtumėte vadovaujamą patirtį.

1. Atlikdami veiksmą **Veiklos duomenys** įveskite šią informaciją:

   - **Veiklos pavadinimas**: veiklos pavadinimas.
   - **Veiklos objektas**: subjektas, apimantis operacijų arba veiklos duomenis.
   - **Pirminis raktas**: laukas, kuris unikaliai identifikuoja įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nustatykite veiklos duomenis su pavadinimu, objektu ir pagrindiniu raktu.":::

1. Pasirinkite **Toliau**.

1. Atlikdami ryšio **veiksmą** pasirinkite Įtraukti ryšį **,** kad prijungtumėte savo veiklos duomenis prie atitinkamo kliento įrašo. Šiuo veiksmu vaizduojamas objektų ryšys.  

   - **Išorinis raktas iš objekto**: laukas jūsų veiklos objekte, kuris bus naudojamas ryšiui su kitu objektu užmegzti.
   - **Objekto pavadinimas**: atitinkamas šaltinio kliento objektas, su kuriuo bus susijęs jūsų veiklos objektas. Ryšį galite nustatyti tik su tais šaltinio kliento objektais, kurie naudojami duomenų suvienodinimo procese.
   - **Ryšio pavadinimas**: pavadinimas, identifikuojantis ryšį tarp objektų. Jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas yra skirtas tik skaityti.

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

## <a name="manage-existing-activities"></a>Esamos veiklos tvarkymas

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

1. Norėdami pašalinti filtrus, pasirinkite **Valyti filtrus** arba pasirinkite **Filtras** ir išvalykite žymimąjį laukelį Filtras.

> [!NOTE]
> Veiklos filtrai pašalinami išeidami iš kliento profilio. Turite juos taikyti kiekvieną kartą, kai atidarote kliento profilį.

[!INCLUDE [footer-include](includes/footer-banner.md)]
