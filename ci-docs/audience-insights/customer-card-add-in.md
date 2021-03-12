---
title: Įdiegti ir konfigūruoti kliento kortelės papildinį
description: „Dynamics 365 Customer Insights“ kliento kortelės papildinio diegimas ir konfigūravimas.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268054"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="b53f7-103">Papildinys Kliento kortelė (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b53f7-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b53f7-104">Gaukite 360 laipsnių jūsų klientų rodinį tiesiogiai „Dynamics 365“ programose.</span><span class="sxs-lookup"><span data-stu-id="b53f7-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="b53f7-105">Peržiūrėkite demografinius duomenis, įžvalgas ir veiklos laiko planavimo juostas naudodami papildinį Kliento kortelė.</span><span class="sxs-lookup"><span data-stu-id="b53f7-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b53f7-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="b53f7-106">Prerequisites</span></span>

- <span data-ttu-id="b53f7-107">„Dynamics 365“ programa (pvz., pardavimo telkinys arba klientų aptarnavimo telkinys), 9.0 arba naujesnė versija su įjungta vieningąja sąsaja.</span><span class="sxs-lookup"><span data-stu-id="b53f7-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="b53f7-108">Kliento profiliai [vartokite iš „Dynamics 365“ programos naudodami „Common Data Service“](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b53f7-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="b53f7-109">Kliento kortelės papildinio naudotojai turi būti [įtraukti kaip vartotojai](permissions.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="b53f7-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="b53f7-110">[Konfigūruokite paiešką ir filtruokite pajėgumus](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="b53f7-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="b53f7-111">Demografijos valdymas: Demografijos laukeliai, tokie kaip amžius ar lytis yra prieinami suvienodintame kliento profilyje.</span><span class="sxs-lookup"><span data-stu-id="b53f7-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="b53f7-112">Papildymo valdiklis: reikalingi aktyvieji [papildymai](enrichment-hub.md), pritaikyti klientų profiliams.</span><span class="sxs-lookup"><span data-stu-id="b53f7-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="b53f7-113">Protingumo valdymas: Jam būtini duomenys sukurti su „Azure Machine Learning“ ([Nuspėjimais](predictions.md) ar [Tinkintais modeliais](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="b53f7-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="b53f7-114">Priemonės valdymas: Jam būtinos [konfigūruotos priemonės](measures.md).</span><span class="sxs-lookup"><span data-stu-id="b53f7-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="b53f7-115">Laiko juostos valdymas: Jam būtinos [konfigūruotos veiklos](activities.md).</span><span class="sxs-lookup"><span data-stu-id="b53f7-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="b53f7-116">Kliento kortelės papildinio diegimas</span><span class="sxs-lookup"><span data-stu-id="b53f7-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="b53f7-117">Kliento kortelės papildinys yra sprendimas, skirtas „Dynamics 365 Customer Engagement“ programoms.</span><span class="sxs-lookup"><span data-stu-id="b53f7-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="b53f7-118">Norėdami įdiegti sprendimą, eikite į „AppSource“ ir ieškokite **„Dynamics“ kliento kortelės**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="b53f7-119">Pasirinkite [papildinį Kliento kortelė svetainėje „AppSource“](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ir pasirinkite **Gauti dabar**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="b53f7-120">Norint įdiegti sprendimą gali reikėti prisijungti naudojant „Dynamics 365“ programos administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="b53f7-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="b53f7-121">Sprendimo diegimas jūsų aplinkoje gali šiek tiek užtrukti.</span><span class="sxs-lookup"><span data-stu-id="b53f7-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="b53f7-122">Papildinio Kliento kortelė konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b53f7-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="b53f7-123">Kaip administratorius eikite „Dynamics 365“ skyrių **Parametrai** ir pasirinkite **Sprendimai**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="b53f7-124">Pasirinkite sprendimo **„Dynamics 365 Customer Insights“ papildinys Kliento kortelė (peržiūra)** nuorodą **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b53f7-125">![Rodomo pavadinimo pasirinkimas](media/select-display-name.png "Rodomo pavadinimo pasirinkimas")</span><span class="sxs-lookup"><span data-stu-id="b53f7-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="b53f7-126">Spustelėkite **Prisijungti** ir įveskite administratoriaus kliento, kurį naudojate „Customer Insights“ konfigūruoti, kredencialus.</span><span class="sxs-lookup"><span data-stu-id="b53f7-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b53f7-127">Patikrinkite, ar naršyklės iššokančiųjų langų blokavimo programa neblokuoja autentifikavimo lango, kai pasirenkate mygtuką **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="b53f7-128">Pasirinkite aplinką, iš kurios reikia naudoti duomenis.</span><span class="sxs-lookup"><span data-stu-id="b53f7-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="b53f7-129">Nustatykite, kuris laukelių žemėlapis įrašomas į „Dynamics 365“ programą.</span><span class="sxs-lookup"><span data-stu-id="b53f7-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="b53f7-130">Norėdami sudaryti žemėlapį su kontaktu, pasirinkte laukelį kliento objekte, kuris atitinka jūsų kontakto objekto ID.</span><span class="sxs-lookup"><span data-stu-id="b53f7-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="b53f7-131">Norėdami sudaryti žemėlapį su paskyra, pasirinkte laukelį kliento objekte, kuris atitinka jūsų paskyros objekto ID.</span><span class="sxs-lookup"><span data-stu-id="b53f7-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b53f7-132">![„Kontakto ID laukas](media/contact-id-field.png "Kontakto ID laukas")</span><span class="sxs-lookup"><span data-stu-id="b53f7-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="b53f7-133">Pasirinkite **Įrašyti konfigūraciją**, kad įrašytumėte šiuos parametrus.</span><span class="sxs-lookup"><span data-stu-id="b53f7-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="b53f7-134">Tada reikės priskirti saugos vaidmenis „Dynamics 365“, kad vartotojai galėtų tinkinti ir matyti kliento kortelę.</span><span class="sxs-lookup"><span data-stu-id="b53f7-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="b53f7-135">„Dynamics 365“ eikite į **Parametrai** > **Sauga** > **Vartotojai**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="b53f7-136">Pažymėkite vartotojus, kad redaguotumėte vartotojų vaidmenis, ir pasirinkite **Valdyti vaidmenis**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="b53f7-137">Vartotojams, kurie tinkins kortelėje rodomą turinį visoje organizacijoje, priskirkite vaidmenį **„Customer Insights“ kortelės tinkintojas**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="b53f7-138">Įtraukite kliento kortelės valdiklius į formas</span><span class="sxs-lookup"><span data-stu-id="b53f7-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="b53f7-139">Norėdami kliento kortelės valdiklius įtraukti į savo kontakto formą, programoje „Dynamics 365“ eikite į **Parametrai** > **Tinkinimai**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="b53f7-140">Pasirinkite **Tinkinti sistemą**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="b53f7-141">Eikite į objektą **Kontaktas**, jį išplėskite ir pasirinkite **Formos**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="b53f7-142">Pasirinkite kontakto formą, į kurią norite įtraukti kliento kortelės valdiklius.</span><span class="sxs-lookup"><span data-stu-id="b53f7-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b53f7-143">![Kontakto formos pasirinkimas](media/contact-active-forms.png "Kontakto formos pasirinkimas")</span><span class="sxs-lookup"><span data-stu-id="b53f7-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="b53f7-144">Norėdami įtraukti valdiklį, formų rengyklėje bet kurį lauką iš **Laukų naršyklės** vilkite į tą vietą, kurioje norite matyti demografinį valdiklį.</span><span class="sxs-lookup"><span data-stu-id="b53f7-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="b53f7-145">Formoje pažymėkite ką tik įtrauktą lauką, tada pasirinkite **Keisti ypatybes**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="b53f7-146">Eikite į skirtuką **Valdikliai** ir pasirinkite **Įtraukti valdiklį**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="b53f7-147">Pasirinkite vieną iš galimų pasirinktinių valdiklių ir spustelėkite **Įtraukti**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="b53f7-148">Dialogo lange **Lauko ypatybės** išvalykite žymės langelį **Rodyti žymą formoje**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="b53f7-149">Pasirinkite valdiklio ypatybę **Žiniatinklis**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="b53f7-150">Naudodami papildymo valdiklį, pasirinkite norimą rodyti papildymo tipą, sukonfigūravę lauką **„enrichmentType“**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="b53f7-151">Įtraukite atskirą kiekvieno papildymo tipo gerinimo valdiklį.</span><span class="sxs-lookup"><span data-stu-id="b53f7-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="b53f7-152">Norėdami publikuoti atnaujintą kontakto formą, pasirinkite **Įrašyti** ir **Publikuoti**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="b53f7-153">Eikite į publikuotą kontakto formą.</span><span class="sxs-lookup"><span data-stu-id="b53f7-153">Go to the published contact form.</span></span> <span data-ttu-id="b53f7-154">Matysite naujai įtrauktą valdiklį.</span><span class="sxs-lookup"><span data-stu-id="b53f7-154">You'll see the newly added control.</span></span> <span data-ttu-id="b53f7-155">Naudojant jį pirmą kartą, jums gali reikėti prisijungti.</span><span class="sxs-lookup"><span data-stu-id="b53f7-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="b53f7-156">Norėdami tinkinti pasirinktiname valdiklyje rodomus duomenis, pasirinkite viršutiniame dešiniajame kampe esantį redagavimo mygtuką.</span><span class="sxs-lookup"><span data-stu-id="b53f7-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="b53f7-157">Atnaujinti kliento kortelės papildinį</span><span class="sxs-lookup"><span data-stu-id="b53f7-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="b53f7-158">Kliento kortelės papildymas automatiškai neatsijungia.</span><span class="sxs-lookup"><span data-stu-id="b53f7-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="b53f7-159">Norėdami atnaujinti į naujausią versiją, atlikite šią procedūrą "Dynamics 365" programoje, kuri turi įdiegtą priedą.</span><span class="sxs-lookup"><span data-stu-id="b53f7-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="b53f7-160">Programoje "Dynamics 365" eikite į **Parametrai** > **Tinkinimas** ir pasirinkite **Sprendimai**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="b53f7-161">Priedų lentelėje ieškokite **"CustomerInsightsCustomerCard"** ir pažymėkite eilutę.</span><span class="sxs-lookup"><span data-stu-id="b53f7-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="b53f7-162">Veiksmų juostroje pasirinkite **Taikyti sprendimo naujinimą**.</span><span class="sxs-lookup"><span data-stu-id="b53f7-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atnaujinkite sprendimą „Dynamics 365“ programų tinkinimo srityje":::

1. <span data-ttu-id="b53f7-164">Pradėjus naujinimo procesą, matysite įkėlimo indikatorių, kol naujinimas bus baigtas.</span><span class="sxs-lookup"><span data-stu-id="b53f7-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="b53f7-165">Jei nėra naujesnės versijos, atnaujinus bus rodomas klaidos pranešimas.</span><span class="sxs-lookup"><span data-stu-id="b53f7-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]