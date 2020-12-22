---
title: Aplinkų kūrimas ir valdymas
description: Sužinokite, kaip prisijungti prie paslaugų ir kaip valdyti aplinkas.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644143"
---
# <a name="manage-environments"></a><span data-ttu-id="37d0c-103">Aplinkų valdymas</span><span class="sxs-lookup"><span data-stu-id="37d0c-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="37d0c-104">Šis straipsnis paaiškina, kaip sukurti naują organizaciją ir kaip aprūpinti aplinką.</span><span class="sxs-lookup"><span data-stu-id="37d0c-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="37d0c-105">Prisijunkite ir sukurkite organizaciją</span><span class="sxs-lookup"><span data-stu-id="37d0c-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="37d0c-106">Atidarykite svetainę [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="37d0c-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="37d0c-107">Pasirinkite **Darbo pradžia**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="37d0c-108">pasirinkite pageidaujamą prisijungimo scenarijų ir pasirinkite atitinkamą nuorodą.</span><span class="sxs-lookup"><span data-stu-id="37d0c-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="37d0c-109">Sutikite su sąlygomis ir pasirinkite **Tęsti**, kad pradėtumėte kurti organizaciją.</span><span class="sxs-lookup"><span data-stu-id="37d0c-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="37d0c-110">Sukūrus aplinką jus nukreips į [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="37d0c-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="37d0c-111">Norėdami ištirti programą, naudokite demonstracinę aplinką arba galite sukurti naują aplinką atlikdami kitame skyriuje nurodytus veiksmus.</span><span class="sxs-lookup"><span data-stu-id="37d0c-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="37d0c-112">Nurodę aplinkos parametrus, pasirinkite **Kurti**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="37d0c-113">Būsite prijungti po to, kai aplinka bus sėkmingai sukurta.</span><span class="sxs-lookup"><span data-stu-id="37d0c-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="37d0c-114">Aplinkos kūrimas esamoje organizacijoje</span><span class="sxs-lookup"><span data-stu-id="37d0c-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="37d0c-115">Yra du naujos aplinkos kūrimo būdai.</span><span class="sxs-lookup"><span data-stu-id="37d0c-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="37d0c-116">Galite nurodyti visiškai naują konfigūraciją arba galite kopijuoti tam tikrus konfigūracijos parametrus iš esamos aplinkos.</span><span class="sxs-lookup"><span data-stu-id="37d0c-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="37d0c-117">Norėdami sukurti aplinką:</span><span class="sxs-lookup"><span data-stu-id="37d0c-117">To create an environment:</span></span>

1. <span data-ttu-id="37d0c-118">Pasirinkite simbolį **Parametrai** programėlės antraštėje.</span><span class="sxs-lookup"><span data-stu-id="37d0c-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="37d0c-119">Pasirinkite **Nauja aplinka**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="37d0c-120">![Aplinkų parametrai](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="37d0c-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="37d0c-121">Dialogo lange **Naujos aplinkos kūrimas** pasirinkite **Nauja aplinka**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="37d0c-122">Jei norite [kopijuoti duomenis iš esamos aplinkos](#additional-considerations-for-copy-configuration-preview), pasirinkite **Kopijuoti iš esamos aplinkos**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="37d0c-123">Matysite visų jūsų organizacijoje pasiekiamų aplinkų sąrašą, iš kurių galima kopijuoti duomenis.</span><span class="sxs-lookup"><span data-stu-id="37d0c-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="37d0c-124">Nurodykite toliau pateiktą informaciją.</span><span class="sxs-lookup"><span data-stu-id="37d0c-124">Provide the following details:</span></span>
   - <span data-ttu-id="37d0c-125">**Pavadinimas**: Šios aplinkos pavadinimas.</span><span class="sxs-lookup"><span data-stu-id="37d0c-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="37d0c-126">Šis laukas jau užpildytas, jei kopijuojate esamą aplinką, tačiau jį galite keisti.</span><span class="sxs-lookup"><span data-stu-id="37d0c-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="37d0c-127">**Sritis**: sritis, kurioje įdiegta ir teikiama ši paslauga.</span><span class="sxs-lookup"><span data-stu-id="37d0c-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="37d0c-128">**Tipas**: pasirinkite, ar norite kurti gamybos ar smėlio dėžės aplinką.</span><span class="sxs-lookup"><span data-stu-id="37d0c-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="37d0c-129">Pasirinktinai galite spustelėti **Išplėstiniai parametrai**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="37d0c-130">**Įrašyti visus duomenis į**: nurodo, kur norite saugoti išvesties duomenis, sugeneruotus iš „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="37d0c-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="37d0c-131">Galimos dvi parinktys: **„Customer Insights“ saugykla** („Azure Data Lake“ valdomas „Customer Insights“ komandos) ir **Azure Data Lake Storage Gen2** (jūsų nuosava „Azure Data Lake Storage“).</span><span class="sxs-lookup"><span data-stu-id="37d0c-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="37d0c-132">Pagal numatytuosius parametrus, pasirenkama „Customer Insights“ saugykla.</span><span class="sxs-lookup"><span data-stu-id="37d0c-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="37d0c-133">Įrašydami duomenis į „Azure Data Lake Storage, sutinkate, kad jūsų duomenys būtų perkelti ir saugomi konkrečiai „Azure“ paskyrai paskirtoje geografinėje vietovėje , kuri gali skirtis nuo vietovės, kurioje saugomi „Dynamics 365 Customer Insights“ duomenys.</span><span class="sxs-lookup"><span data-stu-id="37d0c-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="37d0c-134">Sužinokite daugiau „Microsoft“ patikimumo centre.</span><span class="sxs-lookup"><span data-stu-id="37d0c-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="37d0c-135">Šiuo metu surinkti objektai visada saugomi „Customer Insights“ valdomame „Data Lake“.</span><span class="sxs-lookup"><span data-stu-id="37d0c-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="37d0c-136">Palaikomte tik „Azure Data Lake Gen2“ talpinimo paskyras iš to paties „Azure“ regiono, kurį pasirinkote kurdami aplinką.</span><span class="sxs-lookup"><span data-stu-id="37d0c-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="37d0c-137">Palaikome tik „Azure Data Lake Gen2“ saugyklų paskyras, kurioms įgalinta hierarchinio pavadinimo (HNS) funkcija.</span><span class="sxs-lookup"><span data-stu-id="37d0c-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="37d0c-138">„Azure Data Lake Storage Gen2“ parinkčiai galite pasirinkti tarp resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui.</span><span class="sxs-lookup"><span data-stu-id="37d0c-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="37d0c-139">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="37d0c-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="37d0c-140">**Talpykla** pavadinimas negali būti keičiamas ir bus „klientoįžvalgos“.</span><span class="sxs-lookup"><span data-stu-id="37d0c-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="37d0c-141">Jei norite naudoti [prognozes](predictions.md), įvesktie „Common Data Service“ elemento URL **Serverio adreso** laukelyje skyriuje **Naudoti prognozes**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="37d0c-142">Jums vykdant procesus, tokius kaip duomenų suvartojimas ar segmento sukūrimas, atitinkantys katalogai bus sukuriami talpinimo paskyroje, kurią nurodėte prieš tai.</span><span class="sxs-lookup"><span data-stu-id="37d0c-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="37d0c-143">Duomenų failai ir model.json failai bus sukurti ir įtraukti į atitinkamus poaplankius pagal jūsų vykdytą procesą.</span><span class="sxs-lookup"><span data-stu-id="37d0c-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="37d0c-144">Jei sukuriate keletą „Customer Insights“ aplinkų ir pasirenkate įrašyti išvesties objektus iš tų aplinkų į jūsų talpinimo paskyrą, atskiri katalogai bus sukurti kiekvienai aplinka su ci_<environmentid> talpykloje.</span><span class="sxs-lookup"><span data-stu-id="37d0c-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="37d0c-145">Papildomos pastabos dėl kopijavimo konfigūracijos (peržiūros versija)</span><span class="sxs-lookup"><span data-stu-id="37d0c-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="37d0c-146">Kopijuojami šie konfigūracijos parametrai:</span><span class="sxs-lookup"><span data-stu-id="37d0c-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="37d0c-147">Funkcijų konfigūracijos</span><span class="sxs-lookup"><span data-stu-id="37d0c-147">Feature configurations</span></span>
- <span data-ttu-id="37d0c-148">Gauti / importuoti duomenų šaltiniai</span><span class="sxs-lookup"><span data-stu-id="37d0c-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="37d0c-149">Duomenų sujungimo (susiejimo, atitikimo, suliejimo) konfigūracija</span><span class="sxs-lookup"><span data-stu-id="37d0c-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="37d0c-150">Segmentai</span><span class="sxs-lookup"><span data-stu-id="37d0c-150">Segments</span></span>
- <span data-ttu-id="37d0c-151">Matavimai</span><span class="sxs-lookup"><span data-stu-id="37d0c-151">Measures</span></span>
- <span data-ttu-id="37d0c-152">Ryšiai</span><span class="sxs-lookup"><span data-stu-id="37d0c-152">Relationships</span></span>
- <span data-ttu-id="37d0c-153">Veiklos</span><span class="sxs-lookup"><span data-stu-id="37d0c-153">Activities</span></span>
- <span data-ttu-id="37d0c-154">Paieškos ir filtravimo rodyklė</span><span class="sxs-lookup"><span data-stu-id="37d0c-154">Search & filter Index</span></span>
- <span data-ttu-id="37d0c-155">Eksportavimo paskirties vietos</span><span class="sxs-lookup"><span data-stu-id="37d0c-155">Export destinations</span></span>
- <span data-ttu-id="37d0c-156">Suplanuotas atnaujinimas</span><span class="sxs-lookup"><span data-stu-id="37d0c-156">Scheduled refresh</span></span>
- <span data-ttu-id="37d0c-157">Duomenų papildymai</span><span class="sxs-lookup"><span data-stu-id="37d0c-157">Enrichments</span></span>
- <span data-ttu-id="37d0c-158">Modelio valdymas</span><span class="sxs-lookup"><span data-stu-id="37d0c-158">Model management</span></span>
- <span data-ttu-id="37d0c-159">Vaidmenų priskyrimai</span><span class="sxs-lookup"><span data-stu-id="37d0c-159">Role assignments</span></span>

<span data-ttu-id="37d0c-160">Šie konfigūracijos parametrai *nėra* kopijuojami:</span><span class="sxs-lookup"><span data-stu-id="37d0c-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="37d0c-161">Klientų profiliai.</span><span class="sxs-lookup"><span data-stu-id="37d0c-161">Customer profiles.</span></span>
- <span data-ttu-id="37d0c-162">Duomenų šaltinio kredencialai.</span><span class="sxs-lookup"><span data-stu-id="37d0c-162">Data source credentials.</span></span> <span data-ttu-id="37d0c-163">Turėsite pateikti kiekvieno duomenų šaltinio kredencialus ir rankiniu būdu atnaujinti duomenų šaltinius.</span><span class="sxs-lookup"><span data-stu-id="37d0c-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="37d0c-164">Duomenų šaltiniai iš „Common Data Model” aplanko ir „Common Data Service” valdomojo telkinio.</span><span class="sxs-lookup"><span data-stu-id="37d0c-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="37d0c-165">Šiuos duomenų šaltinius turėsite kurti rankiniu būdu tuo pačiu pavadinimu kaip ir šaltinio aplinka.</span><span class="sxs-lookup"><span data-stu-id="37d0c-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="37d0c-166">Kai kopijuojate aplinką, pamatysite patvirtinimo pranešimą, kad sukurta nauja aplinka.</span><span class="sxs-lookup"><span data-stu-id="37d0c-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="37d0c-167">Pasirinkite **Eiti į duomenų šaltinius**, kad peržiūrėtumėte duomenų šaltinių sąrašą.</span><span class="sxs-lookup"><span data-stu-id="37d0c-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="37d0c-168">Visi duomenų šaltiniai rodys būseną **Reikia kredencialų**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="37d0c-169">Redaguokite duomenų šaltinius ir įveskite kredencialus, kad juos atnaujintumėte.</span><span class="sxs-lookup"><span data-stu-id="37d0c-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37d0c-170">![Nukopijuoti suomenų šaltiniai](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="37d0c-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="37d0c-171">Atnaujinę duomenų šaltinius, eikite į **Duomenys** > **Vienyti**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="37d0c-172">Čia rasite parametrus iš šaltinio aplinkos.</span><span class="sxs-lookup"><span data-stu-id="37d0c-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="37d0c-173">Jei reikia, redaguokite juos arba pasirinkite **Vykdyti**, kad pradėtumėte duomenų sujungimo procesą ir sukurtumėte bendrąjį kliento objektą.</span><span class="sxs-lookup"><span data-stu-id="37d0c-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="37d0c-174">Kai duomenų sujungimas baigtas, eikite į **Priemonės** ir **Segmentai**, kad jie būtų atnaujinti.</span><span class="sxs-lookup"><span data-stu-id="37d0c-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="37d0c-175">Esamos aplinkos redagavimas</span><span class="sxs-lookup"><span data-stu-id="37d0c-175">Edit an existing environment</span></span>

<span data-ttu-id="37d0c-176">Galite redaguoti kai kurią esamos aplinkos informaciją.</span><span class="sxs-lookup"><span data-stu-id="37d0c-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="37d0c-177">Pasirinkite **Administravimas** > **Sistema** > **Apie**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="37d0c-178">Pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-178">Select **Edit**.</span></span>

3. <span data-ttu-id="37d0c-179">Galite atnaujinti aplinkos **Rodomą pavadinimą**, tačiau negalite keisti **Regiono** arba **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="37d0c-180">Jei aplinka sukonfigūruojama saugoti duomenis „Azure Data Lake Storage Gen2“, galite atnaujinti **Paskyros raktą**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="37d0c-181">Tačiau negalite keisti **Paskyros pavadinimo** arba **Konteinerio** pavadinimo.</span><span class="sxs-lookup"><span data-stu-id="37d0c-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="37d0c-182">Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursu pagrįstą ar prenumeravimu pagrįstą jungtį.</span><span class="sxs-lookup"><span data-stu-id="37d0c-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="37d0c-183">Jums atnaujinus negalėsite grįžti prie pagrindinės paskyros po naujinimo.</span><span class="sxs-lookup"><span data-stu-id="37d0c-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="37d0c-184">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="37d0c-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="37d0c-185">Negalite keisti **Talpyklos** informacijos naujinant jungtį.</span><span class="sxs-lookup"><span data-stu-id="37d0c-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="37d0c-186">Paleiskite iš naujo esamą aplinką</span><span class="sxs-lookup"><span data-stu-id="37d0c-186">Reset an existing environment</span></span>

<span data-ttu-id="37d0c-187">Galite paleisti iš naujo aplinką į tuščią būklę, jei norite panaikinti visus konfigūravimus ir pašalinti suvartotus duomenis.</span><span class="sxs-lookup"><span data-stu-id="37d0c-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="37d0c-188">Pasirinkite **Administravimas** > **Sistema** > **Apie**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="37d0c-189">Pasirinkite **Paleisti iš naujo**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="37d0c-190">Šio panaikinimo patvirtinimui, įveskite aplinkos pavadinimą ir pasirinkite **Paleisti iš naujo**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="37d0c-191">Esamos aplinkos naikinimas</span><span class="sxs-lookup"><span data-stu-id="37d0c-191">Delete an existing environment</span></span>

1. <span data-ttu-id="37d0c-192">Pasirinkite **Administravimas** > **Sistema** > **Apie**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="37d0c-193">Pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-193">Select **Delete**.</span></span>

1. <span data-ttu-id="37d0c-194">Norėdami patvirtinti panaikinimą, įveskite aplinkos pavadinimą ir pasirinkite **Naikinti**.</span><span class="sxs-lookup"><span data-stu-id="37d0c-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
