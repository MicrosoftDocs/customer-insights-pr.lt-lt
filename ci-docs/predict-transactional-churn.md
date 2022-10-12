---
title: Operacijos nutraukimo prognozė (yra vaizdo įrašas)
description: Prognozuokite, ar klientas yra rizikingas taip, kad daugiau nebepirks jūsų produktų ar paslaugų.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610522"
---
# <a name="predict-transaction-churn"></a>Nuspėti perdavimo praradimą

Perdavimo nutraukimo prognozė padeda nuprognozuoti, ar klientas daugiau nebepirks jūsų produktų ar paslaugų per tam tikrą laiko langą.

Turite turėti verslo žinių, kad suprastumėte, ką jūsų verslui reiškia churn. Palaikome laiku pagrįstas nutraukimo sąvokas reiškiančias, kad klientas nutraukė po tam tikro nepirkimo laikotarpio.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Aplinkose, pagrįstose verslo klientais, galime prognozuoti kliento transakcijos chroną ir kliento derinį bei kitą informaciją, pvz., produktų kategoriją. Pavyzdžiui, pridėjus aspektą galima nustatyti, kokia tikimybė, kad paskyra "Contoso" nustos pirkti produkto kategoriją "biuro kanceliarinės prekės". Be to, verslo klientams galime naudoti AI ir sugeneruoti galimų priežasčių, kodėl klientas tikriausiai bus antrinės informacijos kategorijos klientas, sąrašą.

> [!TIP]
> Išbandykite operacijos nutraukimo prognozė naudodami duomenų pavyzdžius: [operacijų atsisakymas prognozė pavyzdinis vadovas](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Mažiausiai [Prisidėjusiojo leidimai](permissions.md).
- Bent 10 klientų profilių, pageidautina daugiau nei 1 000 unikalių klientų.
- Kliento identifikatorius – unikalus identifikatorius, atitinkantis operacijas su klientais.
- Operacijų duomenys bent dvigubai viršija pasirinktą laiko tarpą, pvz., nuo dvejų iki trejų metų operacijų istorijos. Idealiu atveju bent dvi operacijos vienam klientui. Operacijų istorijoje turi būti:
  - **Operacijos ID** : unikalus pirkimo arba operacijos identifikatorius.
  - **Operacijos data**: pirkimo arba sandorio data.
  - **Sandorio** vertė: operacijos valiuta arba skaitinės vertės suma.
  - **Unikalus produkto ID**: įsigyto produkto ar paslaugos ID, jei jūsų duomenys yra eilutės prekės lygio.
  - **Ar ši operacija buvo grąža**: teisingas / klaidingas laukas, nurodantis, ar operacija buvo grąža, ar ne. **Jei operacijos** vertė yra neigiama, mes darome išvadą apie grąžą.
- Klientų veiklos duomenys:
  - Kliento identifikatorius – unikalus identifikatorius, skirtas susieti veiklą su klientais.
  - **Pirminis raktas:** unikalus veiklos identifikatorius. Pavyzdžiui, interneto svetainės lankymas ar įrašo naudojimas rodo, kad klientas išbandė jūsų produkto pavyzdį.
  - **Laiko žyma:** įvykio, identifikuojamo pagal pirminį raktą, data ir laikas.
  - **Įvykis:** įvykio, kurį norite naudoti, pavadinimas. Pavyzdžiui, laukelis pavadintas „Naudotojo veiksmas“ prekių parduotuvėje gali būti kliento naudojamas kuponas.
  - **Informacija:** išsami informacija apie įvykį. Pavyzdžiui, laukelis pavadintas „Kupono vertė“ prekių parduotuvėje gali būti kupono valiutos vertė.
- Mažiau nei 20 % trūkstamų reikšmių pateikto objekto duomenų lauke

Jei naudojate verslo paskyras (nuo B iki B), įtraukite klientų duomenis, sulygiuotus su statiniais atributais, kad užtikrintumėte, jog modelis veikia geriausiai:
- **Kliento ID:** unikalus kliento identifikatorius.
- **Sukūrimo data:** data, kada klientas buvo iš pradžių įtrauktas.
- **Valstija arba provincija:** kliento valstija arba provincija.
- **Šalis:** kliento šalis.
- **Pramonė:** pramonės tipas klientas. Pavyzdžiui, laukas pramonės šaka, esančio pramonės šakoje, gali nurodyti, ar klientas buvo mažmeninis.
- **Klasifikavimas:** kliento skirstymas į kategorijas jūsų verslui. Pvz., laukas pavadinimu „ValueSegment", esantis medyje, gali būti kliento pakopa pagal kliento dydį.

> [!NOTE]
> Įmonėms su didesniu klientų pirkimo dažniu (kas kelias savaites) rekomenduojama rinktis trumpesnį prognozės laikotarpį su perkėlimo apibrėžimu. Esant mažam pirkimo dažniui (kas keletą mėnesių arba kartą per metus) pasirinkite ilgesnį prognozės laikotarpį ir perkėlimo apibrėžimą.

## <a name="create-a-transaction-churn-prediction"></a>Kurti perdavimo praradimo nuspėjimą

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį** plytelėje Kliento klientų pasitraukimo **modelis**.

1. Pasirinkite **Operacija** pagal praradimo tipą, tada **Pradėkite**.

1. **Pavadinkite šį modelį** ir **išvesties objekto pavadinimą** tam, kad kad atskirtumėte juos nuo kitų modelių ar objektų.

1. Pasirinkite **Toliau**.

### <a name="define-customer-churn"></a>Apibrėžkite kliento praradimą

Pasirinkite **Įrašyti juodraštį** bet kuriuo metu, kad išsaugotumėte prognozė kaip juodraštį. Juodraštis prognozė rodomas skirtuke **Mano numatymai**.

1. Nustatykite **prognozė langą**. Pavyzdžiui, prognozuoti jūsų klientų nutraukimo riziką kitoms 90 dienų siekiant suderinti su jūsų reklamos laikymo pastangomis. Nutraukimo rizikos prognozavimas ilgesniam ar trumpesniam laikotarpiui gali apsunkinti faktorių nustatymą jūsų atsisakymo rizikos profilyje, bet jis priklauso nuo konkrečių verslo reikalavimų.

1. Įveskite dienų skaičių, kad apibrėžtumėte praradimą **lauke Churn apibrėžimas**. Pavyzdžiui, jei klientas per pastarąsias 30 dienų nepirko, jis gali būti laikomas jūsų įmonės nebepirktuoju.

1. Pasirinkite **Toliau**.

### <a name="add-purchase-history"></a>Įtraukti pirkimų retrospektyvą

1. Pasirinkite **Įtraukti duomenis** į **Kliento operacijų istoriją**.

1. Pasirinkite semantinį veiklos tipą **SalesOrder** arba **SalesOrderLine**, kuriame yra operacijų retrospektyvos informacija. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Šoninė sritis, vaizduojanti semantikos tipo konkrečių veiklų pasirinkimą.":::

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Įtraukite daugiau veiklų arba pasirinkite **Pirmyn**.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Įtraukti papildomus duomenis (pasirinktinai)

1. Pasirinkite **Įtraukti klientų veiklos** duomenis **·**.

1. Pasirinkite semantinės veiklos tipą, kuriame yra norimi naudoti duomenys. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Pasirinkti **Toliau**

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Rinkitės nuspėjimo lygį

Dauguma prognozių kuriami kliento lygiu. Kai kuriose situacijose, kurios gali būti nepakankami, kad būtų patenkinti jūsų verslo poreikiai. Naudokite šią funkciją, kad numatytumėte, pavyzdžiui, kliento filialo, o ne viso kliento praradimą.

1. Pasirinkite **Pasirinkti antrinio lygio** objektą. Jei parinkties nėra, patikrinkite, ar baigėte ankstesnį skyrių.

1. Išplėskite objektus, iš kurių norite pasirinkti antrinį lygį, arba naudokite ieškos filtro lauką pasirinktoms parinktims filtruoti.

1. Pasirinkite atributą, kurį norite naudoti kaip antrinį lygį, tada pažymėkite **Įtraukti**.

1. Pasirinkite **Toliau**.

> [!NOTE]
> Šiame skyriuje galimi objektai rodomi, nes jie turi ryšį su objektu, kurį pasirinkote ankstesniame skyriuje. Jei nematote objekto, kurį norite įtraukti, patikrinkite, ar jis turi galiojantį ryšį, kuris yra **ryšių** srityje. Tik vienas su vienu ir daugelis su vienu ryšiai galioja šiai konfigūracijai.

### <a name="add-additional-data-optional"></a>Įtraukti papildomus duomenis (pasirinktinai)

1. Pasirinkite **Įtraukti klientų veiklos** duomenis **·**.

1. Pasirinkite semantinės veiklos tipą, kuriame yra norimi naudoti duomenys. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Pasirinkti **Toliau**

1. Galite pažymėti **Įtraukti duomenis** skirtus **Klientų duomenims**.

1. Susiekite semaninius atributus su laukais savo kliento duomenyse, kaip nurodyta. Siekiant užtikrinti geriausią modelio efektyvumą, naudojamų laukų duomenys dažnai neturi keistis. Pavyzdžiui, pasirinkus lauką „Klasifikuoti", kuris pakeitė kiekvieną mėnesį, bus naudojama tik paskutinė prognozė reikšmė, net jei kuriant prognozė modelius ta pati reikšmė retrospektyviškai gali būti taikoma klientui.

1. Pasirinkite **Toliau**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Teikia pasirinktinį abonementų su lyginamaisiais indeksais sąrašą

Įtraukite verslo klientų ir klientų, kuriuos norite naudoti kaip kaitvardį, sąrašą. Išsami [informacija apie šias lyginamąsias sąskaitas](#view-prediction-results) apima jų praradimo balą ir įtakingiausias savybes, kurios paveikė jų praradimo prognozė.

1. Pasirinkite **+ Įtraukti klientą**.

1. Pasirinkite klientus, kurie veikia kaip palyginami.

1. Pasirinkite **Toliau**.

---

### <a name="set-update-schedule"></a>Nustatyti grafiko naujinimą

1. Veiksmui **Duomenų atnaujinimai** pasirinkite modelio perkvalifikavimo dažnį. Šis parametras yra svarbus norint atnaujinti prognozių tikslumą, kai nauji duomenys patenka į "Customer Insights". Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

### <a name="review-and-run-the-model-configuration"></a>Modelio konfigūracijos peržiūra ir paleidimas

Peržiūros **ir vykdymo** veiksme rodoma konfigūracijos suvestinė ir suteikiama galimybė atlikti keitimus prieš kuriant prognozė.

1. Pasirinkite **Redaguoti** atlikdami bet kurį iš veiksmų, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte vykdyti modelį. Pasirinkite **Atlikta**. Skirtukas **Mano numatymai** rodomi, kol kuriamas prognozė. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognozė rezultatų peržiūra

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Mano numatymai** pasirinkite norimą peržiūrėti prognozė.

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

Rezultatų puslapyje yra trys pagrindinės duomenų dalys:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

Rezultatų puslapyje yra trys pagrindinės duomenų dalys:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Įtakingų **funkcijų analizės** informacijos puslapyje yra keturios duomenų dalys:

- Dešinėje srityje pasirinkite elementą iš **Geriausių klientų** arba **Lyginamieji klientai**. Abu sąrašus užsakyti pagal mažėjanti jo reikšmė, neatsižvelgiant į tai, ar balas yra tik klientas, ar bendras klientų balas, ir antrinis lygis, pvz., produktų kategorija. Pasirinktas elementas nustato šio puslapio turinį.

  - **Populiariausi klientai**: 10 klientų, kuriems pagal savo balus kyla didžiausia auksčiausios ir mažiausios aukščiausios auksinės grėsmės, sąrašas.
  - **Klientų vertinimas**: konfigūruojant modelį pasirinktų iki 10 klientų sąrašas.

- **Praradimo balas:** Dešinioje srityje rodomas pasirinkto elemento duotuvas.

- **Praradimo rizikos pasiskirstymas:** rodo klientų praradimo rizikos pasiskirstymą ir procentilį, kuriame yra pasirinktas klientas.

- **Populiariausios funkcijos, didinančios ir mažinančios praradimo riziką:** pateikia penkias svarbiausias funkcijas, kurios padidino ir sumažino pasirinkto elemento praradimo riziką dešinėje srityje. Rodo to elemento funkcijos vertę ir jos įtaką kiekvienos įtakingos funkcijos praradimo balui. Taip pat rodoma vidutinė kiekvienos funkcijos reikšmė įvairiuose žemuose, vidutinio ir aukšto verslo klientų segmentuose. Ji padeda geriau kontekstizuoti pažymėto elemento viršutinių funkcijų reikšmes ir palyginti jas su mažais, vidutiniu ir aukštu praradimo klientų segmentais.

  - Žemas: sąskaitos arba paskyros ir antrinio lygio deriniai, kurių praradimo balas yra nuo 0 iki 0,33.
  - Vidutinis: sąskaitos arba sąskaitų ir antrinių lygių deriniai, kurių praradimo balas yra nuo 0,33 iki 0,66.
  - Aukštas: sąskaitos arba sąskaitų ir antrinių lygių deriniai, kurių praradimo balas didesnis nei 0,66.

  Kai jūs prognozuojame, kad jis yra kliento lygyje, visi klientai atsižvelgia į tai, kad susietus vidutinius hiteronų segmentų funkcijų reikšmes. Jei numatoma, kad pirmame kiekvieno kliento lygyje bus prognozės segmentų suvedimas priklauso nuo antrinės pusės srityje pasirinkto elemento lygio. Pavyzdžiui, jei prekė turi antrinį produktų kategorijos (biuro reikmenų) lygį, nustatant vidutines praradimo segmentų funkcijų reikšmes atsižvelgiama tik į tas prekes, kurių produkto kategorija yra biuro reikmenys. Ši logika taikoma tam, kad būtų galima užtikrinti sąžiningą elemento funkcijų reikšmių palyginimą su vidutinėmis reikšmėmis žemuose, vidutinio ir aukštoje stulpelių segmentuose.

  Kai kuriais atvejais vidutinė žemos, vidutinio arba aukšto dangoraižų segmentų reikšmės yra tuščios arba negalima, nes nėra elementų, kurie pagal aukščiau pateiktą apibrėžimą priklausytų atitinkamims segmentams.

  Reikšmių pagal vidutinius žemus, vidutinius ir didelius stulpelius skirstymas į kategorijas, pvz., šalį ar pramonės šaką, skiriasi. Kadangi „vidurkio" funkcijos reikšmės reikšmė nėra taikoma klasifikuotiems elementams, šių stulpelių reikšmės yra klientų dalis, esanti žemuose, vidutinio ir aukšto turinio segmentuose, kurių reikšminė reikšmė tokia pat kaip ir šoniniame skyde pažymėto elemento.

---

 > [!NOTE]
 > Šio modelio išvesties objekte ChurnScore *rodo prognozuojamą praradimo tikimybę, o* IsChurn *yra dvejetainė etiketė,* pagrįsta *ChurnScore* su 0,5 riba. Jei šis numatytasis slenkstis neveikia jūsų scenarijuje, [sukurkite naują segmentą](segments.md#create-a-segment) su pageidaujamu slenksčiu. Ne visi klientai būtinai yra aktyvūs klientai. Kai kurie ilgą laiką gali būti neturėję jokios veiklos ir jau yra laikomi perkeltais pagal perkėlimo apibrėžimą. Klientams, kurie jau yra susidomę, nėra naudinga prognozuoti riziką, nes jie nėra dominančios auditorijos.
>
> Norėdami peržiūrėti praradimo balą, eikite į **Duomenų** > **objektai** ir peržiūrėkite išvesties objekto, kurį nustatėte šiam modeliui, duomenų skirtuką.

[!INCLUDE [footer-include](includes/footer-banner.md)]
