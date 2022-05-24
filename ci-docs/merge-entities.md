---
title: Kliento arba sąskaitos laukų suvienodinimas
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
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740867"
---
# <a name="unify-customer-fields"></a>Suvienodinti kliento laukus

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Šiame suvienijimo proceso etape pasirinkite ir pašalinkite atributus, kuriuos norite sulieti vieningame profilio objekte. Pavyzdžiui, jei trys subjektai turėjo el. pašto duomenis, galbūt norėsite išsaugoti visus tris atskirus el. pašto laukus arba sujungti juos į vieną el. pašto lauką, skirtą vieningam profiliui. Kai kuriuos atributus sistema automatiškai sujungia. Galite sukurti stabilius ir unikalius kliento ID ir su grupe susijusius profilius į klasterį.

:::image type="content" source="media/m3_unify.png" alt-text="Suliejimo puslapis duomenų unifikavimo procese, rodantis lentelę su sulietais laukais, kurie apibrėžia vieningąjį kliento profilį.":::

## <a name="review-and-update-the-customer-fields"></a>Peržiūrėti ir atnaujinti kliento laukus

1. Peržiūrėkite laukų, kurie bus suvienodinti lentelės skirtuke **Kliento laukai**, sąrašą. Jei taikoma, atlikite pakeitimus.

   1. Bet kuriuose kombinuotuose laukuose galite:
      - [Redagavimas](#edit-a-merged-field)
      - [Pervardyti](#rename-fields)
      - [Atskiras](#separate-merged-fields)
      - [Neįtraukti](#exclude-fields)
      - [Judėti aukštyn arba žemyn](#change-the-order-of-fields)

   1. Bet kuriame lauke galite:
      - [Sujungti laukus](#combine-fields-manually)
      - [Laukų grupės sujungimas](#combine-a-group-of-fields)
      - [Pervardyti](#rename-fields)
      - [Neįtraukti](#exclude-fields)
      - [Judėti aukštyn arba žemyn](#change-the-order-of-fields)

1. Pasirinktinai [sugeneruokite kliento ID konfigūraciją](#configure-customer-id-generation).

1. Pasirinktinai [grupuokite profilius į namų ūkius ar grupes](#group-profiles-into-households-or-clusters).

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

### <a name="rename-fields"></a>Pervardyti laukus

Keisti sulietų arba atskirų laukų rodomą pavadinimą. Negalite pakeisti įvesties objekto pavadinimo.

1. Pasirinkite lauką ir pasirinkite **Pervardyti**.

1. Įveskite naują rodomą pavadinimą.

1. Pasirinkite **Atlikta**.

### <a name="separate-merged-fields"></a>Sulietų laukų atskyrimas

Norėdami atskirti sulietus laukus, lentelėje suraskite atributą. Vieningajame kliento profilyje atskiri laukai yra rodomi kaip atskiri duomenų elementai.

1. Pasirinkite sulietą lauką ir pasirinkite **Atskirti laukus**.

1. Patvirtinkite atskyrimą.

### <a name="exclude-fields"></a>Neįtraukti laukų

Neįtraukti sulieto arba atskiro lauko iš vieningo kliento profilio. Jei laukas yra naudojamas kituose procesuose, pavyzdžiui, segmente, pašalinkite jį iš šių procesų prieš išbraukdami jį iš kliento profilio.

1. Pasirinkite lauką ir pasirinkite **Neįtraukti**.

1. Patvirtinkite neišbraukimą.

Norėdami pamatyti visų neįtrauktų laukų sąrašą, pasirinkite **Neįtraukti laukai**. Jei reikia, galite perskaityti neįtrauktą lauką.

### <a name="change-the-order-of-fields"></a>Laukų tvarkos keitimas

Kai kuriuose objektuose yra daugiau išsamios informacijos nei kituose. Jei objekte yra naujausių duomenų apie lauką, galite jam teikti pirmenybę prieš kitus objektus, kai suliejate reikšmes.

1. Pasirinkite lauką.
  
1. Pasirinkite **Perkelti aukštyn / žemyn**, kad nustatytumėte tvarką arba vilkite ir numeskite juos norimoje padėtyje.

### <a name="combine-fields-manually"></a>Laukų sujungimas neautomatiniu būdu

Sujunkite atskirtus laukus, kad sukurtumėte sulietą atributą.

1. Pasirinkite **Sujungti** > **laukus**. Rodoma sritis Sujungti laukus.

1. Nurodykite suliejimo laimėtojo išrinkimo strategiją **Sujungti laukus pagal** išplečiamajame sąraše.

1. Pasirinkite **Įtraukti lauką**, kad sujungtumėte daugiau laukų.

1. Įveskite **Pavadinimą** ir **Išvesties lauko pavadinimą**.

1. Pasirinkite **Atlikta** pakeitimų pritaikymui.

### <a name="combine-a-group-of-fields"></a>Laukų grupės sujungimas

Laukų grupę traktuoti kaip vieną vienetą. Pavyzdžiui, jei mūsų įrašuose yra laukai Adresas1, Adresas2, Miestas, Valstija ir Zip, nenorime sulieti į kito įrašo adresą2, manydami, kad tai padarys mūsų duomenis išsamesnius.

1. Pasirinkite **Sujungti** > **laukų** grupę.

1. Išplečiamajame sąraše Reitinguoti grupes pagal nurodykite suliejimo laimėtojo **strategiją**.

1. Pasirinkite **Įtraukti** ir pasirinkite, ar į laukus norite įtraukti daugiau laukų ar grupių.

1. Pateikite kiekvieno jungtinio **lauko** pavadinimą **ir išvesties pavadinimą**.

1. **Pateikite laukų grupės pavadinimą**.

1. Pasirinkite **Atlikta** pakeitimų pritaikymui.

## <a name="configure-customer-id-generation"></a>Konfigūruoti kliento ID generavimą

Nurodykite, kaip generuoti kliento ID vertes, unikalius kliento profilio identifikatorius. Duomenų suvienijimo proceso laukų suvienodinimo veiksmas sugeneruoja unikalų kliento profilio identifikatorių. Identifikatorius yra *kliento* objekto *CustomerId*, kuris atsiranda dėl duomenų suvienijimo proceso.

*CustomerId* yra pagrįstas ne nulinės laimėtojo pirminių raktų pirmosios reikšmės maiša. Šie raktai gaunami iš objektų, naudojamų duomenų suvienijimui, ir jiems įtakos turi atitikties tvarka.Taigi sugeneruotas kliento ID gali pasikeisti, kai pirminis raktas pasikeičia pagrindiniame atitikties užsakymo objekte. Pirminė rakto reikšmė ne visada gali reikšti tą patį klientą.

Sukonfigūravus stabilų kliento ID galima išvengti tokio veikimo.

1. Pasirinkite skirtuką **Raktai**.

1. Palaikykite pelės žymiklį **eilutėje CustomerId** ir pasirinkite **Konfigūruoti**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="ID generavimo tinkinimo valdiklis.":::

1. Pažymėkite ne daugiau kaip penkis laukus, kurie sudarys unikalųjį kliento ID ir kurie yra labiau stabilūs. Įrašuose, kurie neatitinka jūsų konfigūracijos, naudojamas sistemos sukonfigūruotas ID.  

1. Pasirinkite **Atlikta**.

## <a name="group-profiles-into-households-or-clusters"></a>Grupuokite profilius į indus ar grupes į indus

Galite nustatyti taisykles, kaip grupuoti susijusius profilius į sankaupą. Šiuo metu galimos dviejų tipų grupės – tarpastie ir pasirinktinės grupės. Sistema automatiškai pasirenka naudojant iš anksto nustatytas taisykles, jei *kliento* objektas turi semantiniais laukais *Asmens.Pavardė* ir *Vietos.Adresas*. Taip pat galite sukurti grupę su savo taisyklėmis ir sąlygomis, panašiomis į [atitikties taisykles](match-entities.md#define-rules-for-match-pairs).

1. Pasirinkite **Išplėstinis** > **kurti sankaupą**.

   :::image type="content" source="media/create-cluster.png" alt-text="Naujos grupės kūrimo valdiklis.":::

1. Pasirinkite iš **Namai** ar **Kliento** grupė. Jei semantiniai laukai yra *Asmens.Pavardė* ir *Veitos.Adresas* yra *Kliento* objekte, tai namai automatiškai pasirenkami.

1. Nurodykite grupės pavadinimą ir pasirinkite **Atlikta**.

1. Pasirinkite skirtuką **Grupės** ir raskite sukurtą grupę.

1. Nurodykite savo grupės apibrėžties taisykles ir sąlygas.

1. Pasirinkite **Atlikta**. Klasteris sukuriamas, kai suvienijimo procesas yra baigtas. Sankaupos identifikatoriai įtraukiami kaip nauji laukai į objektą *Klientas*.

> [!div class="nextstepaction"]
> [Kitas žingsnis: suvienijimo peržiūra](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
