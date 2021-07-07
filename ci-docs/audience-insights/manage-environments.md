---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304890"
---
# <a name="manage-environments"></a><span data-ttu-id="ea09d-103">Aplinkų valdymas</span><span class="sxs-lookup"><span data-stu-id="ea09d-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ea09d-104">Šis straipsnis paaiškina, kaip sukurti naują organizaciją ir kaip aprūpinti aplinką.</span><span class="sxs-lookup"><span data-stu-id="ea09d-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="ea09d-105">Prisijunkite ir sukurkite organizaciją</span><span class="sxs-lookup"><span data-stu-id="ea09d-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="ea09d-106">Atidarykite svetainę [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="ea09d-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="ea09d-107">Pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="ea09d-108">pasirinkite pageidaujamą prisijungimo scenarijų ir pasirinkite atitinkamą nuorodą.</span><span class="sxs-lookup"><span data-stu-id="ea09d-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="ea09d-109">Sutikite su sąlygomis ir pasirinkite **Tęsti**, kad pradėtumėte kurti organizaciją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="ea09d-110">Sukūrus aplinką jus nukreips į [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="ea09d-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="ea09d-111">Norėdami ištirti programą, naudokite demonstracinę aplinką arba galite sukurti naują aplinką atlikdami kitame skyriuje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="ea09d-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="ea09d-112">Nurodę aplinkos parametrus, pasirinkite **Kurti**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="ea09d-113">Būsite prijungti po to, kai aplinka bus sėkmingai sukurta.</span><span class="sxs-lookup"><span data-stu-id="ea09d-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="ea09d-114">Aplinkos kūrimas esamoje organizacijoje</span><span class="sxs-lookup"><span data-stu-id="ea09d-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="ea09d-115">Yra du naujos aplinkos kūrimo būdai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="ea09d-116">Galite nurodyti visiškai naują konfigūraciją arba galite kopijuoti tam tikrus konfigūracijos parametrus iš esamos aplinkos.</span><span class="sxs-lookup"><span data-stu-id="ea09d-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

> [!NOTE]
> <span data-ttu-id="ea09d-117">Organizacijos gali sukurti *dvi* aplinkas kiekvienai „Customer Insights“ licencijai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-117">Organizations can create *two* environments for every Customer Insights license.</span></span> <span data-ttu-id="ea09d-118">Jei jūsų organizacija įsigyja daugiau nei vieną licenciją, [kreipkitės į mūsų palaikymo komandą](https://go.microsoft.com/fwlink/?linkid=2079641), kad padidintumėte galimų aplinkų skaičių.</span><span class="sxs-lookup"><span data-stu-id="ea09d-118">If your organization purchases more than once license, please [contact our support team](https://go.microsoft.com/fwlink/?linkid=2079641) to increase the number of available environments.</span></span> <span data-ttu-id="ea09d-119">Norėdami gauti daugiau informacijos apie pajėgumus ir papildomus pajėgumus, atsisiųskite [„Dynamics 365“ licencijų vadovą](https://go.microsoft.com/fwlink/?LinkId=866544).</span><span class="sxs-lookup"><span data-stu-id="ea09d-119">For more information about capacity and add-on capacity, download [Dynamics 365 licensing guide](https://go.microsoft.com/fwlink/?LinkId=866544).</span></span>

<span data-ttu-id="ea09d-120">Norėdami sukurti aplinką:</span><span class="sxs-lookup"><span data-stu-id="ea09d-120">To create an environment:</span></span>

1. <span data-ttu-id="ea09d-121">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-121">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="ea09d-122">Pasirinkite **Nauja**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-122">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ea09d-123">![Aplinkų parametrai.](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="ea09d-123">![Environment settings.](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="ea09d-124">Dialogo lange **Aplinkos kūrimas** pažymėkite **Nauja aplinka**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-124">In the **Create an environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="ea09d-125">Jei norite [kopijuoti duomenis iš esamos aplinkos](#considerations-for-copy-configuration-preview), pasirinkite **Kopijuoti iš esamos aplinkos**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-125">If you want to [copy data from the current environment](#considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="ea09d-126">Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.</span><span class="sxs-lookup"><span data-stu-id="ea09d-126">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="ea09d-127">Nurodykite toliau pateiktą informaciją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-127">Provide the following details:</span></span>
   - <span data-ttu-id="ea09d-128">**Pavadinimas**: Šios aplinkos pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="ea09d-128">**Name**: The name for this environment.</span></span> <span data-ttu-id="ea09d-129">Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.</span><span class="sxs-lookup"><span data-stu-id="ea09d-129">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="ea09d-130">**Tipas**: pasirinkite, ar norite kurti gamybos ar smėlio dėžės aplinką.</span><span class="sxs-lookup"><span data-stu-id="ea09d-130">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>
   - <span data-ttu-id="ea09d-131">**Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga.</span><span class="sxs-lookup"><span data-stu-id="ea09d-131">**Region**: The region into which the service is deployed and hosted.</span></span>
   
1. <span data-ttu-id="ea09d-132">Pasirinktinai galite spustelėti **Išplėstiniai parametrai**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-132">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="ea09d-133">**Įrašyti visus duomenis į**: nurodo, kur norite saugoti išvesties duomenis, sugeneruotus iš „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="ea09d-133">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="ea09d-134">Galėsite pasirinkti dvi galimybes: **„Customer Insights" saugyklą** („Azure Data Lake", kurią valdo „Customer Insights" komanda ir **Azure Data Lake Storage** (komanda ir „Azure Data Lake Storage“).</span><span class="sxs-lookup"><span data-stu-id="ea09d-134">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="ea09d-135">Pagal numatytuosius parametrus, pasirenkama „Customer Insights“ saugykla.</span><span class="sxs-lookup"><span data-stu-id="ea09d-135">By default, the Customer Insights storage option is selected.</span></span>

     > [!NOTE]
     > <span data-ttu-id="ea09d-136">Įrašydami duomenis į „Azure Data Lake Storage, sutinkate, kad jūsų duomenys būtų perkelti ir saugomi konkrečiai „Azure“ paskyrai paskirtoje geografinėje vietovėje , kuri gali skirtis nuo vietovės, kurioje saugomi „Dynamics 365 Customer Insights“ duomenys.</span><span class="sxs-lookup"><span data-stu-id="ea09d-136">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="ea09d-137">Sužinokite daugiau „Microsoft“ patikimumo centre.</span><span class="sxs-lookup"><span data-stu-id="ea09d-137">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
     >
     > <span data-ttu-id="ea09d-138">Šiuo metu surinkti objektai visada saugomi „Customer Insights“ „Managed Data Lake.“</span><span class="sxs-lookup"><span data-stu-id="ea09d-138">Currently, ingested entities are always stored in the Customer Insights Managed Data Lake.</span></span> 
     > 
     > <span data-ttu-id="ea09d-139">Palaikome tik to „Azure Data Lake Storage“ paties „Azure" regiono, kurį pasirinkote kurdami aplinką, abonementus.</span><span class="sxs-lookup"><span data-stu-id="ea09d-139">We support only Azure Data Lake Storage accounts from the same Azure region you selected when creating the environment.</span></span> 
     > 
     > <span data-ttu-id="ea09d-140">Palaikome tik „Azure Data Lake Storage“ abonementus, kurių hierarchinė vardų sritis įjungta.</span><span class="sxs-lookup"><span data-stu-id="ea09d-140">We support only Azure Data Lake Storage accounts that have hierarchical namespace enabled.</span></span>


   - <span data-ttu-id="ea09d-141">Galite „Azure Data Lake Storage“ pasirinkti iš išteklių pagrįstą parinktį ir prenumerata pagrįstą autentifikavimo parinktį.</span><span class="sxs-lookup"><span data-stu-id="ea09d-141">For the Azure Data Lake Storage option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="ea09d-142">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ea09d-142">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ea09d-143">**Talpyklės** pavadinimo keisti negalima, jis bus `customerinsights`.</span><span class="sxs-lookup"><span data-stu-id="ea09d-143">The **Container** name can't be changed and will be `customerinsights`.</span></span>
   
   - <span data-ttu-id="ea09d-144">Jei norite naudoti [prognozes](predictions.md), konfigūruoti duomenų bendrinimą su „Microsoft Dataverse” arba įjungti duomenų paėmimą iš vietinių duomenų šaltinių, nurodykite „Microsoft Dataverse” aplinkos URL skiltyje **Duomenų bendrinimo su „Microsoft Dataverse” konfigūravimas ir papildomų galimybių įjungimas**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-144">If you want to use [predictions](predictions.md), configure data sharing with Microsoft Dataverse, or enable data ingestion from on-premises data sources, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="ea09d-145">Pasirinkite Įjungti **duomenų bendrinimą** ir bendrinkite Customer Insights išvedimo duomenis su Microsoft Dataverse valdomu Data Lake.</span><span class="sxs-lookup"><span data-stu-id="ea09d-145">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="ea09d-146">Duomenų bendrinimas Microsoft Dataverse su valdomasis duomenų telkiniais šiuo metu nepalaikomas, kai įrašote visus duomenis savo Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="ea09d-146">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="ea09d-147">[Prognozės šiuo metu nepalaikomos](predictions.md) trūkstamų objekto reikšmių reikšmės, kai leidžiate bendrinti duomenis su Microsoft Dataverse valdomojo Data Lake duomenimis.</span><span class="sxs-lookup"><span data-stu-id="ea09d-147">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="ea09d-148">![Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.](media/datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="ea09d-148">![Configuration options to enable data sharing with Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="ea09d-149">Jums vykdant procesus, tokius kaip duomenų suvartojimas ar segmento sukūrimas, atitinkantys katalogai bus sukuriami talpinimo paskyroje, kurią nurodėte prieš tai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-149">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="ea09d-150">Duomenų failai ir model.json failai bus kuriami ir įtraukiami į aplankus, atsižvelgiant į proceso pavadinimą.</span><span class="sxs-lookup"><span data-stu-id="ea09d-150">Data files and model.json files will be created and added to folders based on the process name.</span></span>

   <span data-ttu-id="ea09d-151">Jei sukuriate keletą „Customer Insights“ aplinkų ir pasirenkate įrašyti išvesties objektus iš tų aplinkų į jūsų talpinimo paskyrą, atskiri katalogai bus sukurti kiekvienai aplinka su ci_<environmentid> talpykloje.</span><span class="sxs-lookup"><span data-stu-id="ea09d-151">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="considerations-for-copy-configuration-preview"></a><span data-ttu-id="ea09d-152">Kopijavimo konfigūravimo aspektai (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="ea09d-152">Considerations for copy configuration (preview)</span></span>

<span data-ttu-id="ea09d-153">Kopijuojami šie konfigūracijos parametrai:</span><span class="sxs-lookup"><span data-stu-id="ea09d-153">The following configuration settings are copied:</span></span>

- <span data-ttu-id="ea09d-154">Funkcijų konfigūracijos</span><span class="sxs-lookup"><span data-stu-id="ea09d-154">Feature configurations</span></span>
- <span data-ttu-id="ea09d-155">Įtrauktas / importuotas duomenų šaltinis</span><span class="sxs-lookup"><span data-stu-id="ea09d-155">Ingested/imported data sources</span></span>
- <span data-ttu-id="ea09d-156">Duomenų sujungimo (susiejimo, atitikimo, suliejimo) konfigūracija</span><span class="sxs-lookup"><span data-stu-id="ea09d-156">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="ea09d-157">Segmentai</span><span class="sxs-lookup"><span data-stu-id="ea09d-157">Segments</span></span>
- <span data-ttu-id="ea09d-158">Matavimai</span><span class="sxs-lookup"><span data-stu-id="ea09d-158">Measures</span></span>
- <span data-ttu-id="ea09d-159">Ryšiai</span><span class="sxs-lookup"><span data-stu-id="ea09d-159">Relationships</span></span>
- <span data-ttu-id="ea09d-160">Veiklos</span><span class="sxs-lookup"><span data-stu-id="ea09d-160">Activities</span></span>
- <span data-ttu-id="ea09d-161">Paieškos ir filtravimo rodyklė</span><span class="sxs-lookup"><span data-stu-id="ea09d-161">Search & filter Index</span></span>
- <span data-ttu-id="ea09d-162">Eksportavimo paskirties vietos</span><span class="sxs-lookup"><span data-stu-id="ea09d-162">Export destinations</span></span>
- <span data-ttu-id="ea09d-163">Suplanuotas atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="ea09d-163">Scheduled refresh</span></span>
- <span data-ttu-id="ea09d-164">Duomenų papildymai</span><span class="sxs-lookup"><span data-stu-id="ea09d-164">Enrichments</span></span>
- <span data-ttu-id="ea09d-165">Modelio valdymas</span><span class="sxs-lookup"><span data-stu-id="ea09d-165">Model management</span></span>
- <span data-ttu-id="ea09d-166">Vaidmenų priskyrimai</span><span class="sxs-lookup"><span data-stu-id="ea09d-166">Role assignments</span></span>

<span data-ttu-id="ea09d-167">Šie konfigūracijos parametrai *nėra* kopijuojami:</span><span class="sxs-lookup"><span data-stu-id="ea09d-167">The following settings are *not* copied:</span></span>

- <span data-ttu-id="ea09d-168">Klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-168">Customer profiles.</span></span>
- <span data-ttu-id="ea09d-169">Duomenų šaltinio kredencialai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-169">Data source credentials.</span></span> <span data-ttu-id="ea09d-170">Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.</span><span class="sxs-lookup"><span data-stu-id="ea09d-170">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="ea09d-171">Duomenų šaltiniai iš „Common Data Model“ aplanko ir „Dataverse“ valdomojo duomenų „Data Lake".</span><span class="sxs-lookup"><span data-stu-id="ea09d-171">Data sources from Common Data Model folder and Dataverse managed Data Lake.</span></span> <span data-ttu-id="ea09d-172">Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.</span><span class="sxs-lookup"><span data-stu-id="ea09d-172">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="ea09d-173">Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka.</span><span class="sxs-lookup"><span data-stu-id="ea09d-173">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="ea09d-174">Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.</span><span class="sxs-lookup"><span data-stu-id="ea09d-174">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="ea09d-175">Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-175">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="ea09d-176">Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.</span><span class="sxs-lookup"><span data-stu-id="ea09d-176">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ea09d-177">![Nukopijuoti duomenų šaltiniai.](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="ea09d-177">![Data sources copied.](media/data-sources-copied.png)</span></span>

<span data-ttu-id="ea09d-178">Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-178">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="ea09d-179">Čia rasite parametrus iš šaltinio aplinkos.</span><span class="sxs-lookup"><span data-stu-id="ea09d-179">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="ea09d-180">Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.</span><span class="sxs-lookup"><span data-stu-id="ea09d-180">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="ea09d-181">Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.</span><span class="sxs-lookup"><span data-stu-id="ea09d-181">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="ea09d-182">Esamos aplinkos redagavimas</span><span class="sxs-lookup"><span data-stu-id="ea09d-182">Edit an existing environment</span></span>

<span data-ttu-id="ea09d-183">Galite redaguoti kai kurią esamos aplinkos informaciją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-183">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="ea09d-184">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-184">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="ea09d-185">Pasirinkite **Redagavimo** piktogramą.</span><span class="sxs-lookup"><span data-stu-id="ea09d-185">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="ea09d-186">Lauke **Redaguoti aplinką** galite atnaujinti aplinkos rodomą **Pavadinimą**, tačiau negalite keisti  **Regiono** arba **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-186">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="ea09d-187">Jei aplinka sukonfigūruota duomenims saugoti „Azure Data Lake Storage“, galite atnaujinti **kliento raktą**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-187">If an environment is configured to store data in Azure Data Lake Storage, you can update the **Account key**.</span></span> <span data-ttu-id="ea09d-188">Tačiau negalite keisti **Paskyros pavadinimo** arba **Konteinerio** pavadinimo.</span><span class="sxs-lookup"><span data-stu-id="ea09d-188">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="ea09d-189">Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursais pagrįstą arba prenumeravimu pagrįstą jungtį.</span><span class="sxs-lookup"><span data-stu-id="ea09d-189">Optionally, you can update from an account key-based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="ea09d-190">Jums atnaujinus negalėsite grįžti prie pagrindinės paskyros po naujinimo.</span><span class="sxs-lookup"><span data-stu-id="ea09d-190">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="ea09d-191">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="ea09d-191">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="ea09d-192">Negalite keisti **Talpyklos** informacijos naujinant jungtį.</span><span class="sxs-lookup"><span data-stu-id="ea09d-192">You can't change **Container** information when updating the connection.</span></span>

6. <span data-ttu-id="ea09d-193">Taip pat galite nurodytų Microsoft Dataverse aplinkos URL skiltyje **Duomenų bendrinimo su Microsoft Dataverse konfigūravimas ir papildomų galimybių įjungimas**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-193">Optionally, you can provide a Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="ea09d-194">Į šias galimybes įeina duomenų bendrinimas su „Microsoft Dataverse” pagrįstomis programomis ir sprendimais, duomenų paėmimas iš vietinių duomenų šaltinių arba [prognozių](predictions.md) naudojimas.</span><span class="sxs-lookup"><span data-stu-id="ea09d-194">These capabilities include data sharing with applications and solutions based on Microsoft Dataverse, data ingestion from on-premises data sources, or the use [predictions](predictions.md).</span></span> <span data-ttu-id="ea09d-195">Pasirinkite **Įjungti duomenų bendrinimą**, jei „Customer Insights“ išvesties duomenis norite bendrinti su Microsoft Dataverse valdomu „Data Lake“.</span><span class="sxs-lookup"><span data-stu-id="ea09d-195">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data lake.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="ea09d-196">Duomenų bendrinimas Microsoft Dataverse su valdomasis duomenų telkiniais šiuo metu nepalaikomas, kai įrašote visus duomenis savo Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="ea09d-196">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
   > - <span data-ttu-id="ea09d-197">[Trūkstamų objekto verčių prognozė](predictions.md) šiuo metu nepalaikoma, kai įjungiate duomenų bendrinimą su Microsoft Dataverse valdomu „Data Lake“.</span><span class="sxs-lookup"><span data-stu-id="ea09d-197">[Prediction of missing values in an entity](predictions.md) is currently not supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

   <span data-ttu-id="ea09d-198">Įgalinus duomenų bendrinimą su „Microsoft Dataverse”, prasideda visiškas jūsų duomenų šaltinių atnaujinimas ir kiti procesai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-198">After enabling data sharing with Microsoft Dataverse, a full refresh of your data sources and other processes starts.</span></span> <span data-ttu-id="ea09d-199">Jei šiuo metu vykdomi procesai, nematysite duomenų bendrinimo su „Microsoft Dataverse” įjungimo parinkties.</span><span class="sxs-lookup"><span data-stu-id="ea09d-199">If processes are currently running, you don't see the option to enable data sharing with Microsoft Dataverse.</span></span> <span data-ttu-id="ea09d-200">Palaukite, kol šie procesai bus užbaigti arba atšaukite juos, kad įgalintumėte duomenų bendrinimą.</span><span class="sxs-lookup"><span data-stu-id="ea09d-200">Wait for those processes to complete or cancel them to enable data sharing.</span></span> 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Konfigūravimo parinktys duomenų bendrinimui su Microsoft Dataverse įjungti.":::
   
   <span data-ttu-id="ea09d-202">Jums vykdant procesus, tokius kaip duomenų suvartojimas ar segmento sukūrimas, atitinkantys katalogai bus sukuriami talpinimo paskyroje, kurią nurodėte prieš tai.</span><span class="sxs-lookup"><span data-stu-id="ea09d-202">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="ea09d-203">Atsižvelgiant į jūsų vykdomą procesą, duomenų failai ir model.json failai kuriami ir įtraukiami į atitinkamus antrinius aplankus.</span><span class="sxs-lookup"><span data-stu-id="ea09d-203">Data files and model.json files will be created and added to the respective subfolders, depending on the process you run.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="ea09d-204">Paleiskite iš naujo esamą aplinką</span><span class="sxs-lookup"><span data-stu-id="ea09d-204">Reset an existing environment</span></span>

<span data-ttu-id="ea09d-205">Kaip administratorius galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti prarytus duomenis.</span><span class="sxs-lookup"><span data-stu-id="ea09d-205">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="ea09d-206">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-206">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="ea09d-207">Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**).</span><span class="sxs-lookup"><span data-stu-id="ea09d-207">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="ea09d-208">Pasirinkite parinktį **Nustatyti iš naujo**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-208">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="ea09d-209">Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-209">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment"></a><span data-ttu-id="ea09d-210">Esamos aplinkos naikinimas</span><span class="sxs-lookup"><span data-stu-id="ea09d-210">Delete an existing environment</span></span>

<span data-ttu-id="ea09d-211">Kaip administratorius galite panaikinti jūsų administruojamą aplinką.</span><span class="sxs-lookup"><span data-stu-id="ea09d-211">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="ea09d-212">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="ea09d-212">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="ea09d-213">Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį (**...**).</span><span class="sxs-lookup"><span data-stu-id="ea09d-213">Select the environment you want to reset and select the ellipsis (**...**).</span></span> 

3. <span data-ttu-id="ea09d-214">Pasirinkite parinktį **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-214">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="ea09d-215">Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="ea09d-215">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
