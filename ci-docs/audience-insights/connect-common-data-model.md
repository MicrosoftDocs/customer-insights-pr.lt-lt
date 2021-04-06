---
title: Sujungti „Common Data Model“ duomenis su „Azure Data Lake“ paskyra
description: Dirbkite su „Common Data Model“ duomenimis naudodami „Azure Data Lake Storage“.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596555"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="efe1e-103">Jungimasis prie „Common Data Model” aplanko naudojant „Azure Data Lake” klientą</span><span class="sxs-lookup"><span data-stu-id="efe1e-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="efe1e-104">Šis straipsnis pateikia informaciją, kaip vartoti duomenis iš „Common Data Model“ katalogo naudojant jūsų „Azure Data Lake Storage Gen2“ paskyrą.</span><span class="sxs-lookup"><span data-stu-id="efe1e-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="efe1e-105">Svarbi informacija</span><span class="sxs-lookup"><span data-stu-id="efe1e-105">Important considerations</span></span>

- <span data-ttu-id="efe1e-106">„Azure Data Lake“ duomenys turi atitikti bendrojo duomenų modelio standartą.</span><span class="sxs-lookup"><span data-stu-id="efe1e-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="efe1e-107">Kiti formatai šiuo metu nepalaikomi.</span><span class="sxs-lookup"><span data-stu-id="efe1e-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="efe1e-108">Duomenų suvartojimas palaiko tik „Azure Data Lake“ *Gen2* talpinimo paskyras.</span><span class="sxs-lookup"><span data-stu-id="efe1e-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="efe1e-109">Negalite naudoti „Azure Data Lake“ Gen1 talpinimo paskyrų siekiant suvartoti duomenis.</span><span class="sxs-lookup"><span data-stu-id="efe1e-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="efe1e-110">Norėdami autentifikuoti su „Azure“ pagrindinėmis paslaugomis, įsitikinkite, kad sukonfigūravote jas savo nuomotojuje.</span><span class="sxs-lookup"><span data-stu-id="efe1e-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="efe1e-111">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="efe1e-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="efe1e-112">„Azure Data Lake“, kurį norite prijungti ir iš kurio suvartoti duomenis turi būti tame pačiame „Azure“ regione kaip ir „Dynamics 365 Customer Insights“ aplinka.</span><span class="sxs-lookup"><span data-stu-id="efe1e-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="efe1e-113">Ryšiai su „Common Data Model“ katalogu iš kito „Azure“ regiono duomenų telkinio nėra palaikomi.</span><span class="sxs-lookup"><span data-stu-id="efe1e-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="efe1e-114">Norėdami sužinoti „Azure“ aplinkos regioną, eikite į **Administravimas** > **Sistema** > **Apie** publikos įžvalgose.</span><span class="sxs-lookup"><span data-stu-id="efe1e-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="efe1e-115">Duomenys laikomi interneto paslaugose gali būti laikomi kitoje vietoje, o ne ten, kur duomenys apdorojami ar laikomi „Dynamics 365 Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="efe1e-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="efe1e-116"> Importuodami arba prisijungdami prie duomenų, saugomų internetinėse tarnybose, sutinkate, kad duomenys gali būti perkeliami ir saugomi „Dynamics 365 Customer Insights“.  [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="efe1e-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="efe1e-117">Prisijungti prie „Common Data Model“ aplanko</span><span class="sxs-lookup"><span data-stu-id="efe1e-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="efe1e-118">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="efe1e-119">Pasirinkite **Įtraukti duomenų šaltinį**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="efe1e-120">Pasirinkite **Sujungti su „Common Data Model“ katalogu**, pasirinkite **Pavadinimas** duomenų šaltiniui ir rinkitės **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="efe1e-121">Pavadinimų rekomendacijos:</span><span class="sxs-lookup"><span data-stu-id="efe1e-121">Name guidelines:</span></span> 
   - <span data-ttu-id="efe1e-122">Pradėti nuo raidės.</span><span class="sxs-lookup"><span data-stu-id="efe1e-122">Start with a letter.</span></span>
   - <span data-ttu-id="efe1e-123">Naudokite tik raides ir skaičius.</span><span class="sxs-lookup"><span data-stu-id="efe1e-123">Use letters and numbers only.</span></span> <span data-ttu-id="efe1e-124">Specialiųjų simbolių ir tarpų neleidžiama įvesti.</span><span class="sxs-lookup"><span data-stu-id="efe1e-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="efe1e-125">Naudokite nuo 3 iki 64 simbolių.</span><span class="sxs-lookup"><span data-stu-id="efe1e-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="efe1e-126">Galite pasirinkti tarp naudojimo resursais pagrįstos parinkties ir prenumeravimu pagrįstos parinkties autentifikavimui.</span><span class="sxs-lookup"><span data-stu-id="efe1e-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="efe1e-127">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="efe1e-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="efe1e-128">Įveskite **Talpyklos** informaciją ir pasirinkite **Toliau**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="efe1e-129">![Dialogo langas, skirtas naujai „Azure Data Lake“](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="efe1e-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="efe1e-130">Kad galėtumėte prisijungti ir kurti abonementą, jums reikalingas vienas iš šių vaidmenų : konteinerio arba anksčiau nurodytas saugyklos duomenų šaltinis:</span><span class="sxs-lookup"><span data-stu-id="efe1e-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="efe1e-131">„Storage Blob Data“ skaitytojas</span><span class="sxs-lookup"><span data-stu-id="efe1e-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="efe1e-132">„Storage Blob Data“ savininkas</span><span class="sxs-lookup"><span data-stu-id="efe1e-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="efe1e-133">„Storage Blob Data“ pildytojas</span><span class="sxs-lookup"><span data-stu-id="efe1e-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="efe1e-134">Dialogo lange Pasirinkite aplanką **„Įprastas duomenų modelis“**, pasirinkite failą model.json arba manifest.json, iš kurio norite importuoti duomenis, ir pasirinkite **Kitas**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="efe1e-135">Sąraše nebus rodomas bet koks failas model.json arba jison duomenų šaltinis su kitu aplinkos sąrašu.</span><span class="sxs-lookup"><span data-stu-id="efe1e-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="efe1e-136">Gausite galimų objektų sąrašą pasirinktame model.json arba sertifikato.json faile.</span><span class="sxs-lookup"><span data-stu-id="efe1e-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="efe1e-137">Galite peržiūrėti ir pasirinkti objektus iš galimų objektų sąrašo, o tada pasirinkti **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="efe1e-138">Visi pasirinkti objektai bus vartojami iš naujo duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="efe1e-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="efe1e-139">![Dialogo langas, kuriame pateikiamas sąrašas su objektais iš model.json failo](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="efe1e-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="efe1e-140">Nurodykite, kuriems duomenų objektams norite įjungti duomenų profiliavimą ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="efe1e-141">Duomenų profiliavimas įgalina analizės ir kitas galimybes.</span><span class="sxs-lookup"><span data-stu-id="efe1e-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="efe1e-142">Galite pasirinkti visą objektą, kuris pasirenka visus atributus iš objekto ar pasirinkite tam tikrus jūsų pasirinkimo atributus.</span><span class="sxs-lookup"><span data-stu-id="efe1e-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="efe1e-143">Pagal nutylėjimą, nėra jokio objekto įjungto duomenų profiliavimui.</span><span class="sxs-lookup"><span data-stu-id="efe1e-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="efe1e-144">![Teksto laukelis rodo duomenų profiliavimą](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="efe1e-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="efe1e-145">Įrašius pasirinkimus, atidaromas puslapis **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="efe1e-146">Dabar turėtumėte matyti „Common Data Model“ aplanko ryšį kaip duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="efe1e-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="efe1e-147">Model.json failas arba anonsas.json gali būti susiejantis tik su vienu duomenų šaltinis toje pačioje aplinkoje.</span><span class="sxs-lookup"><span data-stu-id="efe1e-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="efe1e-148">Tačiau tą patį failą model.json arba manifest.json galima naudoti duomenų šaltiniams keliose aplinkose.</span><span class="sxs-lookup"><span data-stu-id="efe1e-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="efe1e-149">Bendrojo duomenų modelio aplanko duomenų šaltinio redagavimas</span><span class="sxs-lookup"><span data-stu-id="efe1e-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="efe1e-150">Galite naujinti prieigos raktą paskyros talpinimui, kurioje yra „Common Data Model“ katalogas.</span><span class="sxs-lookup"><span data-stu-id="efe1e-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="efe1e-151">Taip pat galite pakeisti failą model.json arba manifest.jison.</span><span class="sxs-lookup"><span data-stu-id="efe1e-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="efe1e-152">Jei norite prisijungti prie kito konteinerio iš saugyklos kliento arba keisti saugyklos pavadinimą, [sukurkite naują duomenų šaltinio ryšį](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="efe1e-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="efe1e-153">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="efe1e-154">Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="efe1e-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="efe1e-155">Sąraše pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="efe1e-156">Taip pat galite atnaujinti **Prieigos raktą** ir pasirinkti **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="efe1e-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Esamo duomenų šaltinio prieigos rakto redagavimo ir naujinimo dialogo langas](media/edit-access-key.png)

5. <span data-ttu-id="efe1e-158">Pasirinktinai galite naujinti iš paskyros pagrindinių pagrįstų jungčių į resursais pagrįstą ar prenumeravimu pagrįstą jungtį.</span><span class="sxs-lookup"><span data-stu-id="efe1e-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="efe1e-159">Dėl daugiau informacijos, žr. [Sujungti publikos įžvalgas ir „Azure Data Lake Storage Gen2“ paskyrą „Azure“ pagrindinės paslaugas publikos įžvalgoms](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="efe1e-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="efe1e-160">Negalite keisti **Talpyklos** informacijos naujinant jungtį.</span><span class="sxs-lookup"><span data-stu-id="efe1e-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Dialogo langas, skirtas įvesti informacijai apie „Azure Data Lake” ryšį su esamu saugyklos abonementu įvesti](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="efe1e-162">Kad galėtumėte prisijungti ir kurti abonementą, jums reikalingas vienas iš šių vaidmenų : konteinerio arba anksčiau nurodytas saugyklos duomenų šaltinis:</span><span class="sxs-lookup"><span data-stu-id="efe1e-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="efe1e-163">„Storage Blob Data“ skaitytojas</span><span class="sxs-lookup"><span data-stu-id="efe1e-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="efe1e-164">„Storage Blob Data“ savininkas</span><span class="sxs-lookup"><span data-stu-id="efe1e-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="efe1e-165">„Storage Blob Data“ pildytojas</span><span class="sxs-lookup"><span data-stu-id="efe1e-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="efe1e-166">Galite pasirinkti kitą model.json arba atskirai.json failą su skirtingu objektų iš konteinerio objektų rinkiniu.</span><span class="sxs-lookup"><span data-stu-id="efe1e-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="efe1e-167">Pasirinktinai, galite pasirinkti papildomus vartojamus objektus.</span><span class="sxs-lookup"><span data-stu-id="efe1e-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="efe1e-168">Jei nėra priklausomybių, taip pat galite pašalinti jau pažymėtus objektus.</span><span class="sxs-lookup"><span data-stu-id="efe1e-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="efe1e-169">Jei yra esamo modelio.json arba manifest.json failo ir objektų rinkinio priklausomybių, bus rodomas klaidos pranešimas, kuriame negalite pažymėti kito modelio.json arba manifest.json failo.</span><span class="sxs-lookup"><span data-stu-id="efe1e-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="efe1e-170">Pašalinkite šias priklausomybes prieš keisdami failą model.json arba manifest.json arba sukurkite naują duomenų šaltinį naudodami failą model.json arba manifest.json, kad išvengtumėte priklausomybių pašalinimo.</span><span class="sxs-lookup"><span data-stu-id="efe1e-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="efe1e-171">Pasirinktinai, galite pasirinkti papildomus atributus ar objektus, kuriems bus įjungtas duomenų profiliavimas ar išjungti jau pasirinktus.</span><span class="sxs-lookup"><span data-stu-id="efe1e-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]