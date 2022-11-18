---
title: Nežinomų profilių valdymas naudojant "Customer Insights"
description: Dirbkite su nežinomais klientų profiliais, sukurtais ir valdomais naudojant ""Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776831"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Nežinomų profilių valdymas naudojant "Customer Insights"

Interneto vartotojai internete dažnai yra neidentifikuojami arba anonimiški. Net lojaliausi klientai gali atrodyti "nežinomi", jei jie nėra prisijungę skirtinguose įrenginiuose. Daugeliui prekių ženklų žinomi arba autentifikuoti vartotojai yra mažuma, nepaisant didėjančių klientų lūkesčių, susijusių su personalizavimu. Atsižvelgiant į atitinkamų trečiųjų šalių slapukų ateitį, norint pasiekti suasmenintą patirtį, labai svarbu valdyti vartotojo nuostatas pagal pirmosios šalies duomenis.

Įsimintinas personalizavimas priklauso nuo to, kaip gerai pažįstate savo klientą, o "Customer Insights" padeda tai padaryti stebėdama visus savo klientus.  Jums nereikia apriboti ar sustabdyti duomenų, surinktų klientų veiklos ciklas pradžioje, naudojimo. "Customer Insights" leidžia atsinešti savo duomenis, kad sukurtumėte kliento profilį nežinomiems vartotojams. Tada galite naudoti šį profilį tolesniems veiksmams, nepaisant to, kad trūksta kontaktinės informacijos. Importuokite pirmosios šalies duomenis iš tokių šaltinių kaip žiniatinklio, mobiliųjų įrenginių ar CRM sistemos į "Customer Insights", kad nuolat papildytumėte klientų profilius. Suvienodindami daugiau sąveikų, [nežinomą *klientą paverskite* žinomu *klientu*](unknown-to-known.md).

## <a name="sample-scenario"></a>Pavyzdinis scenarijus

Tarkime, kad vartotojas naudoja savo mobilųjį įrenginį naršydamas jūsų el. prekybos svetainėje. Svetainė priskiria lankytojui "mobile_guest123" kaip unikalų identifikatorių ir jūs pradedate rinkti elgesio veiklą pagal jo veiklą internete. Pavyzdžiui, kuriuose puslapiuose jie lankėsi, kiek laiko praleido tuose puslapiuose arba kurias nuorodas spustelėjo. Nežinote jų vardo ar el. pašto adreso, tačiau šie duomenys gali padėti suteikti prekių ženklams prasmingų įžvalgų apie šį konkretų naudotoją. Savo ruožtu galite įdėti šias įžvalgas į darbą, kai kitą kartą naudotojas apsilankys svetainėje. Pateikite užklausą "Customer Insights", kad "mobile_guest123" nuskaitytų naudotojo segmentų sąrašą, pvz., "natūralus", "mobiliųjų įrenginių išankstinio užsakymo klientai", "didelės vertės klientai" ir kt., arba nuskaitytų profilį, kad sukurtų suasmenintas žiniatinklio funkcijas. Taip pat galite eksportuoti duomenis į bet kurią aktyvinimo sistemą, kad padarytumėte tą patį.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Pirmosios šalies duomenų įtraukimas į "Customer Insights"
- Kiekvienas objektas turi unikalų ID, kuris nustatomas kaip pirminis raktas
- Kiekvienas objektas, turintis pirminį personalizavimo raktą, yra suvienodintas
- Jūsų svetainės turinio valdymo sistema gali naudoti API (žiniatinklio personalizavimui, pagrįstam tiesioginiu bendravimu su "Customer Insights")

Toliau pateiktoje lentelėje pateikiamas supaprastintas pavyzdys, kaip didelės vertės žiniatinklio įvykiai gali būti užfiksuoti.

|Įvykio ID|EventTimeStamp|Vartotojo ID|PrimaryKey|Įvykio pavadinimas|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|ABC123|SlapukasID1|Produkto rodinys|
|2|09-18-2022 10:05:00|ABC123|SlapukasID1|Produkto rodinys|
|3|09-18-2022 10:10:00|ABC123|SlapukasID1|Įtraukti į krepšelį|
|4|09-21-2022 09:05:00|ABC123|SlapukasID1|Produkto rodinys|

## <a name="data-ingestion"></a>Duomenų įsisavinimas

Daugiau informacijos apie galimas duomenų įsisavinimo parinktis rasite [Duomenų šaltinių apžvalga](data-sources.md).

## <a name="data-unification"></a>Duomenų suvienodinimas

Daugiau informacijos apie klientų profilių suvienodinimą ieškokite [Duomenų suvienodinimo apžvalga](data-unification.md).

## <a name="get-insights"></a>Gauti įžvalgų

[Praturtinkite](enrichment-hub.md) savo duomenis, kurkite priemones [ir kurkite](measures.md)[segmentus](segments.md) tolesniam aktyvinimui.

Pavyzdžiui, galite kurti nežinomų naudotojų, kurie naršė tuos pačius produktų puslapius, bet niekada nebaigė atsiskaitymo, segmentus.

## <a name="activation"></a>Aktyvinimas

Turėdami savo duomenis "Customer Insights" ir įžvalgas, paruoštas darbui, galite naudoti "Customer Insights" personalizavimui:

1. [Naudokite "OData" API segmento narystei arba kliento profiliui gauti Daugiau pavyzdžių ieškokite](apis.md)"OData" užklausų pavyzdžiuose, skirtuose "Customer Insights" API [...](odata-examples.md).

1. [Eksportuokite](export-destinations.md) duomenis į aktyvinimo sistemas.

Pavyzdys: nežinomas naudotojas kelis kartus apsilanko svetainėje ir apsilanko įvairių odinių batų modelių produktų puslapiuose. Turėdami šiuos duomenis, pasiekiamus "Customer Insights", galite įtraukti nežinomą naudotoją į žmonių, kurie domisi odiniais batais, segmentą. Naudokite šį segmentą, kad informuotumėte savo svetainę, kad suasmenintumėte suasmenintus sulaukiančius lankytojus. Kito apsilankymo metu svetainė atpažįsta nežinomą vartotoją ir gali pasiūlyti jiems 10% kuponą odiniams batams.

[!INCLUDE [footer-include](includes/footer-banner.md)]
