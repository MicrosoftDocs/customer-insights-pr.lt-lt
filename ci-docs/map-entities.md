---
title: Duomenų suvienijimo šaltinio laukų pasirinkimas
description: Pirmasis suvienijimo proceso veiksmas yra objektų, atributų, pirminių raktų ir semantinių tipų pasirinkimas, kad duomenys būtų susieti su vieningu kliento profiliu.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139792"
---
# <a name="select-source-fields-for-data-unification"></a>Duomenų suvienijimo šaltinio laukų pasirinkimas

Pirmasis suvienijimo žingsnis yra duomenų rinkiniuose esančių objektų ir laukų, kuriuos norite suvienodinti, pasirinkimas. Pasirinkite objektus, kuriuose yra su klientais susijusios informacijos, pvz., vardas, adresas, telefono numeris ir el. paštas. Galite pasirinkti vieną ar daugiau objektų.

## <a name="select-entities-and-fields"></a>Pasirinkti objektus ir laukus

1. Eikite į **Duomenų** > **suvienodinimas**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Nukreipimo puslapio suvienodinimo, skirto pirmam vykdymo patirčiai su paryškinta darbo pradžia, ekrano nuotrauka.":::

1. Pasirinkite **Pradėti**.

1. Puslapyje Šaltinio **laukai** pasirinkite **Pasirinkti objektus ir laukus**. Rodoma **sritis Pasirinkti objektus ir laukus**.

1. Pažymėkite bent vieną objektą.

1. Kiekvienam pasirinktam objektui identifikuokite laukus, kuriuos norite naudoti, kad suderintumėte kliento įrašus ir laukus, kuriuos norite įtraukti į vieningąjį profilį. Šie laukai vadinami *Atributais*. Galite pasirinkti reikiamus atributus atskirai iš objekto arba įtraukti visus objekto atributus pažymėdami žymimąjį laukelį objekto lygiu. Galite ieškoti raktažodžių visuose atributuose ir objektuose, kad pasirinktumėte reikiamus atributus, kuriuos norite susieti.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Pasirinktų objektų ir atributų ekrano kopija.":::

   Šiame pavyzdyje įtraukiame objektus **Kontaktai** ir **KlientasLoyalty**. Pasirinkę šiuos objektus galite gauti įžvalgų apie tai, kurie internetinio verslo klientai yra lojalumo programos nariai.

1. Pasirinkite **Taikyti**, kad patvirtintumėte pasirinkimus. Rodomi pasirinkti objektai ir atributai.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pirminio rakto ir atributų semantinio tipo pasirinkimas

   :::image type="content" source="media/m3_select_primary.png" alt-text="Pasirinktų objektų, kurių pirminis raktas nepasirinktas, ekrano kopija." lightbox="media/m3_select_primary.png":::

Su kiekvienu objektu atlikite šiuos veiksmus.

1. Pasirinkite pagrindinį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.

1. Norėdami naudoti dirbtinio intelekto modelius išmaniosioms semantikos prognozė, sutaupykite laiko ir pagerinkite tikslumą, užtikrinkite, kad **įjungtas išmanusis susiejimas**. Išmanusis susiejimas paryškina DI pagrįstą semantikos rekomendaciją lauke **Tipas**. Galite nepaisyti siūlomo pasirinkimo pasirinkdami bet kurį semantinį tipą iš galimų parinkčių sąrašo.

1. Kiekvienam atributui pasirinkite semantinį **tipą**, kuris geriausiai apibūdina tą atributą, pvz., vardą, miestą arba el. pašto adresą.

   > [!NOTE]
   > Vienas laukas turi būti susietas su semantiniu tipu *Person.FullName*, kad kliento kortelėje būtų įrašytas kliento vardas. Priešingu atveju kliento kortelės bus be vardo.

   1. Norėdami pakeisti sistemos identifikuojamą atributo tipą, pasirinkite kitą tipą. Jei tipo nėra, sukurkite pasirinktinį semantinį tipą pasirinkdami atributo lauką **Tipas** ir įvesdami pasirinktinį semantinio tipo pavadinimą.

   1. Norėdami į viešai pasiekiamus profilio vaizdus arba logotipus įtraukti atributą, kuriame yra URL, pasirinkite objektą ir lauką, kuriame yra URL. **Lauke Tipas** įveskite:
      - Asmuo: Person.ProfileImage
      - Organizacija: Organization.LogoImage

   1. Norėdami gauti abonemento pavadinimo atributą, lauke Tipas **įveskite "Organization.Name"**.

1. Peržiūrėkite atributus, kuriuose automatiškai identifikuojamas semantinis tipas. Šie atributai išvardyti dalyje **Peržiūrėti susietus laukus**. Tik to paties tipo atributai gali būti derinami atliekant veiksmą **Vieningieji kliento laukai**. Semantiniai tipai naudojami automatiškai siūlyti įžvalgas. Įsitikinkite, kad pasirinkti tipai yra nuoseklūs visuose pasirinktuose objektuose.

1. Atributams, kurie nėra automatiškai susieti su semantiniu tipu, pasirinkite semantinio tipo lauką, įveskite pasirinktinį atributo tipo pavadinimą arba palikite juos nepažymėtus. Šie atributai išvardyti dalyje **Duomenų apibrėžimas neuždengtuose laukuose**.

1. Atlikę kiekvieno objekto veiksmus, pasirinkite **Įrašyti šaltinio laukus**.

1. Pasirinkite **Toliau**.

> [!div class="nextstepaction"]
> [Kitas veiksmas: pašalinkite dublikatus](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
