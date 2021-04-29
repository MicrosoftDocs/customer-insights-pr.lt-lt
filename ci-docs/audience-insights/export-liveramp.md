---
title: „LiveRamp“ jungtis
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „LiveRamp“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760337"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="b0bd3-103">Segmentų eksportavimas į „LiveRamp&reg;“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b0bd3-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="b0bd3-104">Suaktyvinkite duomenis naudodami „LiveRamp“, kad prisijungtumėte prie daugiau nei 500 skaitmeninių, socialinių ir TV platformų.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="b0bd3-105">Nukreipkite, sustabdykite ir asmeniškai pritaikykite skelbimų kampanijas dirbdami su duomenimis „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b0bd3-106">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="b0bd3-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="b0bd3-107">Norint naudoti šią jungtį reikalinga „LiveRamp“ prenumerata.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b0bd3-108">Norėdami gauti prenumeratą, [kreipkitės tiesiogiai į „LiveRamp“](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b0bd3-109">[Sužinokite daugiau apie „LiveRamp Onboarding“](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="b0bd3-110">Ryšio su „LiveRamp“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="b0bd3-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="b0bd3-111">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b0bd3-112">Pasirinkite **Pridėti ryšį** ir pasirinkite **„LiveRamp“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="b0bd3-113">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b0bd3-114">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b0bd3-115">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b0bd3-116">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-116">Choose who can use this connection.</span></span> <span data-ttu-id="b0bd3-117">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b0bd3-118">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b0bd3-119">Įveskite savo „LiveRamp“ saugaus FTP (SFTP) kliento **vartotojo vardą** ir **slaptažodį**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b0bd3-120">Šie kredencialai gali skirtis nuo jūsų „LiveRamp Onboarding“ kredencialų.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b0bd3-121">Pasirinkite **Tikrinti**, kad patikrintumėte ryšį su „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b0bd3-122">Sėkmingą patikrinę pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b0bd3-123">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b0bd3-124">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b0bd3-124">Configure an export</span></span>

<span data-ttu-id="b0bd3-125">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b0bd3-126">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b0bd3-127">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b0bd3-128">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b0bd3-129">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="b0bd3-130">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b0bd3-131">Lauke **Pasirinkite pagrindinį identifikatorių** pasirinkite **El. paštas**, **Vardas, pavardė ir adresas** arba **Telefonas**, kad šie duomenys būtų nusiųsti „LiveRamp“ tapatybei nustatyti.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0bd3-132">![„LiveRamp“ jungtis su atributų susiejimu](media/export-liveramp-segments.png "„LiveRamp“ jungtis su atributų susiejimu")</span><span class="sxs-lookup"><span data-stu-id="b0bd3-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="b0bd3-133">Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b0bd3-134">Pasirinkite **Pridėti atribute**, kad žymėtumėte daugiau atributų siuntimui į „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b0bd3-135">„LiveRamp“ nusiuntus daugiau pagrindinio identifikatoriaus atributų tikėtina, kad sutapimo dažnis bus aukštesnis.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b0bd3-136">Pasirinkite segmentus, kuriuos norite eksportuoti į „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b0bd3-137">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-137">Select **Save**.</span></span>

<span data-ttu-id="b0bd3-138">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b0bd3-139">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b0bd3-140">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b0bd3-141">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="b0bd3-141">Data privacy and compliance</span></span>

<span data-ttu-id="b0bd3-142">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Liveramp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b0bd3-143">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Liveramp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b0bd3-144">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b0bd3-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b0bd3-145">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="b0bd3-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
