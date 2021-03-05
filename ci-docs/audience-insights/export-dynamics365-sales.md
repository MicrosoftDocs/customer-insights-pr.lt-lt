---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Sales“
description: Sužinokite, kaip sukonfigūruoti ryšį su „Dynamics 365 Sales“.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269018"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="b4563-103">„Dynamics 365 for Sales“ jungtis (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b4563-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b4563-104">Naudokite savo klientų duomenis kurdami rinkodaros sąrašus, vykdydami darbo eigas ir siųsdami pasiūlymus su „Dynamics 365 Sales“.</span><span class="sxs-lookup"><span data-stu-id="b4563-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b4563-105">Būtinoji sąlyga</span><span class="sxs-lookup"><span data-stu-id="b4563-105">Prerequisite</span></span>

1. <span data-ttu-id="b4563-106">Kontaktų įrašai turi būti "Dynamics 365 Sales", kad segmentą būtų galima eksportuoti iš "Customer Insights" į "Marketing".</span><span class="sxs-lookup"><span data-stu-id="b4563-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b4563-107">Sužinokite daugiau, kaip pasiekti ["Dynamics 365 Sales" kontaktus naudojant Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b4563-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b4563-108">Eksportuojant segmentus iš auditorijos įžvalgų į "Sales" nebus sukurta naujų kontaktų įrašų pardavimo egzemplioriuose.</span><span class="sxs-lookup"><span data-stu-id="b4563-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b4563-109">Kontaktų įrašai iš "Sales" turi būti įtraukti į auditorijos įžvalgas ir naudojami duomenų šaltinis.</span><span class="sxs-lookup"><span data-stu-id="b4563-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b4563-110">Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.</span><span class="sxs-lookup"><span data-stu-id="b4563-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="b4563-111">„Sales“ jungties konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b4563-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="b4563-112">Publikos įžvalgose, eikite į **Administravimas** > **Eksportavimo paskirties vietos**.</span><span class="sxs-lookup"><span data-stu-id="b4563-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b4563-113">Srityje **„Dynamics 365 Sales“** pasirinkite **Nustatyti**.</span><span class="sxs-lookup"><span data-stu-id="b4563-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="b4563-114">Nurodykite atpažįstamą eksportavimo paskirties vietos pavadinimą lauke **Rodomas pavadinimas**.</span><span class="sxs-lookup"><span data-stu-id="b4563-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b4563-115">Lauke **Serverio adresas** įveskite savo organizacijos „Sales“ URL.</span><span class="sxs-lookup"><span data-stu-id="b4563-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b4563-116">Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Sales“ klientą.</span><span class="sxs-lookup"><span data-stu-id="b4563-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b4563-117">Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.</span><span class="sxs-lookup"><span data-stu-id="b4563-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b4563-118">Pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="b4563-118">Select **Next**.</span></span>

1. <span data-ttu-id="b4563-119">Pasirinkite vieną ar daugiau segmentų.</span><span class="sxs-lookup"><span data-stu-id="b4563-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="b4563-120">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="b4563-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b4563-121">Duomenų eksportavimas</span><span class="sxs-lookup"><span data-stu-id="b4563-121">Export the data</span></span>

<span data-ttu-id="b4563-122">Galite [eksportuoti duomenis pareikalavus](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b4563-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b4563-123">Eksportavimas taip pat bus vykdomas per kiekvieną [suplanuotą naujinimą](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b4563-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]