---
title: Kliento veiklos
description: Apibrėžkite klientų veiklas ir peržiūrėkite jas klientų profilių laiko planavimo juostose.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c99ec2e7d5e4bf32a509bbe4c0c53999129b2305
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732470"
---
# <a name="customer-activities"></a>Kliento veiklos

Sujunkite klientų veiklas iš [įvairių duomenų šaltinių į](data-sources.md) Dynamics 365 Customer Insights, kad sukurtumėte laiko planavimo juostą, kurioje veiklos išvardytos chronologiškai. Įtraukite laiko planavimo juostą į "Dynamics 365" programas naudodami [kliento kortelės priedo sprendimą arba Power BI ataskaitų](customer-card-add-in.md) sritį.

## <a name="define-an-activity"></a>Veiklos apibrėžimas

Jūsų duomenų šaltiniuose gali būti objektų su operacijų ir veiklos duomenimis iš kelių duomenų šaltinių. Identifikuokite šiuos objektus ir pasirinkite veiklas, kurias norite peržiūrėti kliento laiko planavimo juostoje. Pasirinkite objektą, kuriame yra jūsų tikslinė veikla arba veiklos.

Objekte turi būti bent vienas **Data** tipo atributas, kurį reikia įtraukti į kliento planavimo juostą; negalite įtraukti objektų be **Data** laukų. Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.

1. Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.

1. Pasirinkite **Pridėti veiklą**, jei norite pradėti valdomą patirtį veiklos nustatymo procesui.

1. Žingsnyje **Veiklos duomenys** nustatykite šių laukelių reikšmes:

   - **Veiklos pavadinimas**: pasirinkite savo veiklos pavadinimą.
   - **Objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.
   - **Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nustatykite veiklos duomenis su pavadinimu, objektu ir pagrindiniu raktu.":::

1. Norėdami pereiti prie kito veiksmo, pasinkite **Toliau**.

1. Ryšių **žingsnyje** konfigūruokite išsamią informaciją, kad veiklos duomenys būtų susieti su atitinkamo kliento įrašu. Šiuo veiksmu vaizduojamas objektų ryšys.  

   - **Pirma:** veiklos objekto, kuris bus naudojamas ryšiui su kitu objektu užmegzti, laukelis „Svetimas“.
   - **Antra:** atitinkamas šaltinio kliento objektas, su kuriuo sąveikaus jūsų veiklos objektas. Ryšį galite nustatyti tik su tais šaltinio kliento objektais, kurie naudojami duomenų suvienodinimo procese.
   - **Trečia:** jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas veiks tik skaitymo režimu. Jei tokio ryšio nėra, bus sukurtas naujas ryšys tokiu pavadinimu, kurį pateikiate šiame lauke.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Objekto ryšio apibrėžimas.":::

   > [!TIP]
   > B2B aplinkose galite pažymėti kliento objektus ir kitus objektus. Jei pažymėsite kliento objektą, ryšio kelias bus nustatomas automatiškai. Kitiems objektams turite nustatyti ryšio kelią virš vieno ar daugiau objektų, kol pasieksite kliento objektą.

1. Norėdami pereiti prie kito veiksmo, pasinkite **Toliau**. 

1. **Veiklos suvienodinimo** žingsnyje pasirinkite veiklos įvykį ir veiklos pradžios laiką. 
   - **Būtini laukai**
      - **Įvykio veikla**: laukelis, kuris yra šios veiklos įvykis.
      - **Laiko žyma**: laukelis, nurodantis jūsų veiklos pradžios laiką.

   - **Pasirinktiniai laukai**
      - **Papildoma informacija**: laukelis su svarbia šios veiklos informacija.
      - **Piktograma:** piktograma, geriausiai atspindinti šį veiklos tipą.
      - **Žiniatinklio adresas**: laukelis, kuriame yra URL su informacija apie šią veiklą. Pavyzdžiui, tai gali būti operacijų sistema, skirta šiai veiklai. Šis URL gali būti bet kuris laukas iš duomenų šaltinio arba jį galima sukurti kaip naują lauką naudojant „Power Query“ transformaciją. URL duomenys bus išsaugoti *Unified Activity* objektui, kurį galima naudoti tolesniuose srautuose naudojant [API](apis.md).

   - **Rodyti laiko planavimo juostoje**
      - Pasirinkite, jei norite rodyti šią veiklą jūsų klientų profilių laiko planavimo juostos rodinyje. Pasirinkite **Taip**, jei norite rodyti veiklą laiko planavimo uostoje, arba **Ne**, jei ją norite paslėpti.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Kliento veiklos duomenis nurodykite „Unified Activity“ objekte.":::

1. Norėdami pereiti prie kito veiksmo, pasirinkite **Pirmyn**. Galite pažymėti **Baigti ir peržiūrėti**, kad veiklą įrašytumėte dabar, kai veiklos tipas nustatytas kaip **Kitas**. 

1. Žingsnyje **Veiklos tipas** pasirinkite veiklos tipą ir pasirinktinai pažymėkite, ar norite po kelis veiklos tipus susieti ir naudoti kitose „Customer Insights“ srityse. Šiuo metu *Atsiliepimo*, *Lojalumo*, *Pardavimo užsakymo*, *Pardavimo užsakymo eilutės* ir *Prenumeratos* veiklos tipus galima semantiškai susieti po to, kai sutiksite susieti laukus. Jei veiklos tipas nėra aktualus naujai veiklai, galite pasirinkti *Kita* arba *Kurti naują* pasirinktinio veiklos tipo atveju.

1. Norėdami pereiti prie kito veiksmo, pasirinkite **Pirmyn**. 

1. Žingsnyje **Atsiliepimas** patikrinkite savo pasirinkimus. Grįžkite prie bet kurio iš ankstesnių veiksmų ir prireikus atnaujinkite informaciją.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Peržiūrėkite nurodytus veiklos laukelius.":::
   
1. Pasirinkite **Įrašyti veiklą**, kad pritaikytumėte pakeitimus, ir pasirinkite **Atlikta**, kad grįžtumėte prie **Duomenys** > **Veikla**. Čia matote, kurios veiklos nustatytos būti rodomos laiko planavimo juostoje. 

1. Puslapyje **Veiklos** pasirinkite **Vykdyti**, kad apdorotumėte veiklą. 

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Esamos veiklos tvarkymas

Srityje **Duomenys** > **Veikla** galite peržiūrėti visas įrašytas veiklas ir jas valdyti. Kiekvienai veiklai skiriama eilutė, kurioje taip pat pateikiama išsami informacija apie šaltinį, objektą ir veiklos tipą.

Pasirinkus veiklą galimi nurodyti veiksmai. 

- **Redaguoti**: peržiūros žingsnyje atidaro veiklos sąranką. Atlikdami šį veiksmą galite keisti bet kurią arba visą dabartinę konfigūraciją. Pakeitę konfigūraciją, pasirinkite **Įrašyti veiklą**, tada pasirinkite **Vykdyti**, kad būtų apdoroti pakeitimai.

- **Pervardykite**: atidaromas dialogas, kuriame galite įvesti kitą pažymėtos veiklos pavadinimą. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

- **Trinti**: atidaro dialogą, kad patvirtintų pažymėtos veiklos trynimą. Taip pat iš karto galite ištrinti daugiau nei vieną veiklą, pažymėdami veiklas ir pažymėdami trynimo piktogramą. Pasirinkite **Naikinti** naikinimo patvirtinimui.

## <a name="view-activity-timelines-on-customer-profiles"></a>Veiklos laiko planavimo juostų rodinys klientų profiliuose

Sukonfigūrę klientų veiklas, veiklos konfigūracijoje pasirinkite **Rodyti veiklos laiko planavimo juostoje** ir profilyje raskite visas kliento veiklas.

Norėdami atidaryti kliento laiko planavimo juostą, eikite į **Klientai** ir pasirinkite norimą peržiūrėti kliento profilį.

Jei klientas dalyvauja jūsų sukonfigūruotoje veikloje, ją rasite skyriuje **Veiklos laiko planavimo juosta**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Peržiūrėkite sukonfigūruotas veiklas klientų profiliuose.":::

Yra keli veiklos filtravimo būdai veiklos laiko planavimo juostoje:

- Galite pažymėti vieną arba daugelį veiklos piktogramų, jei norite tobulinti rezultatus ir įtraukti tik pažymėtus tipus.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtruoti veiklas pagal tipą naudojant piktogramas.":::

- Galite pažymėti **Filtras,** kad atidarytumėte filtrų skydą ir sukonfigūruotumėte laiko planavimo juostos filtrus.

   1. Galite filtruoti pagal *ActivityType* ir *Data*
   1. Pažymėkite **Taikyti**, kad būtų naudojami veiklos laiko planavimo juostos filtrai.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Naudodami filtrų skydą konfigūruokite filtravimo sąlygas.":::

Norėdami pašalinti filtrus, pažymėkite **x** šalia kiekvieno laiko planavimo juostai taikomojo filtro arba pažymėkite **Valyti filtrus**.


> [!NOTE]
> Veiklos filtrai pašalinami išeidami iš kliento profilio. Juos turite taikyti kiekvieną kartą juos atidarydami kliento profilyje.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
