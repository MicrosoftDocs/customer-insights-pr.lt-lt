---
title: Semantiniai susiejimai (peržiūra)
description: Semantinio susiejimo apžvalga ir kaip juos naudoti.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622945"
---
# <a name="semantic-mappings"></a>Semantinis susiejimas

Naudojant semantiniai susiejimai leidžia susieti ne veiklos duomenis su iš anksto apibrėžtomis schemomis. Šios schemos padeda auditorijos įžvalgoms geriau suprasti jūsų duomenų atributus. Nuoseklus susiejimas ir pateikiami duomenys suteikia naujų įžvalgų ir funkcijų auditorijos įžvalgose. Norėdami susieti savo veiklos duomenis su schemomis, peržiūrėkite [veiklų](activities.md) dokumentaciją.

**Šiuo metu aplinkose, pagrįstose verslo klientais, yra įgalinti semantiniai susiejimai**. *ContactProfile* yra vienintelis sekos susiejimo tipas, kuris šiuo metu pasiekiamas auditorijos įžvalgose.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>ContactProfile semantinio objekto susiejimo apibrėžimas

1. Auditorijos įžvalgose eikite į **duomenų** > **semantiniai susiejimai (peržiūra)**.

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

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="manage-existing-semantic-mappings"></a>Valdyti esamus semaninius susiejimus

**Duomenų** > **semantikų susiejimuose (peržiūroje)** galite peržiūrėti visus įrašytus semaninius susiejimus ir juos valdyti. Kiekvieną semaninį susiejimą nurodo atskira eilutė. Rasite išsamią informaciją apie šaltinio objektą, semaninį tipą, susiejimo tipą ir jo būseną.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Semantinio susiejimo valdymo parinktys.":::

- Peržiūros **Redaguoti** Atverkite semantinio susiejimo nustatymo peržiūros veiksmo konfigūraciją. Galite pakeisti dabartinę konfigūraciją. Pasirinkite **Įrašyti** ir **Vykdyti**, kad apdorotumėte pakeitimus.

- **Atnaujinti**: atnaujina pažymėtą semaninį susiejimą su naujausiais objektų, kurie yra konfigūracijos dalis, duomenimis. Atnaujinus bet kurį nurodytą semaninį susiejimą bus atnaujinti visi to paties tipo semantiniai susiejimai.

- **Pervardykite**: atidaromas dialogas, kuriame galite įvesti kitą pažymėto semantinio susiejimo pavadinimą. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

- **Naikinti**: atidaro dialogą, kad patvirtintų pažymėto semantinio susiejimo naikinimą. Taip pat vienu metu galite panaikinti daugiau nei vieną semaninį susiejimą pažymėdami semaninius susiejimus ir naikinimo piktogramą. Pasirinkite **Naikinti** naikinimo patvirtinimui.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
