---
title: Kliento kortelės papildinys, skirtas „Dynamics 365” programoms
description: Šiame papildinyje galite rodyti duomenis iš auditorijos įžvalgų „Dynamics 365” programose.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059598"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d3ad6-103">Papildinys Kliento kortelė (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="d3ad6-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d3ad6-104">Gaukite 360 laipsnių jūsų klientų rodinį tiesiogiai „Dynamics 365“ programose.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d3ad6-105">Įdiegę Kliento kortelės papildinį palaikomoje „Dynamics 365” programoje, galite pasirinkti rodyti demografinius duomenis, įžvalgas ir veiklos laiko planavimo juostas.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="d3ad6-106">Papildinyje duomenys bus nuskaityti iš „Customer Insights” nepaveikiant duomenų prijungtoje „Dynamics 365” programoje.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d3ad6-107">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="d3ad6-107">Prerequisites</span></span>

- <span data-ttu-id="d3ad6-108">Papildinys veikia tik su „Dynamics 365” modeliu pagrįstomis programomis, pavyzdžiui, „Sales” arba „Customer Service” 9.0 arba naujesne versija.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="d3ad6-109">Norint, kad jūsų „Dynamics 365” duomenys būtų susieti su auditorijos įžvalgų kliento profiliais, jie turi būti [įtraukti iš „Dynamics 365” programos naudojant „Common Data Service” jungtį](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="d3ad6-110">Kad būtų galima matyti duomenis, visi „Dynamics 365” Kliento kortelės papildinio vartotojai turi būti [įtraukti kaip vartotojai](permissions.md) į auditorijos įžvalgas.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="d3ad6-111">[Sukonfigūruotos ieškos ir filtravimo galimybės](search-filter-index.md) yra reikalingos auditorijos įžvalgose, kad veiktų duomenų peržvalga.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="d3ad6-112">Kiekvienas papildinio valdiklis remiasi tam tikrais auditorijos įžvalgų duomenimis:</span><span class="sxs-lookup"><span data-stu-id="d3ad6-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="d3ad6-113">Priemonės valdymas: Jam būtinos [konfigūruotos priemonės](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="d3ad6-114">Intelekto valdiklis: Jam reikia duomenų, sugeneruotų naudojant [prognozes](predictions.md) arba [pasirinktinius modelius](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="d3ad6-115">Demografijos valdymas: Demografijos laukeliai, tokie kaip amžius ar lytis yra prieinami suvienodintame kliento profilyje.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="d3ad6-116">Papildymo valdiklis: reikalingi aktyvieji [papildymai](enrichment-hub.md), pritaikyti klientų profiliams.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="d3ad6-117">Laiko juostos valdymas: Jam būtinos [konfigūruotos veiklos](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad6-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d3ad6-118">Kliento kortelės papildinio diegimas</span><span class="sxs-lookup"><span data-stu-id="d3ad6-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d3ad6-119">Kliento kortelės papildinys yra sprendimas, skirtas „Dynamics 365” platformos „Customer Engagement” programoms.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d3ad6-120">Norėdami įdiegti sprendimą, eikite į „AppSource“ ir ieškokite **„Dynamics“ kliento kortelės**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d3ad6-121">Pasirinkite [papildinį Kliento kortelė svetainėje „AppSource“](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ir pasirinkite **Gauti dabar**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d3ad6-122">Norint įdiegti sprendimą gali reikėti prisijungti naudojant „Dynamics 365“ programos administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d3ad6-123">Sprendimo diegimas jūsų aplinkoje gali šiek tiek užtrukti.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d3ad6-124">Papildinio Kliento kortelė konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="d3ad6-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d3ad6-125">Kaip administratorius eikite „Dynamics 365“ skyrių **Parametrai** ir pasirinkite **Sprendimai**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d3ad6-126">Pasirinkite sprendimo **„Dynamics 365 Customer Insights“ papildinys Kliento kortelė (peržiūra)** nuorodą **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3ad6-127">![Rodomo pavadinimo pasirinkimas](media/select-display-name.png "Rodomo pavadinimo pasirinkimas")</span><span class="sxs-lookup"><span data-stu-id="d3ad6-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d3ad6-128">Spustelėkite **Prisijungti** ir įveskite administratoriaus kliento, kurį naudojate „Customer Insights“ konfigūruoti, kredencialus.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d3ad6-129">Patikrinkite, ar naršyklės iššokančiųjų langų blokavimo programa neblokuoja autentifikavimo lango, kai pasirenkate mygtuką **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d3ad6-130">Pasirinkite „Customer Insights“ aplinką, iš kurios norite iškviesti duomenis.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d3ad6-131">Apibrėžkite laukų susiejimą su įrašais „Dynamics 365” programoje.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="d3ad6-132">Atsižvelgdami į jūsų „Customer Insights” duomenis, galite pasirinkti susieti toliau pateiktas parinktis:</span><span class="sxs-lookup"><span data-stu-id="d3ad6-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="d3ad6-133">Norėdami sudaryti žemėlapį su kontaktu, pasirinkite laukelį kliento objekte, kuris atitinka jūsų kontakto objekto ID.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d3ad6-134">Norėdami sudaryti žemėlapį su paskyra, pasirinkite laukelį kliento objekte, kuris atitinka jūsų paskyros objekto ID.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d3ad6-135">![Kontakto ID laukas](media/contact-id-field.png "Kontakto ID laukas")</span><span class="sxs-lookup"><span data-stu-id="d3ad6-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d3ad6-136">Pasirinkite **Įrašyti konfigūraciją**, kad įrašytumėte šiuos parametrus.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d3ad6-137">Tada reikės priskirti saugos vaidmenis „Dynamics 365“, kad vartotojai galėtų tinkinti ir matyti kliento kortelę.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d3ad6-138">„Dynamics 365“ eikite į **Parametrai** > **Sauga** > **Vartotojai**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d3ad6-139">Pažymėkite vartotojus, kad redaguotumėte vartotojų vaidmenis, ir pasirinkite **Valdyti vaidmenis**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d3ad6-140">Vartotojams, kurie tinkins kortelėje rodomą turinį visoje organizacijoje, priskirkite vaidmenį **„Customer Insights“ kortelės tinkintojas**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d3ad6-141">Įtraukite kliento kortelės valdiklius į formas</span><span class="sxs-lookup"><span data-stu-id="d3ad6-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d3ad6-142">Norėdami kliento kortelės valdiklius įtraukti į savo kontakto formą, programoje „Dynamics 365“ eikite į **Parametrai** > **Tinkinimai**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d3ad6-143">Pasirinkite **Tinkinti sistemą**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d3ad6-144">Eikite į objektą **Kontaktas**, jį išplėskite ir pasirinkite **Formos**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d3ad6-145">Pasirinkite kontakto formą, į kurią norite įtraukti kliento kortelės valdiklius.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d3ad6-146">![Kontakto formos pasirinkimas](media/contact-active-forms.png "Kontakto formos pasirinkimas")</span><span class="sxs-lookup"><span data-stu-id="d3ad6-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d3ad6-147">Norėdami įtraukti valdiklį, formų rengyklėje bet kurį lauką iš **Laukų naršyklės** vilkite į tą vietą, kurioje norite matyti demografinį valdiklį.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d3ad6-148">Formoje pažymėkite ką tik įtrauktą lauką, tada pasirinkite **Keisti ypatybes**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d3ad6-149">Eikite į skirtuką **Valdikliai** ir pasirinkite **Įtraukti valdiklį**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d3ad6-150">Pasirinkite vieną iš galimų pasirinktinių valdiklių ir spustelėkite **Įtraukti**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d3ad6-151">Dialogo lange **Lauko ypatybės** išvalykite žymės langelį **Rodyti žymą formoje**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d3ad6-152">Pasirinkite valdiklio ypatybę **Žiniatinklis**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="d3ad6-153">Naudodami papildymo valdiklį, pasirinkite norimą rodyti papildymo tipą, sukonfigūravę lauką **„enrichmentType“**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d3ad6-154">Įtraukite atskirą kiekvieno papildymo tipo gerinimo valdiklį.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d3ad6-155">Norėdami publikuoti atnaujintą kontakto formą, pasirinkite **Įrašyti** ir **Publikuoti**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d3ad6-156">Eikite į publikuotą kontakto formą.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-156">Go to the published contact form.</span></span> <span data-ttu-id="d3ad6-157">Matysite naujai įtrauktą valdiklį.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-157">You'll see the newly added control.</span></span> <span data-ttu-id="d3ad6-158">Naudojant jį pirmą kartą, jums gali reikėti prisijungti.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d3ad6-159">Norėdami tinkinti pasirinktiname valdiklyje rodomus duomenis, pasirinkite viršutiniame dešiniajame kampe esantį redagavimo mygtuką.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="d3ad6-160">Atnaujinti kliento kortelės papildinį</span><span class="sxs-lookup"><span data-stu-id="d3ad6-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="d3ad6-161">Kliento kortelės papildymas automatiškai neatsijungia.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="d3ad6-162">Norėdami atnaujinti į naujausią versiją, atlikite šią procedūrą „Dynamics 365” programoje, kuri turi įdiegtą priedą.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="d3ad6-163">Programoje „Dynamics 365” eikite į **Parametrai** > **Tinkinimas** ir pasirinkite **Sprendimai**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="d3ad6-164">Priedų lentelėje ieškokite **„CustomerInsightsCustomerCard”** ir pažymėkite eilutę.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="d3ad6-165">Veiksmų juostoje pasirinkite **Taikyti sprendimo naujinimą**.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atnaujinkite sprendimą „Dynamics 365“ programų tinkinimo srityje":::

1. <span data-ttu-id="d3ad6-167">Pradėjus naujinimo procesą, matysite įkėlimo indikatorių, kol naujinimas bus baigtas.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="d3ad6-168">Jei nėra naujesnės versijos, atnaujinus bus rodomas klaidos pranešimas.</span><span class="sxs-lookup"><span data-stu-id="d3ad6-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
