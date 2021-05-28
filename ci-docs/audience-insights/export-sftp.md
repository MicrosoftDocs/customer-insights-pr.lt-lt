---
title: Eksportuoti „Customer Insights“ duomenis į SFTP šeimininkus
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į SFTP vietą.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3663a48955f0b1db8a96e25403e5f8947bc6a220
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976949"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="4cdca-103">Segmentų sąrašų ir kitų duomenų eksportavimas į SFTP (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="4cdca-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="4cdca-104">Savo kliento duomenis trečiųjų šalių programose naudokite eksportuodami juos į saugiųjų failų perkėlimo protokolo (SFTP) vietą.</span><span class="sxs-lookup"><span data-stu-id="4cdca-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="4cdca-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="4cdca-105">Prerequisites for connection</span></span>

- <span data-ttu-id="4cdca-106">SFTP pagrindinio kompiuterio ir atitinkamų kredencialų pasiekiamumas.</span><span class="sxs-lookup"><span data-stu-id="4cdca-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4cdca-107">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="4cdca-107">Known limitations</span></span>

- <span data-ttu-id="4cdca-108">Eksportavimo trukmė priklauso nuo sistemos efektyvumo.</span><span class="sxs-lookup"><span data-stu-id="4cdca-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="4cdca-109">Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties.</span><span class="sxs-lookup"><span data-stu-id="4cdca-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="4cdca-110">Objektų, kurių klientų profiliai yra iki 100 milijonų, eksportavimas gali užtrukti 90 minučių naudojant rekomenduojamą minimalią dviejų procesorių IR 1 GB atminties konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="4cdca-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="4cdca-111">Ryšio su SFTP nustatymas</span><span class="sxs-lookup"><span data-stu-id="4cdca-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="4cdca-112">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4cdca-113">Pasirinkite **Pridėti ryšį** ir pasirinkite **SFTP**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="4cdca-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="4cdca-114">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4cdca-115">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="4cdca-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4cdca-116">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="4cdca-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4cdca-117">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="4cdca-117">Choose who can use this connection.</span></span> <span data-ttu-id="4cdca-118">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="4cdca-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4cdca-119">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4cdca-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4cdca-120">Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="4cdca-121">Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.</span><span class="sxs-lookup"><span data-stu-id="4cdca-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="4cdca-122">Pasirinkite, ar savo duomenis norite eksportuoti kaip **Gzipped** arba **Unzipped**, ir pasirinkite eksportuotų failų **laukelio skyriklį**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="4cdca-123">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4cdca-124">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="4cdca-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4cdca-125">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="4cdca-125">Configure an export</span></span>

<span data-ttu-id="4cdca-126">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="4cdca-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4cdca-127">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4cdca-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4cdca-128">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4cdca-129">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4cdca-130">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje SFTP.</span><span class="sxs-lookup"><span data-stu-id="4cdca-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="4cdca-131">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="4cdca-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4cdca-132">Pažymėkite objektus, pvz.: segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="4cdca-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4cdca-133">Eksportavus, kiekvienas pažymėtas objektas padalijamas į penkis išvesties failus.</span><span class="sxs-lookup"><span data-stu-id="4cdca-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="4cdca-134">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="4cdca-134">Select **Save**.</span></span>

<span data-ttu-id="4cdca-135">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="4cdca-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4cdca-136">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4cdca-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4cdca-137">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4cdca-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4cdca-138">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="4cdca-138">Data privacy and compliance</span></span>

<span data-ttu-id="4cdca-139">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="4cdca-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4cdca-140">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskirties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="4cdca-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4cdca-141">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4cdca-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4cdca-142">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="4cdca-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
