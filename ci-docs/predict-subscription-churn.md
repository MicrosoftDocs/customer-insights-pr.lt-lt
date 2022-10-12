---
title: Prenumeratos praradimo numatymas (yra vaizdo įrašas)
description: Prognozuokite, ar yra rizika, kad klientas nebenaudoti prenumeruojamų jūsų įmonės produktų ar paslaugų.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610246"
---
# <a name="predict-subscription-churn"></a>Prenumeratos praradimo prognozavimas

Prognozuokite, ar yra rizika, kad klientas nebenaudoti prenumeruojamų jūsų įmonės produktų ar paslaugų. Prenumeratos duomenys apima aktyvias ir neaktyvias kiekvieno kliento prenumeratas, todėl kiekvienam kliento ID yra keli įrašai.

Turite turėti verslo žinių, kad suprastumėte, ką jūsų verslui reiškia churn. Mes palaikome laiku pagrįstus praradimo apibrėžimus, o tai reiškia, kad laikoma, jog klientas prarado tam tikrą laikotarpį po prenumeratos pabaigos.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Išbandykite prenumeratos praradimo prognozė naudodami duomenų pavyzdžius: [prenumeratos atsisakymas prognozė pavyzdinis vadovas](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Būtinosios sąlygos

- Mažiausiai [Prisidėjusiojo leidimai](permissions.md).
- Bent 10 klientų profilių, pageidautina daugiau nei 1 000 unikalių klientų.
- Kliento identifikatorius – unikalus identifikatorius, atitinkantis prenumeratas su klientais.
- Prenumeratos duomenys bent dvigubai didesni už pasirinktą laiko langą. Geriausia, nuo dviejų iki trijų duomenų prenumeratos metų. Prenumeratos istorijoje turi būti:
  - **Prenumeratos ID:** unikalus prenumeratos identifikatorius.
  - **Prenumeratos pabaigos data:** kliento prenumeratos galiojimo pabaigos data.
  - **Prenumeratos pradžios data:** kliento prenumeratos pradžios data.
  - **Operacijos data:** data, kada įvyko prenumeratos pakeitimas. Pavyzdžiui, klientas, įsigijo arba atšaukė prenumeratą.
  - **Ar tai pasikartojanti prenumerata:** Bulio logika teisingas / klaidingas laukas, kuris nustato, ar prenumerata bus atnaujinta su tuo pačiu prenumeratos ID be kliento įsikišimo.
  - **Pasikartojimo dažnumas (mėnesiais):** pasikartojančių prenumeratų atveju – mėnuo, kurį prenumerata bus atnaujinta. Pavyzdžiui, metinės prenumeratos, kuri kiekvienais metais automatiškai pratęsiama klientui dar metams, reikšmė yra 12.
  - **Prenumeratos suma**: valiutos kiekis, kurį klientas moka už prenumeratos atnaujinimą. Tai gali būti naudinga apžvelgiant skirtingų prenumeratos lygių tendencijas.
- Bent du veiklos įrašai 50% klientų, kuriems norite apskaičiuoti praradimą. Klientų veikla turi apimti:
  - **Pirminis raktas:** unikalus veiklos identifikatorius. Pavyzdžiui, apsilankymas svetainėje arba naudojimo įrašas, rodantis, kad klientas peržiūrėjo televizinio šou epizodą.
  - **Laiko žyma:** įvykio, identifikuojamo pagal pirminį raktą, data ir laikas.
  - **Įvykis:** įvykio, kurį norite naudoti, pavadinimas. Pavyzdžiui, vaizdo transliavimo paslaugos lauke „UserAction“ galėtų būti reikšmė „Peržiūrėta“.
  - **Informacija:** išsami informacija apie įvykį. Pavyzdžiui, vaizdo transliavimo paslaugos lauke „ShowTitle“ galėtų būti kliento peržiūrėto vaizdo įrašo reikšmė.
- Mažiau nei 20 % trūkstamų reikšmių pateikto objekto duomenų lauke.

## <a name="create-a-subscription-churn-prediction"></a>Prenumeratos praradimo prognozės kūrimas

Pasirinkite **Įrašyti juodraštį** bet kuriuo metu, kad išsaugotumėte prognozė kaip juodraštį. Juodraštis prognozė rodomas skirtuke **Mano numatymai**.

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Kurti** pasirinkite **Naudoti modelį** plytelėje Kliento klientų pasitraukimo **modelis**.

1. Pasirinkite **Prenumeratos** pagal praradimo tipą, tada **Pradėkite**.

1. **Pavadinkite šį modelį** ir **išvesties objekto pavadinimą** tam, kad kad atskirtumėte juos nuo kitų modelių ar objektų.

1. Pasirinkite **Toliau**.

### <a name="define-customer-churn"></a>Apibrėžkite kliento praradimą

1. Įveskite **Dienų skaičių nuo prenumeratos pabaigos**, kurį jūsų įmonė taikys prarastam klientui. Šis laikotarpis paprastai yra susijęs su verslo veikla, pvz., pasiūlymais ar kitomis rinkodaros pastangomis, kuriomis siekiama išvengti kliento praradimo.

1. Įveskite dienų skaičių **, kad ištirtumėte ateitį, kad numatytumėte praradimą**. Pavyzdžiui, prognozuoti jūsų klientų nutraukimo riziką kitoms 90 dienų siekiant suderinti su jūsų reklamos laikymo pastangomis. Jei prognozuojama, kad ši riziką užtruks ilgiau ar trumpiau, gali būti sunkiau atsižvelgti į jūsų netekimų riziką, atsižvelgiant į konkrečius jūsų įmonės reikalavimus.

1. Pasirinkite **Toliau**.

### <a name="add-required-data"></a>Įtraukti būtinus duomenis

1. Pasirinkite **Įtraukti duomenis** į Prenumeratų **istoriją**.

1. Pasirinkite semantinį veiklos tipą **Prenumerata**, kuriame yra reikiama prenumeratų retrospektyvos informacija. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Būtinų duomenų įtraukimas į prenumeratos atsisakymo modelį":::

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Pasirinkite **Įtraukti klientų veiklos** duomenis **·**.

1. Pasirinkite semantinį veiklos tipą, kuris teikia kliento veiklos informaciją. Jei veikla nenustatyta, pasirinkite **čia** ir sukurkite ją.

1. Dalyje **Veikla**, jei kuriant veiklą veiklos atributai buvo semantiškai susieti, pasirinkite konkrečius atributus arba objektą, į kurį norite sutelkti dėmesį skaičiuojant. Jei semantinis susiejimas neįvyko, pasirinkite **Redaguoti** ir susieti duomenis.

1. Pasirinkite **Pirmyn** ir peržiūrėkite šiam modeliui reikalingus atributus.

1. Pasirinkite **Įrašyti**.

1. Įtraukite daugiau veiklų arba pasirinkite **Pirmyn**.

### <a name="set-update-schedule"></a>Nustatyti grafiko naujinimą

1. Pasirinkite dažnį, kad perkvalifikuotumėte savo modelį. Šis parametras yra svarbus norint atnaujinti prognozių tikslumą, kai programoje "Customer Insights" praryjami nauji duomenys. Dauguma įmonių gali apmokyti iš naujo kartą per mėnesį, kad prognozių tikslumas būtų geras.

1. Pasirinkite **Toliau**.

### <a name="review-and-run-the-model-configuration"></a>Modelio konfigūracijos peržiūra ir paleidimas

Peržiūros **ir vykdymo** veiksme rodoma konfigūracijos suvestinė ir suteikiama galimybė atlikti keitimus prieš kuriant prognozė.

1. Pasirinkite **Redaguoti** atlikdami bet kurį iš veiksmų, kad peržiūrėtumėte ir atliktumėte bet kokius pakeitimus.

1. Jei esate patenkinti savo pasirinkimais, pasirinkite **Įrašyti ir paleisti**, kad pradėtumėte vykdyti modelį. Pasirinkite **Atlikta**. Skirtukas **Mano numatymai** rodomi, kol kuriamas prognozė. Atsižvelgiant į prognozavimui naudojamų duomenų kiekį, procesas gali užtrukti kelias valandas.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognozė rezultatų peržiūra

1. Eikite į **"Intelligence Predictions"** > **·**.

1. Skirtuke **Mano numatymai** pasirinkite norimą peržiūrėti prognozė.

Rezultatų puslapyje yra trys pagrindinės duomenų dalys:

- **Mokymo modelio našumas**: A, B arba C klasės nurodo prognozė našumą ir gali padėti priimti sprendimą naudoti išvesties objekte saugomus rezultatus.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Modelio balo informacijos lauko vaizdas su A laipsniu":::

  Laipsniai nustatomi pagal šias taisykles:
  - **A**, kai modelis tiksliai prognozavo bent 50% visų prognozių ir kai tikslių prognozių procentas klientams, kurie pūtė, yra didesnis už istorinį vidutinį praradimo rodiklį bent 10%.
  - **B**, kai modelis tiksliai numatė bent 50% visų prognozių ir kai tikslių prognozių procentas klientams, kurie prarado, yra iki 10% didesnis nei istorinis vidutinis praradimo rodiklis.
  - **C**, kai modelis tiksliai prognozavo mažiau nei 50% visų prognozių arba kai tikslių prognozių procentas klientams, kurie prarado, yra mažesnis už istorinį vidutinį praradimo rodiklį.
  
- **Praradimo tikimybė (klientų skaičius)**: Klientų grupės pagal prognozuojamą praradimo riziką. Pasirinktinai kurkite klientų [,](prediction-based-segment.md) turinčių didelę praradimo riziką, segmentus. Tokie segmentai padeda suprasti, kokios turėtų būti priklausymo segmentui ribinės reikšmės.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Diagrama, vaizduojanti praradimo rezultatų paskirstymą, suskirstyta į intervalus nuo 0 proc. iki 100 proc.":::

- **Svarbiausi veiksniai:** kuriant prognozę, atsižvelgiama į daugelį veiksnių. Visi faktoriai turi savo apskaičiuotą svarbą sujungtoms prognozėms, kurias sukuria modelis. Naudokite šiuos veiksnius, kad patikrintumėte prognozė rezultatus. Arba naudokite šią informaciją vėliau, kad sukurtumėte [segmentus](.//prediction-based-segment.md), kurie galėtų padėti paveikti klientų praradimo riziką.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Sąrašas, kuriame matomi svarbiausi veiksniai ir jų svarba prognozuojant praradimo rezultatą.":::

> [!NOTE]
> Šio modelio išvesties objekte ChurnScore *yra prognozuojama praradimo tikimybė, o* IsChurn *yra dvejetainė etiketė,* pagrįsta *ChurnScore* su 0,5 riba. Jei šis numatytasis slenkstis neveikia jūsų scenarijuje, [sukurkite naują segmentą](segments.md) su pageidaujamu slenksčiu. Norėdami peržiūrėti praradimo balą, eikite į **Duomenų** > **objektai** ir peržiūrėkite išvesties objekto, kurį nustatėte šiam modeliui, duomenų skirtuką.

[!INCLUDE [footer-include](includes/footer-banner.md)]
