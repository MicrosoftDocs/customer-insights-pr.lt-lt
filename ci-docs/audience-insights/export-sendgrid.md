---
title: „Customer Insights” duomenų eksportavimas į „SendGrid”
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „SendGrid“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976926"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="60254-103">Segmentų eksportavimas į „SendGrid“ (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="60254-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="60254-104">Eksportuokite vieningųjų klientų profilių segmentus į „SendGrid” kontaktų sąrašus ir naudokite juos kampanijoms bei el. pašto rinkodarą naudojant „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="60254-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="60254-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="60254-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="60254-106">Turite [„SendGrid” abonementą](https://sendgrid.com/) ir atitinkamus administratoriaus kredencialus.</span><span class="sxs-lookup"><span data-stu-id="60254-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="60254-107">„SendGrid” yra kontaktų sąrašų ir atitinkamų ID.</span><span class="sxs-lookup"><span data-stu-id="60254-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="60254-108">Daugiau informacijos žr. [„SendGrid“ – Kontaktų tvarkymas](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="60254-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="60254-109">Turite [sukonfigūruotus segmentus](segments.md) publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="60254-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="60254-110">Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.</span><span class="sxs-lookup"><span data-stu-id="60254-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="60254-111">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="60254-111">Known limitations</span></span>

- <span data-ttu-id="60254-112">Iš viso iki 100 000 profilių į „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="60254-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="60254-113">Eksportavimas į „SendGrid” ribojamas segmentais.</span><span class="sxs-lookup"><span data-stu-id="60254-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="60254-114">Iki 100 000 profilių eksportavimas į „SendGrid” gali užtrukti iki kelių valandų.</span><span class="sxs-lookup"><span data-stu-id="60254-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="60254-115">Profilių, kuriuos galite eksportuoti į „SendGrid”, skaičius yra priklausomas ir apribotas pagal jūsų sutartį su „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="60254-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="60254-116">Ryšio su „SendGrid“ nustatymas</span><span class="sxs-lookup"><span data-stu-id="60254-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="60254-117">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="60254-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="60254-118">Pasirinkite **Pridėti ryšį** ir pasirinkite **„SendGrid“**, kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="60254-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="60254-119">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="60254-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="60254-120">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="60254-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="60254-121">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="60254-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="60254-122">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="60254-122">Choose who can use this connection.</span></span> <span data-ttu-id="60254-123">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="60254-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="60254-124">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="60254-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="60254-125">Įveskite savo **„SendGrid” API raktą**[„SendGrid” API raktas](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="60254-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="60254-126">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="60254-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="60254-127">Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį su „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="60254-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="60254-128">Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.</span><span class="sxs-lookup"><span data-stu-id="60254-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="60254-129">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="60254-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="60254-130">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="60254-130">Configure an export</span></span>

<span data-ttu-id="60254-131">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="60254-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="60254-132">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="60254-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="60254-133">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="60254-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="60254-134">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="60254-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="60254-135">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „SendGrid“.</span><span class="sxs-lookup"><span data-stu-id="60254-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="60254-136">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="60254-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="60254-137">Įveskite **[„SendGrid” sąrašo ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="60254-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="60254-138">**Duomenų atitikties** skyriuje **El. pašto** laukelyje, pasirinkite laukelį jūsų suvienodintame kliento profilyje, kuris rodo kliento el. pašto adresą.</span><span class="sxs-lookup"><span data-stu-id="60254-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="60254-139">Pakartokite tuos pačius žingsnius kitiems pasirinktiniams laukams, pvz.:**Vardas**, **Pavardė**, **Šalis / regionas**, **Valstija**, **Miestas**, **Pašto kodas**.</span><span class="sxs-lookup"><span data-stu-id="60254-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="60254-140">Pasirinkite segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="60254-140">Select the segments you want to export.</span></span> <span data-ttu-id="60254-141">Primygtinai **rekomenduojame eksportuoti ne daugiau nei 100 000 klientų profilių** į „SendGrid”.</span><span class="sxs-lookup"><span data-stu-id="60254-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="60254-142">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="60254-142">Select **Save**.</span></span>

<span data-ttu-id="60254-143">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="60254-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="60254-144">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="60254-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="60254-145">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="60254-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="60254-146">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="60254-146">Data privacy and compliance</span></span>

<span data-ttu-id="60254-147">Kai leidžiate perduoti duomenis į „SendGrid”, leidžiate perduoti duomenis už tos „Dynamics 365 Customer Insights” sienos ribų, įskaitant galimai slaptus „Dynamics 365 Customer Insights” duomenis, pvz.: asmeninius duomenis.</span><span class="sxs-lookup"><span data-stu-id="60254-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="60254-148">„Microsoft” tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad „SendGrid” atitiktų privatumo arba saugos reikalavimus.</span><span class="sxs-lookup"><span data-stu-id="60254-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="60254-149">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="60254-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="60254-150">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="60254-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]