---
title: Suliekite objektus duomenų suvienyjime
description: Suliekite objektus tam, kad sukurtumėte suvienytus kliento profilius.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 5d5ff4c6f091d1b50d0f6c8366bbe4f0e6428dac
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268512"
---
# <a name="merge-entities"></a>Suliekite objektus

Suliejimo etapas yra paskutinis duomenų sujungimo proceso etapas. Jo tikslas – suderinti prieštaringus duomenis. Prieštaringų duomenų pavyzdžiai: kliento vardas, randamas dviejuose jūsų duomenų rinkiniuose, bet kiekviename iš jų rašomas šiek tiek skirtingai (pvz., „Grant Marshall“ ir „Grant Marshal“), arba telefono numeris, kurio formatas skiriasi (617-803-091X ir 617803091X). Šių prieštaringų duomenų taškų sujungimas atliekamas „atributas pagal atributą“ pagrindu.

Užbaigus [sutapdinimo etapą](match-entities.md) pradedamas suliejimo etapas, pasirinkus plytelę **Sulieti**, pateikiamą puslapyje **Sujungti**.

## <a name="review-system-recommendations"></a>Sistemos rekomendacijų peržiūra

Puslapyje **Sulieti** galite pasirinkti ir pašalinti atributus, kurie bus sulieti jūsų sujungtame kliento profilio objekte (konfigūravimo proceso rezultatas). Kai kuriuos atributus sistema sulieja automatiškai.

### <a name="view-merged-attributes"></a>Sulietų atributų peržiūra

Norėdami peržiūrėti atributus, įtrauktus į vieną iš automatiškai sulietų atributų, pažymėkite tą sulietą atributą. Du atributai, kurie sudaro sulietą atributą, rodomi dviejose naujose eilėse po sulietu atributu.

> [!div class="mx-imgBorder"]
> ![Sulieto atributo pasirinkimas](media/configure-data-merge-profile-attributes.png "Sulieto atributo pasirinkimas")

### <a name="separate-merged-attributes"></a>Sulietų atributų atskyrimas

Norėdami atskirti bet kurį automatiškai sulietą atributą arba atšaukti jo suliejimą, tą atributą susiraskite lentelėje **Profilio atributai**.

1. Pasirinkite mygtuką su daugtaškiu (...).
  
2. Išplečiamajame sąraše pasirinkite **Atskiri laukai**.

### <a name="remove-merged-attributes"></a>Sulietų atributų pašalinimas

Norėdami pašalinti atributą iš galutinio kliento profilio objekto, tą atributą susiraskite lentelėje **Profilio atributai**.

1. Pasirinkite mygtuką su daugtaškiu (...).
  
2. Išplečiamajame sąraše pasirinkite **Nesulieti**.

   Atributas perkeliamas į sekciją **Pašalinta iš kliento įrašo**.

## <a name="manually-add-a-merged-attribute"></a>Sulieto atributo įtraukimas rankiniu būdu

Norėdami įtraukti sulietą atributą, nueikite į puslapį **Suliejimas**.

1. Pasirinkite **Įtraukti sulietą atributą**.

2. Nurodykite **Pavadinimą**, kad jį vėliau galėtumėte identifikuoti puslapyje **Suliejimas**.

3. Papildomai galite nurodyti **Rodomą pavadinimą**, kuris rodomas sujungtame kliento profilio objekte.

4. Sukonfigūruokite **Pasirinkti dubliuotus atributus**, kad pasirinktumėte atributus, kuriuos norite sulieti iš sutapdintų objektų. Taip pat galite ieškoti atributų.

5. Nustatykite **Rikiuoti pagal svarbą**, kad suteiktumėte prioritetą vienam atributui. Pavyzdžiui, jei objekte *WebAccountCSV* pateikiami tiksliausi duomenys apie atributą *Vardai ir pavardės*, pasirinkdami *WebAccountCSV*, galite nustatyti, kad šiam objektui būtų teikiama daugiau svarbos nei *ContactCSV*. Todėl kai reikia išgauti atributo *Vardas ir pavardė* detales, *WebAccountCSV* suteikiamas pirmasis prioritetas, o *ContactCSV* perkeliamas į antrąjį prioritetą.

## <a name="run-your-merge"></a>Suliejimo vykdymas

Nesvarbu, ar atributus suliejate rankiniu būdu, ar leidžiate juos sulieti sistemai, visada galite vykdyti savo suliejimą. Norėdami pradėti procesą, puslapyje **Sulieti** pasirinkite **Vykdyti**.

> [!div class="mx-imgBorder"]
> ![Duomenų suliejimo įrašymas ir vykdymas](media/configure-data-merge-save-run.png "Duomenų suliejimo įrašymas ir vykdymas")

Norėdami atlikti papildomų pakeitimų ir iš naujo paleisti veiksmą, vykdomą suliejimą galite atšaukti. Spustelėkite **Atnaujinama...** ir pasirodžiusiame šoniniame skydo pasirinkite **Atšaukti užduotį**.

Kai tekstas **Atnaujinama...** pasikeičia į **Sėkmingai atlikta**, suliejimas yra baigtas, o duomenų prieštaravimai buvo išspręsti pagal jūsų apibrėžtą strategiją. Sulieti ir nesulieti atributai įtraukiami į vieningojo profilio objektą. Neįtraukti atributai į vieningojo profilio objektą neįtraukiami.

Jei tai nėra pirmas kartas, kai sėkmingai įvykdėte suliejimą, visi proceso pabaigos procesai, įskaitant papildymą, segmentaciją ir matavimą, bus automatiškai paleisti iš naujo. Kai visi proceso pabaigos procesai bus įvykdyti pakartotinai, klientų profiliuose bus matomi bet kokie atlikti pakeitimai.

> [!TIP]
> Esama [šešių būsenos tipų](system.md#status-types) užduotims/procesams. Be to, dauguma procesų [priklauso nuo kitų tolesnių procesų](system.md#refresh-policies). Galite spustelėti proceso būseną, kad matytumėte išsamią informaciją apie visos užduoties vykdymo eigą. Pasirinkę parinktį **Peržiūrėti**, pateiktą prie vienos iš užduočių, rasite papildomos informacijos: apdorojimo laiką, paskutinę apdorojimo datą ir visus su užduotimi susijusius įspėjimus bei klaidas.

## <a name="next-step"></a>Kitas veiksmas

Norėdami gauti daugiau įžvalgų apie savo klientus, sukonfigūruokite [veiklas](activities.md), [papildymą](enrichment-microsoft-graph.md) arba [ryšius](relationships.md).

Jei jau sukonfigūravote veiklas, papildymą arba ryšius arba jei sukonfigūravote segmentus, jie bus apdorojami automatiškai, kad būtų naudojami naujausi kliento duomenys.




[!INCLUDE[footer-include](../includes/footer-banner.md)]