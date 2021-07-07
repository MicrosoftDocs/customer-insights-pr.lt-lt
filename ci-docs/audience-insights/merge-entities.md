---
title: Suliekite objektus duomenų suvienyjime
description: Suliekite objektus tam, kad sukurtumėte suvienytus kliento profilius.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305658"
---
# <a name="merge-entities"></a>Suliekite objektus

Suliejimo etapas yra paskutinis duomenų sujungimo proceso etapas. Jo tikslas – suderinti prieštaringus duomenis. Prieštaringų duomenų pavyzdžiai: kliento vardas, randamas dviejuose jūsų duomenų rinkiniuose, bet kiekviename iš jų rašomas šiek tiek skirtingai (pvz., „Grant Marshall“ ir „Grant Marshal“), arba telefono numeris, kurio formatas skiriasi (617-803-091X ir 617803091X). Šių prieštaringų duomenų taškų sujungimas atliekamas „atributas pagal atributą“ pagrindu.

:::image type="content" source="media/merge-fields-page.png" alt-text="Suliejimo puslapis duomenų unifikavimo procese, rodantis lentelę su sulietais laukais, kurie apibrėžia vieningąjį kliento profilį.":::

Užbaigus [sutapdinimo etapą](match-entities.md) pradedamas suliejimo etapas, pasirinkus plytelę **Sulieti**, pateikiamą puslapyje **Sujungti**.

## <a name="review-system-recommendations"></a>Sistemos rekomendacijų peržiūra

**Duomenys** > **Suvienodinti** > **Sulieti** galite pasirinkti ir išskirti atributus iš suliejimo jūsų vieningojo kliento profilio objekte. Vieningasis kliento profilis yra duomenų unifikavimo proceso rezultatas. Kai kuriuos atributus sistema sulieja automatiškai.

Norėdami peržiūrėti atributus, įtrauktus į vieną iš jūsų automatiškai sulietų atributų, pasirinkite sulietą atributą lentelės skirtuke **Kliento laukai**. Atributai, kurie sudaro sulietą atributą, yra rodomi dviejose naujose eilutėse po sulietu atributu.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Sulietų laukų atskyrimas, pervardijimas, išbraukimas ir redagavimas

Galite pakeisti, kaip sistema apdoroja sulietus atributus, kad sugeneruotų vieningąjį kliento profilį. Pažymėkite **Rodyti daugiau** ir pasirinkite norimą keisti parinktį.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Parinktys išplečiamajame meniu Rodyti daugiau, kad valdytume sulietus atributus.":::

Daugiau informacijos rasite tolesniuose skyriuose.

## <a name="separate-merged-fields"></a>Sulietų laukų atskyrimas

Norėdami atskirti sulietus laukus, lentelėje suraskite atributą. Vieningajame kliento profilyje atskiri laukai yra rodomi kaip atskiri duomenų elementai. 

1. Pasirinkite sulietą lauką.
  
1. Pažymėkite **Rodyti daugiau** ir pasirinkite **Atskirti laukus**.
 
1. Patvirtinkite atskyrimą.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

## <a name="rename-merged-fields"></a>Sulietų laukų pervardijimas

Pakeiskite sulietų atributų rodomą pavadinimą. Negalite pakeisti įvesties objekto pavadinimo.

1. Pasirinkite sulietą lauką.
  
1. Pažymėkite **Rodyti daugiau** ir pasirinkite **Pervadinti**.

1. Patvirtinkite pakeistą rodomą pavadinimą. 

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

## <a name="exclude-merged-fields"></a>Sulietų laukų išbraukimas

Išbraukite atributą iš vieningojo kliento profilio. Jei laukas yra naudojamas kituose procesuose, pavyzdžiui, segmente, pašalinkite jį iš šių procesų prieš išbraukdami jį iš kliento profilio. 

1. Pasirinkite sulietą lauką.
  
1. Pažymėkite **Rodyti daugiau** ir pasirinkite **Išbraukti**.

1. Patvirtinkite neišbraukimą.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus. 

Puslapyje **Sulieti** pasirinkite **Išbraukti laukai**, kad peržiūrėtumėte visų išbrauktų laukų sąrašą. Ši sritis jums leidžia vėl įtraukti išbrauktus laukus.

## <a name="manually-combine-fields"></a>Laukų sujungimas neautomatiniu būdu

Sulietą atributą nurodykite rankiniu būdu. 

1. Puslapyje **Sulieti** pasirinkite **Sujungti laukus**.

1. Įveskite **Pavadinimą** ir **Išvesties lauko pavadinimą**.

1. Pasirinkite lauką, kurį norite įtraukti. Pasirinkite **Įtraukti laukus**, kad sujungtumėte daugiau laukų.

1. Patvirtinkite neišbraukimą.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus. 

## <a name="change-the-order-of-fields"></a>Laukų tvarkos keitimas

Kai kuriuose objektuose yra daugiau išsamios informacijos nei kituose. Jei objekte yra naujausių duomenų apie lauką, galite jam teikti pirmenybę prieš kitus objektus, kai suliejate reikšmes.

1. Pasirinkite sulietą lauką.
  
1. Pažymėkite **Rodyti daugiau** ir pasirinkite **Redaguoti**.

1. Srityje **Sujungti laukus** pasirinkite **Perkelti aukštyn/žemyn**, kad nustatytumėte jų tvarką arba juos nuvilktumėte į norimą padėtį.

1. Patvirtinkite pakeitimą.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

## <a name="run-your-merge"></a>Suliejimo vykdymas

Nesvarbu, ar atributus suliejate rankiniu būdu, ar leidžiate juos sulieti sistemai, visada galite vykdyti savo suliejimą. Norėdami pradėti procesą, puslapyje **Sulieti** pasirinkite **Vykdyti**.

> [!div class="mx-imgBorder"]
> ![Duomenų suliejimo įrašymas ir vykdymas](media/configure-data-merge-save-run.png "Duomenų suliejimo įrašymas ir vykdymas")

Pasirinkite **Vykdyti tik suliejimą**, jei norite tik peržiūrėti išvestį, kuri atsispindi vieningajame kliento objekte. Tolesni procesai bus atnaujinti taip, kaip [apibrėžta atnaujinimo grafike](system.md#schedule-tab).

Pasirinkite **Vykdyti suliejimą ir tolesnius procesus**, kad atnaujintumėte sistemą savo pakeitimais. Visi procesai, įskaitant papildymą, segmentus ir priemones, bus vykdomi iš naujo automatiškai. Užbaigus visus tolesnius procesus, klientų profiliai atspindės visus jūsų atliktus pakeitimus.

Jei norite atlikti daugiau pakeitimų ir iš naujo vykdyti veiksmą, galite atšaukti vykdomą suliejimą. Spustelėkite **Atnaujinama...** ir pasirodžiusiame šoniniame skydo pasirinkite **Atšaukti užduotį**.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="next-step"></a>Kitas veiksmas

Norėdami gauti daugiau įžvalgų apie savo klientus, sukonfigūruokite [veiklas](activities.md), [papildymą](enrichment-hub.md) arba [ryšius](relationships.md).

Jei jau sukonfigūravote veiklas, papildymą ar segmentus, jie bus automatiškai apdorojami, kad naudotų naujausius kliento duomenys.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
