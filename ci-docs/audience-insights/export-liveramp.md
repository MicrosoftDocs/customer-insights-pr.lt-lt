---
title: „LiveRamp“ jungtis
description: Sužinokite kaip eksportuoti duomenis į „LiveRamp“.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270168"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="0d82e-103">„LiveRamp&reg;“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="0d82e-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="0d82e-104">Aktyvinkite savo duomenis „LiveRamp“, kad prisijungtumėte prie daugiau nei 500 platformų skaitmeninėse, socialinėse ir TV ekosistemose.</span><span class="sxs-lookup"><span data-stu-id="0d82e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="0d82e-105">Nukreipkite, sustabdykite ir asmeniškai pritaikykite skelbimų kampanijas dirbdami su duomenimis „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="0d82e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0d82e-106">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="0d82e-106">Prerequisites</span></span>

- <span data-ttu-id="0d82e-107">Norint naudoti šią jungtį reikalinga „LiveRamp“ prenumerata.</span><span class="sxs-lookup"><span data-stu-id="0d82e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="0d82e-108">Norėdami gauti prenumeratą, [kreipkitės tiesiogiai į „LiveRamp“](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="0d82e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="0d82e-109">[Sužinokite daugiau apie „LiveRamp Onboarding“](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="0d82e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="0d82e-110">Prisijungimas prie „LiveRamp“</span><span class="sxs-lookup"><span data-stu-id="0d82e-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="0d82e-111">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="0d82e-112">**„LiveRamp“** plytoje pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="0d82e-113">Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0d82e-114">Įveskite savo „LiveRamp“ saugaus FTP (SFTP) kliento **vartotojo vardą** ir **slaptažodį**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="0d82e-115">Šie kredencialai gali skirtis nuo jūsų „LiveRamp Onboarding“ kredencialų.</span><span class="sxs-lookup"><span data-stu-id="0d82e-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="0d82e-116">Pasirinkite **Tikrinti**, kad patikrintumėte ryšį su „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="0d82e-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="0d82e-117">Sėkmingą patikrinę pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="0d82e-118">Pasirinkite **Toliau**, kad nustatytumėte „LiveRamp“ jungtį.</span><span class="sxs-lookup"><span data-stu-id="0d82e-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="0d82e-119">Jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="0d82e-119">Configure the connector</span></span>

1. <span data-ttu-id="0d82e-120">Lauke **Pasirinkite pagrindinį identifikatorių** pasirinkite **El. paštas**, **Vardas, pavardė ir adresas** arba **Telefonas**, kad šie duomenys būtų nusiųsti „LiveRamp“ tapatybei nustatyti.</span><span class="sxs-lookup"><span data-stu-id="0d82e-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="0d82e-121">Susiekite atitinkamus pasirinkto pagrindinio identifikatoriaus atributus iš bendrojo kliento profilio.</span><span class="sxs-lookup"><span data-stu-id="0d82e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="0d82e-122">Pasirinkite **Įtraukti atributą**, kad susietumėte papildomus atributus, kurie bus siunčiami „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="0d82e-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="0d82e-123">„LiveRamp“ nusiuntus daugiau pagrindinio identifikatoriaus atributų tikėtina, kad sutapimo dažnis bus aukštesnis.</span><span class="sxs-lookup"><span data-stu-id="0d82e-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="0d82e-124">Pasirinkite segmentus, kuriuos norite eksportuoti į „LiveRamp“.</span><span class="sxs-lookup"><span data-stu-id="0d82e-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="0d82e-125">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="0d82e-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0d82e-126">![„LiveRamp“ jungtis su atributų susiejimu](media/export-liveramp-segments.png "„LiveRamp“ jungtis su atributų susiejimu")</span><span class="sxs-lookup"><span data-stu-id="0d82e-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="0d82e-127">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="0d82e-127">Export the data</span></span>

<span data-ttu-id="0d82e-128">Jei įvykdytos visos būtinosios eksportavimo sąlygos, eksportavimas netrukus bus pradėtas.</span><span class="sxs-lookup"><span data-stu-id="0d82e-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="0d82e-129">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0d82e-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="0d82e-130">Kai eksportavimas sėkmingai baigtas, galite prisijungti prie „LiveRamp Onboarding“, kad suaktyvintumėte savo duomenis ir juos paskirstytumėte.</span><span class="sxs-lookup"><span data-stu-id="0d82e-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d82e-131">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="0d82e-131">Data privacy and compliance</span></span>

<span data-ttu-id="0d82e-132">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Liveramp“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="0d82e-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d82e-133">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Liveramp“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="0d82e-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d82e-134">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0d82e-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d82e-135">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="0d82e-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]