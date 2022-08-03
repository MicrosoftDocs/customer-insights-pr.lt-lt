---
title: Duomenų subjekto teisių (DSR) prašymai pagal BDAR | „Microsoft Docs”
description: Atsakymas į duomenų subjekto prašymus programoje „Dynamics 365 Customer Insights”.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146705"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Duomenų subjekto teisių (DSR) prašymai pagal BDAR

Europos Sąjungos Bendrasis duomenų apsaugos reglamentas (BDAR) įsigaliojo 2018 m. gegužės 25 d. Jis suteikia asmenims svarbių teisių dėl jų duomenų. BDAR paskirtis yra apsaugoti ir užtikrinti asmenų privatumo teises. Daugiau informacijos apie „Microsoft" su sauga ir jos sąrangos tėkme galite sužinoti svetainėje [Microsoft Trust Center“](https://www.microsoft.com/trust-center).

Esame įsipareigoję padėti klientams atitikti jų BDAR reikalavimus. Ji apima teisę naikinti ir eksportuoti duomenis, į kuriuos įtraukta asmeninė informacija, pvz., vartotojo ID, telefono numeriai ir el. pašto adresai. Administratoriai gali įgyvendinti vartotojų užklausas, kad būtų panaikinti arba eksportuoti asmeniniai duomenys.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Atsakymas į duomenų subjekto prašymus panaikinti duomenis programoje „Dynamics 365 Customer Insights”, laikantis BDAR

Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR). Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.

#### <a name="manage-data-subject-delete-requests"></a>Duomenų subjektų prašymų naikinti duomenis valdymas

"Customer Insights" siūlo šias produkte naudojamas funkcijas, kaip ištrinti konkretaus kliento ar vartotojo asmeninius duomenis:

- **Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”. Pirmiausia atlikite BDAR ištrynimo užklausas pradinėje duomenų šaltinis.
- **Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis programoje „Customer Insights”.

##### <a name="manage-requests-to-delete-customer-data"></a>Klientų duomenų naikinimo prašymų tvarkymas

"Customer Insights" administratorius gali atlikti šiuos veiksmus, kad pašalintų kliento duomenis, kurie buvo panaikinti duomenų šaltinis. Prieš atlikdami toliau nurodytus veiksmus, įsitikinkite, kad ištrynimo užklausa buvo atlikta duomenų šaltinis. 

1. Prisijunkite prie Dynamics 365 Customer Insights.
1. Eikite į **duomenų** > **duomenų šaltinius**
1. Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:
   1. Pasirinkite vertikalią daugtaškį (&vellip;) ir pasirinkite **Atnaujinti**.
   1. Patikrinkite duomenų šaltinio būseną dalyje **Būsena**. Varnelė reiškia, kad atnaujinti pavyko. Įspėjamasis trikampis reiškia, kad įvyko klaida. Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.
1. Po sėkmingo duomenų šaltinių atnaujinimo taip pat paleiskite tolesnius atnaujinimus. Ypač, jei nesuplanavote pasikartojančio visiško "Customer Insights" atnaujinimo. 

> [!IMPORTANT]
> Statiniai segmentai neįtraukiami į visišką atnaujinimą arba paleidimą pasroviui po ištrynimo užklausos. Norėdami užtikrinti, kad klientų duomenys taip pat būtų pašalinti iš statinių segmentų, atkurkite statinius segmentus naudodami atnaujintus šaltinio duomenis.

> [!div class="mx-imgBorder"]
> ![Prašymų naikinti klientų duomenis pagal BDAR tvarkymas.](media/gdpr-data-sources.png "Prašymų naikinti klientų duomenis pagal BDAR tvarkymas")

##### <a name="manage-delete-requests-for-user-data"></a>Tvarkyti užklausų naikinimą vartotojo duomenims

Norėdamas naikinti „Customer Insights” vartotojų duomenis, „Customer Insights” administratorius gali atlikti šiuos veiksmus:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Eikite į **administratoriaus** > **saugos** > **teisės**.
3. Pažymėkite vartotojo, kurį norite naikinti, žymės langelį.
4. Pasirinkite **Šalinti**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Atsakymas į BDAR duomenų subjekto eksportavimo užklausas

Vykdydami savo įsipareigojimą bendradarbiauti su jumis keliaudami pagal Bendrąjį duomenų apsaugos reglamentą (BDAR), parengėme dokumentus, kurie padės jums atsakyti į duomenų subjektų užklausas.

#### <a name="manage-export-and-view-requests"></a>Eksporto tvarkymas ir prašymų peržiūra

Teisė į duomenų perkeliamumą leidžia duomenų subjektui prašyti jų asmens duomenų kopijos elektroniniu formatu („struktūrizuotas, dažnai naudojamas, mašininio skaitomumo ir sąveikus formatas“), kurį galima perduoti kitam duomenų valdytojui.

##### <a name="export-customer-data-tenant-admin"></a>Perkelti kliento duomenis (nuomotojo administratorius)

Nuomotojas administratorius gali vadovautis šiais veiksmais duomenims perkelti:

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant kliento el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins kliento, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

##### <a name="export-user-data-tenant-admin"></a>Eksportuoti vartotojo duomenis (nuomotojo administravimas)

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant vartotojo el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo administravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins vartotojo, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Duomenų ištrynimo tvarkymas Dynamics 365 Customer Insights

1. Duomenys bus ištrinti (duomenų skaidiniai ir momentinės nuotraukos), jei duomenų skaidiniai ir momentinės nuotraukos bus neaktyvūs ilgiau nei 30 dienų, o tai reiškia, kad jie buvo pakeisti nauju duomenų skaidiniu ir momentine nuotrauka atnaujinant duomenų šaltinius.
2. Ne visi duomenys ir momentinės nuotraukos ištrinami. Naujausias duomenų skaidinys ir momentinė duomenų nuotrauka iš esmės yra aktyvūs, nes jie naudojami "Customer Insights". Kalbant apie naujausius duomenis, nesvarbu, ar duomenų šaltiniai nebuvo atnaujinti per pastarąsias 30 dienų.

[!INCLUDE [footer-include](includes/footer-banner.md)]
