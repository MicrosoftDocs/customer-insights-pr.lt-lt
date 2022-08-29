---
title: Vieningojo kontakto profilio kūrimas (peržiūra)
description: Atlikite duomenų suvienijimo procesą, kad sukurtumėte vieną pagrindinį kontaktų duomenų rinkinį.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305077"
---
# <a name="create-a-unified-contact-profile-preview"></a>Vieningojo kontakto profilio kūrimas (peržiūra)

Suvienodinę [verslo abonementus](map-entities.md), galite pasirinktinai suvienodinti tų abonementų kontaktus ir susieti vieningus kontaktus su vieningaisiais abonementais. Kontaktų suvienijimo procesas susieja kontaktinius duomenis iš kelių duomenų šaltinių, pašalina dublikatus, sugretina duomenis objektuose, nustato semantinį susiejimą, sukuria ryšius tarp kontaktų ir abonementų ir sukuria vieningą kontaktų profilį.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Pirmieji keli veiksmai yra identiški vienijančių paskyrų veiksmams.

## <a name="prerequisites"></a>Būtinosios sąlygos

Abonemento ir kontaktų įrašai turi turėti unikalų raktą (vadinamą išoriniu raktu), kuris juos jungia. Pavyzdžiui, abonemento įraše ir kontakto įraše esantis abonemento ID, susiejantis abonementą ir kontaktą.

## <a name="preview-limitations"></a>Peržiūros apribojimai

- Kontaktai be nuorodos į paskyrą atmetami.
- Jei abonementas dubliuojamas, nugalėtojo įrašas identifikuojamas pagal suliejimo nuostatas. "Loser" įrašai nėra atrenkami, todėl jų atsisakoma. Kontaktai, susiję su pralaimėjusiais įrašais, atmetami.
- Abonementas gali turėti kelis kontaktus, bet kontaktas susiejamas su vienu abonementu.
- Kontakto atributai, susieti semantinio susiejimo veiksme, yra vieninteliai atributai, kurie gali būti rodomi kliento kortelėje. Tačiau yra 17 atributų.

## <a name="select-source-fields"></a>Pasirinkite šaltinio laukus

1. Dalyje **Suvienodinti kontaktus (peržiūra)** pasirinkite **Darbo pradžia**.

1. [Pasirinkite kontaktų duomenų šaltinių objektus ir laukus](map-entities.md), įskaitant pirminius raktus ir atributų tipus.

1. Pasirinkite **Toliau**.

## <a name="remove-duplicate-records"></a>Pasikartojančių įrašų šalinimas

1. Pasirinktinai [apibrėžkite pasirinktų objektų dubliavimo taisykles](remove-duplicates.md).

1. Pasirinkite **Toliau**.

## <a name="match-conditions"></a>Rungtynių sąlygos

1. [Apibrėžkite atitikties tvarką ir kelių objektų atitikties taisykles](match-entities.md).

1. Pasirinkite **Toliau**.

## <a name="unify-contact-fields"></a>Kontaktų laukų suvienodinimas

1. [Sujunkite ir išskirkite kontaktų laukus](merge-entities.md).

1. Pasirinkite **Toliau**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Apibrėžti suvienodintų kontaktų semantinius laukus

Šis suvienijimo proceso veiksmas susieja jūsų vieningus kontaktų laukus su semantiniais tipais. B-to-B klientų kortelėse rodomos sąskaitos. Pasirinkus kortelę, rodomi visi su paskyra susieti kontaktai. Laukai, kuriuos susiejate atlikdami šį veiksmą, yra laukai, kurie bus rodomi kortelėse.

1. Pasirinkite semantinį tipą, susiejantį su kiekvienu vieningu lauku. Pasirinkite **Nėra**, jei semantinis tipas nepasiekiamas.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Semantinių laukų puslapio ekrano kopija semantinių tipų apibrėžimui." lightbox="media/semantic_mapping.png":::

1. Susieję visus vieningus laukus, pasirinkite **Pirmyn**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Ryšio tarp kontaktų ir abonementų nustatymas

Šis suvienijimo proceso veiksmas sujungia jūsų kontaktinius duomenis su atitinkamais paskyros duomenimis.

1. Apie kiekvieną objektą įveskite šią informaciją:

   - **Išorinis raktas iš kontakto objekto**: pasirinkite atributą, kuris sujungia kontakto objektą su klientu.
   - **Norėdami kliento objekto**: pasirinkite su kontaktu susietą kliento objektą.

   :::image type="content" source="media/contact_relationship.png" alt-text="Ryšio puslapio, skirto kontakto ir abonemento objektams sujungti, ekrano nuotrauka.":::

1. Pasirinkite **Toliau**.

## <a name="review-contact-unification"></a>Kontaktų suvienijimo peržiūra

Peržiūrėkite keitimų suvestinę, sukurkite vieningą profilį ir peržiūrėkite rezultatus.

### <a name="review-and-create-contact-profiles"></a>Peržiūrėti ir kurti kontaktų profilius

Šis paskutinis suvienijimo proceso veiksmas rodo proceso veiksmų suvestinę ir suteikia galimybę atlikti keitimus prieš kuriant vieningąjį kontakto profilį.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Peržiūrėkite ir kurkite kontaktų profilius ekrano kopija.":::

1. Pasirinkite **Redaguoti** atliekant bet kurį kontaktų suvienijimo veiksmą, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Kurti kontaktų profilius**. Puslapis " **Suvienodinti** " rodomas kuriant vieningą kontaktų profilį.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Puslapio Suvienodinti kontaktus su plytelėmis, kuriose rodoma eilė arba Atnaujinimas, ekrano nuotrauka.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Suvienijimo algoritmo užbaigimas užtrunka šiek tiek laiko ir jūs negalite pakeisti konfigūracijos, kol ji nebus baigta.

### <a name="view-the-results-of-contact-unification"></a>Kontaktų suvienijimo rezultatų peržiūra

Užbaigus suvienijimą, **puslapyje Duomenų** > **suvienodinimas** rodomas suvienodintų kontaktų profilių skaičius. Kiekvieno suvienijimo proceso veiksmo rezultatai rodomi kiekvienoje plytelėje. Pavyzdžiui, **laukuose** Šaltinis rodomas susietų atributų (laukų) skaičius, o **Pasikartojančių įrašų** skaičius rodo rastų pasikartojančių įrašų skaičių.

:::image type="content" source="media/unified_contacts.png" alt-text="Duomenų suvienodinimo puslapio ekrano nuotrauka suvienodinus kontaktus.":::

> [!TIP]
> Plytelė Atitikimo **sąlygos** rodoma tik tada, jei buvo pasirinkti keli objektai.

Rekomenduojame peržiūrėti rezultatus, ypač rungtynių taisyklių [kokybę](data-unification-update.md#manage-match-rules), ir, jei reikia, jas patikslinti.

Jei reikia, [pakeiskite kontaktų suvienijimo parametrus](data-unification-update.md) ir iš naujo paleiskite vieningą profilį.

### <a name="verify-output-entities-from-data-unification"></a>Išvesties objektų tikrinimas iš duomenų suvienijimo

Eikite į **Duomenų** > **objektai**, kad patikrintumėte išvesties objektus.

Vieningasis kontakto profilio objektas, vadinamas *ContactProfile*, rodomas **skyriuje Semantiniai objektai**. Pirmasis sėkmingas suvienijimo vykdymas sukuria vieningą *contactProfile objektą*. Visi vėlesni važiavimai išplečia tą objektą.

Objektas *ContactsCustomer* (peržiūra) sukuriamas ir rodomas sekcijoje **Profiliai**. Šiame objekte yra kontaktiniai duomenys be saitų į abonementus. Šis objektas naudojamas kaip įvestis į kontaktų suvienijimo semantinį susiejimą ir ryšio veiksmus.

Kopijavimo ir sujungimo objektai sukuriami ir rodomi **skyriuje Sistema**. Kiekvienam šaltinio objektui sukuriamas besidubliuojantis objektas su pavadinimu **Deduplication_DataSource_Entity**. Objekte **ContactsConflationMatchPairs** yra informacijos apie kelių objektų atitikmenis.

Dublikatų naikinimo išvesties objektas turi šią informaciją:
- ID/Raktai
  - Laukai Pirminis raktas ir Alternatyvus ID. Alternatyvųjį ID lauką sudaro visi alternatyvūs įrašo ID.
  - Dublikatų naikinimo grupės ID lauke rodoma grupė arba klasteris, nustatytas objektu, grupuojantis visus panašius įrašus pagal nurodytus dublikatų naikinimo laukus. Jis naudojamas sistemos apdorojimo tikslais. Jei nėra nurodytų neautomatiniu būdu nurodomų dublikatų naikinimo taisyklių ir taikomos sistemos apibrėžtos dublikatų naikinimo taisyklės, šis laukas gali būti nerandamas dublikatų naikinimo išvesties objektui.
  - „Deduplication_WinnerId”: Šiame lauke yra nustatytų grupių arba grupių laimėtojo ID. Jei „Deduplication_WinnerId” reikšmė yra tokia pati kaip įrašo pirminio rakto reikšmė, tai reiškia, kad įrašas yra nugalėtojas.
- Laukai, naudojami dublikatų naikinimo taisyklėms apibrėžti.
- Taisyklių ir Rezultato laukeliai žymi gretinimo algoritmo grąžintą rezultatą ir, kurios iš dublikatų naikinimo taisyklių buvo taikomos.

## <a name="next-step"></a>Kitas veiksmas

Konfigūruokite [veiklą](activities.md), [papildymą](enrichment-hub.md) ar [ryšius](relationships.md), kad gautumėte daugiau įžvalgų apie savo kontaktus.
