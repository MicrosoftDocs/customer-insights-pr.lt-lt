---
title: Duomenų suvienodinimo objektų ir atributų susiejimas
description: Pažymėkite objektus, atributus, pirminius raktus ir semantikus, kuriuos norite susieti duomenis su vieningu kliento profiliu.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673273"
---
# <a name="map-entities-and-attributes"></a>Susiekite objektus ir atributus

**Žemėlapis** yra pirmasis etapas duomenų suvienodinimo publikos įžvalgų procese. Susiejimą sudaro trys etapai:

- *Objekto pasirinkimas*: nustatykite suderinamus objektus, kurie nukreipia į duomenų rinkinį su išsamesne informacija apie jūsų klientus.
- *Atributo pasirinkimas*: kiekvienam objektui nustatykite stulpelius, kuriuos norite sujungti ir suderinti *atitikimo* ir *sujungimo* etapuose. Šie stulpeliai yra vadinami *Atributais*.
- *Pirminio rakto ir semantinio tipo pasirinkimas*: kiekvienam objektui nustatykite atributą, kurį norite apibrėžti kaip to objekto pirminį raktą, ir kiekvienam atributui nustatykite semantinį tipą, geriausiai apibūdinantį tą atributą.

Daugiau informacijos apie bendrą duomenų suvienodinimo srautą galite rasti čia [Suvienodinti](data-unification.md).

## <a name="select-the-first-entities"></a>Pasirinkti pirmus objektus

1. Publikos įžvalgose, eikite į **Duomenys** > **Sujungti** > **Žemėlapis**.

2. Pradėkite schemos etapą pasirinkdami **Pasirinkti objektus**.

3. Pasirinkite objektus ir atributus, kuriuos norite naudoti *gretinimo* ir *suliejimo* etapuose. Reikiamus atributus galite pasirinkti atskirai iš objekto arba įtraukti visus objekto atributus pažymėdami žymės langelį **Įtraukti visus laukus** objekto lygyje. Rekomenduojame pasirinkti bent du objektus, kad duomenų suvienijimo procesas būtų naudingas.

   > [!div class="mx-imgBorder"]
   > ![Objektų įtraukimo pavyzdys.](media/data-manager-configure-map-add-entities-example.png "Įtraukti objektų pavyzdį")

   Šiame pavyzdyje įtraukiame objektus **eCommerceContacts** ir **loyCustomers**. Pasirinkę šiuos objektus galite gauti įžvalgų apie tai, kurie internetinio verslo klientai yra lojalumo programos nariai.
   
   Galite ieškoti raktažodžių visuose atributuose ir objektuose, kad pasirinktumėte reikiamus atributus, kuriuos norite susieti.
   
     > [!div class="mx-imgBorder"]
   > ![Laukų ieškos pavyzdys.](media/data-manager-configure-map-search-fields-example.png "Laukų ieškos pavyzdys")

4. Pasirinkite **Taikyti**, kad patvirtintumėte pasirinkimus.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pirminio rakto ir atributų semantinio tipo pasirinkimas

Pasirinkus objektus, puslapyje **Susieti** išvardijami pasirinkti objektai, kad galėtumėte juos peržiūrėti. Apibrėžkite objekto pirminį raktą ir nurodykite objekto atributo semantinį tipą.

- **Pirminis raktas**: kiekvienam savo objektui pasirinkite vieną atributą kaip pirminį raktą. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai ir bus rodomi lauke, kad galėtumėte pasirinkti.

- **Atributo semantinis tipas**: jūsų atributų kategorijos, pavyzdžiui, el. pašto adresas arba pavadinimas. Norėdami naudoti DI modelius išmaniojoje semantikos prognozėje, taupyti laiką ir pagerinti tikslumą, nustatykite parametro **Išmanusis susiejimas** parinktį **ĮJUNGTA**. Išmanusis susiejimas paryškina DI pagrįstą semantikos rekomendaciją lauke **Tipas**. Jei nustatysite parinktį **IŠJUNGTA**, matysite įprastas susiejimo rekomendacijas. Galite pasirinkti bet kurį semantinį tipą iš galimų parinkčių sąrašo ir perrašyti siūlomą žymėjimą.

> [!div class="mx-imgBorder"]
> ![Atributo tipas ir semantinė prognozė.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Atributo tipas ir semantinė prognozė")

Taip pat galima pridėti pasirinktinį semantinį tipą. Pasirinkite šiam atributui skirtą lauko tipą ir įrašykite savo pasirinktą semantinio tipo pavadinimą. Tokiu būdu taip pat galite pakeisti atributų tipus, kurie buvo identifikuoti sistemos.

Visi atributai, kuriems automatiškai nustatomas semantinis tipas, sugrupuojami skyriuje **Susietų laukų peržiūra**. Peržiūrėkite šiuos atributus ir jų semantinius tipus, nes jie bus naudojami jūsų objektams sulieti duomenų sujungimo proceso suliejimo etape.

Atributai, kurie automatiškai nesusiejami su semantiniu tipu, sugrupuojami skyriuje **Nesusietų laukų duomenų apibrėžimas**. Pasirinkite nesusietų atributų semantinio tipo lauką arba įveskite pasirinktinį atributo tipo pavadinimą.

> [!div class="mx-imgBorder"]
> ![Pirminio rakto ir atributo tipas.](media/data-manager-configure-map-add-attributes.png "Pirminio rakto ir atributo tipas")

> [!NOTE]
> Vienas laukas turi būti susiejamas su semantiniu tipu Person.FullName, kad kliento pavardė būtų automatiškai įvesta kliento kortelėje. Priešingu atveju kliento kortelės bus be vardo. 

## <a name="add-and-remove-attributes-and-entities"></a>Atributų ir objektų įtraukimas bei šalinimas

1. Dalyje **Sujungti** > **Susieti** pasirinkite **Redaguoti laukus**.

2. Srityje **Redaguoti laukus** įtraukite arba pašalinkite atributus ir objektus. Naudokite iešką arba slinkite, kad rastumėte ir pažymėtumėte dominančius atributus ir objektus. Jei atributas ar objektas jau sugretintas, jų pašalinti negalima.

   > [!div class="mx-imgBorder"]
   > ![Įtraukti arba ištrinti atributus.](media/configure-data-map-edit.png "Įtraukti arba ištrinti atributus")

3. Pasirinkite **Taikyti**.

## <a name="add-images-to-profiles"></a>Vaizdų įtraukimas į profilius

Jei objekte yra viešai prieinamų profilio vaizdų ar logotipų URL, galite juos įtraukti į sujungtą kliento profilį.

Pasirinkite objektą ir raskite lauką, kuriame yra profilio vaizdo URL. Įvesties lauke **Tipas** rankiniu būdu įveskite toliau nurodytą reikšmę. 
- Asmuo: Person.ProfileImage
- Organizacija: Organization.LogoImage

Atlikite kitus sujungimo veiksmus ir įsitikinkite, kad atributas, kuriame yra vaizdo URL, taip pat įtraukiamas į veiksmą [Sulieti](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Nustatyti atributus organizacijoms

Organizacijoms (peržiūra) atributo tipas turi būti susietas su „Organization.Name“
> [!div class="mx-imgBorder"]
> ![Pirminis raktas ir atributo tipas B2B.](media/configure-data-map-edit-b2b.png "Pirminis raktas ir atributo tipas B2B")

## <a name="next-step"></a>Kitas veiksmas

Duomenų suvienijimo proceso metu nueikite į **suderinimo** puslapį. Aplankykite [**suderinti**](match-entities.md) norėdami sužinoti apie šį etapą.

> [!TIP]
> Peržiūrėkite šį vaizdo įrašą: [Pradžia: vieningo kliento profilio sukūrimas](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]