---
title: „Customer Insights“ duomenų eksportavimas į „Salesforce Marketing Cloud"
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Salesforce Marketing Cloud“.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314645"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="e707c-103">Segmentų ir kitų duomenų eksportavimas į „Salesforce Marketing Cloud" (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="e707c-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="e707c-104">„Salesforce Marketing Cloud" debesyje naudokite klientų duomenis eksportuodami juos „Secure File Transfer Protocol“ (SFTP) vietoje.</span><span class="sxs-lookup"><span data-stu-id="e707c-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e707c-105">Būtinosios ryšio sąlygos</span><span class="sxs-lookup"><span data-stu-id="e707c-105">Prerequisites for connection</span></span>

- <span data-ttu-id="e707c-106">SFTP pagrindinio kompiuterio ir atitinkamų administratoriaus kredencialų pasiekiamumas.</span><span class="sxs-lookup"><span data-stu-id="e707c-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="e707c-107">Kaip nustatyti „Salesforce Marketing Cloud" debesies SFTP vietoves</span><span class="sxs-lookup"><span data-stu-id="e707c-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="e707c-108">Žinomi apribojimai</span><span class="sxs-lookup"><span data-stu-id="e707c-108">Known limitations</span></span>

- <span data-ttu-id="e707c-109">Eksportavimo trukmė priklauso nuo sistemos efektyvumo.</span><span class="sxs-lookup"><span data-stu-id="e707c-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="e707c-110">Kaip minimalią serverio konfigūraciją rekomenduojame naudoti du procesorius IR 1 GB atminties.</span><span class="sxs-lookup"><span data-stu-id="e707c-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="e707c-111">Objektų eksportavimas naudojant iki 100 milijonų klientų profilių gali užtrukti 90 minučių naudojant rekomenduojamą mažiausią konfigūraciją.</span><span class="sxs-lookup"><span data-stu-id="e707c-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="e707c-112">Ryšio su „Salesforce Marketing Cloud" debesimi nustatyti</span><span class="sxs-lookup"><span data-stu-id="e707c-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="e707c-113">Eikite į **Administravimas** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="e707c-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e707c-114">Pasirinkite **Įtraukti ryšį** ir pasirinkite **Salesforce Marketing Cloud,** kad sukonfigūruotumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="e707c-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="e707c-115">Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**.</span><span class="sxs-lookup"><span data-stu-id="e707c-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e707c-116">Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="e707c-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e707c-117">Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.</span><span class="sxs-lookup"><span data-stu-id="e707c-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e707c-118">Pasirinkite, kas gali naudoti šį ryšį.</span><span class="sxs-lookup"><span data-stu-id="e707c-118">Choose who can use this connection.</span></span> <span data-ttu-id="e707c-119">Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai.</span><span class="sxs-lookup"><span data-stu-id="e707c-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e707c-120">Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e707c-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e707c-121">Savo SFDRE paskyroje pateikite **vartotojo vardą**, **slaptažodį**, **pagrindinio kompiuterio pavadinimą** ir **eksportavimo aplanką**.</span><span class="sxs-lookup"><span data-stu-id="e707c-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="e707c-122">Pasirinkite **Tikrinti**, kad išbandytumėte jungtį.</span><span class="sxs-lookup"><span data-stu-id="e707c-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e707c-123">Pasirinkę **Sutinku**, kad patvirtintumėte **Duomenų privatumą ir atitiktį**.</span><span class="sxs-lookup"><span data-stu-id="e707c-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e707c-124">Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.</span><span class="sxs-lookup"><span data-stu-id="e707c-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e707c-125">Eksportavimo konfigūravimas</span><span class="sxs-lookup"><span data-stu-id="e707c-125">Configure an export</span></span>

<span data-ttu-id="e707c-126">Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio.</span><span class="sxs-lookup"><span data-stu-id="e707c-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e707c-127">Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e707c-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e707c-128">Eikite į **Duomenys** > **Eksportavimas**.</span><span class="sxs-lookup"><span data-stu-id="e707c-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e707c-129">Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.</span><span class="sxs-lookup"><span data-stu-id="e707c-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e707c-130">Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje SFTP.</span><span class="sxs-lookup"><span data-stu-id="e707c-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="e707c-131">Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.</span><span class="sxs-lookup"><span data-stu-id="e707c-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e707c-132">Pasirinkite, ar savo duomenis norite eksportuoti kaip **Gzipped** arba **Unzipped**, ir pasirinkite eksportuotų failų **laukelio skyriklį**.</span><span class="sxs-lookup"><span data-stu-id="e707c-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e707c-133">Pažymėkite objektus, pvz.: segmentus, kuriuos norite eksportuoti.</span><span class="sxs-lookup"><span data-stu-id="e707c-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e707c-134">Eksportavus, kiekvienas pažymėtas objektas padalijamas į penkis išvesties failus.</span><span class="sxs-lookup"><span data-stu-id="e707c-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="e707c-135">Pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="e707c-135">Select **Save**.</span></span>

<span data-ttu-id="e707c-136">Eksportavimo įrašymas eksportavimo iš karto nevykdo.</span><span class="sxs-lookup"><span data-stu-id="e707c-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e707c-137">Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e707c-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e707c-138">Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e707c-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="e707c-139">„Customer Insights“ iš SFTP vietos duomenų importavimas į „Salesforce Marketing Cloud"</span><span class="sxs-lookup"><span data-stu-id="e707c-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="e707c-140">[„Salesforce Marketing Cloud" debesyje sukurkite duomenų](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) plėtinius, kad importuotute „Customer Insights" duomenų failą iš SFTP vietos.</span><span class="sxs-lookup"><span data-stu-id="e707c-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="e707c-141">[Importuokite duomenis iš SFTP vietos](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) į „Salesforce Marketing Cloud" duomenų plėtinį.</span><span class="sxs-lookup"><span data-stu-id="e707c-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="e707c-142">Nustatykite automatizavimą, kad duomenys būtų importuoti į duomenų plėtinius.</span><span class="sxs-lookup"><span data-stu-id="e707c-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="e707c-143">Sužinokite daugiau apie [failų numetimo automatizavimą ir suplanuotus automatizavimus](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="e707c-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="e707c-144">Apibrėžkite [failų numetimo](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) automatizavimą arba [suplanuotą automatizavimą](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="e707c-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="e707c-145">Štai automatizavimo su [SFTP pavyzdys](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="e707c-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e707c-146">Duomenų privatumas ir atitiktis</span><span class="sxs-lookup"><span data-stu-id="e707c-146">Data privacy and compliance</span></span>

<span data-ttu-id="e707c-147">Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į per SFTP, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys.</span><span class="sxs-lookup"><span data-stu-id="e707c-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e707c-148">„Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad eksportavimo paskirties vieta atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus.</span><span class="sxs-lookup"><span data-stu-id="e707c-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e707c-149">Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e707c-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e707c-150">Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šio eksportavimo paskirties vietą bet kuriuo metu, kad nutrauktų šios funkcijos naudojimą.</span><span class="sxs-lookup"><span data-stu-id="e707c-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
