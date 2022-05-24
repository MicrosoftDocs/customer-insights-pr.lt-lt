---
title: Pasirinkti duomenų suvienijimo šaltinio laukus
description: Pirmasis suvienijimo proceso žingsnis yra objektų, atributų, pirminių raktų ir semantinių tipų pasirinkimas, kad duomenys būtų susieti su vieningu kliento profiliu.
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
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741005"
---
# <a name="select-source-fields-for-data-unification"></a>Pasirinkti duomenų suvienijimo šaltinio laukus

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pirmasis suvienijimo žingsnis yra objektų ir laukų pasirinkimas jūsų duomenų rinkiniuose, kuriuos norite suvienyti. Pasirinkite objektus, kuriuose yra su klientais susijusi informacija, pvz., vardas, adresas, telefono numeris ir el. paštas. Galite pasirinkti vieną ar daugiau objektų.

## <a name="select-entities-and-fields"></a>Pasirinkti objektus ir laukus

1. Eikite į **"Data** > **Unify"**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Pirmojo paleidimo patirties suliejimo ekrano nuotrauka, kurioje pažymėta darbo pradžia.":::

1. Pasirinkite **Pradėti**.

1. **Puslapyje Šaltinio laukai** pasirinkite **Pasirinkti objektus ir laukus**. Rodoma **sritis Pasirinkti objektus ir laukus**.

1. Pasirinkite bent vieną objektą.

1. Nurodykite kiekvieno pasirinkto objekto laukus, kuriuos norite naudoti, kad atitiktų kliento įrašus ir laukus, kuriuos norite įtraukti į vieningą profilį. Šie laukai vadinami *atributais*. Reikiamus atributus galite pasirinkti atskirai iš objekto arba įtraukti visus objekto atributus pažymėdami žymės langelį objekto lygiu. Galite ieškoti raktažodžių visuose atributuose ir objektuose, kad pasirinktumėte reikiamus atributus, kuriuos norite susieti.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Pasirinktų objektų ir atributų ekrano nuotrauka.":::

   Šiame pavyzdyje įtraukiame **objektus Kontaktai** ir **CustomerLoyalty**. Pasirinkę šiuos objektus galite gauti įžvalgų apie tai, kurie internetinio verslo klientai yra lojalumo programos nariai.

1. Pasirinkite **Taikyti**, kad patvirtintumėte pasirinkimus. Rodomi pasirinkti objektai ir atributai.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pirminio rakto ir atributų semantinio tipo pasirinkimas

   :::image type="content" source="media/m3_select_primary.png" alt-text="Pasirinktų objektų, kurių pirminis raktas nepasirinktas, ekrano nuotrauka." lightbox="media/m3_select_primary.png":::

Kiekvienam objektui atlikite šiuos veiksmus.

1. Pasirinkite pirminį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.

1. Norėdami naudoti dirbtinio intelekto modelius išmaniesiems semantikos prognozė, sutaupyti laiko ir pagerinti tikslumą, įsitikinkite, kad įjungtas **išmanusis žemėlapis**. Išmanusis susiejimas paryškina DI pagrįstą semantikos rekomendaciją lauke **Tipas**. Galite nepaisyti siūlomo pasirinkimo pasirinkdami bet kurį semantinį tipą iš galimo parinkčių sąrašo.

1. Kiekvienam atributui pasirinkite semantinį **tipą**, kuris geriausiai apibūdina tą atributą, pvz., vardą, miestą arba el. pašto adresą.

   > [!NOTE]
   > Vienas laukas turi būti susietas su semantiniu tipu *Person.FullName*, kad pirkėjo kortelėje būtų užpildytas pirkėjo vardas. Priešingu atveju kliento kortelės bus be vardo.

   1. Norėdami pakeisti sistemos identifikuotą atributo tipą, pasirinkite kitą tipą. Jei tipo nėra, sukurkite pasirinktinį semantinį tipą pasirinkdami **atributo lauką Tipas** ir įvesdami pasirinktinį semantinio tipo pavadinimą.

   1. Norėdami įtraukti atributą, kuriame yra URL, į viešai prieinamus profilio vaizdus ar logotipus, pasirinkite objektą ir lauką, kuriame yra URL. Lauke **Tipas** įveskite:
      - Asmuo: Person.ProfileImage
      - Organizacija: Organization.LogoImage

   1. Sąskaitos pavadinimo atributui lauke Tipas **įveskite**"Organization.Name".

1. Peržiūrėkite atributus, kuriuose semantinis tipas identifikuojamas automatiškai. Šie atributai išvardyti dalyje **Peržiūrėti susietus laukus**. Veiksme **Vieningas klientas laukuose** galima derinti tik to paties tipo atributus. Semantiniai tipai naudojami automatiškai siūlyti įžvalgas. Įsitikinkite, kad jūsų pasirinkti tipai yra nuoseklūs visuose pasirinktuose objektuose.

1. Atributams, kurie nėra automatiškai susieti su semantiniu tipu, pasirinkite semantinio tipo lauką, įveskite pasirinktinį atributo tipo pavadinimą arba palikite juos nesusietus. Šie atributai išvardyti dalyje **Apibrėžti duomenis nesusietuose laukuose**.

1. Atlikę kiekvieno objekto veiksmus, pasirinkite **Įrašyti šaltinio laukus**.

1. Pasirinkite **Toliau**.

> [!div class="nextstepaction"]
> [Kitas žingsnis: dublikatų šalinimas](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
