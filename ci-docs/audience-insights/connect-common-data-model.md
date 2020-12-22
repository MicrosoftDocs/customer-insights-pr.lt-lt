---
title: Sujungti „Common Data Model“ duomenis su „Azure Data Lake“ paskyra
description: Dirbkite su „Common Data Model“ duomenimis naudodami „Azure Data Lake Storage“.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643468"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="a1f10-103">Jungimasis prie „Common Data Model” aplanko naudojant „Azure Data Lake” klientą</span><span class="sxs-lookup"><span data-stu-id="a1f10-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="a1f10-104">Šis straipsnis pateikia informaciją, kaip vartoti duomenis iš „Common Data Model“ katalogo naudojant jūsų „Azure Data Lake Storage Gen2“ paskyrą.</span><span class="sxs-lookup"><span data-stu-id="a1f10-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a1f10-105">Svarbi informacija</span><span class="sxs-lookup"><span data-stu-id="a1f10-105">Important considerations</span></span>

- <span data-ttu-id="a1f10-106">„Azure Data Lake“ duomenys turi atitikti bendrojo duomenų modelio standartą.</span><span class="sxs-lookup"><span data-stu-id="a1f10-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="a1f10-107">Kiti formatai šiuo metu nepalaikomi.</span><span class="sxs-lookup"><span data-stu-id="a1f10-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="a1f10-108">Duomenų suvartojimas palaiko tik „Azure Data Lake“ *Gen2* talpinimo paskyras.</span><span class="sxs-lookup"><span data-stu-id="a1f10-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="a1f10-109">Negalite naudoti „Azure Data Lake“ Gen1 talpinimo paskyrų siekiant suvartoti duomenis.</span><span class="sxs-lookup"><span data-stu-id="a1f10-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="a1f10-110">Norėdami autentifikuoti su „Azure“ pagrindinėmis paslaugomis, įsitikinkite, kad sukonfigūravote jas savo nuomotojuje.</span><span class="sxs-lookup"><span data-stu-id="a1f10-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="a1f10-111">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a1f10-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="a1f10-112">„Azure Data Lake“, kurį norite prijungti ir iš kurio suvartoti duomenis turi būti tame pačiame „Azure“ regione kaip ir „Dynamics 365 Customer Insights“ aplinka.</span><span class="sxs-lookup"><span data-stu-id="a1f10-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="a1f10-113">Ryšiai su „Common Data Model“ katalogu iš „Data Lake“ kitame „Azure“ regione nėra palaikomi.</span><span class="sxs-lookup"><span data-stu-id="a1f10-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="a1f10-114">Norėdami sužinoti „Azure“ aplinkos regioną, eikite į **Administravimas** > **Sistema** > **Apie** publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="a1f10-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="a1f10-115">Duomenys laikomi interneto paslaugose gali būti laikomi kitoje vietoje, o ne ten, kur duomenys apdorojami ar laikomi „Dynamics 365 Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="a1f10-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a1f10-116">Importuodami arba prisijungdami prie duomenų, saugomų internetinėse tarnybose, sutinkate, kad duomenys gali būti perkeliami ir saugomi „Dynamics 365 Customer Insights“.  [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a1f10-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="a1f10-117">Prisijungti prie „Common Data Model“ aplanko</span><span class="sxs-lookup"><span data-stu-id="a1f10-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="a1f10-118">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="a1f10-119">Pasirinkite **Įtraukti duomenų šaltinį**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="a1f10-120">Pasirinkite **Sujungti su „Common Data Model“ katalogu**, pasirinkite **Pavadinimas** duomenų šaltiniui ir rinkitės **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="a1f10-121">Galite pasirinkti tarp naudojimo resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui.</span><span class="sxs-lookup"><span data-stu-id="a1f10-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="a1f10-122">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a1f10-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a1f10-123">Įveskite **Talpyklos** informaciją ir pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1f10-124">![Dialogo lango lauke įveskite prisijungimo prie „Azure Data Lake“ informaciją](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="a1f10-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="a1f10-125">**Pasirinkite „Common Data Model“ katalogą** teksto laukelyje pasirinkite model.json failą, iš kurio importuosite duomenis ir rinkitės **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="a1f10-126">Bet kuris model.json failas susietas su kitu duomenų šaltiniu aplinkoje nebus rodoma sąraše.</span><span class="sxs-lookup"><span data-stu-id="a1f10-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="a1f10-127">Gausite esamų objektų sąrašą pasirinktame model.json faile.</span><span class="sxs-lookup"><span data-stu-id="a1f10-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="a1f10-128">Galite peržiūrėti ir pasirinkti objektus iš galimų objektų sąrašo, o tada pasirinkti **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="a1f10-129">Visi pasirinkti objektai bus vartojami iš naujo duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="a1f10-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1f10-130">![Dialogo langas, kuriame pateikiamas sąrašas su objektais iš model.json failo](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a1f10-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="a1f10-131">Nurodykite, kuriems duomenų objektams norite įjungti duomenų profiliavimą ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="a1f10-132">Duomenų profiliavimas įgalina analizės ir kitas galimybes.</span><span class="sxs-lookup"><span data-stu-id="a1f10-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="a1f10-133">Galite pasirinkti visą objektą, kuris pasirenka visus atributus iš objekto ar pasirinkite tam tikrus jūsų pasirinkimo atributus.</span><span class="sxs-lookup"><span data-stu-id="a1f10-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="a1f10-134">Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.</span><span class="sxs-lookup"><span data-stu-id="a1f10-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1f10-135">![Teksto laukelis rodo duomenų profiliavimą](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a1f10-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="a1f10-136">Įrašius pasirinkimus, atidaromas puslapis **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="a1f10-137">Dabar turėtumėte matyti „Common Data Model“ aplanko ryšį kaip duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="a1f10-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="a1f10-138">Model.josn failas gali būti susietas su vienu duomenų šaltiniu vienoje aplinkoje.</span><span class="sxs-lookup"><span data-stu-id="a1f10-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="a1f10-139">Nepaisant to, tas pats model.json failas gali būti naudojamas duomenų šaltiniams keliose aplinkose.</span><span class="sxs-lookup"><span data-stu-id="a1f10-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="a1f10-140">Bendrojo duomenų modelio aplanko duomenų šaltinio redagavimas</span><span class="sxs-lookup"><span data-stu-id="a1f10-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="a1f10-141">Galite naujinti prieigos raktą paskyros talpinimui, kurioje yra „Common Data Model“ katalogas.</span><span class="sxs-lookup"><span data-stu-id="a1f10-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="a1f10-142">Taip pat galite keisti model.json failą.</span><span class="sxs-lookup"><span data-stu-id="a1f10-142">You may also change the model.json file.</span></span> <span data-ttu-id="a1f10-143">Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="a1f10-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="a1f10-144">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a1f10-145">Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="a1f10-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a1f10-146">Sąraše pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a1f10-147">Taip pat galite atnaujinti **Prieigos raktą** ir pasirinkti **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="a1f10-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Esamo duomenų šaltinio prieigos rakto redagavimo ir naujinimo dialogo langas](media/edit-access-key.png)

5. <span data-ttu-id="a1f10-149">Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursu pagrįstą ar prenumeravimu pagrįstą jungtį.</span><span class="sxs-lookup"><span data-stu-id="a1f10-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="a1f10-150">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="a1f10-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="a1f10-151">Negalite keisti **Talpyklos** informacijos naujinant jungtį.</span><span class="sxs-lookup"><span data-stu-id="a1f10-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a1f10-152">![Dialogo lango lauke įveskite prisijungimo prie „Azure Data Lake“ informaciją](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="a1f10-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="a1f10-153">Taip pat galite pasirinkti kitą model.json failą su kitu objektų rinkiniu iš konteinerio.</span><span class="sxs-lookup"><span data-stu-id="a1f10-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="a1f10-154">Pasirinktinai, galite pasirinkti papildomus vartojamus objektus.</span><span class="sxs-lookup"><span data-stu-id="a1f10-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="a1f10-155">Jei nėra priklausomybių, taip pat galite pašalinti jau pažymėtus objektus.</span><span class="sxs-lookup"><span data-stu-id="a1f10-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a1f10-156">Jei esamame model.json faile yra priklausomybių ir objektų rinkinys, pasirodys klaidos pranešimas ir jūs negalėsite pasirinkti kito model.json failo.</span><span class="sxs-lookup"><span data-stu-id="a1f10-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="a1f10-157">Prieš keisdami model.json failą pašalinkite priklausomybes arba sukurkite naują duomenų šaltinį su model.json failu, kurį norite naudoti, kad nereikėtų šalinti priklausomybių.</span><span class="sxs-lookup"><span data-stu-id="a1f10-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="a1f10-158">Pasirinktinai, galite pasirinkti papildomus atributus ar objektus, kuriems bus įjungtas duomenų profiliavimas ar išjungti jau pasirinktus.</span><span class="sxs-lookup"><span data-stu-id="a1f10-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
