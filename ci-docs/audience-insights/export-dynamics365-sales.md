---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Sales“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Sales“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759614"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="b0194-103">„Dynamics 365 Sales“ segmentų naudojimas (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="b0194-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b0194-104">Naudokite savo klientų duomenis kurdami rinkodaros sąrašus, vykdydami darbo eigas ir siųsdami pasiūlymus su „Dynamics 365 Sales“.</span><span class="sxs-lookup"><span data-stu-id="b0194-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="b0194-105">Būtinoji ryšio sąlyga</span><span class="sxs-lookup"><span data-stu-id="b0194-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="b0194-106">Kontaktų įrašai turi būti „Dynamics 365 Sales”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Sales”.</span><span class="sxs-lookup"><span data-stu-id="b0194-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b0194-107">Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Sales” kontaktus naudojant „Common Data Services”](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b0194-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b0194-108">Eksportuojant segmentus iš auditorijos įžvalgų į „Sales” nebus sukurta naujų kontaktų įrašų pardavimo egzemplioriuose.</span><span class="sxs-lookup"><span data-stu-id="b0194-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b0194-109">Kontaktų įrašai iš „Sales” turi būti įtraukti į auditorijos įžvalgas ir naudojami kaip duomenų šaltinis.</span><span class="sxs-lookup"><span data-stu-id="b0194-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b0194-110">Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.</span><span class="sxs-lookup"><span data-stu-id="b0194-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="b0194-111">„Sales“ ryšio sąranka</span><span class="sxs-lookup"><span data-stu-id="b0194-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="b0194-112">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="b0194-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b0194-113">Pasirinkite **Pridėti ryšį** ir pasirinkite **„Dynamics 365 Sales“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0194-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="b0194-114">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="b0194-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b0194-115">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0194-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b0194-116">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="b0194-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b0194-117">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0194-117">Choose who can use this connection.</span></span> <span data-ttu-id="b0194-118">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="b0194-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b0194-119">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b0194-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b0194-120">Lauke **Serverio adresas** įveskite savo organizacijos „Sales“ URL.</span><span class="sxs-lookup"><span data-stu-id="b0194-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b0194-121">Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Sales“ klientą.</span><span class="sxs-lookup"><span data-stu-id="b0194-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b0194-122">Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.</span><span class="sxs-lookup"><span data-stu-id="b0194-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b0194-123">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="b0194-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b0194-124">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="b0194-124">Configure an export</span></span>

<span data-ttu-id="b0194-125">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="b0194-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b0194-126">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b0194-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b0194-127">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="b0194-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b0194-128">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="b0194-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b0194-129">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Dynamics 365 Sales“ talpykla.</span><span class="sxs-lookup"><span data-stu-id="b0194-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="b0194-130">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="b0194-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b0194-131">Pasirinkite vieną ar daugiau segmentų.</span><span class="sxs-lookup"><span data-stu-id="b0194-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="b0194-132">Pasirinkite **Įrašyti**</span><span class="sxs-lookup"><span data-stu-id="b0194-132">Select **Save**</span></span>

<span data-ttu-id="b0194-133">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="b0194-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b0194-134">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b0194-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b0194-135">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b0194-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
