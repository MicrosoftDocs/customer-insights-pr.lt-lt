---
title: Suliekite objektus duomenų suvienyjime
description: Suliekite objektus tam, kad sukurtumėte suvienytus kliento profilius.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 978a7c9bc440398fa39e9fa1d366d74e5c7aaea0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643853"
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

1. Pažymėkite sulietą lauką.
  
1. Pažymėkite **Rodyti daugiau** ir pasirinkite **Išbraukti**.

1. Patvirtinkite neišbraukimą.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus. 

Puslapyje **Sulieti** pasirinkite **Išbraukti laukai**, kad peržiūrėtumėte visų išbrauktų laukų sąrašą. Ši sritis jums leidžia vėl įtraukti išbrauktus laukus.

## <a name="edit-a-merged-field"></a>Sulieto lauko redagavimas

1.  Pažymėkite sulietą lauką.

1.  Pažymėkite **Rodyti daugiau** ir pasirinkite **Redaguoti**.

1.  Nurodykite, kaip sujungti arba sulieti laukus viena iš trijų parinkčių:
    - **Svarba**: nustato laiminčią reikšmę pagal svarbos reitingą, nurodytą dalyvaujantiems laukams. Tai yra numatytoji suliejimo parinktis. Pasirinkite **Perkelti aukštyn/žemyn**, kad nustatytumėte svarbos vertinimą.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Svarbos parinktis suliejimo laukų dialogo lange."::: 
    - **Naujausia** : nustato laiminčią vertę pagal didžiausią naujumą. Norint apibrėžti naujumą, kiekvienam dalyvaujančiam objektui suliejimo laukų aprėptyje reikia datos arba skaitinio lauko.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Naujumo parinktis suliejimo laukų dialogo lange.":::
    - **Seniausia** : nustato laiminčią vertę pagal mažiausią naujumą. Norint apibrėžti naujumą, kiekvienam dalyvaujančiam objektui suliejimo laukų aprėptyje reikia datos arba skaitinio lauko.

1.  Norėdami dalyvauti suliejimo procese, galite įtraukti daugiau laukų.

1.  Sulietą lauką galite pervadinti.

1. Pasirinkite **Atlikta** jūsų pakeitimų pritaikymui.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus. 

## <a name="combine-fields-manually"></a>Laukų sujungimas neautomatiniu būdu

Sulietą atributą nurodykite rankiniu būdu.

1. Puslapyje Suliejimas **pasirinkite** **Sujungti**.

1. Pasirinkite **parinktį Laukai**.

1. Nurodykite suliejimo laimėtojo išrinkimo strategiją **Sujungti laukus pagal** išplečiamajame sąraše.

1. Pasirinkite lauką, kurį norite įtraukti. Pasirinkite **Įtraukti laukus**, kad sujungtumėte daugiau laukų.

1. Įveskite **Pavadinimą** ir **Išvesties lauko pavadinimą**.

1. Pasirinkite **Atlikta** pakeitimų pritaikymui.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus. 

## <a name="combine-a-group-of-fields"></a>Laukų grupės sujungimas

Laukų grupę traktuoti kaip vieną vienetą. Pavyzdžiui, kai mūsų įrašuose yra laukų Adresas1, Adresas2, Miestas, Valstija ir Zip. Mes tikriausiai nenorime susijungti į kito įrašo adresą2, manydami, kad tai padarys mūsų duomenis išsamesnius

1. Puslapyje Suliejimas **pasirinkite** **Sujungti**.

1. Pasirinkite pasirinktį **Laukų** grupė.

1. Išplečiamajame sąraše Reitinguoti grupes pagal nurodykite suliejimo laimėtojo **strategiją**.

1. Pasirinkite **Įtraukti** ir pasirinkite, jei į laukus norite įtraukti daugiau laukų ar papildomų grupių.

1. Pateikite kiekvieno jungtinio **lauko** pavadinimą **ir išvesties pavadinimą**.

1. **Pateikite laukų grupės pavadinimą**. 

1. Pasirinkite **Atlikta** pakeitimų pritaikymui.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

## <a name="change-the-order-of-fields"></a>Laukų tvarkos keitimas

Kai kuriuose objektuose yra daugiau išsamios informacijos nei kituose. Jei objekte yra naujausių duomenų apie lauką, galite jam teikti pirmenybę prieš kitus objektus, kai suliejate reikšmes.

1. Pasirinkite sulietą lauką.
  
1. Pažymėkite **Rodyti daugiau** ir pasirinkite **Redaguoti**.

1. Srityje **Sujungti laukus** pasirinkite **Perkelti aukštyn/žemyn**, kad nustatytumėte jų tvarką arba juos nuvilktumėte į norimą padėtį.

1. Patvirtinkite pakeitimą.

1. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

## <a name="configure-customer-id-generation"></a>Kliento ID generavimo konfigūravimas 

Sukonfigūravę suliejimo laukus galite apibrėžti, kaip generuoti Kliento ID reikšmes, unikalius kliento profilio identifikatorius. Duomenų suvienodinimo proceso suliejimo žingsnis sugeneruoja unikalų kliento profilio identifikatorių. Identifikatorius yra *Kliento* objekto Kliento ID, kuris gaunamas iš duomenų suvienodinimo proceso. 

Kliento objekto Kliento ID yra pagrįsta pirmosios ne nulinės laimėjusios pirminių raktų reikšmės maiša. Šie raktai gaunami iš objektų, naudojamų gretinimo ir suliejimo etapuose, ir juos sąlygoja atitikmenų tvarka.Tad sugeneruot Kliento ID gali pasikeisti, kai pirminė rakto reikšmė pakeičia atitikmens tvarkos pirminį objektą. Todėl pirminio rakto reikšmė ne visada gali būti ta pati kaip ir tas klientas.

Sukonfigūravus stabilų kliento ID galima išvengti tokio veikimo.

**Konfigūruoti unikalųjį kliento ID**

1. Eikite į **Vienyti** > **Sulieti**.

1. Pasirinkite skirtuką **Raktai**. 

1. Laikykite pelės žymeklį virš **Kliento ID** ir pasirinkite **Konfigūruoti** parinktį.
   :::image type="content" source="media/customize-stable-id.png" alt-text="ID generavimo tinkinimo valdiklis.":::

1. Pažymėkite ne daugiau kaip penkis laukus, kurie sudarys unikalųjį kliento ID ir kurie yra labiau stabilūs. Įrašuose, kurie neatitinka jūsų konfigūracijos, naudojamas sistemos sukonfigūruotas ID.  

1. Pasirinkite **Atlikta** ir vykdykite suliejimo procesą, kad jūsų pakeitimai būtų pritaikyti.

## <a name="group-profiles-into-households-or-clusters"></a>Grupuokite profilius į indus ar grupes į indus

Kaip kliento profilio generavimo konfigūravimo proceso dalį galite apibrėžti taisykles, pagal šias taisykles susijusius profilius grupuoti į grupę. Šiuo metu galimos dviejų tipų grupės – tarpastie ir pasirinktinės grupės. Sistema automatiškai pasirenka naudojant iš anksto nustatytas taisykles, jei *kliento* objektas turi semantiniais laukais *Asmens.Pavardė* ir *Vietos.Adresas*. Taip pat galite sukurti grupę su savo taisyklėmis ir sąlygomis, panašiomis į [atitikties taisykles](match-entities.md#define-rules-for-match-pairs).

**Nustatykite kasos aparatą arba grupę**

1. Eikite į **Vienyti** > **Sulieti**.

1. Skirtuke **Sulieti** rinkitės **Išplėstinis** > **kūrimo grupė**.

   :::image type="content" source="media/create-cluster.png" alt-text="Naujos grupės kūrimo valdiklis.":::

1. Pasirinkite iš **Namai** ar **Kliento** grupė. Jei semantiniai laukai yra *Asmens.Pavardė* ir *Veitos.Adresas* yra *Kliento* objekte, tai namai automatiškai pasirenkami.

1. Nurodykite grupės pavadinimą ir pasirinkite **Atlikta**.

1. Pasirinkite skirtuką **Grupės** ir raskite sukurtą grupę.

1. Nurodykite savo grupės apibrėžties taisykles ir sąlygas.

1. Pasirinkite **Vykdyti**, kad būtų vykdomas suliejimo procesas ir sukurta grupė.

Atlikus suliejimo procesą, grupės identifikatoriai į kliento objektą įtraukiami kaip *nauji* laukai.

## <a name="run-your-merge"></a>Suliejimo vykdymas

Nesvarbu, ar atributus suliejate rankiniu būdu, ar leidžiate juos sulieti sistemai, visada galite vykdyti savo suliejimą. Norėdami pradėti procesą, puslapyje **Sulieti** pasirinkite **Vykdyti**.

> [!div class="mx-imgBorder"]
> ![Duomenų suliejimo įrašymas ir vykdymas.](media/configure-data-merge-save-run.png "Duomenų suliejimo įrašymas ir vykdymas")

Pasirinkite **Vykdyti tik suliejimą**, jei norite tik peržiūrėti išvestį, kuri atsispindi vieningajame kliento objekte. Tolesni procesai bus atnaujinti taip, kaip [apibrėžta atnaujinimo grafike](system.md#schedule-tab).

Pasirinkite **Vykdyti suliejimą ir tolesnius procesus**, kad atnaujintumėte sistemą savo pakeitimais. Visi procesai, įskaitant papildymą, segmentus ir priemones, bus vykdomi iš naujo automatiškai. Užbaigus visus tolesnius procesus, klientų profiliai atspindės visus jūsų atliktus pakeitimus.

Jei norite atlikti daugiau pakeitimų ir iš naujo vykdyti veiksmą, galite atšaukti vykdomą suliejimą. Spustelėkite **Atnaujinama...** ir pasirodžiusiame šoniniame skydo pasirinkite **Atšaukti užduotį**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Detalizavimo kelias, kuriuo galima apdoroti išsamią informaciją iš užduoties būsenos saito.":::

## <a name="next-step"></a>Kitas veiksmas

Norėdami gauti daugiau įžvalgų apie savo klientus, sukonfigūruokite [veiklas](activities.md), [papildymą](enrichment-hub.md) arba [ryšius](relationships.md).

Jei jau sukonfigūravote veiklas, papildymą ar segmentus, jie bus automatiškai apdorojami, kad naudotų naujausius kliento duomenys.

[!INCLUDE [footer-include](includes/footer-banner.md)]
