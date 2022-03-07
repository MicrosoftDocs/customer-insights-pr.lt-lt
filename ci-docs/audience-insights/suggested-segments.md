---
title: Mašininis mokymas siūlomų segmentų kūrimas
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
ms.openlocfilehash: 82345a7d7cf7fd38d74080552799de0b92461d78
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353599"
---
# <a name="suggested-segments-preview"></a>Siūlomi segmentai (peržiūra)

Naudodami AI modelį, galite atrasti klientų klientus su susidavimo segmentais. Ši mašininis mokymas funkcija siūlo segmentus, pagrįstus priemonėmis arba kliento atributais. Tai gali padėti pagerinti jūsų KPI arba geriau suprasti atributų įtaką kitų atributų kontekste. 

> [!NOTE]
> Siūloma segmentų funkcija naudoja automatizuotas priemones duomenims įvertinti ir pagal juos numatyti, todėl ją galima naudoti kaip profiliavimo metodą, kaip apibrėžta Bendrajame duomenų apsaugos reglamente (BDAR). Jūsų duomenų naudojantis šia funkcija siekiant tvarkyti duomenis gali būti taikomos BDAR ar kitų teisės aktų nuostatos. Jūs esate atsakingas už tai, kad jūsų naudojimas, įskaitant šią funkciją, užtikrina visų taikytinų įstatymų ir pagrindų, įskaitant įstatymus, susijusius su privatumu, asmeniniais duomenimis, sistemų vientisumu, duomenų apsauga ir „Dynamics 365 Customer Insights“ ryšių slaptumu.

:::image type="content" source="media/suggested-segments.png" alt-text="Siūlomų segmentų puslapis, kuriame pateikiama išsami informacija apie pasiūlymą srityje.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Siūlomi segmentai KPI tobulinti

Kaip auditorijos įžvalgų vartotojas tikriausiai [sukūrėte keletą priemonių](measures.md) padedančių sekti pagrindinius efektyvumo indikatorius (KPI). Svarbu suprasti, kaip tam tikri atributai daro įtaką šiam KPI, kad būtų galima kurti segmentus ir vykdyti itin tikslinę kampaniją.   
Pavyzdžiui, galite sekti priemonę, vadinamą *TotalSpendPerCustomer*. Kaip verslas, šis skaičius turėtų didėti. Pažymėsite priemonę kaip pirminį atributą, galėsite pažymėti atributus, kuriuos norite įvertinti dėl įtakos. Tarkime, narystės *pakopa, narystės* laikotarpis ir *esamų* žodžių *sutemimas*. Tada „Customer Insights” gali pasiūlyti segmentą, kuriame galima nurodyti, kas yra tos priemonės įtaka. Pavyzdžiui, *buhalteriai* esantys *Auksiniai* nariai ir kurie bent penkerius metus yra jūsų įmonėje, yra *mažiausiai penkerius metus* yra labiausiai lemiantys *TotalSpendPerCustomer* poveikio darytojai. Gausite įvertintą kiekvieno pasiūlymo segmento dydį. Šią informaciją galite naudoti tikslinėms auditorijoms kurti.

## <a name="understand-what-influences-a-customer-attribute"></a>Supraskite, kas daro įtaką kliento atributui

Kaip pirminį atributą galite pasirinkti kliento atributą, o ne priemonę. AI modelis, remdamasis jūsų pasirinktu įtakos atributų pasirinkimu, sukuria pasiūlymų seką, iš kurios matyti, kaip pasirinkti atributai daro įtaką pirminiam atributui.   
Pavyzdžiui, kaip pagrindinį *atributą pasirinksite apdovanojimų* narį (taip / ne). *Kadencija*, *Užimtumas* ir *palaikymo bilietų skaičius* nustatomi kaip kiti įtakos atributai. AI modelis galėtų pasiūlyti segmentų, daugiausia nurodantį, kad IT profesionalai, naudojantys per dvejus metus, yra apdovanojimų nariai. Kitas pasiūlymas galėtų akcentuoti, kad buhalteriai, turintys nuomotojus per metus ir mažiau nei tris palaikymo bilietus, yra apdovanojimų nariai. 

## <a name="artificial-intelligence-usage"></a>Dirbtinio intelekto naudojimas

Naudojant pirminius atributus ir įtakos atributus sprendimų medžio algoritmas pasiūlo įdomius segmentus. Pasiūlymai grindžiami taisyklėmis ar modeliais, kuriuos išrinko AI susiejimas. Tik nuo vidutinės populiacijos gerokas besiskiriantys segmentai rodomi kaip pasiūlymai. Palyginimas su vidutiniu persodinimas pagrįstas pasirinktu matu arba pirminiu atributu.

### <a name="responsible-ai"></a>Atsakingas AI

Siūlomi segmentai leidžia pasirinkti atributus naujiems segmentams kurti ir duomenims apdoroti. Pasirinkdami atributus, taip pat ir slaptus atributus, pavyzdžiui, rasė, seksualinė orientacija arba lytis, turite užtikrinti, kad tuos duomenis galite ir turėtumėte apdoroti. Esate atsakingas už visų jūsų organizacijai taikomų įstatymų laikymąsi ir organizacijos principus bei privatumo strategijas.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Skirtingi pirminių atributų su skirstyti ir skaitinėmis reikšmėmis rezultatai

Jei pasirinksite skaitinį atributą arba kategorijų atributą kaip pagrindinį atributą, segmentų pasiūlymai skirsis. Skirstyto atributo reikšmėse yra dvi ar daugiau kategorijų arba tipų. Skaitinis atributas turi kiekybinius duomenis ir su jais susijusio matavimo prasmę.

Su skaičių atributais, tokiais kaip *metinės pajamos* ar *narystės laikotarpis* kaip pagrindiniu atributu, sistema siūlo segmentus, kurių vidutinė skaitinio atributo reikšmė yra didesnė arba mažesnė, palyginti su visais klientais.

Toks kategorijos atributas kaip *kliento pasitenkinimas* kaip pirminis atributas, lemia siūlomus segmentus, kurių klientų, priklausančių konkrečiai kategorijai, procentas yra didesnis arba mažesnis, palyginti su visų tai pačiai kategorijai priklausančių klientų procentine dalimi. Pavyzdžiui, *klientų pasitenkinimas* pasirenkamas kaip pirminis atributas ir jį sudaro trys kategorijos (*Žemas*, *vidutinis* ir *didelis*). Bus siūloma, kad kiekvienos kategorijos segmentai turėtų daugiau arba mažiau klientų, priklausančių tai kategorijai, palyginti su visų tai pačiai kategorijai priklausančių klientų dalimi. Jei 22 % visų klientų turi aukštą pasitenkinimo lygį, bus siūlomi tik segmentai, kurių klientų pasitenkinimo lygis yra didesnis arba mažesnis, palyginti su 22 %, ir kurie atitinka *aukštą* klientų pasitenkinimo lygį, palyginti su *aukštu* lygiu. Panašiai, jei segmentai yra statistiniu atžvilgiu svarbūs, bus siūlomi kiekvienai iš kitų kategorijų (*žema* ir *vidutinė*).

> [!NOTE]
> Šiuo metu palaikome tik pirminius kategorijų atributus, kurių kategorijų yra iki 10. Jei norite peržiūrėti segmento pasiūlymus, pagrįstus pirminiu atributu, turiu daugiau nei 10 kategorijų, rekomenduojame sugrupuoti kai kurias kategorijas, kad kategorijų skaičius būtų mažesnis nei 10. Šis apribojimas taikomas tik pirminiams atributams. Norėdami naudoti klasifikuojamuosius atributus, šiuo metu palaikome ne daugiau kaip 100 kategorijų.

## <a name="generate-suggested-segments"></a>Kurti siūlomus segmentus

1. Eikite į **Segmentai**.

1. Pažymėkite skirtuką **Pasiūlymai**.

1. Pasirinkite **Gauti naujų pasiūlymų, kad būtų galima pradėti** interaktyviąją patirtį.

1. Rinkitės priemonę ar kliento atributą kaip pagrindinį atributą ir rinkitės **Toliau**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Siūlomų segmentų pasiūlymų pagrindinio atributo pasirinkimas.":::

1. Pažymėkite veikimo atributus ir rinkitės **įrašyti**.
   
   > [!TIP]
   > Kelių objektų atributų parinkimas pagerina tikimybę įvertinti, kaip jie daro įtaką pirminiam atributui. Neįtraukite atributų, kurie neturi įtakos pirminiam atributui. Pavyzdžiui, jei visi jūsų klientai yra iš konkrečios šalies, neįtraukite *šalies* atributo, nes jis neturės jokio poveikio išeitims.

1. Atsižvelgiant į klientų profilių ir pasirinktų atributų skaičių, pasirinktų atributų procesas gali užtrukti kelias minutes. 

## <a name="view-details-of-a-suggested-segment"></a>Peržiūrėkite siūlomo segmento informaciją

Sugeneravote AI modelį, jie pateikiami segmentų pasiūlymuose **Segmentai** > **Siūlymai (peržiūra)**.
 
Pasirinkite siūlomą segmentą ir peržiūrėkite išsamią to pasiūlymo informaciją. Taip pat galite peržiūrėti atributų reikšmes arba taisykles, kurias AI modelis išmoko pasiūlyti pasirinktą segmentą.

## <a name="save-a-suggestion-as-a-segment"></a>Įrašykite siūlymą kaip segmentą

1. Eikite į **Segmentai** > **Pasiūlymai (peržiūra)**.

1. Pasirinkite norimą įrašyti segmentą. 

1. Šoninėje juostoje pasirinkite **Įrašyti kaip segmentą**. 

1. Įrašius segmentą, jis bus rodomas segmentų sąraše **Visi segmentai** skirtuke. Dabar jį galima [atnaujinti, redaguoti arba panaikinti kaip bet kurį kitą segmentą](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Pasiūlymų rinkinio atnaujinimas arba redagavimas

1. Eikite į **Segmentai** > **Pasiūlymai (peržiūra)**.

1. Pasirinkite **Atnaujinti pasiūlymus,** kad išlikdami sukonfigūruoti atributai būtų atnaujinti pasiūlymus. Arba pasirinkite **Redaguoti atributus**, kad modifikuotumėte sukonfigūruotus atributus. Sistema iš naujo taisys AI modelį, generuos segmentų pasiūlymus, pagrįstus naujausiais duomenimis, ir pakeis dabartinius pasiūlymus.

## <a name="limitations"></a>Apribojimai

1. Numatomas segmento dydžio neatitikimas: jei pasirinksite pirminį atributą, kuriame yra tuščios reikšmės, jis gali turėti įtakos numatomam segmento dydžiui segmento pasiūlymuose. Įrašant tokį segmentą faktinis segmento dydis gali skirtis nuo pradinio įvertinimo.
 
2. Bulio logikos tipo pirminiai atributai neveikia: šiuo metu palaikome tik eilučių ir skaitinius duomenų tipus kaip pagrindinį atributą.

3. Siūlomų segmentų nepakanka: atminkite, kad pasirinkti atributai ir šių atributų reikšmių platinimas daro įtaką rezultatams. Norėdami gauti skirtingų rezultatų, galite pakeisti savo įtakos atributus ar net pirminį atributą.



[!INCLUDE[footer-include](../includes/footer-banner.md)]