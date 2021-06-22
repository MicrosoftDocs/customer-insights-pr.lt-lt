---
title: Ryšiai tarp objektų ir objektų kelių
description: Sukurkite ir valdykite ryšius tarp objektų daugeliui duomenų šaltinių.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171174"
---
# <a name="relationships-between-entities"></a>Objektų ryšiai

Ryšiai jungia objektus ir apibrėžia jūsų duomenų grafą, kai objektai turi bendrą identifikatorių – išorinį raktą. Šis išorinis raktas gali būti nurodomas iš vieno objekto į kitą. Sujungti objektai įgalina segmentų ir matavimų apibrėžimus, remiantis keliais duomenų šaltiniais.

Yra trys ryšių tipai: 
- Neredaguotini sistemos ryšiai, kurios sukūrė sistema kaip duomenų suvienodinimo proceso dalį
- Neredaguotini paveldėti ryšiai, automatiškai sukuriami įtraukiant duomenų šaltinius 
- Redaguotini pasirinktiniai ryšiai, kuriuos sukūrė ir sukonfigūravo vartotojai

## <a name="non-editable-system-relationships"></a>Neredaguotini sistemos ryšiai

Duomenų suvienodinimo metu sistemos ryšiai yra sukuriami automatiškai pagal pažangųjį gretinimą. Šie ryšiai padeda susieti kliento profilį su atitinkamais įrašais. Šioje diagramoje pavaizduotas trijų sistema pagrįstų ryšių kūrimas. Kliento objektas sugretinamas su kitais objektais, kad būtų galima sukurti vieningąjį *Kliento* objektą.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama su ryšio keliais į kliento objektą su trimis 1-n ryšiais.":::

- ***„Kliento su Kontaktu”* ryšys** buvo sukurtas tarp *Kliento* ir *Kontakto* objektų. *Kliento* objektas gauna rakto lauką **„Contact_contactID”**, susiejamą su *Kontakto* objekto rakto lauku **Kontakto ID**.
- ***„Kliento su Abonementu”* ryšys** buvo sukurtas tarp *Kliento* ir *Abonemento* objektų. *Kliento* objektas gauna rakto lauką **„Account_accountID”**, susiejamą su *Abonemento* objekto rakto lauku **Abonemento ID**.
- ***„Kliento su Žiniatinklio abonementu”* ryšys** buvo sukurtas tarp *Kliento* ir *Žiniatinklio abonemento* objektų. *Kliento* objektas gauna rakto lauką **„AWebAccount_webaccountID”**, susiejamą su *Žiniatinklio abonemento* objekto rakto lauku **Žiniatinklio abonemento ID**.

## <a name="non-editable-inherited-relationships"></a>Neredaguotini paveldėti ryšiai

Duomenų įtraukimo proceso metu sistema patikrina duomenų šaltinius esamiems ryšiams. Jei nėra jokių ryšių, sistema juos sukuria automatiškai. Šie ryšiai taip pat naudojami procesų pabaigose.

## <a name="create-a-custom-relationship"></a>Pasirinktinio ryšio kūrimas

Ryšys susideda iš *šaltinio objekto*, kuriame yra išorinis raktas, ir *paskirties objekto*, kurį nurodo šaltinio objekto išorinis raktas. 

1. Auditorijos įžvalgose eikite į **Duomenys** > **Ryšiai**.

2. Pasirinkite **Naujas ryšys**.

3. Srityje **Naujas ryšys** nurodykite tolesnę informaciją:

   :::image type="content" source="media/relationship-add.png" alt-text="Naujo ryšio šoninė sritis su tuščiais įvesties laukais.":::

   - **Ryšio pavadinimas**: Pavadinimas, atspindintis ryšio tikslą. Pavyzdys: „Klientas į Palaikymo atvejį”.
   - **Aprašymas**: Ryšio aprašymas.
   - **Šaltinio objektas**: Objektas, naudojamas kaip ryšio šaltinis. Pavyzdys: Palaikymo atvejis.
   - **Paskirties objektas**: Objektas, naudojamas kaip ryšio paskirtis. Pavyzdys: Klientas.
   - **Šaltinio skaičius**: Nurodykite šaltinio objekto skaičių. Skaičius apibūdina galimų rinkinio elementų skaičių. Jis visada susijęs su paskirties skaičiumi. Galite pasirinkti iš **Vieno** ir **Daugelio**. Palaikomi tik „daugelis su vienu“ ir „vienas su vienu“ tipo ryšiai.  
     - „Daugelis su vienu”: Keli šaltinio įrašai gali būti susiję su vienu paskirties įrašu. Pavyzdys: Keli palaikymo atvejai iš vieno kliento.
     - „Vienas su vienu”: Vienas šaltinio įrašas susijęs su vienu paskirties įrašu. Pavyzdys: Vienas lojalumo ID vienam klientui.

     > [!NOTE]
     > Ryšius „daugelis su daugeliu” galima kurti naudojant du „daugelis su vienu” ryšius ir susiejimo objektą, sujungiantį šaltinio ir paskirties objektus.

   - **Paskirties skaičius**: Pasirinkite paskirties objekto įrašų skaičių. 
   - **Šaltinio rakto laukas**: Išorinio rakto laukas šaltinio objekte. Pavyzdys: Atvejo palaikymas gali naudoti Atvejo ID kaip išorinio rakto lauką.
   - **Paskirties rakto laukas**: Paskirties objekto rakto laukas. Kliento pavyzdys gali naudoti **Kliento ID** rakto lauką.

4. Pasirinkite **Įrašyti** pasirinktinio ryšio kūrimui.

## <a name="view-relationships"></a>Ryšių peržiūra

Ryšių puslapyje išvardyti visi sukurti ryšiai. Kiekviena eilutė nurodo ryšį, kuriame taip pat pateikiama išsami informacija apie šaltinio objektą, paskirties objektą ir skaičių. 

:::image type="content" source="media/relationships-list.png" alt-text="Ryšių ir parinkčių sąrašas Ryšių puslapio veiksmų juostoje.":::

Šiame puslapyje pateikiamas esamų ir naujų ryšių parinkčių rinkinys: 
- **Naujas ryšys**: [Kurti pasirinktinį ryšį](#create-a-custom-relationship).
- **Vizualizavimo priemonė**: [Naršykite ryšių vizualizavimo priemonę](#explore-the-relationship-visualizer), kad matytumėte esamų ryšių ir jų skaičiaus tinklo diagramą.
- **Filtruoti pagal**: Pasirinkite sąraše norimų rodyti ryšių tipą.
- **Ieškoti ryšių**: Naudokite tekstinę iešką ryšių ypatybėms.

### <a name="explore-the-relationship-visualizer"></a>Ryšių vizualizavimo priemonės naršymas

Ryšių vizualizavimo priemonė rodo esamų ryšių tarp susietų objektų ir jų skaičiaus tinklo diagramą.

Norėdami tinkinti rodinį, galite pakeisti laukų padėtį nuvilkdami juos į drobę.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Ryšių vizualizavimo priemonės tinklo diagramos su ryšiais tarp susijusių objektų ekrano kopija.":::

Galimos parinktys: 
- **Eksportuoti kaip vaizdą**: Įrašo dabartinį rodinį kaip vaizdinį failą.
- **Pakeisti į horizontalų/vertikalų išdėstymą**: Pakeičia objektų ir ryšių lygiuotę.
- **Redaguoti**: Atnaujina pasirinktinių ryšių ypatybes redagavimo srityje ir įrašo pakeitimus.

## <a name="manage-existing-relationships"></a>Esamų ryšių valdymas 

Ryšių puslapyje kiekvieną ryšį atspindi eilutė. 

Pasirinkite ryšį ir vieną iš šių parinkčių: 
 
- **Redaguoti**: Atnaujina pasirinktinių ryšių ypatybes redagavimo srityje ir įrašo pakeitimus.
- **Naikinti**: Naikina pasirinktinius ryšius.
- **Peržiūrėti**: Rodomi sistemos sukurti ir paveldėti ryšiai. 

## <a name="next-step"></a>Tolesnis veiksmas

Sistemos ir pasirinktiniai ryšiai naudojami [segmentams kurti](segments.md), remiantis keliais duomenų šaltiniais, kurie nebėra izoliuoti.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
