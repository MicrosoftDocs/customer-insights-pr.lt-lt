---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Sales“
description: Sužinokite, kaip sukonfigūruoti ryšį su „Dynamics 365 Sales“.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643828"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="2e41a-103">„Dynamics 365 for Sales“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="2e41a-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2e41a-104">Naudokite savo klientų duomenis kurdami rinkodaros sąrašus, vykdydami darbo eigas ir siųsdami pasiūlymus su „Dynamics 365 Sales“.</span><span class="sxs-lookup"><span data-stu-id="2e41a-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="2e41a-105">Būtinoji sąlyga</span><span class="sxs-lookup"><span data-stu-id="2e41a-105">Prerequisite</span></span>

<span data-ttu-id="2e41a-106">Kontaktiniai įrašai [iš „Dynamics 365 Sales“ suvartotos naudojant „Common Data Service“](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2e41a-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="2e41a-107">„Sales“ jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="2e41a-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="2e41a-108">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="2e41a-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2e41a-109">Srityje **„Dynamics 365 Sales“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="2e41a-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="2e41a-110">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="2e41a-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2e41a-111">Lauke **Serverio adresas** įveskite savo organizacijos „Sales“ URL.</span><span class="sxs-lookup"><span data-stu-id="2e41a-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2e41a-112">Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Sales“ klientą.</span><span class="sxs-lookup"><span data-stu-id="2e41a-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2e41a-113">Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.</span><span class="sxs-lookup"><span data-stu-id="2e41a-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2e41a-114">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="2e41a-114">Select **Next**.</span></span>

1. <span data-ttu-id="2e41a-115">Pasirinkite vieną ar daugiau segmentų.</span><span class="sxs-lookup"><span data-stu-id="2e41a-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="2e41a-116">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="2e41a-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2e41a-117">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="2e41a-117">Export the data</span></span>

<span data-ttu-id="2e41a-118">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2e41a-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2e41a-119">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2e41a-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
