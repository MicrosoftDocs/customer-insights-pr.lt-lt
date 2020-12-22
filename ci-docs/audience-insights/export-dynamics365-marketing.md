---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Marketing“
description: Sužinokite, kaip sukonfigūruoti ryšį su „Dynamics 365 Marketing“.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643783"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="b2212-103">„Dynamics 365 for Marketing“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b2212-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b2212-104">Naudokite [segmentus](segments.md) tam, kad sukurtumėte kampanijas ir susisiektumėte su konkrečiomis klientų grupėmis su „Dynamics 365 Marketing“.</span><span class="sxs-lookup"><span data-stu-id="b2212-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="b2212-105">Daugiau informacijos žr. [Segmentų naudojimas iš „Dynamics 365 Customer Insights“ su „Dynamics 365 Marketing“](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="b2212-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b2212-106">Būtinoji sąlyga</span><span class="sxs-lookup"><span data-stu-id="b2212-106">Prerequisite</span></span>

<span data-ttu-id="b2212-107">Kontaktiniai įrašai [iš „Dynamics 365 Marketing“ suvartotos „Common Data Service“](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b2212-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="b2212-108">„Marketing“ jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b2212-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="b2212-109">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="b2212-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b2212-110">Srityje **„Dynamics 365 Marketing“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="b2212-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="b2212-111">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="b2212-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b2212-112">Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.</span><span class="sxs-lookup"><span data-stu-id="b2212-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b2212-113">Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.</span><span class="sxs-lookup"><span data-stu-id="b2212-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="b2212-114">Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.</span><span class="sxs-lookup"><span data-stu-id="b2212-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b2212-115">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="b2212-115">Select **Next**.</span></span>

1. <span data-ttu-id="b2212-116">Pasirinkite vieną ar daugiau segmentų.</span><span class="sxs-lookup"><span data-stu-id="b2212-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="b2212-117">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="b2212-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b2212-118">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="b2212-118">Export the data</span></span>

<span data-ttu-id="b2212-119">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b2212-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b2212-120">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b2212-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
