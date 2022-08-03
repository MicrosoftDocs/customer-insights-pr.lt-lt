---
title: Kliento laukų suvienodinimas duomenų suvienijimui
description: Suliekite objektus tam, kad sukurtumėte suvienytus kliento profilius.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139667"
---
# <a name="unify-customer-fields-for-data-unification"></a>Kliento laukų suvienodinimas duomenų suvienijimui

Atlikdami šį suvienijimo proceso veiksmą, pasirinkite ir išskirkite atributus, kuriuos norite sulieti savo vieningajame profilio objekte. Pavyzdžiui, jei trys objektai turėjo el. pašto duomenis, galbūt norėsite išsaugoti visus tris atskirus el. pašto laukus arba sujungti juos į vieną vieningo profilio el. pašto lauką. Kai kuriuos atributus sistema automatiškai sujungia. Galite sukurti stabilius ir unikalius klientų ID ir sugrupuoti su grupe susijusius profilius į klasterį.

:::image type="content" source="media/m3_unify.png" alt-text="Suliejimo puslapis duomenų unifikavimo procese, rodantis lentelę su sulietais laukais, kurie apibrėžia vieningąjį kliento profilį.":::

## <a name="review-and-update-the-customer-fields"></a>Klientų laukų peržiūra ir naujinimas

1. Peržiūrėkite laukų, kurie bus suvienodinti lentelės skirtuke **Kliento laukai**, sąrašą. Jei taikoma, atlikite bet kokius pakeitimus.

   1. Visuose sujungtuose laukuose galite:
      - [Redagavimas](#edit-a-merged-field)
      - [Pervardyti](#rename-fields)
      - [Atskiras](#separate-merged-fields)
      - [Neįtraukti](#exclude-fields)
      - [Judėti aukštyn arba žemyn](#change-the-order-of-fields)

   1. Bet kuriam atskiram laukui galite:
      - [Sujungti laukus](#combine-fields-manually)
      - [Laukų grupės sujungimas](#combine-a-group-of-fields)
      - [Pervardyti](#rename-fields)
      - [Neįtraukti](#exclude-fields)
      - [Judėti aukštyn arba žemyn](#change-the-order-of-fields)

1. Pasirinktinai [generuokite kliento ID konfigūraciją](#configure-customer-id-generation).

1. Pasirinktinai grupuokite [profilius į namų ūkius ar grupes](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Kitas žingsnis: suvienijimo peržiūra](review-unification.md)

### <a name="edit-a-merged-field"></a>Sulieto lauko redagavimas

1. Pasirinkite sulietą lauką ir pasirinkite **Redaguoti**. Rodoma sritis Sujungti laukus.

1. Nurodykite, kaip sujungti arba sulieti laukus viena iš trijų parinkčių:
    - **Svarba**: nustato laiminčią reikšmę pagal svarbos reitingą, nurodytą dalyvaujantiems laukams. Tai yra numatytoji suliejimo parinktis. Pasirinkite **Perkelti aukštyn/žemyn**, kad nustatytumėte svarbos vertinimą.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Svarbos parinktis suliejimo laukų dialogo lange.":::

    - **Naujausia** : nustato laiminčią vertę pagal didžiausią naujumą. Norint apibrėžti naujumą, kiekvienam dalyvaujančiam objektui suliejimo laukų aprėptyje reikia datos arba skaitinio lauko.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Naujumo parinktis suliejimo laukų dialogo lange.":::

    - **Seniausia** : nustato laiminčią vertę pagal mažiausią naujumą. Norint apibrėžti naujumą, kiekvienam dalyvaujančiam objektui suliejimo laukų aprėptyje reikia datos arba skaitinio lauko.

1. Norėdami dalyvauti suliejimo procese, galite įtraukti daugiau laukų.

1. Sulietą lauką galite pervadinti.

1. Pasirinkite **Atlikta** jūsų pakeitimų pritaikymui.

### <a name="rename-fields"></a>Laukų pervardijimas

Pakeiskite rodomą sulietų arba atskirų laukų pavadinimą. Negalite pakeisti įvesties objekto pavadinimo.

1. Pasirinkite lauką ir pasirinkite **Pervardyti**.

1. Įveskite naują rodomą pavadinimą.

1. Pasirinkite **Atlikta**.

### <a name="separate-merged-fields"></a>Sulietų laukų atskyrimas

Norėdami atskirti sulietus laukus, lentelėje suraskite atributą. Vieningajame kliento profilyje atskiri laukai yra rodomi kaip atskiri duomenų elementai.

1. Pasirinkite sulietą lauką ir pasirinkite **Atskiri laukai**.

1. Patvirtinkite atskyrimą.

### <a name="exclude-fields"></a>Laukų išskyrimas

Išskirkite sulietą arba atskirą lauką iš vieningo kliento profilio. Jei laukas yra naudojamas kituose procesuose, pavyzdžiui, segmente, pašalinkite jį iš šių procesų prieš išbraukdami jį iš kliento profilio.

1. Pasirinkite lauką ir pasirinkite **Išskirti**.

1. Patvirtinkite neišbraukimą.

Norėdami peržiūrėti visų neįtrauktų laukų sąrašą, pasirinkite **Išskirti laukai**. Jei reikia, galite perskaityti neįtrauktą lauką.

### <a name="change-the-order-of-fields"></a>Laukų tvarkos keitimas

Kai kuriuose objektuose yra daugiau išsamios informacijos nei kituose. Jei objekte yra naujausių duomenų apie lauką, galite jam teikti pirmenybę prieš kitus objektus, kai suliejate reikšmes.

1. Pasirinkite lauką.
  
1. Pasirinkite **Perkelti aukštyn / žemyn**, kad nustatytumėte tvarką, arba vilkite ir numeskite juos į norimą padėtį.

### <a name="combine-fields-manually"></a>Neautomatinis laukų sujungimas

Sujunkite atskirtus laukus, kad sukurtumėte sulietą atributą.

1. Pasirinkite **Sujungti** > **laukus**. Rodoma sritis Sujungti laukus.

1. Nurodykite suliejimo laimėtojo išrinkimo strategiją **Sujungti laukus pagal** išplečiamajame sąraše.

1. Pasirinkite **Įtraukti lauką**, kad sujungtumėte daugiau laukų.

1. Įveskite **Pavadinimą** ir **Išvesties lauko pavadinimą**.

1. Pasirinkite **Atlikta** pakeitimų pritaikymui.

### <a name="combine-a-group-of-fields"></a>Laukų grupės sujungimas

Laukų grupę traktuokite kaip vieną vienetą. Pavyzdžiui, jei mūsų įrašuose yra laukai Adresas1, Adresas2, Miestas, Valstija ir Zip, nenorime sujungti į kito įrašo adresą2, manydami, kad tai padarys mūsų duomenis išsamesnius.

1. Pasirinkite **Sujungti** > **laukų** grupę.

1. Nurodykite suliejimo laimėtojo **strategiją grupėse Reitingas pagal** išplečiamąjį meniu.

1. Pasirinkite **Įtraukti** ir pasirinkite, ar į laukus norite įtraukti daugiau laukų ar grupių.

1. Pateikite kiekvieno sujungto **lauko** pavadinimą **ir išvesties pavadinimą**.

1. Pateikite **laukų grupės pavadinimą**.

1. Pasirinkite **Atlikta** pakeitimų pritaikymui.

## <a name="configure-customer-id-generation"></a>Kliento ID generavimo konfigūravimas

Apibrėžkite, kaip generuoti kliento ID reikšmes, unikalius kliento profilio identifikatorius. Suvienodinimo laukų veiksmas duomenų suvienijimo procese sugeneruoja unikalų kliento profilio identifikatorių. Identifikatorius yra *klientoidas* objekte *Klientas*, kuris atsiranda dėl duomenų suvienijimo proceso.

" *CustomerId* " yra pagrįstas ne nulinio laimėtojo pirminių raktų pirmosios vertės maiša. Šie raktai gaunami iš objektų, naudojamų duomenų suvienijimui, ir jiems įtakos turi atitikties tvarka.Taigi sugeneruotas kliento ID gali keistis, kai pirminiame atitikties užsakymo objekte pasikeičia pirminio rakto reikšmė. Pirminio rakto reikšmė ne visada gali reikšti tą patį klientą.

Sukonfigūravus stabilų kliento ID galima išvengti tokio veikimo.

1. Pasirinkite skirtuką **Raktai**.

1. Užveskite pelės žymeklį **eilutėje CustomerId** ir pasirinkite **Konfigūruoti**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="ID generavimo tinkinimo valdiklis.":::

1. Pažymėkite ne daugiau kaip penkis laukus, kurie sudarys unikalųjį kliento ID ir kurie yra labiau stabilūs. Įrašuose, kurie neatitinka jūsų konfigūracijos, naudojamas sistemos sukonfigūruotas ID.  

1. Pasirinkite **Atlikta**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupuokite profilius į indus ar grupes į indus

Galite apibrėžti taisykles, kaip sugrupuoti susijusius profilius į klasterį. Šiuo metu galimos dviejų tipų grupės – tarpastie ir pasirinktinės grupės. Sistema automatiškai pasirenka naudojant iš anksto nustatytas taisykles, jei *kliento* objektas turi semantiniais laukais *Asmens.Pavardė* ir *Vietos.Adresas*. Taip pat galite sukurti grupę su savo taisyklėmis ir sąlygomis, panašiomis į [atitikties taisykles](match-entities.md#define-rules-for-match-pairs).

1. Pasirinkite **Išplėstinis** > **kūrimo klasteris**.

   :::image type="content" source="media/create-cluster.png" alt-text="Naujos grupės kūrimo valdiklis.":::

1. Pasirinkite iš **Namai** ar **Kliento** grupė. Jei semantiniai laukai yra *Asmens.Pavardė* ir *Veitos.Adresas* yra *Kliento* objekte, tai namai automatiškai pasirenkami.

1. Nurodykite grupės pavadinimą ir pasirinkite **Atlikta**.

1. Pasirinkite skirtuką **Grupės** ir raskite sukurtą grupę.

1. Nurodykite savo grupės apibrėžties taisykles ir sąlygas.

1. Pasirinkite **Atlikta**. Klasteris sukuriamas, kai suvienijimo procesas yra baigtas. Klasterio identifikatoriai įtraukiami kaip nauji laukai į objektą *Klientas*.

> [!div class="nextstepaction"]
> [Kitas žingsnis: suvienijimo peržiūra](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
