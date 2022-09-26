---
title: Nežinomų profilių valdymas naudojant "Customer Insights"
description: Darbas su nežinomais klientų profiliais, kurie kuriami ir valdomi Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556406"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Nežinomų profilių valdymas naudojant "Customer Insights"

Interneto vartotojai dažnai yra neidentifikuoti ir anonimiški internete. Jei jie nėra prisijungę, nes naudoja skirtingus įrenginius ar kanalus, tai netgi pasakytina apie lojaliausius klientus. Kadangi trečiųjų šalių slapukai greičiausiai netrukus išnyks, vartotojo nuostatų valdymas, pagrįstas pirmosios šalies duomenimis, yra labai svarbus norint pasiekti diferencijuotą suasmenintą patirtį. Daugeliui prekių ženklų žinomi ar autentifikuoti vartotojai yra mažuma, nepaisant didėjančių klientų lūkesčių, susijusių su personalizavimu. Įmonėms smagu žinoti, kas yra jų klientai, remiantis patikimais, išsamiais ir vieningais duomenimis.

Įsimintinas suasmeninimas priklauso nuo jūsų klientų duomenų turtingumo ir išsamumo, o "Customer Insights" padeda pasiekti šiuos tikslus. Jums nereikia riboti ar sustabdyti duomenų, surinktų klientų veiklos ciklas pradžioje, naudojimo. "Customer Insights" leidžia atsinešti savo duomenis, kad sukurtumėte kliento profilį nežinomiems vartotojams. Tada galite naudoti tą profilį tolesniems veiksmams, nepaisant to, kad trūksta kontaktinės informacijos. Importuokite pirmosios šalies duomenis iš šaltinių, pvz., žiniatinklio, mobiliųjų įrenginių ar CRM sistemų, į "Customer Insights", kad nuolat praturtintumėte klientų profilius. Suvienodindami daugiau sąveikų, [paverskite nežinomą *klientą* žinomu *klientu*](unknown-to-known.md).

## <a name="sample-scenario"></a>Scenarijaus pavyzdys

Elektroninė prekyba yra sparčiausiai augantis kanalas per pastarąjį dešimtmetį. Tarkime, kad naudotojas naudoja savo mobilųjį įrenginį naršydamas jūsų el. prekybos svetainę. Svetainė priskiria lankytojui "mobile_guest123" kaip unikalų identifikatorių ir jūs pradedate rinkti elgesio veiklą pagal jo veiklą internete. Pavyzdžiui, kuriuose puslapiuose jie lankėsi, kiek laiko praleido tuose puslapiuose arba kokias nuorodas spustelėjo. Nežinote jų vardo ar el. pašto adreso, bet šie duomenys gali padėti suteikti prekių ženklams prasmingų įžvalgų apie šį konkretų naudotoją. Savo ruožtu galite įdėti šias įžvalgas į darbą kitą kartą, kai naudotojas apsilankys svetainėje. Užklausos "Customer Insights", skirtos "mobile_guest123", kad gautumėte naudotojo segmentų sąrašą, pvz., "natūralus", "išankstinis klientų užsakymas mobiliesiems", "didelės vertės klientai" ir kt., arba gaukite profilį, kad sukurtumėte suasmenintas žiniatinklio funkcijas. Taip pat galite eksportuoti duomenis į bet kurią aktyvinimo sistemą, kad padarytumėte tą patį.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Pirmosios šalies duomenų nurijimas į "Customer Insights"
- Kiekvienas objektas turi unikalų ID, kuris nustatomas kaip pirminis raktas
- Kiekvienas objektas, turintis pirminį personalizavimo raktą, yra vieningas
- Jūsų svetainės turinio valdymo sistema gali naudoti API (žiniatinklio suasmeninimui, pagrįstam tiesioginiu bendravimu su "Customer Insights")

Šioje lentelėje pateiktas supaprastintas pavyzdys, kaip būtų galima užfiksuoti didelės vertės žiniatinklio įvykius.

|EventID|EventTimeStamp|Vartotojo ID|Pirminis raktas|Įvykio pavadinimas|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Produkto rodinys|
|2|09-18-2022 10:05:00|abc123|CookieID1|Produkto rodinys|
|3|09-18-2022 10:10:00|abc123|CookieID1|Įtraukti į krepšelį|
|4|09-21-2022 09:05:00|abc123|CookieID1|Produkto rodinys|

## <a name="data-ingestion"></a>Duomenų įsisavinimas

Daugiau informacijos apie galimas duomenų įsisavinimo parinktis rasite [Duomenų šaltinių apžvalga](data-sources.md).

## <a name="data-unification"></a>Duomenų suvienodinimas

Daugiau informacijos apie klientų profilių suvienodinimą ieškokite [Duomenų suvienijimo apžvalga](data-unification.md).

## <a name="get-insights"></a>Gauti įžvalgų

[Praturtinkite](enrichment-hub.md) savo duomenis, kurkite [priemones](measures.md) ir kurkite [segmentus](segments.md), kad galėtumėte toliau aktyvinti.

Pavyzdžiui, galite kurti nežinomų vartotojų segmentus, kurie naršė tuose pačiuose produktų puslapiuose, bet niekada neužbaigė atsiskaitymo.

## <a name="activation"></a>Aktyvinimas

Turėdami savo duomenis "Customer Insights" ir parengtas naudoti įžvalgas, galite naudoti "Customer Insights" asmeniniams poreikiams:

1. [Naudokite "OData" API](apis.md), kad gautumėte segmento narystę arba kliento profilį Daugiau pavyzdžių ieškokite ["OData" užklausų pavyzdžiuose, skirtuose "Customer Insights" API](odata-examples.md).

1. [Eksportuokite](export-destinations.md) duomenis į aktyvinimo sistemas.

Pavyzdys: nežinomas naudotojas kelis kartus apsilanko svetainėje ir apsilanko įvairių modelių odinių batų produktų puslapiuose. Turėdami šiuos duomenis, pasiekiamus "Customer Insights", galite įtraukti nežinomą naudotoją į žmonių, kurie domisi odiniais batais, segmentą. Naudokite šį segmentą, kad informuotumėte savo svetainės kūrimą suasmenindami grįžtančius lankytojus. Kito apsilankymo metu svetainė atpažįsta nežinomą vartotoją ir galėtų pasiūlyti jiems 10% kuponą ant odinių batų.

[!INCLUDE [footer-include](includes/footer-banner.md)]
