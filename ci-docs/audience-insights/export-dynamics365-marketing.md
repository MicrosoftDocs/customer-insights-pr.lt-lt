---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Marketing“
description: Sužinokite, kaip sukonfigūruoti ryšį su „Dynamics 365 Marketing“.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597613"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="ae8b5-103">„Dynamics 365 Marketing“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="ae8b5-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ae8b5-104">Naudokite [segmentus](segments.md) tam, kad sukurtumėte kampanijas ir susisiektumėte su konkrečiomis klientų grupėmis su „Dynamics 365 Marketing“.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="ae8b5-105">Daugiau informacijos žr. [Segmentų naudojimas iš „Dynamics 365 Customer Insights“ su „Dynamics 365 Marketing“](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="ae8b5-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ae8b5-106">Būtinoji sąlyga</span><span class="sxs-lookup"><span data-stu-id="ae8b5-106">Prerequisite</span></span>

- <span data-ttu-id="ae8b5-107">Kontaktų įrašai turi būti „Dynamics 365 Marketing”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Marketing”.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="ae8b5-108">Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Marketing ”kontaktus naudojant „Common Data Services”](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ae8b5-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ae8b5-109">Eksportuojant segmentus iš auditorijos įžvalgų į „Marketing” nebus sukurta naujų kontaktų įrašų rinkodaros egzemplioriuose.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="ae8b5-110">Kontaktų įrašai iš „Marketing” turi būti įtraukti į auditorijos įžvalgas ir naudojami duomenų šaltinis.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ae8b5-111">Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="ae8b5-112">„Marketing“ jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="ae8b5-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="ae8b5-113">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae8b5-114">Srityje **„Dynamics 365 Marketing“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="ae8b5-115">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ae8b5-116">Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ae8b5-117">Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="ae8b5-118">Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ae8b5-119">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-119">Select **Next**.</span></span>

1. <span data-ttu-id="ae8b5-120">Pasirinkite vieną ar daugiau segmentų.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="ae8b5-121">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="ae8b5-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae8b5-122">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="ae8b5-122">Export the data</span></span>

<span data-ttu-id="ae8b5-123">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ae8b5-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ae8b5-124">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae8b5-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]