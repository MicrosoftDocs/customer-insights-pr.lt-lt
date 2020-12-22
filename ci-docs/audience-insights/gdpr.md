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
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="b951d-103">Duomenų subjekto teisių (DSR) prašymai pagal BDAR</span><span class="sxs-lookup"><span data-stu-id="b951d-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="b951d-104">Atsakant į BDAR duomenų subjekto panaikinimo užklausas „Dynamics 365 Customer Insights“ publikos įžvalgų galimybėms</span><span class="sxs-lookup"><span data-stu-id="b951d-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="b951d-105">Teisė naikinti asmens duomenis iš įmonės klientų duomenų bazės buvo įtvirtinta kaip pagrindinė ir saugoma įstatymų Bendrajame duomenų apsaugos reglamente (BDAR).</span><span class="sxs-lookup"><span data-stu-id="b951d-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="b951d-106">Asmens duomenų naikinimas apima visų asmens duomenų ir sistemos sugeneruotų žurnalų, išskyrus tikrinimo žurnalų informacijos, naikinimą.</span><span class="sxs-lookup"><span data-stu-id="b951d-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="b951d-107">Duomenų subjektų prašymų naikinti duomenis valdymas</span><span class="sxs-lookup"><span data-stu-id="b951d-107">Manage data subject delete requests</span></span>

<span data-ttu-id="b951d-108">Publikos įžvalgos siūlo tolesnes produkto patirtis siekiant panaikinti asmens duomenis konkretiems klientams ar vartotojams:</span><span class="sxs-lookup"><span data-stu-id="b951d-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="b951d-109">**Prašymų naikinti klientų duomenis valdymas**: klientų duomenys įtraukiami į „Customer Insights” iš pradinių duomenų šaltinių, nepriklausančių „Customer Insights”.</span><span class="sxs-lookup"><span data-stu-id="b951d-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="b951d-110">Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis pradiniame šaltinyje.</span><span class="sxs-lookup"><span data-stu-id="b951d-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="b951d-111">**Tvarkyti užklausų naikinimą „Customer Insights“ naudotojo duomenims**: Duomenys vartotojams yra sukuriami „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="b951d-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="b951d-112">Visi prašymai naikinti duomenis pagal BDAR turi būti tenkinami naikinant duomenis programoje „Customer Insights”.</span><span class="sxs-lookup"><span data-stu-id="b951d-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="b951d-113">Prašymų naikinti klientų duomenis tvarkymas</span><span class="sxs-lookup"><span data-stu-id="b951d-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="b951d-114">„Customer Insights“ administratorius gali atlikti šiuos veiksmus ir pašalinti kliento duomenis, kurie buvo panaikinti duomenų šaltinyje:</span><span class="sxs-lookup"><span data-stu-id="b951d-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="b951d-115">Prisijunkite prie Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b951d-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="b951d-116">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**</span><span class="sxs-lookup"><span data-stu-id="b951d-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="b951d-117">Kiekvienam duomenų šaltiniui sąraše, kuriame yra panaikintų kliento duomenų:</span><span class="sxs-lookup"><span data-stu-id="b951d-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="b951d-118">Pasirinkite (...), tada pasirinkite **Atnaujinti**.</span><span class="sxs-lookup"><span data-stu-id="b951d-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="b951d-119">Patikrinkite duomenų šaltinio būseną dalyje **Būsena**.</span><span class="sxs-lookup"><span data-stu-id="b951d-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="b951d-120">Varnelė reiškia, kad atnaujinti pavyko.</span><span class="sxs-lookup"><span data-stu-id="b951d-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="b951d-121">Įspėjamasis trikampis reiškia, kad įvyko klaida.</span><span class="sxs-lookup"><span data-stu-id="b951d-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="b951d-122">Jei rodomas įspėjamasis trikampis, kreipkitės į D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b951d-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b951d-123">![Prašymų naikinti klientų duomenis pagal BDAR tvarkymas](media/gdpr-data-sources.png "Prašymų naikinti klientų duomenis pagal BDAR tvarkymas")</span><span class="sxs-lookup"><span data-stu-id="b951d-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="b951d-124">Tvarkyti užklausų naikinimą vartotojo duomenims</span><span class="sxs-lookup"><span data-stu-id="b951d-124">Manage delete requests for user data</span></span>

<span data-ttu-id="b951d-125">Norėdamas naikinti „Customer Insights” vartotojų duomenis, „Customer Insights” administratorius gali atlikti šiuos veiksmus:</span><span class="sxs-lookup"><span data-stu-id="b951d-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="b951d-126">Prisijunkite prie Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b951d-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="b951d-127">Publikos įžvalgose, eikite į **Administratorius** > **Leidimai**.</span><span class="sxs-lookup"><span data-stu-id="b951d-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="b951d-128">Pažymėkite vartotojo, kurį norite naikinti, žymės langelį.</span><span class="sxs-lookup"><span data-stu-id="b951d-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="b951d-129">Pasirinkite **Šalinti**.</span><span class="sxs-lookup"><span data-stu-id="b951d-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b951d-130">![BDAR tvarkymas užklausų naikinimui vartotojo duomenims](media/gdpr-permissions.png "BDAR naikinimo užklausų tvarkymas vartotojo duomenims")</span><span class="sxs-lookup"><span data-stu-id="b951d-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="b951d-131">Atsakymas į BDAR duomenų subjekto eksportavimo užklausas</span><span class="sxs-lookup"><span data-stu-id="b951d-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="b951d-132">Esame įsipareigoję jums kaip partneriui padėti taikant Bendrąjį duomenų apsaugos reglamentą (BDAR), todėl sukūrėme dokumentaciją, padėsiančią jums pasirengti.</span><span class="sxs-lookup"><span data-stu-id="b951d-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="b951d-133">Šis dokumentas aprašo žingsnius, kuriuos galite atlikti šiandien siekiant palaikyti BDAR atitiktį naudojant publikos įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="b951d-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="b951d-134">Eksporto tvarkymas ir prašymų peržiūra</span><span class="sxs-lookup"><span data-stu-id="b951d-134">Manage export and view requests</span></span>

<span data-ttu-id="b951d-135">Teisė į duomenų perkeliamumą leidžia duomenų subjektui prašyti jų asmens duomenų kopijos elektroniniu formatu („struktūrizuotas, dažnai naudojamas, mašininio skaitomumo ir sąveikus formatas“), kurį galima perduoti kitam duomenų valdytojui.</span><span class="sxs-lookup"><span data-stu-id="b951d-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="b951d-136">Perkelti kliento duomenis (nuomotojo administratorius)</span><span class="sxs-lookup"><span data-stu-id="b951d-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="b951d-137">Nuomotojas administratorius gali vadovautis šiais veiksmais duomenims perkelti:</span><span class="sxs-lookup"><span data-stu-id="b951d-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="b951d-138">Siųsti el. laišką D365CI@microsoft.com prašyme nurodant kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="b951d-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="b951d-139">„Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo adminsitravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="b951d-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="b951d-140">Patvirtins kliento, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.</span><span class="sxs-lookup"><span data-stu-id="b951d-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="b951d-141">Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.</span><span class="sxs-lookup"><span data-stu-id="b951d-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="b951d-142">Eksportuoti vartotojo duomenis (nuomotojo adminsitravimas)</span><span class="sxs-lookup"><span data-stu-id="b951d-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="b951d-143">Siųsti el. laišką D365CI@microsoft.com prašyme nurodant vartotojo el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="b951d-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="b951d-144">„Customer Insights“ komanda nusiųs el. laišką į registruoto nuomotojo adminsitravimo el. laiško adresą prašydama patvirtinti eksportavimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="b951d-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="b951d-145">Patvirtins vartotojo, dėl kurio buvo pateiktas prašymas, duomenų eksportavimo patvirtinimą.</span><span class="sxs-lookup"><span data-stu-id="b951d-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="b951d-146">Gaus eksportuotus duomenis, naudodamasis nuomotojo administratoriaus el. pašto adresu.</span><span class="sxs-lookup"><span data-stu-id="b951d-146">Receive the exported data through the tenant admin email address.</span></span>
