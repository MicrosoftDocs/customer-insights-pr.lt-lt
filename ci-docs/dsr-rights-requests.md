---
title: Duomenų subjekto teisių (DSR) prašymai pagal BDAR | „Microsoft Docs”
description: Atsakymas į duomenų subjekto prašymus programoje „Dynamics 365 Customer Insights”.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387121"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Duomenų subjekto teisių (DSR) prašymai pagal BDAR

Europos Sąjungos Bendrasis duomenų apsaugos reglamentas (BDAR) įsigaliojo 2018 m. gegužės 25 d. Jis suteikia asmenims svarbių teisių dėl jų duomenų. BDAR paskirtis yra apsaugoti ir užtikrinti asmenų privatumo teises. Daugiau apie "Microsoft" įsipareigojimą užtikrinti saugą ir atitiktį [skaitykite "Microsoft" patikimumo centre](https://www.microsoft.com/trust-center).

Esame įsipareigoję padėti klientams atitikti jų BDAR reikalavimus. Tai apima teisę ištrinti arba eksportuoti duomenis, kurie apima asmeninę informaciją, pvz., vartotojo ID, telefono numerius ir el. pašto adresus. Administratoriai gali įgyvendinti vartotojų užklausas, kad būtų panaikinti arba eksportuoti asmeniniai duomenys.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Atsakydamas į BDAR duomenų subjekto užklausų dėl "Customer Insights" ištrynimą

Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR). Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.

### <a name="manage-data-subject-delete-requests"></a>Duomenų subjektų prašymų naikinti duomenis valdymas

"Customer Insights" siūlo šias produkte naudojamas funkcijas, kaip ištrinti konkretaus kliento ar vartotojo asmeninius duomenis:

- **Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”. Pirmiausia atlikite BDAR ištrynimo užklausas pradinėje duomenų šaltinis.
- **Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“. Atlikite visas BDAR ištrynimo užklausas programoje "Customer Insights".

#### <a name="manage-requests-to-delete-customer-data"></a>Klientų duomenų naikinimo prašymų tvarkymas

Kaip "Customer Insights" administratorius, pašalinkite "Customer Insights" klientų duomenis, kurie buvo panaikinti duomenų šaltinis. Patikrinkite, ar BDAR ištrynimo užklausos buvo atliktos pradinėje duomenų šaltinis.

1. Prisijunkite prie Dynamics 365 Customer Insights.

1. Eikite į **Duomenys** > **Duomenų šaltiniai**.

1. Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:
   1. Pasirinkite duomenų šaltinis, tada pasirinkite **Atnaujinti**.
   1. Patikrinkite duomenų šaltinio būseną dalyje **Būsena**. Varnelė reiškia, kad atnaujinti pavyko. Įspėjamasis trikampis reiškia, kad įvyko klaida. Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Prašymų naikinti klientų duomenis pagal BDAR tvarkymas.":::

1. Po sėkmingo duomenų šaltinių atnaujinimo taip pat paleiskite tolesnius atnaujinimus. Ypač, jei nesuplanavote pasikartojančio visiško "Customer Insights" atnaujinimo.

   > [!IMPORTANT]
   > Statiniai segmentai neįtraukiami į visišką atnaujinimą arba paleidimą pasroviui po ištrynimo užklausos. Norėdami užtikrinti, kad klientų duomenys taip pat būtų pašalinti iš statinių segmentų, atkurkite statinius segmentus naudodami atnaujintus šaltinio duomenis.

#### <a name="manage-delete-requests-for-user-data"></a>Tvarkyti užklausų naikinimą vartotojo duomenims

Kaip "Customer Insights" administratorius, ištrinkite "Customer Insights" vartotojo duomenis.

1. Prisijunkite prie Dynamics 365 Customer Insights.

1. Eikite į administratoriaus **saugos** > **> ir pasirinkite skirtuką** Vartotojai **.**

1. Pažymėkite vartotojų, kuriuos norite panaikinti, žymės langelį.

1. Pasirinkite **Šalinti**.

1. Patvirtinkite naikinimą.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Atsakymas į BDAR duomenų subjekto eksportavimo užklausas

Teisė į duomenų perkeliamumą leidžia duomenų subjektui prašyti jų asmens duomenų kopijos elektroniniu formatu („struktūrizuotas, dažnai naudojamas, mašininio skaitomumo ir sąveikus formatas“), kurį galima perduoti kitam duomenų valdytojui.

### <a name="manage-export-and-view-requests"></a>Eksporto tvarkymas ir prašymų peržiūra

Tvarkykite užklausas eksportuoti kliento arba vartotojo duomenis.

#### <a name="export-customer-data-tenant-admin"></a>Perkelti kliento duomenis (nuomotojo administratorius)

Kaip nuomotojo administratorius eksportuokite kliento duomenis.

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant kliento el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins kliento, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

#### <a name="export-user-data-tenant-admin"></a>Eksportuoti vartotojo duomenis (nuomotojo administravimas)

Kaip nuomotojo administratorius eksportuokite vartotojo duomenis.

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant vartotojo el. pašto adresą. "Customer Insights" komanda siunčia el. laišką registruoto nuomotojo administratoriaus el. pašto adresu, prašydama patvirtinimo eksportuoti duomenis.
1. Patvirtins vartotojo, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
1. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Duomenų ištrynimo tvarkymas Dynamics 365 Customer Insights

Duomenys ištrinami (duomenų skaidiniai ir momentinės nuotraukos), jei duomenų skaidiniai ir momentinės nuotraukos yra neaktyvūs ilgiau nei 30 dienų, o tai reiškia, kad jie buvo pakeisti nauju duomenų skaidiniu ir momentine nuotrauka atnaujinant duomenų šaltinius.

Ne visi duomenys ir momentinės nuotraukos ištrinami. Naujausias duomenų skaidinys ir momentinė duomenų nuotrauka yra aktyvūs, nes jie naudojami "Customer Insights". Kalbant apie naujausius duomenis, nesvarbu, ar duomenų šaltiniai nebuvo atnaujinti per pastarąsias 30 dienų.

[!INCLUDE [footer-include](includes/footer-banner.md)]
