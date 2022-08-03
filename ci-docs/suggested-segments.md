---
title: Siūlomi segmentai pagal priemones (peržiūra)
description: Leiskite mašininis mokymas rasti naujus ir suskirstytus segmentus, pagrįstus klientų atributais.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170967"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Siūlomi segmentai pagal priemones (peržiūra)

Naudodami AI modelį, galite atrasti klientų klientus su susidavimo segmentais. Ši mašininis mokymas funkcija siūlo segmentus, pagrįstus priemonėmis arba kliento atributais. Tai gali padėti pagerinti pagrindinius efektyvumo indikatorius (KPI) arba geriau suprasti atributų įtaką kitų atributų kontekste.

> [!NOTE]
> Siūlomų segmentų funkcija naudoja automatines priemones duomenims įvertinti ir prognozėms pagal tuos duomenis atlikti. Todėl jis gali būti naudojamas kaip profiliavimo metodas, nes šis terminas apibrėžtas Bendrajame duomenų apsaugos reglamente (toliau – BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingas už tai, kad jūsų naudojimas, įskaitant šią funkciją, užtikrina visų taikytinų įstatymų ir pagrindų, įskaitant įstatymus, susijusius su privatumu, asmeniniais duomenimis, sistemų vientisumu, duomenų apsauga ir „Dynamics 365 Customer Insights“ ryšių slaptumu.

:::image type="content" source="media/suggested-segments.png" alt-text="Siūlomų segmentų puslapis, kuriame pateikiama išsami informacija apie pasiūlymą srityje.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Siūlomi segmentai KPI tobulinti

Jei naudojate [priemones, sukurtas](measures.md) KPI sekti, kurkite segmentus, kad peržiūrėtumėte KPI įtakas. Šią informaciją galite naudoti norėdami vykdyti labai tikslinę kampaniją.

Pavyzdžiui, galite sekti priemonę, vadinamą *TotalSpendPerCustomer*. Kaip verslas, šis skaičius turėtų didėti. Pasirinkdami matą kaip pagrindinį atributą, pasirinkite atributus, kuriuos norite įvertinti kaip įtaką. Tarkime, narystės *pakopa, narystės* laikotarpis ir *esamų* žodžių *sutemimas*. Tada „Customer Insights” gali pasiūlyti segmentą, kuriame galima nurodyti, kas yra tos priemonės įtaka. Pavyzdžiui, *buhalteriai* esantys *Auksiniai* nariai ir kurie bent penkerius metus yra jūsų įmonėje, yra *mažiausiai penkerius metus* yra labiausiai lemiantys *TotalSpendPerCustomer* poveikio darytojai. Gausite įvertintą kiekvieno pasiūlymo segmento dydį. Šią informaciją galite naudoti tikslinėms auditorijoms kurti.

## <a name="understand-what-influences-a-customer-attribute"></a>Supraskite, kas daro įtaką kliento atributui

Kaip pirminį atributą galite pasirinkti kliento atributą, o ne priemonę. AI modelis, remdamasis jūsų pasirinktu įtakos atributų pasirinkimu, sukuria pasiūlymų seką, iš kurios matyti, kaip pasirinkti atributai daro įtaką pirminiam atributui.

Pavyzdžiui, kaip pagrindinį *atributą pasirinksite apdovanojimų* narį (taip / ne). *Kadencija*, *Užimtumas* ir *palaikymo bilietų skaičius* nustatomi kaip kiti įtakos atributai. AI modelis galėtų pasiūlyti segmentų, daugiausia nurodantį, kad IT profesionalai, naudojantys per dvejus metus, yra apdovanojimų nariai. Kitas pasiūlymas galėtų akcentuoti, kad buhalteriai, turintys nuomotojus per metus ir mažiau nei tris palaikymo bilietus, yra apdovanojimų nariai.

## <a name="artificial-intelligence-usage"></a>Dirbtinio intelekto naudojimas

Naudojant pirminius atributus ir įtakos atributus sprendimų medžio algoritmas pasiūlo įdomius segmentus. Pasiūlymai grindžiami taisyklėmis ar modeliais, kuriuos išrinko AI susiejimas. Tik nuo vidutinės populiacijos gerokas besiskiriantys segmentai rodomi kaip pasiūlymai. Palyginimas su vidutiniu persodinimas pagrįstas pasirinktu matu arba pirminiu atributu.

### <a name="responsible-ai"></a>Atsakingas AI

Naudodami siūlomus segmentus pasirenkate atributus, kad sukurtumėte naujus segmentus ir apdorotumėte pasirinktus duomenis. Pasirinkdami atributus, taip pat ir slaptus atributus, pavyzdžiui, rasė, seksualinė orientacija arba lytis, turite užtikrinti, kad tuos duomenis galite ir turėtumėte apdoroti. Esate atsakingas už visų jūsų organizacijai taikomų įstatymų laikymąsi ir organizacijos principus bei privatumo strategijas.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Skirtingi pirminių atributų su skirstyti ir skaitinėmis reikšmėmis rezultatai

Jei pasirinksite skaitinį atributą arba kategorijų atributą kaip pagrindinį atributą, segmentų pasiūlymai skirsis. Skirstyto atributo reikšmėse yra dvi ar daugiau kategorijų arba tipų. Skaitinis atributas turi kiekybinius duomenis ir su jais susijusio matavimo prasmę.

Su skaičių atributais, tokiais kaip *metinės pajamos* ar *narystės laikotarpis* kaip pagrindiniu atributu, sistema siūlo segmentus, kurių vidutinė skaitinio atributo reikšmė yra didesnė arba mažesnė, palyginti su visais klientais.

Toks kategorijos atributas kaip *kliento pasitenkinimas* kaip pirminis atributas, lemia siūlomus segmentus, kurių klientų, priklausančių konkrečiai kategorijai, procentas yra didesnis arba mažesnis, palyginti su visų tai pačiai kategorijai priklausančių klientų procentine dalimi. Pavyzdžiui, *klientų pasitenkinimas* pasirenkamas kaip pirminis atributas ir jį sudaro trys kategorijos (*Žemas*, *vidutinis* ir *didelis*). Bus siūlomi kiekvienos kategorijos segmentai, kuriuose yra didesnė arba mažesnė tai kategorijai priklausančių klientų procentinė dalis, palyginti su visų tos pačios kategorijos klientų dalimi. Jei 22 % visų klientų turi aukštą pasitenkinimo lygį, bus siūlomi tik segmentai, kurių klientų pasitenkinimo lygis yra didesnis arba mažesnis, palyginti su 22 %, ir kurie atitinka *aukštą* klientų pasitenkinimo lygį, palyginti su *aukštu* lygiu. Panašiai, jei segmentai yra statistiniu atžvilgiu svarbūs, bus siūlomi kiekvienai iš kitų kategorijų (*žema* ir *vidutinė*).

> [!NOTE]
> Šiuo metu palaikome tik pirminius kategorijų atributus, kurių kategorijų yra iki 10. Jei norite matyti segmentų pasiūlymus pagal pirminį atributą, kuriame yra daugiau nei 10 kategorijų, rekomenduojame sugrupuoti kai kurias kategorijas, kad kategorijų skaičius sumažėtų iki 10 ar mažiau. Šis apribojimas taikomas tik pirminiams atributams. Norėdami naudoti klasifikuojamuosius atributus, šiuo metu palaikome ne daugiau kaip 100 kategorijų.

## <a name="generate-suggested-segments"></a>Kurti siūlomus segmentus

1. Eikite į **Segmentai** ir pasirinkite skirtuką **Pasiūlymai (peržiūra).**

1. Pasirinkite **Rasti naujų pasiūlymų** ir pasirinkite **Patobulinti matą / metriką**. Pasirinkite **Pradėti**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Siūlomų segmentų tobulinimo priemonės pasirinkimas.":::

1. Pasirinkite kliento atributą arba matą kaip pagrindinį atributą ir pasirinkite **Pirmyn**.

1. Pasirinkite įtakojančius atributus ir pasirinkite **Vykdyti**.

   > [!TIP]
   > Kelių objektų atributų parinkimas pagerina tikimybę įvertinti, kaip jie daro įtaką pirminiam atributui. Neįtraukite atributų, kurie neturi įtakos pirminiam atributui. Pavyzdžiui, jei visi jūsų klientai yra iš konkrečios šalies, neįtraukite *šalies* atributo, nes jis neturės jokio poveikio išeitims.

Atsižvelgiant į klientų profilių ir pasirinktų atributų skaičių, pasirinktų atributų procesas gali užtrukti kelias minutes.

## <a name="manage-suggested-segments"></a>Siūlomų segmentų tvarkymas

Eikite į **Segmentai** ir pasirinkite skirtuką **Pasiūlymai (peržiūra).** Sekcijoje **Atributais pagrįsti segmento pasiūlymai** pasirinkite siūlomą segmentą, kad peržiūrėtumėte galimus veiksmus.

- **Peržiūrėkite** siūlomą segmento informaciją ir atributų reikšmes arba taisykles, kurias išmoko AI modelis.
- **Išsaugokite kaip segmentą** pasiūlymą kaip segmentą. Jis rodomas skirtuke **Visi segmentai** ir gali būti [atnaujintas, redaguojamas arba ištrintas](segments.md).
- **Redaguokite atributus** ir modifikuokite sukonfigūruotus atributus, kurie pakeis dabartinius pasiūlymus.
- **Atnaujinkite pasiūlymus**, kad atnaujintumėte pasiūlymus, išlaikydami sukonfigūruotus atributus.

## <a name="limitations"></a>Apribojimai

1. Numatomas segmento dydžio neatitikimas: jei pasirinksite pirminį atributą, kuriame yra tuščios reikšmės, jis gali turėti įtakos numatomam segmento dydžiui segmento pasiūlymuose. Įrašant tokį segmentą faktinis segmento dydis gali skirtis nuo pradinio įvertinimo.

2. Bulio logikos tipo pirminiai atributai neveikia: šiuo metu palaikome tik eilučių ir skaitinius duomenų tipus kaip pagrindinį atributą.

3. Siūlomų segmentų nepakanka: atminkite, kad pasirinkti atributai ir šių atributų reikšmių platinimas daro įtaką rezultatams. Norėdami gauti skirtingų rezultatų, galite pakeisti savo įtakos atributus ar net pirminį atributą.

[!INCLUDE [footer-include](includes/footer-banner.md)]