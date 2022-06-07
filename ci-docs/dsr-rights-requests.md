---
title: Duomenų subjekto teisių (DSR) prašymai pagal BDAR | „Microsoft Docs”
description: Atsakymas į duomenų subjekto prašymus programoje „Dynamics 365 Customer Insights”.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808571"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Duomenų subjekto teisių (DSR) prašymai pagal BDAR

Europos Sąjungos Bendrasis duomenų apsaugos reglamentas (BDAR) įsigaliojo 2018 m. gegužės 25 d. Jis suteikia asmenims svarbių teisių dėl jų duomenų. BDAR paskirtis yra apsaugoti ir užtikrinti asmenų privatumo teises. Daugiau informacijos apie „Microsoft" su sauga ir jos sąrangos tėkme galite sužinoti svetainėje [Microsoft Trust Center“](https://www.microsoft.com/trust-center).

Esame įsipareigoję padėti klientams atitikti jų BDAR reikalavimus. Ji apima teisę naikinti ir eksportuoti duomenis, į kuriuos įtraukta asmeninė informacija, pvz., vartotojo ID, telefono numeriai ir el. pašto adresai. Administratoriai gali įgyvendinti vartotojų užklausas, kad būtų panaikinti arba eksportuoti asmeniniai duomenys.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Atsakymas į duomenų subjekto prašymus panaikinti duomenis programoje „Dynamics 365 Customer Insights”, laikantis BDAR

Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR). Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.

#### <a name="manage-data-subject-delete-requests"></a>Duomenų subjektų prašymų naikinti duomenis valdymas

"Customer Insights" siūlo šias produkto funkcijas, kad ištrintų konkretaus kliento ar vartotojo asmens duomenis:

- **Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis pradiniame šaltinyje.
- **Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“. Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis programoje „Customer Insights”.

##### <a name="manage-requests-to-delete-customer-data"></a>Klientų duomenų naikinimo prašymų tvarkymas

„Customer Insights“ administratorius gali atlikti šiuos veiksmus ir pašalinti kliento duomenis, kurie buvo panaikinti duomenų šaltinyje:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Eiti į **duomenų** > **šaltinius**
3. Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:
   1. Pasirinkite vertikalią daugtaškį (&vellip;) ir pasirinkite **Atnaujinti**.
   2. Patikrinkite duomenų šaltinio būseną dalyje **Būsena**. Varnelė reiškia, kad atnaujinti pavyko. Įspėjamasis trikampis reiškia, kad įvyko klaida. Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Prašymų naikinti klientų duomenis pagal BDAR tvarkymas.](media/gdpr-data-sources.png "Prašymų naikinti klientų duomenis pagal BDAR tvarkymas")

##### <a name="manage-delete-requests-for-user-data"></a>Tvarkyti užklausų naikinimą vartotojo duomenims

Norėdamas naikinti „Customer Insights” vartotojų duomenis, „Customer Insights” administratorius gali atlikti šiuos veiksmus:

1. Prisijunkite prie Dynamics 365 Customer Insights.
2. Eikite į **Administratoriaus** > **·** > **saugos** teisės.
3. Pažymėkite vartotojo, kurį norite naikinti, žymės langelį.
4. Pasirinkite **Šalinti**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Atsakymas į BDAR duomenų subjekto eksportavimo užklausas

Vykdydami savo įsipareigojimą bendradarbiauti su jumis kelionėje į Bendrąjį duomenų apsaugos reglamentą (BDAR), parengėme dokumentus, kurie padės jums atsakyti į duomenų subjektų užklausas.

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

## <a name="consent-management-preview"></a>Sutikimo valdymas (peržiūra)

Sutikimo valdymo galimybė tiesiogiai nerenka vartotojo duomenų. Ji importuoja ir apdoroja tik sutikimo duomenis, kuriuos naudotojai pateikia kitose programose.

Norėdami pašalinti sutikimo duomenis apie konkrečius naudotojus, pašalinkite juos duomenų šaltiniuose, prarytuose pagal sutikimo valdymo galimybę. Atnaujinus duomenų šaltinis, pašalinti duomenys bus ištrinti ir sutikimo centre. Programos, naudojančios sutikimo objektą, taip pat ištrins duomenis, kurie buvo pašalinti šaltinyje po [atnaujinimo](system.md#refresh-processes). Rekomenduojame greitai atnaujinti duomenų šaltinius, kai atsakoma į duomenų subjekto užklausą pašalinti vartotojo duomenis iš visų kitų procesų ir programų.

[!INCLUDE [footer-include](includes/footer-banner.md)]