---
title: Kliento veiklos
description: Apibrėžkite klientų veiklas ir peržiūrėkite jas klientų profilių laiko planavimo juostose.
ms.date: 09/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c5697df8a7d011c70384c8bc5e4773d7fcc25a62
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494421"
---
# <a name="customer-activities"></a>Kliento veiklos

Suderinkite kliento veiklą iš [įvairių duomenų šaltinių](data-sources.md) sistemoje Dynamics 365 Customer Insights, kad sukurtumėte laiko juostą, kurioje veiklos sąrašas pateikiamas chronologine tvarka. Laiko planavimo juostą įtraukite į „Dynamics 365“ programas naudodami sprendimą [Kliento kortelės priedas](customer-card-add-in.md) arba Power BI ataskaitų sritį.

## <a name="define-an-activity"></a>Veiklos apibrėžimas

Jūsų duomenų šaltiniuose gali būti objektų su operacijų ir veiklos duomenimis iš kelių duomenų šaltinių. Identifikuokite šiuos objektus ir pasirinkite veiklas, kurias norite peržiūrėti kliento laiko planavimo juostoje. Pasirinkite objektą, kuriame yra jūsų tikslinė veikla arba veiklos.

> [!NOTE]
> Objekte turi būti bent vienas **Data** tipo atributas, kurį reikia įtraukti į kliento planavimo juostą; negalite įtraukti objektų be **Data** laukų. Valdiklis **Įtraukti veiklą** yra išjungtas, jei nerastas toks objektas.

1. Publikos įžvalgose, eikite į **Duomenys** > **Veiklos**.

1. Pasirinkite **Pridėti veiklą**, jei norite pradėti valdomą patirtį veiklos nustatymo procesui.

1. Žingsnyje **Veiklos duomenys** nustatykite šių laukelių reikšmes:

   - **Veiklos pavadinimas**: pasirinkite savo veiklos pavadinimą.
   - **Objektas**: pasirinkite objektą, kuriame yra operacijų arba veiklos duomenų.
   - **Pirminis raktas**: pasirinkite lauką, kuris identifikuoja unikalų įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Nustatykite veiklos duomenis su pavadinimu, objektu ir pagrindiniu raktu.":::

1. Norėdami pereiti prie kito veiksmo, pasinkite **Toliau**.

1. Atlikdami veiksmą **Santykis** konfigūruokite išsamią informaciją, kad veiklos duomenys būtų susieti su atitinkamu klientu. Šiuo veiksmu vaizduojamas objektų ryšys.  

   - **Pirma:** veiklos objekto, kuris bus naudojamas ryšiui su kitu objektu užmegzti, laukelis „Svetimas“.
   - **Antra:** atitinkamas šaltinio kliento objektas, su kuriuo sąveikaus jūsų veiklos objektas. Ryšį galite nustatyti tik su tais šaltinio kliento objektais, kurie naudojami duomenų suvienodinimo procese.
   - **Trečia:** jei ryšys tarp šio veiklos objekto ir pasirinkto šaltinio kliento objekto jau yra, ryšio pavadinimas veiks tik skaitymo režimu. Jei tokio ryšio nėra, bus sukurtas naujas ryšys tokiu pavadinimu, kurį pateikiate šiame lauke.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Objekto ryšio apibrėžimas.":::

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

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.


## <a name="manage-existing-activities"></a>Esamos veiklos tvarkymas

Srityje **Duomenys** > **Veikla** galite peržiūrėti visas įrašytas veiklas ir jas valdyti. Kiekvienai veiklai skiriama eilutė, kurioje taip pat pateikiama išsami informacija apie šaltinį, objektą ir veiklos tipą.

Pasirinkus veiklą galimi nurodyti veiksmai. 

- **Redaguoti**: peržiūros žingsnyje atidaro veiklos sąranką. Atlikdami šį veiksmą galite keisti bet kurią arba visą dabartinę konfigūraciją. Pakeitę konfigūraciją, pasirinkite **Įrašyti veiklą**, tada pasirinkite **Vykdyti**, kad būtų apdoroti pakeitimai.

- **Pervardykite**: atidaromas dialogas, kuriame galite įvesti kitą pažymėtos veiklos pavadinimą. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

- **Trinti**: atidaro dialogą, kad patvirtintų pažymėtos veiklos trynimą. Taip pat iš karto galite ištrinti daugiau nei vieną veiklą, pažymėdami veiklas ir pažymėdami trynimo piktogramą. Pasirinkite **Trinti** ir patvirtinkite ištrynimą.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
