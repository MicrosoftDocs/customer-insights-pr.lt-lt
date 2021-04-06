---
title: Eksportuoti „Customer Insights“ duomenis į SFTP šeimininkus
description: Sužinokite, kaip sukonfigūruoti ryšį su SFTP pagrindiniu kompiuteriu.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598395"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="87c5e-103">SFTP jungtis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="87c5e-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="87c5e-104">Naudokite savo kliento duomenis trečiosios šalies programose eksportuodami juos į „Secure File Transfer Protocol“ (SFTP) šeimininką.</span><span class="sxs-lookup"><span data-stu-id="87c5e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="87c5e-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="87c5e-105">Prerequisites</span></span>

- <span data-ttu-id="87c5e-106">SFTP pagrindinio kompiuterio ir atitinkamų kredencialų pasiekiamumas.</span><span class="sxs-lookup"><span data-stu-id="87c5e-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="87c5e-107">Prisijungti prie SFTP</span><span class="sxs-lookup"><span data-stu-id="87c5e-107">Connect to SFTP</span></span>

1. <span data-ttu-id="87c5e-108">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="87c5e-109">Dalyje **SFTP** pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="87c5e-110">Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="87c5e-111">Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="87c5e-112">Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.</span><span class="sxs-lookup"><span data-stu-id="87c5e-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="87c5e-113">Po sėkmingos patikros pasirinkite, ar norite eksportuoti duomenis **„Gzipped”** ar **„Unzipped”** ir pažymėkite eksportuotų failų **laukų skyriklį**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="87c5e-114">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="87c5e-115">Norėdami pradėti konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="87c5e-116">Sprendimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="87c5e-116">Configure the export</span></span>

1. <span data-ttu-id="87c5e-117">Pažymėkite objektus, pvz.: segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="87c5e-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87c5e-118">Eksportuojant kiekvienas pažymėtas objektas bus iki penkių išvesties failų.</span><span class="sxs-lookup"><span data-stu-id="87c5e-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="87c5e-119">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="87c5e-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="87c5e-120">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="87c5e-120">Export the data</span></span>

<span data-ttu-id="87c5e-121">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="87c5e-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="87c5e-122">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="87c5e-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="87c5e-123">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="87c5e-123">Known limitations</span></span>

- <span data-ttu-id="87c5e-124">Eksportavimo trukmė priklauso nuo sistemos efektyvumo.</span><span class="sxs-lookup"><span data-stu-id="87c5e-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="87c5e-125">Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties.</span><span class="sxs-lookup"><span data-stu-id="87c5e-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="87c5e-126">Objektų, kurių klientų profiliai yra iki 100 milijonų, eksportavimas gali užtrukti 90 minučių naudojant rekomenduojamą minimalią dviejų procesorių IR 1 GB atminties konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="87c5e-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="87c5e-127">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="87c5e-127">Data privacy and compliance</span></span>

<span data-ttu-id="87c5e-128">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="87c5e-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="87c5e-129">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskirties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="87c5e-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="87c5e-130">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="87c5e-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="87c5e-131">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="87c5e-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]