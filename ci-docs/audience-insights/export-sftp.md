---
title: Eksportuoti „Customer Insights“ duomenis į SFTP šeimininkus
description: Sužinokite, kaip sukonfigūruoti ryšį su SFTP priegloba.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643513"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="869d8-103">SFTP jungtis (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="869d8-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="869d8-104">Naudokite savo kliento duomenis trečiosios šalies programose eksportuodami juos į „Secure File Transfer Protocol“ (SFTP) šeimininką.</span><span class="sxs-lookup"><span data-stu-id="869d8-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="869d8-105">Būtinosios sąlygos</span><span class="sxs-lookup"><span data-stu-id="869d8-105">Prerequisites</span></span>

- <span data-ttu-id="869d8-106">SFTP prieglobos ir atitinkamų kredencialų pasiekiamumas.</span><span class="sxs-lookup"><span data-stu-id="869d8-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="869d8-107">Prisijungimas prie SFTP</span><span class="sxs-lookup"><span data-stu-id="869d8-107">Connect to SFTP</span></span>

1. <span data-ttu-id="869d8-108">Eikite į **Administratorius** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="869d8-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="869d8-109">Dalyje **SFTP** pažymėkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="869d8-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="869d8-110">Nurodykite atpažįstamą pavadinimą lauke **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="869d8-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="869d8-111">Pateikite **Vartotojo vardą**, **Slaptažodį** ir **Šemininko pavadinimą** jūsų SFTP paskyrai.</span><span class="sxs-lookup"><span data-stu-id="869d8-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="869d8-112">Pavyzydys: Jei jūsų SFTP serverio šaknies katalogas yra /root/folder ir norėtumėte duomenis eksportuoti į /root/folder/ci_export_destination_folder, šemininkas turėtų būti sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="869d8-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="869d8-113">Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.</span><span class="sxs-lookup"><span data-stu-id="869d8-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="869d8-114">Sėkmingai patvirtinę, pasirinkite, ar norite eksportuojamus duomenis **Suglaudinti** arba **Išskleisti**, ir pasirinkite eksportuojamų failų **lauko skyriklį**.</span><span class="sxs-lookup"><span data-stu-id="869d8-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="869d8-115">Pasirinkę **Sutinku**, patvirtinkite **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="869d8-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="869d8-116">Norėdami pradėti konfigūruoti eksportavimą, pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="869d8-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="869d8-117">Ryšio konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="869d8-117">Configure the connection</span></span>

1. <span data-ttu-id="869d8-118">Pasirinkite eksportuotinus **kliento atributus**.</span><span class="sxs-lookup"><span data-stu-id="869d8-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="869d8-119">Galite eksportuoti vieną ar keletą atributų.</span><span class="sxs-lookup"><span data-stu-id="869d8-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="869d8-120">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="869d8-120">Select **Next**.</span></span>

1. <span data-ttu-id="869d8-121">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="869d8-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="869d8-122">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="869d8-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="869d8-123">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="869d8-123">Export the data</span></span>

<span data-ttu-id="869d8-124">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="869d8-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="869d8-125">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="869d8-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="869d8-126">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="869d8-126">Data privacy and compliance</span></span>

<span data-ttu-id="869d8-127">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="869d8-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="869d8-128">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskrties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus.</span><span class="sxs-lookup"><span data-stu-id="869d8-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="869d8-129">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="869d8-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="869d8-130">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="869d8-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
