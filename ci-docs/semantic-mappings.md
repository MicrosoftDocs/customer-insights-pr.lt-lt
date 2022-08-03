---
title: Semantiniai susiejimai (peržiūros versija)
description: Semantinio susiejimo apžvalga ir kaip juos naudoti.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183641"
---
# <a name="semantic-mappings-preview"></a>Semantiniai susiejimai (peržiūros versija)

Naudojant semantiniai susiejimai leidžia susieti ne veiklos duomenis su iš anksto apibrėžtomis schemomis. Šios schemos padeda "Customer Insights" geriau suprasti jūsų duomenų atributus. Semantinis susiejimas ir pateikti duomenys įgalina naujas įžvalgas ir funkcijas "Customer Insights". Norėdami susieti savo veiklos duomenis su schemomis, peržiūrėkite [veiklų](activities.md) dokumentaciją.

**Šiuo metu aplinkose, pagrįstose verslo klientais, yra įgalinti semantiniai susiejimai**. *ContactProfile* yra vienintelis semantinio susiejimo tipas, šiuo metu pasiekiamas "Customer Insights".

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantinio objekto susiejimo apibrėžimas

1. Eikite į **Duomenų** > **semantiniai susiejimai (peržiūra)**.

1. Norėdami **pradėti interaktyviąją patirtį** pažymėkite Įtraukti semaninį susiejimą.

1. Atlikdami objekto **duomenų žingsnį**, nustatykite šių laukų reikšmes:

   - **Semantinio objekto susiejimo pavadinimas**: semantinio objekto susiejimo pavadinimas.
   - **Šaltinio objektas**: objektas, apimantis kontaktinius duomenis.
   - **Pirminis raktas**: laukas, kuris unikaliai identifikuoja kontakto įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nustatykite semantinio objekto susiejimą su pavadinimu, šaltinio objektu ir pirminiu raktu.":::

1. Pasirinkite **Toliau**.

1. Ryšių **žingsnyje** konfigūruokite išsamią informaciją, kad kontaktiniai duomenys būtų susieti su atitinkamo kliento įrašu. Šiuo veiksmu vaizduojamas objektų ryšys.  

   Galima įgyvendinti du ryšių maršrutų tipus: **Tiesioginius ryšius** ir **Išsamūs ryšiai**. Norėdami gauti daugiau informacijos, eikite į [Tiesioginius ir persodinamus ryšio maršrutus](relationships.md#relationship-paths).

   1. Pasirinkite **Įtraukti ryšį**, kad sukonfigūruotumėte ryšį.
   1. Pasirinkite atributą iš šaltinio objekto, prijungiančių jūsų kontakto objektą su kitu objektu.
   1. Pasirinkite objektą, prie kurio norite prijungti kontaktinį objektą. Pasirinkite objektą iš sekcijos **Kliento objektai** arba Tarpinis **objektas**. Jei pasirinksite tarpinį objektą, apibrėžkite antrą ryšį, kad prisijungtumėte prie tikslinio abonemento objekto.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pažymėkite kliento objektą arba objektą Tarpinis.":::

   1. Įveskite žaidimo **Ryšio pavadinimas**. Jei ryšys tarp jūsų objektų jau yra, ryšio pavadinimas yra skirtas tik skaityti. Jei ryšio nėra, bus sukurtas naujas ryšys jūsų suteiku pavadinimu.
   1. Pasirinkite **Taikyti**, kad užbaigtumėte ryšių konfigūraciją.

   > [!NOTE]
   > Galite konfigūruoti daugiau ryšių tarp kontakto objekto ir kitų kliento objektų su integuojainiais objektais.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Įvairių ryšių vizualizavimas jungia kontaktų objektus su kliento objektais.":::

1. Pasirinkite **Toliau**.

1. Norėdami **nustatyti semantinio tipo** žingsnį, pasirinkite **semantinio tipo**. Šiuo metu yra vienas **semantinis tipas** vadinamas *ContactProfile*.

1. Susiekite savo kontaktinį ID su *ContactProfile* semantinio tipo **kontakto ID**. Pasirinktinai susiekite kitus laukus, pvz., vardas, pavardė, lytį ar el. paštą.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Susiekite kontaktų duomenų atributus su pateikiamais reikiamais ir pasirinktiniais laukais.":::

1. Pasirinkite **Toliau**.

1. Atlikdami **peržiūrą** peržiūrėkite semantinio susiejimo konfigūraciją. Norėdami atlikti pakeitimus, **pasirinkite Redaguoti** atitinkamoje sekcijoje.

1. Pasirinkite **Įrašyti**.

1. Norėdami apdoroti semantinį susiejimą, pasirinkite **Vykdyti**. Arba pasirinkite **Uždaryti**, kad išsaugotumėte semantinį susiejimą jo neapdorodami. Norėdami jį paleisti vėliau, pasirinkite semantinį susiejimą ir pasirinkite **Atnaujinti**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Valdyti esamus semaninius susiejimus

Eikite į **Duomenų** > **semantiniai susiejimai (peržiūra),** kad peržiūrėtumėte išsaugotus semantinius susiejimus, jų šaltinio objektą, semantinį tipą, susiejimo tipą ir būseną.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semantinio susiejimo valdymo parinktys.":::

Pasirinkite semantinį susiejimą, kad peržiūrėtumėte galimus veiksmus.
- **Redaguokite** dabartinę konfigūraciją. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.
- **Atnaujinkite** semantinį susiejimą, kad įtrauktumėte naujausius duomenis. Atnaujinus bet kurį nurodytą semaninį susiejimą bus atnaujinti visi to paties tipo semantiniai susiejimai.
- **Pervardykite** semantinį susiejimą. Pasirinkite **Įrašyti**.
- **Panaikinkite** semantinį susiejimą. Norėdami ištrinti daugiau nei vieną semantinį susiejimą vienu metu, pasirinkite semantinius susiejimus ir ištrynimo piktogramą. Pasirinkite **Naikinti** naikinimo patvirtinimui.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>"ContactProfile" semantinio objekto susiejimo naudojimas kontakto lygio veiklai kurti

Sukūrę *"ContactProfile* " semantinio objekto susiejimą, galite užfiksuoti kontaktų veiklą. Tai leidžia paskyros veiklos laiko juostoje matyti, kuris kontaktas buvo atsakingas už kiekvieną veiklą. Dauguma veiksmų atliekami pagal įprastą veiklos susiejimo konfigūraciją.

   > [!NOTE]
   > Kad kontakto lygio veikla veiktų, veiklos duomenyse turite turėti **ir kliento ID,** ir **contactID** atributus kiekvienam įrašui.

1. [Apibrėžkite *"ContactProfile* " semantinio objekto susiejimą](#define-a-contactprofile-semantic-entity-mapping) ir paleiskite semantinį susiejimą.

1. Eikite į **Duomenų** > **veikla**.

1. Pasirinkite **Įtraukti veiklą**, kad sukurtumėte naują veiklą.

1. Pavadinkite veiklą, pasirinkite šaltinio veiklos objektą ir pasirinkite pirminį veiklos objekto raktą.

1. Atlikdami veiksmą **Ryšiai** sukurkite netiesioginį ryšį tarp savo veiklos šaltinio duomenų su klientais, naudodami savo kontaktinius duomenis kaip tarpinį objektą. Norėdami gauti daugiau informacijos, žiūrėkite [tiesioginių ir netiesioginių ryšių kelius](relationships.md#relationship-paths).
   - Veiklos, vadinamos *Pirkimais*, ryšio pavyzdys:
      - **Pirkimai Šaltinio veiklos duomenys** > **Kontaktiniai duomenys** atribute **ContactID**
      - **Kontaktiniai duomenų** > **paskyros duomenys** atribute **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Ryšio sąrankos pavyzdys.":::

1. Nustatę ryšius, pasirinkite **Pirmyn** ir užbaikite veiklos susiejimo konfigūraciją. Išsamių veiklos kūrimo veiksmų ieškokite [veiklos](activities.md) apibrėžime.

1. Paleiskite veiklos susiejimas.

1. Paleidę kontakto lygio veiklos susiejimą, pasirinkite **Klientai**. Kontakto lygio veikla rodoma jūsų kliento laiko juostoje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Galutinis rezultatas sukonfigūravus kontaktinę veiklą":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontakto lygio veiklos laiko planavimo juostos filtravimas

Jūsų klientų veiklos laiko juostoje yra jų ID arba vardai, atsižvelgiant į jūsų *ContactProfile* konfigūraciją, skirti veiklai, kurią jie veikė. Filtruokite veiklas pagal kontaktus laiko planavimo juostoje, kad pamatytumėte konkrečius jus dominančius kontaktus. Norėdami peržiūrėti visas veiklas, kurios nepriskirtos konkrečiam kontaktui, pasirinkite **Veikla, nesusieta su kontaktu**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Galimos kontakto lygio veiklos filtravimo parinktys.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
