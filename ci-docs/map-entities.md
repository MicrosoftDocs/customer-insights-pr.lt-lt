---
title: Duomenų suvienijimo šaltinio laukų pasirinkimas
description: Pirmasis suvienijimo proceso veiksmas yra objektų, atributų, pirminių raktų ir semantinių tipų pasirinkimas, kad duomenys būtų susieti su vieningu kliento profiliu.
recommendations: false
ms.date: 08/12/2022
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
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304575"
---
# <a name="select-source-fields-for-data-unification"></a>Duomenų suvienijimo šaltinio laukų pasirinkimas

Pirmasis suvienijimo žingsnis yra duomenų rinkiniuose esančių objektų ir laukų, kuriuos norite suvienodinti, pasirinkimas. Pasirinkite objektus, kuriuose yra su klientais susijusios informacijos, pvz., vardas, adresas, telefono numeris ir el. paštas. Galite pasirinkti vieną ar daugiau objektų.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Pasirinkti objektus ir laukus

1. Eikite į **Duomenų** > **suvienodinimas**.

   Atskiriems klientams (nuo B iki C) **nukreipimo puslapyje "Unify** " rodoma, kurioje rodomi **laukai Pradėti** atliekant pirmąjį veiksmą **Šaltinio**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Nukreipimo puslapio suvienodinimo ekrano kopija, skirta pirmajam atskirų klientų paleidimui.":::

   Verslo paskyrų (nuo B iki B) **nukreipimo puslapyje "Unify"** rodomi "Unify" abonementai **·**, kuriuose rodomi **laukai Darbo pradžia** atliekant pirmąjį veiksmą Šaltinio.**·** Kontaktų **suvienijimo (peržiūros)** veiksmai yra pasirinktiniai ir laukia, kol bus baigtas paskyros suvienijimas.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Nukreipimo puslapio suvienodinimo, skirto verslo paskyroms pirmą kartą paleisti, ekrano kopija.":::

1. Pasirinkite **Pradėti**.

1. Puslapyje Šaltinio **laukai** pasirinkite **Pasirinkti objektus ir laukus**. Rodoma **sritis Pasirinkti objektus ir laukus**.

1. Pažymėkite bent vieną objektą.

1. Kiekvienam pasirinktam objektui identifikuokite laukus, kuriuos norite naudoti, kad suderintumėte kliento įrašus ir laukus, kuriuos norite įtraukti į vieningąjį profilį. Šie laukai vadinami *Atributais*. Galite pasirinkti reikiamus atributus atskirai iš objekto arba įtraukti visus objekto atributus pažymėdami žymimąjį laukelį objekto lygiu. Galite ieškoti raktažodžių visuose atributuose ir objektuose, kad pasirinktumėte reikiamus atributus, kuriuos norite susieti.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Pasirinktų objektų ir atributų ekrano kopija.":::

   Šiame pavyzdyje pridedame **el. prekyboscontacts ir** loyCustomer **objektus**. Pasirinkę šiuos objektus galite gauti įžvalgų apie tai, kurie internetinio verslo klientai yra lojalumo programos nariai.

1. Pasirinkite **Taikyti**, kad patvirtintumėte pasirinkimus. Rodomi pasirinkti objektai ir atributai.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pirminio rakto ir atributų semantinio tipo pasirinkimas

   :::image type="content" source="media/m3_select_primary.png" alt-text="Pasirinktų objektų, kurių pirminis raktas dar nepasirinktas, ekrano kopija." lightbox="media/m3_select_primary.png":::

Su kiekvienu objektu atlikite šiuos veiksmus.

1. Pasirinkite pagrindinį **raktą**. Pirminis raktas yra atributas, unikalus objektui. Kad atributas būtų tinkamas pirminis raktas, jame neturėtų būti pasikartojančių reikšmių, trūkstamų reikšmių arba neapibrėžtų reikšmių. Eilutės, sveikojo skaičiaus ir GUID duomenų tipo atributai palaikomi kaip pirminiai raktai.

1. Norėdami naudoti dirbtinio intelekto modelius išmaniosioms semantikos prognozė, kurios taupo laiką ir pagerina tikslumą, įsitikinkite, kad **įjungtas išmanusis susiejimas**. Išmanusis susiejimas pateikia dirbtiniu intelektu pagrįstas semantines **rekomendacijas lauke Tipas**.

1. Kiekvienam atributui pasirinkite semantinį **tipą**, kuris geriausiai apibūdina tą atributą, pvz., vardą, miestą arba el. pašto adresą.

   > [!NOTE]
   > Jei naudojate nuo B iki C, vienas laukas turi būti susietas su semantiniu tipu *Person.FullName*, kad kliento kortelėje būtų įrašytas kliento vardas. B-to-B paskyros pavadinimas turėtų būti susietas su *Organization.Name*. Priešingu atveju kliento kortelės bus be vardo.

   1. Norėdami perrašyti sistemos nustatytą atributo tipą, pasirinkite kitą parinktį. Jei tipo nėra, sukurkite pasirinktinį semantinį tipą pasirinkdami atributo lauką **Tipas** ir įvesdami pasirinktinį semantinio tipo pavadinimą.

   1. Norėdami į viešai pasiekiamus profilio vaizdus arba logotipus įtraukti atributą, kuriame yra URL, pasirinkite objektą ir lauką, kuriame yra URL. **Lauke Tipas** įveskite:
      - Asmuo: Person.ProfileImage
      - Organizacija: Organization.LogoImage

1. Peržiūrėkite atributus, kuriuose automatiškai identifikuojamas semantinis tipas. Šie atributai išvardyti dalyje **Peržiūrėti susietus laukus**. Veiksme Suvienodinti **kliento laukus galima sujungti tik to paties tipo atributus**. Semantiniai tipai naudojami automatiškai siūlyti įžvalgas. Įsitikinkite, kad pasirinkti tipai yra nuoseklūs visuose pasirinktuose objektuose.

1. Atributams, kurie nėra automatiškai susieti su semantiniu tipu, pasirinkite semantinio tipo lauką, įveskite pasirinktinio atributo tipo pavadinimą arba palikite juos nepažymėtus. Šie atributai išvardyti dalyje **Duomenų apibrėžimas neuždengtuose laukuose**.

1. Atlikę kiekvieno objekto veiksmus, pasirinkite **Įrašyti šaltinio laukus**.

1. Pasirinkite **Toliau**.

> [!div class="nextstepaction"]
> [Kitas veiksmas: pašalinkite dublikatus](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
