---
title: Ryšiai tarp objektų ir objektų kelių
description: Sukurkite ir valdykite ryšius tarp objektų daugeliui duomenų šaltinių.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183576"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Ryšiai tarp objektų ir objektų kelių

Ryšiai jungia objektus ir apibrėžia jūsų duomenų grafą, kai objektai turi bendrą identifikatorių – išorinį raktą. Šis išorinis raktas gali būti nurodomas iš vieno objekto į kitą. Sujungti objektai įgalina segmentų ir matavimų apibrėžimus, remiantis keliais duomenų šaltiniais.

Yra trys ryšių tipai: 
- Neredaguojamus sistemos ryšius sistema sukuria kaip duomenų suvienijimo proceso dalį
- Neredaguojami paveldimi ryšiai sukuriami automatiškai iš praryjančių duomenų šaltinių
- Redaguojamus pasirinktinius ryšius kuria ir konfigūruoja vartotojai

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

1. Eikite į **Duomenys** > **Ryšiai**.

2. Pasirinkite **Naujas ryšys**.

3. Srityje **Naujas ryšys** nurodykite tolesnę informaciją:

   :::image type="content" source="media/relationship-add.png" alt-text="Naujo ryšio šoninė sritis su tuščiais įvesties laukais.":::

   - **Ryšio pavadinimas**: Pavadinimas, atspindintis ryšio tikslą. Pavyzdys: „Klientas į Palaikymo atvejį”.
   - **Aprašymas**: Ryšio aprašymas.
   - **Šaltinio objektas**: Objektas, naudojamas kaip ryšio šaltinis. Pavyzdys: Palaikymo atvejis.
   - **Paskirties objektas**: Objektas, naudojamas kaip ryšio paskirtis. Pavyzdys: Klientas.
   - **Šaltinio kardinalumas**: šaltinio subjekto kardinalumas. Skaičius apibūdina galimų rinkinio elementų skaičių. Jis visada susijęs su paskirties skaičiumi. Galite pasirinkti iš **Vieno** ir **Daugelio**. Palaikomi tik „daugelis su vienu“ ir „vienas su vienu“ tipo ryšiai.  
     - „Daugelis su vienu”: Keli šaltinio įrašai gali būti susiję su vienu paskirties įrašu. Pavyzdys: Keli palaikymo atvejai iš vieno kliento.
     - „Vienas su vienu”: Vienas šaltinio įrašas susijęs su vienu paskirties įrašu. Pavyzdys: Vienas lojalumo ID vienam klientui.

     > [!NOTE]
     > Ryšius „daugelis su daugeliu” galima kurti naudojant du „daugelis su vienu” ryšius ir susiejimo objektą, sujungiantį šaltinio ir paskirties objektus.

   - **Tikslinis kardinalumas**: tikslinio subjekto įrašų kardinalumas.
   - **Šaltinio rakto laukas**: laukas Išorinis raktas šaltinio objekte. Pavyzdys: "SupportCase" naudoja **CaseID** kaip išorinio rakto lauką.
   - **Paskirties rakto laukas**: tikslinio objekto pagrindinis laukas. Pavyzdys: klientas naudoja **"CustomerID** " kaip pagrindinį lauką.

4. Pasirinkite **Įrašyti** pasirinktinio ryšio kūrimui.

## <a name="set-up-account-hierarchies"></a>Nustatyti klientų hierarchijas

Aplinkos, sukonfigūruotos naudoti verslo paskyras kaip pagrindinę tikslinę auditoriją, gali konfigūruoti susijusių verslo paskyrų hierarchijas. Pavyzdžiui, įmonė, kuri turi atskirus verslo vienetus.

Organizacijos kuria abonementų hierarchijas, kad galėtų geriau valdyti abonementus ir jų ryšius tarpusavyje. "Customer Insights" palaiko tėvų ir antrinių paskyrų hierarchijas, kurios jau yra perpildytuose klientų duomenyse. Pavyzdžiui, klientai iš „Dynamics 365 Sales". Šias hierarchijas galima konfigūruoti **puslapyje Ryšiai**.

1. Eikite į **Duomenys** > **Ryšiai**.
1. Pasirinkti **Klientų hierarchija** skirtuką.
1. Pasirinkti **Nauja klientų hierarchija**.
1. Srityje **Kliento hierarchija** pateikite hierarchijos pavadinimą. Sistema sukuria išvesties objekto pavadinimą, bet jūs galite jį pakeisti.
1. Pažymėkite objektą, kuriame yra jūsų abonementų hierarchija. Paprastai tai yra tame pačiame objektuje, kuriame yra klientai.
1. **Pasirinkite paskyros UID** ir **pirminį UID** iš pasirinkto objekto.
1. Pasirinkite **Įrašyti**, kad užbaigtumėte paskyros hierarchiją.

## <a name="manage-existing-relationships"></a>Esamų ryšių valdymas

Eikite **į puslapį Ryšiai** ir peržiūrėkite visus sukurtus ryšius, jų šaltinio objektą, paskirties objektą ir kardinalumą.

:::image type="content" source="media/relationships-list.png" alt-text="Ryšių ir parinkčių sąrašas Ryšių puslapio veiksmų juostoje.":::

**Naudokite ryšių** parinktis Filtruoti pagal **arba** Ieškoti, kad rastumėte konkretų ryšį. Norėdami pamatyti esamų ryšių ir jų kardinalumo tinklo diagramą, pasirinkite [**Vizualizatorius**](#explore-the-relationship-visualizer).

Pasirinkite ryšį, kad peržiūrėtumėte galimus veiksmus:
- **Redaguoti**: Atnaujina pasirinktinių ryšių ypatybes redagavimo srityje ir įrašo pakeitimus.
- **Naikinti**: Naikina pasirinktinius ryšius.
- **Peržiūrėti**: Rodomi sistemos sukurti ir paveldėti ryšiai.

### <a name="explore-the-relationship-visualizer"></a>Ryšių vizualizavimo priemonės naršymas

Ryšių vizualizavimo priemonė rodo esamų ryšių tarp susietų objektų ir jų skaičiaus tinklo diagramą. Taip pat vizualizuoja ryšio kelią.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Ryšių vizualizavimo priemonės tinklo diagramos su ryšiais tarp susijusių objektų ekrano kopija.":::

Norėdami tinkinti rodinį, galite pakeisti laukų padėtį nuvilkdami juos į drobę. Kitos parinktys: 
- **Eksportuoti kaip vaizdą**: Įrašo dabartinį rodinį kaip vaizdinį failą.
- **Pakeisti į horizontalų/vertikalų išdėstymą**: Pakeičia objektų ir ryšių lygiuotę.
- **Redaguoti**: Atnaujina pasirinktinių ryšių ypatybes redagavimo srityje ir įrašo pakeitimus.

## <a name="relationship-paths"></a>Ryšio keliai

Ryšio kelias apibūdina objektus, kurie susieti su ryšiais tarp šaltinio objekto ir tikslinio objekto. Jis naudojamas kuriant segmentą arba matą, kuriame yra kitų objektų nei vieningas profilio objektas, ir yra kelios parinktys, leidžiančios pasiekti vieningojo profilio objektą. Įvairūs ryšio keliai gali pateikti skirtingus rezultatus.

Pavyzdžiui, objektas, *eCommerce_eCommercePurchases* su vieningojo profilio kliento objektu, turi *Kliento* ryšius:

- eCommerce_eCommercePurchases > klientas
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > klientas
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Klientas

Ryšių kelias nurodo, kuriuos objektus galite naudoti kurdami priemonių arba segmentų taisykles. Pasirinkus parinktį su ilgiausią ryšio kelią tikriausiai bus gauti mažiau rezultatų, nes sutampantys įrašai turi būti visų objektų dalis. Šiame pavyzdyje klientas turi būti įsigijęs prekes per el. komerciją(eCommerce_eCommercePurchases) at a point of sale(POS_posPurchases) ir dalyvauti mūsų lojalumo programoje (loyaltyScheme_loyCustomers). Pasirinkę pirmą parinktį tikriausiai gausite daugiau rezultatų, nes klientams reikės tik vieno papildomo objekto.

### <a name="direct-relationship"></a>Tiesioginis ryšys

Ryšys yra konvertuojamas kaip **tiesioginis ryšys**, kai šaltinio objektas yra susijęs su paskirties objektu su tik vienu ryšiu.

Pavyzdžiui, jei veiklos objektas vadinamas *eCommerce_eCommercePurchases* jungiasi prie paskirties objekto *eCommerce_eCommerceContacts* per *ContactId* tai yra tiesioginis ryšys.

:::image type="content" source="media/direct_Relationship.png" alt-text="Šaltinio objektas tiesiogiai jungiasi prie tikslinio objekto.":::

#### <a name="multi-path-relationship"></a>Kelių kelių santykiai

**Kelių maršrutų ryšys** yra specialaus tipo tiesioginis ryšys, jungiantis šaltinio objektą su daugiau nei vienu tiksliniu objektu.

Pavyzdžiui, jei veiklos objektas, kurio pavadinimas *eCommerce_eCommercePurchases*  yra susijęs su dviem tiksliniais abiem *eCommerce_eCommerceContacts* ir *loyaltyScheme_loyCustomers*,tai yra kelių maršrutų ryšys.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Naudojant kelių objektų ryšį šaltinio objektas tiesiogiai jungiasi prie daugiau nei vieno tikslinio objekto.":::

### <a name="indirect-relationship"></a>Netiesioginis ryšys

Ryšys yra konvertuojamas kaip **netiesioginis ryšys**, kai šaltinio objektas yra susijęs su vienu ar daugiau papildomų objektų prieš susiejant su tiksliniu objektu.

#### <a name="multi-hop-relationship"></a>Kelių šuolių santykiai

**Kelių šaltinių ryšys** yra *nelydusis ryšys* leidžiantis šaltinio objektą susieti su paskirties objektu per vieną ar daugiau objektų.

Pvz., jei veiklos objektas, vadinamas *eCommerce_eCommercePurchasesWest*, jungiasi prie išsamus objektas, vadinamas *eCommerce_eCommercePurchasesEast* ir tada jungiasi su tiksliniu obkektu vadinamu *eCommerce_eCommerceContacts*, tai yra kelių objektų ryšys.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Šaltinio objektas tiesiogiai jungiasi prie tikslinio objekto su susijusiu objektu.":::

### <a name="multi-hop-multi-path-relationship"></a>Kelių šaltinių, kelių maršrutų ryšys

Kelių -inerti ir kelių ryšiai gali būti naudojami kartu kuriant **kelių šaltinių, kelių maršrutų ryšius**. Šis specialus tipas sujungia kelių objektų ir **kelių šaltinių** ir **kelių maršrutų ryšius**. Jis leidžia jums prisijungti prie daugiau nei vieno tikslinio objekto naudojant tarpinius objektus.

Pvz., jei veiklos objektas, vadinamas *eCommerce_eCommercePurchasesWest* sujungia su tarpiniu objektu pavadinimu *eCommerce_eCommercePurchasesEast* ir tada jungiasi su tiksliniu obkektu vadinamu *eCommerce_eCommerceContacts* ir *loyaltyScheme_loyCustomers*, nes tai yra kelių šaltinių, kelių maršrutų ryšys.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Šaltinio objektas tiesiogiai jungiasi prie vieno tikslinio objekto ir per tarpinį objektą jungiasi su kitu tiksliniu objektu.":::

## <a name="next-step"></a>Tolesnis veiksmas

Sistemos ir pasirinktiniai ryšiai naudojami [segmentams kurti](segments.md) ir [priemonėms](measures.md) pagrįstoms keliais duomenų šaltiniais, kurių nebenaudojama.

[!INCLUDE [footer-include](includes/footer-banner.md)]
