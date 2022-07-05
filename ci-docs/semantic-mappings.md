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
ms.openlocfilehash: b3a0643ab71c98ce212f4e4581a584d8382c67eb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083146"
---
# <a name="semantic-mappings-preview"></a>Semantiniai susiejimai (peržiūros versija)

Naudojant semantiniai susiejimai leidžia susieti ne veiklos duomenis su iš anksto apibrėžtomis schemomis. Šios schemos padeda "Customer Insights" geriau suprasti jūsų duomenų atributus. Semantinis susiejimas ir pateikti duomenys įgalina naujas įžvalgas ir funkcijas "Customer Insights". Norėdami susieti savo veiklos duomenis su schemomis, peržiūrėkite [veiklų](activities.md) dokumentaciją.

**Šiuo metu aplinkose, pagrįstose verslo klientais, yra įgalinti semantiniai susiejimai**. *ContactProfile* yra vienintelis semantinio susiejimo tipas, šiuo metu pasiekiamas "Customer Insights".

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantinio objekto susiejimo apibrėžimas

1. Eikite į **Duomenų** > **semantiniai susiejimai (peržiūra)**.

1. Norėdami **pradėti interaktyviąją patirtį** pažymėkite Įtraukti semaninį susiejimą.

1. Atlikdami objekto **duomenų žingsnį**, nustatykite šių laukų reikšmes:

   - **Semantinio objekto susiejimo pavadinimas**: suteikite savo semantinio objekto susiejimo pavadinimą.
   - **Šaltinio objektas**: pažymėkite objektą, kuriame yra kontaktų duomenys.
   - **Pirminis raktas**: pažymėkite lauką, kuris unikaliai nustato kontakto įrašą. Jame neturėtų būti jokių pasikartojančių reikšmių, tuščių reikšmių arba trūkstamų reikšmių.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Nustatykite semantinio objekto susiejimą su pavadinimu, šaltinio objektu ir pirminiu raktu.":::

1. Norėdami tęsti, spustelėkite **Pirmyn**.

1. Ryšių **žingsnyje** konfigūruokite išsamią informaciją, kad kontaktiniai duomenys būtų susieti su atitinkamo kliento įrašu. Šiuo veiksmu vaizduojamas objektų ryšys.  

   Galima įgyvendinti du ryšių maršrutų tipus: **Tiesioginius ryšius** ir **Išsamūs ryšiai**. Norėdami gauti daugiau informacijos, eikite į [Tiesioginius ir persodinamus ryšio maršrutus](relationships.md#relationship-paths).

   1. Pažymėkite **Įtraukti ryšį**, konfigūruokite ryšį.
   1. Pasirinkite atributą iš šaltinio objekto, prijungiančių jūsų kontakto objektą su kitu objektu.
   1. Pasirinkite objektą, prie kurio norite prijungti kontaktinį objektą. Objektą galite pasirinkti iš **Abonemento objektų** ar **Tarpinio objekto** sprendimas". Jei pažymėsite, kad objektas yra nuosaikus, turite apibrėžti antrą ryšį, kad galėtumėte prisijungti prie tikslinio kliento objekto.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pažymėkite kliento objektą arba objektą Tarpinis.":::

   1. Įveskite žaidimo **Ryšio pavadinimas**. Jei ryšys tarp jūsų objektų jau yra, ryšio pavadinimas yra skirtas tik skaityti. Jei ryšio nėra, bus sukurtas naujas ryšys jūsų suteiku pavadinimu.
   1. Pasirinkite **Taikyti**, kad užbaigtumėte ryšių konfigūraciją.

   > [!NOTE]
   > Galite konfigūruoti daugiau ryšių tarp kontakto objekto ir kitų kliento objektų su integuojainiais objektais.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Įvairių ryšių vizualizavimas jungia kontaktų objektus su kliento objektais.":::

1. Baigę **konfigūruoti** ryšį, pažymėkite Kitas.

1. Norėdami **nustatyti semantinio tipo** žingsnį, pasirinkite **semantinio tipo**. Šiuo metu yra vienas **semantinis tipas** vadinamas *ContactProfile*.

1. Susiekite savo duomenis su *ContactProfile* **semantinio tipo** rodomais laukais.
   - Būtinas laukas: Kontakto ID
   - Pasirinktiniai laukai: vardas, pavardė, gimimo data, lytis, pagrindinis el. pašto adresas ir pagrindinis telefonas

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Susiekite kontaktų duomenų atributus su pateikiamais reikiamais ir pasirinktiniais laukais.":::

1. Norėdami tęsti, spustelėkite **Pirmyn**.

1. Peržiūros **žingsnyje** peržiūrėkite semantinio susiejimo konfigūraciją. Pasirinkite **Redaguoti** atitinkamą skyrių, kad būtų atlikti pakeitimai.

1. Pažymėkite **Įrašyti**, kad įrašytumėte naują **semantinio susiejimo** parinktį.

1. Įrašę galite pažymėti **Vykdyti** procesų sekantį susiejimą arba galite pažymėti **Uždaryti** kad įrašytumėte savo semantinį susiejimą jo neap apdorojimo.

1. Norėdami vėliau paleisti semaninį susiejimą, pažymėkite semaninį susiejimą ir **atnaujinkite**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Valdyti esamus semaninius susiejimus

**Duomenų** > **semantikų susiejimuose (peržiūroje)** galite peržiūrėti visus įrašytus semaninius susiejimus ir juos valdyti. Kiekvieną semaninį susiejimą nurodo atskira eilutė. Rasite išsamią informaciją apie šaltinio objektą, semaninį tipą, susiejimo tipą ir jo būseną.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semantinio susiejimo valdymo parinktys.":::

- Peržiūros **Redaguoti** Atverkite semantinio susiejimo nustatymo peržiūros veiksmo konfigūraciją. Galite pakeisti dabartinę konfigūraciją. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

- **Atnaujinti**: atnaujina pažymėtą semaninį susiejimą su naujausiais objektų, kurie yra konfigūracijos dalis, duomenimis. Atnaujinus bet kurį nurodytą semaninį susiejimą bus atnaujinti visi to paties tipo semantiniai susiejimai.

- **Pervardykite**: atidaromas dialogas, kuriame galite įvesti kitą pažymėto semantinio susiejimo pavadinimą. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

- **Naikinti**: atidaro dialogą, kad patvirtintų pažymėto semantinio susiejimo naikinimą. Taip pat vienu metu galite panaikinti daugiau nei vieną semaninį susiejimą pažymėdami semaninius susiejimus ir naikinimo piktogramą. Pasirinkite **Naikinti** naikinimo patvirtinimui.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>"ContactProfile" semantinio objekto susiejimo naudojimas kontakto lygio veiklai kurti

Sukūrę *"ContactProfile* " semantinio objekto susiejimą, galite užfiksuoti kontaktų veiklą. Tai leidžia paskyros veiklos laiko juostoje matyti, kuris kontaktas buvo atsakingas už kiekvieną veiklą. Dauguma veiksmų atliekami pagal įprastą veiklos susiejimo konfigūraciją.

   > [!NOTE]
   > Kad kontakto lygio veikla veiktų, veiklos duomenyse turite turėti **ir kliento ID,** ir **contactID** atributus kiekvienam įrašui.

1. [Apibrėžkite *"ContactProfile* " semantinio objekto susiejimą.](#define-a-contactprofile-semantic-entity-mapping) Ir paleiskite semantinį atvaizdavimą.

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

1. Jūsų kontakto lygio veikla dabar bus matoma kliento laiko juostoje.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Galutinis rezultatas sukonfigūravus kontaktinę veiklą":::

### <a name="contact-level-activity-timeline-filtering"></a>Kontakto lygio veiklos laiko planavimo juostos filtravimas

Sukonfigūravus kontakto lygio veiklos susiejimą ir jį paleidus, jūsų klientų veiklos laiko juosta bus atnaujinta. Tai apima jų ID arba pavadinimus, atsižvelgiant į jūsų *"ContactProfile* " konfigūraciją, skirtą veiklai, kurią jie veikė. Laiko planavimo juostoje galite filtruoti veiklą pagal kontaktus, kad pamatytumėte konkrečius jus dominančius kontaktus. Be to, galite matyti visas veiklas, kurios nepriskirtos konkrečiam kontaktui, pasirinkdami **Veikla, nesusieta su kontaktu**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Galimos kontakto lygio veiklos filtravimo parinktys.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
