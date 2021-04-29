---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Marketing“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Marketing“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759647"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="8344e-103">„Dynamics 365 Marketing“ segmentų naudojimas (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="8344e-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8344e-104">Naudokite [segmentus](segments.md) tam, kad sukurtumėte kampanijas ir susisiektumėte su konkrečiomis klientų grupėmis su „Dynamics 365 Marketing“.</span><span class="sxs-lookup"><span data-stu-id="8344e-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="8344e-105">Daugiau informacijos žr. [Segmentų naudojimas iš „Dynamics 365 Customer Insights“ su „Dynamics 365 Marketing“](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="8344e-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="8344e-106">Būtinoji ryšio sąlygą</span><span class="sxs-lookup"><span data-stu-id="8344e-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="8344e-107">Kontaktų įrašai turi būti „Dynamics 365 Marketing”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Marketing”.</span><span class="sxs-lookup"><span data-stu-id="8344e-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="8344e-108">Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Marketing ”kontaktus naudojant „Common Data Services”](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="8344e-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="8344e-109">Eksportuojant segmentus iš auditorijos įžvalgų į „Marketing” nebus sukurta naujų kontaktų įrašų rinkodaros egzemplioriuose.</span><span class="sxs-lookup"><span data-stu-id="8344e-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="8344e-110">Kontaktų įrašai iš „Marketing” turi būti įtraukti į auditorijos įžvalgas ir naudojami duomenų šaltinis.</span><span class="sxs-lookup"><span data-stu-id="8344e-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="8344e-111">Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.</span><span class="sxs-lookup"><span data-stu-id="8344e-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="8344e-112">Ryšio su rinkodara sąranka</span><span class="sxs-lookup"><span data-stu-id="8344e-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="8344e-113">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="8344e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8344e-114">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Dynamics 365 Marketing“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="8344e-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="8344e-115">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="8344e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8344e-116">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="8344e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8344e-117">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="8344e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8344e-118">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="8344e-118">Choose who can use this connection.</span></span> <span data-ttu-id="8344e-119">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="8344e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8344e-120">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8344e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8344e-121">Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.</span><span class="sxs-lookup"><span data-stu-id="8344e-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="8344e-122">Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.</span><span class="sxs-lookup"><span data-stu-id="8344e-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="8344e-123">Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.</span><span class="sxs-lookup"><span data-stu-id="8344e-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="8344e-124">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="8344e-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8344e-125">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="8344e-125">Configure an export</span></span>

<span data-ttu-id="8344e-126">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="8344e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8344e-127">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8344e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8344e-128">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="8344e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8344e-129">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="8344e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8344e-130">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Dynamics 365 Marketing“ talpykla.</span><span class="sxs-lookup"><span data-stu-id="8344e-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="8344e-131">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="8344e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8344e-132">Pasirinkite vieną ar daugiau segmentų.</span><span class="sxs-lookup"><span data-stu-id="8344e-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="8344e-133">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="8344e-133">Select **Save**.</span></span>

<span data-ttu-id="8344e-134">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="8344e-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8344e-135">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8344e-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8344e-136">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8344e-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
