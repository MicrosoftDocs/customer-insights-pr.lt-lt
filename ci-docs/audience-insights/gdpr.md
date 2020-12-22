---
title: Duomenų subjekto teisių (DSR) prašymai pagal BDAR | „Microsoft Docs”
description: Atsakykite į duomenų subjekto užklausas „Dynamics 365 Customer Insights“ publikos įžvalgų galimybėms.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406408"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Duomenų subjekto teisių (DSR) prašymai pagal BDAR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Atsakant į BDAR duomenų subjekto panaikinimo užklausas „Dynamics 365 Customer Insights“ publikos įžvalgų galimybėms

Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR). Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.

### <a name="manage-data-subject-delete-requests"></a>Duomenų subjektų prašymų naikinti duomenis valdymas

Publikos įžvalgos siūlo tolesnes produkto patirtis siekiant panaikinti asmens duomenis konkretiems klientams ar vartotojams:

- **Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis pradiniame šaltinyje.
- **Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis programoje „Customer Insights”.

#### <a name="manage-delete-requests-for-customer-data"></a>Prašymų naikinti klientų duomenis tvarkymas

„Customer Insights“ administratorius gali atlikti šiuos veiksmus ir pašalinti kliento duomenis, kurie buvo panaikinti duomenų šaltinyje:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**
3. Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:
   1. Pasirinkite (...), tada pasirinkite **Atnaujinti**.
   2. Patikrinkite duomenų šaltinio būseną dalyje **Būsena**. Varnelė reiškia, kad atnaujinti pavyko. Įspėjamasis trikampis reiškia, kad įvyko klaida. Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Prašymų naikinti klientų duomenis pagal BDAR tvarkymas](media/gdpr-data-sources.png "Prašymų naikinti klientų duomenis pagal BDAR tvarkymas")

#### <a name="manage-delete-requests-for-user-data"></a>Tvarkyti užklausų naikinimą vartotojo duomenims

Norėdamas naikinti „Customer Insights” vartotojų duomenis, „Customer Insights” administratorius gali atlikti šiuos veiksmus:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Publikos įžvalgose, eikite į **Administratorius** > **Leidimai**.
3. Pažymėkite vartotojo, kurį norite naikinti, žymės langelį.
4. Pasirinkite **Šalinti**.

> [!div class="mx-imgBorder"]
> ![BDAR tvarkymas užklausų naikinimui vartotojo duomenims](media/gdpr-permissions.png "BDAR naikinimo užklausų tvarkymas vartotojo duomenims")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Atsakymas į BDAR duomenų subjekto eksportavimo užklausas

Esame įsipareigoję jums kaip partneriui padėti taikant Bendrąjį duomenų apsaugos reglamentą (BDAR), todėl sukūrėme dokumentaciją, padėsiančią jums pasirengti. Šis dokumentas aprašo žingsnius, kuriuos galite atlikti šiandien siekiant palaikyti BDAR atitiktį naudojant publikos įžvalgas.

### <a name="manage-export-and-view-requests"></a>Eksporto tvarkymas ir prašymų peržiūra

Teisė į duomenų perkeliamumą leidžia duomenų subjektui prašyti jų asmens duomenų kopijos elektroniniu formatu („struktūrizuotas, dažnai naudojamas, mašininio skaitomumo ir sąveikus formatas“), kurį galima perduoti kitam duomenų valdytojui.

#### <a name="export-customer-data-tenant-admin"></a>Perkelti kliento duomenis (nuomotojo administratorius)

Nuomotojas administratorius gali vadovautis šiais veiksmais duomenims perkelti:

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant kliento el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo adminsitravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins kliento, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.

#### <a name="export-user-data-tenant-admin"></a>Eksportuoti vartotojo duomenis (nuomotojo adminsitravimas)

1. Siųsti el. laišką D365CI@microsoft.com prašyme nurodant vartotojo el. pašto adresą. „Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo adminsitravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.
2. Patvirtins vartotojo, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.
3. Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.
