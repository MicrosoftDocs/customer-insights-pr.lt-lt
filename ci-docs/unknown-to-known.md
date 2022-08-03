---
title: Suasmeninkite savo patirtį naudodami duomenis apie žinomus ir nežinomus vartotojus
description: Įtraukite informaciją apie anksčiau nežinomus vartotojus, kai žinote jų tapatybę.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173821"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Suasmeninkite savo patirtį naudodami duomenis apie žinomus ir nežinomus vartotojus

Klientų duomenų tvarkymas nėra naujas iššūkis, tačiau jis tampa vis sudėtingesnis, nes vartotojai naršo įvairiuose prekių ženklų siūlomuose skaitmeniniuose kanaluose. Vartotojas, kuris yra žinomas (autentifikuotas) viename kanale, tampa nežinomas (neautentifikuotas) kitame kanale, jei jis nėra prisijungęs. Problema dažnai yra ta, kad neautentifikuoti (nežinomi) vartotojai neturi bendro ID. Jis gali būti naudojamas prasmingiems profilių atributams susieti ir vieningiems klientų profiliams generuoti. "Customer Insights" padeda išspręsti šią problemą, nurijus duomenis iš sekimo metodų šaltinio sistemose. Konsoliduoti nežinomi ir žinomi profiliai suteikia organizacijoms išsamų naujausių profilių ir jų istorinių operacijų, elgsenos ir demografinių rodiklių rodinį. Tai netgi žengia dar vieną žingsnį, pateikdama tapatybės sprendimą, leidžiantį suvienodinti klientų veiklą keliuose kanaluose, įskaitant svetainę, pirkimą parduotuvėje, lojalumo programas ir pan.

## <a name="sample-scenario"></a>Scenarijaus pavyzdys

Pagalvokime apie kavos tinklą, kuris turi plačią klientų bazę, kuri perka kavą ir maistą parduotuvėse ir užsako produktus internetu. Dažnai internetiniai lankytojai nėra autentifikuojami naršant produktus, todėl jie tampa "nežinomais vartotojais". Kavos tinklui sunku pateikti suasmenintus pasiūlymus ir patirtį, jei vartotojai nežinomi. Kita vertus, klientai gali prisijungti prie savo paskyros ir tapti "žinomais vartotojais" įmonei prisijungdami prie lojalumo sistemos, kuri savo ruožtu leidžia labiau suasmeninti patirtį. Klientų įžvalgos gali padėti kavos tinklui gauti įžvalgų apie žinomus ir anksčiau nežinomus vartotojus.

Naudodama "Customer Insights", įmonė gali sujungti klientų profilius su veiklos duomenimis iš neautentifikuotų (nežinomų) seansų po to, kai vartotojas prisijungia ir tampa žinomas. Kavos grandinė gali perkelti duomenis iš kitų duomenų šaltinių naudodama įtaisytąsias jungtis į "Customer Insights", kad sujungtų įvairių kanalų klientų tapatybes.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Žiniatinklio duomenys renkami ir juose yra "lankytojų ID" visiems lankytojams.
- Žiniatinklio duomenyse yra "autentifikuotų vartotojų ID", skirti prisijungusiems lankytojams. Šie ID yra susieti su lojalumo sistema.
- Didelės vertės įvykių duomenys, pvz., "Produkto rodinys" ir "Apmokėjimas", apibrėžiami ir įtraukiami į šaltinio duomenis kartu su įvykio laiko žyma ir įvykio ID.

Šioje lentelėje pateiktas supaprastintas pavyzdys, kaip būtų galima užfiksuoti didelės vertės žiniatinklio įvykius.

|EventID|EventTimeStamp|Vartotojo ID|Lojalumo ID|Įvykio pavadinimas|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Produkto rodinys|
|2|07-23-2022 10:05:00|abc123|707|Lojalumo prisijungimas|
|3|07-23-2022 10:10:00|abc123|707|Paimti ir užrakinti|
|4|07-23-2022 10:20:00|xyz789|--|Produkto rodinys|

## <a name="data-ingestion"></a>Duomenų įsisavinimas

Duomenys apie klientus gali būti gaunami iš jūsų svetainės kaip įvykių duomenys ir gali būti saugomi jūsų vidaus ar trečiųjų šalių duomenų analizės paslaugose. Žiniatinklio duomenyse yra žinomų ir nežinomų vartotojų, jei svetainėje yra autentifikavimo srautas, integruojamas su autentifikavimo paslauga. Pavyzdžiui, el. prekybos sistema, kuri reikalauja, kad vartotojai pateiktų išsamią informaciją, kad užbaigtų pirkimo operaciją. Arba lojalumo sistema, kuriai reikalingas autentifikavimas, kad būtų patvirtintas galiojantis premijų nuolaidų gavėjas.

Aukščiau pateiktame pavyzdyje pateiktuose įvykių duomenyse yra skirtingi žinomų ir nežinomų vartotojų profilio ID. 1 ir 4 atvejais vartotojai nežinomi, o 2 ir 3 atvejais vartotojas, turintis ID abc123, užsiregistruoja lojalumo programoje.

:::image type="content" source="media/website-data-source.png" alt-text="Duomenų šaltiniai, įskaitant Contoso svetainę.":::

Daugiau informacijos apie galimas duomenų įsisavinimo parinktis rasite [Duomenų šaltinių apžvalga](data-sources.md).

## <a name="data-unification"></a>Duomenų suvienodinimas

Nežinomų tapatybių suliejimas su žinomomis tapatybėmis padeda įgalinti suasmeninimą pagal vartotojo elgseną, neatsižvelgiant į jų profilio būseną (žinomą ar nežinomą). Suasmenintas turinys visiems naudotojams padeda klientams greitai pasiekti aktualiausius produktus ar paslaugas, kurie tuo metu juos domina.

Kadangi kai kurie mūsų duomenų naudotojai yra žinomi, galime naudoti "Customer Insights", kad sujungtume tuos duomenis su naudotojo profiliu. Daugiau informacijos apie klientų profilių suvienodinimą ieškokite [Duomenų suvienijimo apžvalga](data-unification.md).

1. Pasirinkite šaltinio laukus iš žiniatinklio duomenų objekto. Naudokite profilio duomenis, saugomus jūsų žiniatinklio duomenyse, ir pasirinkite laukus, kurie nurodo ID su demografiniais duomenimis.

   :::image type="content" source="media/website-source-fields.png" alt-text="Žiniatinklio duomenų šaltinis šaltinio laukai.":::

1. Įtraukite taisyklių, kad sulietumėte pasikartojančius įrašus. Žiniatinklio duomenims pasirinkite labiausiai užpildytus duomenis.

1. Konfigūruokite atitikties taisykles ir sąlygas. Šiame pavyzdyje pateikti žiniatinklio profilių įvykių duomenys bus suderinti ID su profiliais iš kitų duomenų šaltinių, kuriuose yra klientų informacijos. Nustatykite tikslias ID atitikties taisykles kaip atskiras taisykles su kiekvienu kitu profilio objektu, turinčiu atitinkamą pirminį raktą arba ID atitiktį. Pavyzdyje žiniatinklio įvykių profilio duomenys naudojami kaip paskutinis atitinkantis objektas, kad pirmiausia būtų sujungti kiti profilio duomenys.
   1. Netikrinant **Įtraukti visus įrašus** sukuriami suvienodinti žinomų vartotojų profiliai ir įtraukiami atitinkami nežinomi vartotojų ID. Tai naudinga scenarijuose, kai norite peržiūrėti ankstesnę žinomų naudotojų elgesio veiklą, kai jie vis dar buvo nežinomi.
   1. Tikrinimas **Įtraukti visus įrašus** sukuria atskirus profilio įrašus nežinomiems vartotojams. Nežinomi vartotojai gauna unikalų kliento ID. Ateityje, kai žinomas profilis bus susietas su žiniatinklio įvykių profilio duomenimis, naujai žinomo vartotojo kelionę bus galima peržiūrėti ir naudoti personalizavimui, remiantis ir ankstesniais nežinomais elgesio duomenimis.

:::image type="content" source="media/website-match-rule.png" alt-text="Svetainės duomenų šaltinis objekto atitikties taisyklė.":::

## <a name="get-insights"></a>Gauti įžvalgų

Jei klientų profiliai kuriami nežinomiems ir žinomiems vartotojams, didelės vertės žiniatinklio įvykių duomenis galima naudoti kaip [veiklą](activities.md). Šią veiklą galima naudoti norint sukurti daugiau įžvalgų. Pavyzdžiui, klientai, kurie apsilankė svetainėje prieš šešis mėnesius (kai jie vis dar buvo nežinomi), arba klientai, neturintys lojalumo ID, niekada neužbaigė atsiskaitymo.

:::image type="content" source="media/website-known-unknown.png" alt-text="Kliento puslapio su žinomais ir nežinomais klientais ekrano kopija.":::

[Praturtinkite](enrichment-hub.md) savo duomenis, kurkite [priemones](measures.md) ir kurkite [segmentus](segments.md), kad galėtumėte toliau aktyvinti.

Pavyzdžiui, galite kurti žinomų vartotojų segmentus, kurie peržiūrėjo kai kuriuos produktus, bet niekada neužbaigė atsiskaitymo.

Daugiau informacijos ieškokite [Segmentų apžvalga](segments.md).

## <a name="activate-insights"></a>Įžvalgų aktyvinimas

Yra keli būdai, kaip eksportuoti duomenis ir imtis veiksmų, pagrįstų pagrindinėmis įžvalgomis.

Daugiau informacijos ieškokite [Eksportavimo apžvalga](export-destinations.md).
