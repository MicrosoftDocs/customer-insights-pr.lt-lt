---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598303"
---
# <a name="manage-environments"></a><span data-ttu-id="792b3-103">Aplinkų valdymas</span><span class="sxs-lookup"><span data-stu-id="792b3-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="792b3-104">Šis straipsnis paaiškina, kaip sukurti naują organizaciją ir kaip aprūpinti aplinką.</span><span class="sxs-lookup"><span data-stu-id="792b3-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="792b3-105">Prisijunkite ir sukurkite organizaciją</span><span class="sxs-lookup"><span data-stu-id="792b3-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="792b3-106">Atidarykite svetainę [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="792b3-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="792b3-107">Pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="792b3-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="792b3-108">pasirinkite pageidaujamą prisijungimo scenarijų ir pasirinkite atitinkamą nuorodą.</span><span class="sxs-lookup"><span data-stu-id="792b3-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="792b3-109">Sutikite su sąlygomis ir pasirinkite **Tęsti**, kad pradėtumėte kurti organizaciją.</span><span class="sxs-lookup"><span data-stu-id="792b3-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="792b3-110">Sukūrus aplinką jus nukreips į [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="792b3-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="792b3-111">Norėdami ištirti programą, naudokite demonstracinę aplinką arba galite sukurti naują aplinką atlikdami kitame skyriuje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="792b3-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="792b3-112">Nurodę aplinkos parametrus, pasirinkite **Kurti**.</span><span class="sxs-lookup"><span data-stu-id="792b3-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="792b3-113">Būsite prijungti po to, kai aplinka bus sėkmingai sukurta.</span><span class="sxs-lookup"><span data-stu-id="792b3-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="792b3-114">Aplinkos kūrimas esamoje organizacijoje</span><span class="sxs-lookup"><span data-stu-id="792b3-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="792b3-115">Yra du naujos aplinkos kūrimo būdai.</span><span class="sxs-lookup"><span data-stu-id="792b3-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="792b3-116">Galite nurodyti visiškai naują konfigūraciją arba galite kopijuoti tam tikrus konfigūracijos parametrus iš esamos aplinkos.</span><span class="sxs-lookup"><span data-stu-id="792b3-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="792b3-117">Norėdami sukurti aplinką:</span><span class="sxs-lookup"><span data-stu-id="792b3-117">To create an environment:</span></span>

1. <span data-ttu-id="792b3-118">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="792b3-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="792b3-119">Pasirinkite **Naujas**.</span><span class="sxs-lookup"><span data-stu-id="792b3-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="792b3-120">![Aplinkų parametrai](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="792b3-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="792b3-121">Dialogo lange **Naujos aplinkos kūrimas** pasirinkite **Nauja aplinka**.</span><span class="sxs-lookup"><span data-stu-id="792b3-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="792b3-122">Jei norite [kopijuoti duomenis iš esamos aplinkos](#additional-considerations-for-copy-configuration-preview), pasirinkite **Kopijuoti iš esamos aplinkos**.</span><span class="sxs-lookup"><span data-stu-id="792b3-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="792b3-123">Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.</span><span class="sxs-lookup"><span data-stu-id="792b3-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="792b3-124">Nurodykite toliau pateiktą informaciją.</span><span class="sxs-lookup"><span data-stu-id="792b3-124">Provide the following details:</span></span>
   - <span data-ttu-id="792b3-125">**Pavadinimas**: Šios aplinkos pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="792b3-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="792b3-126">Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.</span><span class="sxs-lookup"><span data-stu-id="792b3-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="792b3-127">**Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga.</span><span class="sxs-lookup"><span data-stu-id="792b3-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="792b3-128">**Tipas**: pasirinkite, ar norite kurti gamybos ar smėlio dėžės aplinką.</span><span class="sxs-lookup"><span data-stu-id="792b3-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="792b3-129">Pasirinktinai galite spustelėti **Išplėstiniai parametrai**.</span><span class="sxs-lookup"><span data-stu-id="792b3-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="792b3-130">**Įrašyti visus duomenis į**: nurodo, kur norite saugoti išvesties duomenis, sugeneruotus iš „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="792b3-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="792b3-131">Galimos dvi parinktys: **„Customer Insights“ saugykla** („Azure Data Lake“ valdomas „Customer Insights“ komandos) ir **„Azure Data Lake Storage Gen2”** (jūsų nuosava „Azure Data Lake Storage“).</span><span class="sxs-lookup"><span data-stu-id="792b3-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="792b3-132">Pagal numatytuosius parametrus, pasirenkama „Customer Insights“ saugykla.</span><span class="sxs-lookup"><span data-stu-id="792b3-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="792b3-133">Įrašydami duomenis į „Azure Data Lake Storage, sutinkate, kad jūsų duomenys būtų perkelti ir saugomi konkrečiai „Azure“ paskyrai paskirtoje geografinėje vietovėje , kuri gali skirtis nuo vietovės, kurioje saugomi „Dynamics 365 Customer Insights“ duomenys.</span><span class="sxs-lookup"><span data-stu-id="792b3-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="792b3-134">Sužinokite daugiau „Microsoft“ patikimumo centre.</span><span class="sxs-lookup"><span data-stu-id="792b3-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="792b3-135">Šiuo metu surinkti objektai visada saugomi „Customer Insights“ valdomame duomenų telkinyje.</span><span class="sxs-lookup"><span data-stu-id="792b3-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="792b3-136">Palaikome tik „Azure Data Lake Gen2“ talpinimo paskyras iš to paties „Azure“ regiono, kurį pasirinkote kurdami aplinką.</span><span class="sxs-lookup"><span data-stu-id="792b3-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="792b3-137">Palaikome tik „Azure Data Lake Gen2“ saugyklų paskyras, kurioms įgalinta hierarchinio pavadinimo (HNS) funkcija.</span><span class="sxs-lookup"><span data-stu-id="792b3-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="792b3-138">„Azure Data Lake Storage Gen2“ parinkčiai galite pasirinkti tarp resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui.</span><span class="sxs-lookup"><span data-stu-id="792b3-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="792b3-139">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="792b3-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="792b3-140">**Talpykla** pavadinimas negali būti keičiamas ir bus „klientoįžvalgos“.</span><span class="sxs-lookup"><span data-stu-id="792b3-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="792b3-141">Jei norite naudoti [prognozes](predictions.md) arba konfigūruoti duomenų bendrinimą su programomis ir sprendimais, pagrįstais Microsoft Dataverse, Microsoft Dataverse dalyje **Konfigūruoti duomenų bendrinimą su papildomomis galimybėmis Microsoft Dataverse** pateikite aplinkos URL.</span><span class="sxs-lookup"><span data-stu-id="792b3-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="792b3-142">Pasirinkite Įjungti **duomenų bendrinimą** ir bendrinkite Customer Insights išvedimo duomenis su Microsoft Dataverse valdomu Data Lake.</span><span class="sxs-lookup"><span data-stu-id="792b3-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="792b3-143">Duomenų bendrinimas Microsoft Dataverse su valdomasis duomenų telkiniais šiuo metu nepalaikomas, kai įrašote visus duomenis savo Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="792b3-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="792b3-144">[Prognozės šiuo metu nepalaikomos](predictions.md) trūkstamų objekto reikšmių reikšmės, kai leidžiate bendrinti duomenis su Microsoft Dataverse valdomojo Data Lake duomenimis.</span><span class="sxs-lookup"><span data-stu-id="792b3-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="792b3-145">![Konfigūravimo parinktys norint įjungti duomenų bendrinimą naudojant Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="792b3-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="792b3-146">Jums vykdant procesus, tokius kaip duomenų suvartojimas ar segmento sukūrimas, atitinkantys katalogai bus sukuriami talpinimo paskyroje, kurią nurodėte prieš tai.</span><span class="sxs-lookup"><span data-stu-id="792b3-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="792b3-147">Duomenų failai ir model.json failai bus sukurti ir įtraukti į atitinkamus poaplankius pagal jūsų vykdytą procesą.</span><span class="sxs-lookup"><span data-stu-id="792b3-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="792b3-148">Jei sukuriate keletą „Customer Insights“ aplinkų ir pasirenkate įrašyti išvesties objektus iš tų aplinkų į jūsų talpinimo paskyrą, atskiri katalogai bus sukurti kiekvienai aplinka su ci_<environmentid> talpykloje.</span><span class="sxs-lookup"><span data-stu-id="792b3-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="792b3-149">Papildomos pastabos dėl kopijavimo konfigūracijos (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="792b3-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="792b3-150">Kopijuojami šie konfigūracijos parametrai:</span><span class="sxs-lookup"><span data-stu-id="792b3-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="792b3-151">Funkcijų konfigūracijos</span><span class="sxs-lookup"><span data-stu-id="792b3-151">Feature configurations</span></span>
- <span data-ttu-id="792b3-152">Įtrauktas / importuotas duomenų šaltinis</span><span class="sxs-lookup"><span data-stu-id="792b3-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="792b3-153">Duomenų sujungimo (susiejimo, atitikimo, suliejimo) konfigūracija</span><span class="sxs-lookup"><span data-stu-id="792b3-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="792b3-154">Segmentai</span><span class="sxs-lookup"><span data-stu-id="792b3-154">Segments</span></span>
- <span data-ttu-id="792b3-155">Matavimai</span><span class="sxs-lookup"><span data-stu-id="792b3-155">Measures</span></span>
- <span data-ttu-id="792b3-156">Ryšiai</span><span class="sxs-lookup"><span data-stu-id="792b3-156">Relationships</span></span>
- <span data-ttu-id="792b3-157">Veiklos</span><span class="sxs-lookup"><span data-stu-id="792b3-157">Activities</span></span>
- <span data-ttu-id="792b3-158">Paieškos ir filtravimo rodyklė</span><span class="sxs-lookup"><span data-stu-id="792b3-158">Search & filter Index</span></span>
- <span data-ttu-id="792b3-159">Eksportavimo paskirties vietos</span><span class="sxs-lookup"><span data-stu-id="792b3-159">Export destinations</span></span>
- <span data-ttu-id="792b3-160">Suplanuotas atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="792b3-160">Scheduled refresh</span></span>
- <span data-ttu-id="792b3-161">Duomenų papildymai</span><span class="sxs-lookup"><span data-stu-id="792b3-161">Enrichments</span></span>
- <span data-ttu-id="792b3-162">Modelio valdymas</span><span class="sxs-lookup"><span data-stu-id="792b3-162">Model management</span></span>
- <span data-ttu-id="792b3-163">Vaidmenų priskyrimai</span><span class="sxs-lookup"><span data-stu-id="792b3-163">Role assignments</span></span>

<span data-ttu-id="792b3-164">Šie konfigūracijos parametrai *nėra* kopijuojami:</span><span class="sxs-lookup"><span data-stu-id="792b3-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="792b3-165">Klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="792b3-165">Customer profiles.</span></span>
- <span data-ttu-id="792b3-166">Duomenų šaltinio kredencialai.</span><span class="sxs-lookup"><span data-stu-id="792b3-166">Data source credentials.</span></span> <span data-ttu-id="792b3-167">Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.</span><span class="sxs-lookup"><span data-stu-id="792b3-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="792b3-168">Duomenų šaltiniai iš „Common Data Model” aplanko ir „Common Data Service” valdomojo telkinio.</span><span class="sxs-lookup"><span data-stu-id="792b3-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="792b3-169">Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.</span><span class="sxs-lookup"><span data-stu-id="792b3-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="792b3-170">Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka.</span><span class="sxs-lookup"><span data-stu-id="792b3-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="792b3-171">Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.</span><span class="sxs-lookup"><span data-stu-id="792b3-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="792b3-172">Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**.</span><span class="sxs-lookup"><span data-stu-id="792b3-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="792b3-173">Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.</span><span class="sxs-lookup"><span data-stu-id="792b3-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="792b3-174">![Nukopijuoti duomenų šaltiniai](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="792b3-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="792b3-175">Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Suvienodinti**.</span><span class="sxs-lookup"><span data-stu-id="792b3-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="792b3-176">Čia rasite parametrus iš šaltinio aplinkos.</span><span class="sxs-lookup"><span data-stu-id="792b3-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="792b3-177">Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.</span><span class="sxs-lookup"><span data-stu-id="792b3-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="792b3-178">Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.</span><span class="sxs-lookup"><span data-stu-id="792b3-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="792b3-179">Esamos aplinkos redagavimas</span><span class="sxs-lookup"><span data-stu-id="792b3-179">Edit an existing environment</span></span>

<span data-ttu-id="792b3-180">Galite redaguoti kai kurią esamos aplinkos informaciją.</span><span class="sxs-lookup"><span data-stu-id="792b3-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="792b3-181">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="792b3-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="792b3-182">Pasirinkite **Redagavimo** piktogramą.</span><span class="sxs-lookup"><span data-stu-id="792b3-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="792b3-183">Lauke **Redaguoti aplinką** galite atnaujinti aplinkos rodomą **Pavadinimą**, tačiau negalite keisti  **Regiono** arba **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="792b3-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="792b3-184">Jei aplinka sukonfigūruojama saugoti duomenis „Azure Data Lake Storage Gen2“, galite atnaujinti **Paskyros raktą**.</span><span class="sxs-lookup"><span data-stu-id="792b3-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="792b3-185">Tačiau negalite keisti **Paskyros pavadinimo** arba **Konteinerio** pavadinimo.</span><span class="sxs-lookup"><span data-stu-id="792b3-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="792b3-186">Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursais pagrįstą arba prenumeravimu pagrįstą jungtį.</span><span class="sxs-lookup"><span data-stu-id="792b3-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="792b3-187">Jums atnaujinus negalėsite grįžti prie pagrindinės paskyros po naujinimo.</span><span class="sxs-lookup"><span data-stu-id="792b3-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="792b3-188">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="792b3-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="792b3-189">Negalite keisti **Talpyklos** informacijos naujinant jungtį.</span><span class="sxs-lookup"><span data-stu-id="792b3-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="792b3-190">Paleiskite iš naujo esamą aplinką</span><span class="sxs-lookup"><span data-stu-id="792b3-190">Reset an existing environment</span></span>

<span data-ttu-id="792b3-191">Kaip administratorius galite iš naujo nustatyti aplinką į tuščią būseną, jei norite panaikinti visas konfigūracijas ir pašalinti prarytus duomenis.</span><span class="sxs-lookup"><span data-stu-id="792b3-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="792b3-192">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="792b3-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="792b3-193">Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį **...**.</span><span class="sxs-lookup"><span data-stu-id="792b3-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="792b3-194">Pasirinkite parinktį **Nustatyti iš naujo**.</span><span class="sxs-lookup"><span data-stu-id="792b3-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="792b3-195">Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.</span><span class="sxs-lookup"><span data-stu-id="792b3-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="792b3-196">Esamos aplinkos naikinimas (galima tik administratoriams)</span><span class="sxs-lookup"><span data-stu-id="792b3-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="792b3-197">Kaip administratorius galite panaikinti jūsų administruojamą aplinką.</span><span class="sxs-lookup"><span data-stu-id="792b3-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="792b3-198">Programos antraštėje pasirinkite **Aplinkos** parinkėją.</span><span class="sxs-lookup"><span data-stu-id="792b3-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="792b3-199">Pažymėkite aplinką, kurią norite nustatyti iš naujo, ir pažymėkite daugtaškį **...**.</span><span class="sxs-lookup"><span data-stu-id="792b3-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="792b3-200">Pasirinkite parinktį **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="792b3-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="792b3-201">Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="792b3-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]