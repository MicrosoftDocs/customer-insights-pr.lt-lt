---
title: Prisijungti prie objektų „Common Data Service“ valdomame ežere
description: Duomenų importavimas iš „Common Data Service“ valdomo duomenų telkinio.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596969"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="a5d09-103">Prisijungimas prie „Common Data Service“ valdomo duomenų telkinio</span><span class="sxs-lookup"><span data-stu-id="a5d09-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5d09-104">Šiame straipsnyje pateikiama informacija apie tai, kaip esami „Dynamics 365“ klientai gali greitai prisijungti prie analitinių objektų „Common Data Service“ valdomame duomenų telkinyje.</span><span class="sxs-lookup"><span data-stu-id="a5d09-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="a5d09-105">Norėdami tęsti ir peržiūrėti valdomo duomenų telkinio objektų sąrašą, turite būti „Common Data Service“ organizacijos administratorius.</span><span class="sxs-lookup"><span data-stu-id="a5d09-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a5d09-106">Svarbi informacija</span><span class="sxs-lookup"><span data-stu-id="a5d09-106">Important considerations</span></span>

<span data-ttu-id="a5d09-107">Duomenys, saugomi internetinėse tarnybose, pavyzdžiui, „Azure Data Lake Storage“, gali būti saugomi kitoje vietoje, kurioje duomenys yra apdorojami ar saugomi „Dynamics 365 Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="a5d09-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a5d09-108"> Importuodami arba prisijungdami prie duomenų, saugomų internetinėse tarnybose, sutinkate, kad duomenys gali būti perkeliami ir saugomi „Dynamics 365 Customer Insights“.  [Sužinokite daugiau „Microsoft“ patikimumo centre.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a5d09-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="a5d09-109">Prisijungimas prie „Common Data Service” valdomojo telkinio</span><span class="sxs-lookup"><span data-stu-id="a5d09-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="a5d09-110">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a5d09-111">Pasirinkite **Įtraukti duomenų šaltinį**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="a5d09-112">Pasirinkite **Prisijungti prie „Common Data Service”** ir pasirinkite **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="a5d09-113">Įveskite duomenų šaltinio **Pavadinimą** ir pasirinkite **Pirmyn**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="a5d09-114">Pavadinimų rekomendacijos:</span><span class="sxs-lookup"><span data-stu-id="a5d09-114">Name guidelines:</span></span> 
   - <span data-ttu-id="a5d09-115">Pradėti nuo raidės.</span><span class="sxs-lookup"><span data-stu-id="a5d09-115">Start with a letter.</span></span>
   - <span data-ttu-id="a5d09-116">Naudokite tik raides ir skaičius.</span><span class="sxs-lookup"><span data-stu-id="a5d09-116">Use letters and numbers only.</span></span> <span data-ttu-id="a5d09-117">Specialiųjų simbolių ir tarpų neleidžiama įvesti.</span><span class="sxs-lookup"><span data-stu-id="a5d09-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="a5d09-118">Naudokite nuo 3 iki 64 simbolių.</span><span class="sxs-lookup"><span data-stu-id="a5d09-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="a5d09-119">Nurodykite **Serverio adresas**, skirtą jūsų „Common Data Service” organizacijai, ir pasirinkite **Prisijungti**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a5d09-120">![Dialogo langas įvesti „Common Data Service” serverio adresą](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="a5d09-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="a5d09-121">Pasirinkite objektus, kuriuos norite suvartoti iš esančio sąrašo.</span><span class="sxs-lookup"><span data-stu-id="a5d09-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="a5d09-122">Jei kai kurie objektai jau pažymėti, jie gali būti naudojami kitose „Dynamics 365” programose (pvz., „Dynamics 365 Sales Insights” arba „Customer Service Insights”).</span><span class="sxs-lookup"><span data-stu-id="a5d09-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="a5d09-123">Šio pasirinkimo keisti negalima.</span><span class="sxs-lookup"><span data-stu-id="a5d09-123">You can't change the selection.</span></span> <span data-ttu-id="a5d09-124">Šie objektai bus pasiekiami sukūrus duomenų šaltinį.</span><span class="sxs-lookup"><span data-stu-id="a5d09-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a5d09-125">![Dialogo langas, kuriame yra „Common Data Service” organizacijos objektų sąrašas](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a5d09-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="a5d09-126">Įrašykite savo pasirinkimą, kad pradėtumėte sinchronizuoti pažymėtus objektus su „Common Data Service” valdomuoju telkiniu.</span><span class="sxs-lookup"><span data-stu-id="a5d09-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="a5d09-127">Puslapyje **Duomenų šaltiniai** rasite naujai pridėtą ryšį.</span><span class="sxs-lookup"><span data-stu-id="a5d09-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="a5d09-128">Jis bus eilėje atnaujinti ir rodyti objektus, turinčius skaičių 0, kol visi objektai bus susinchronizuoti.</span><span class="sxs-lookup"><span data-stu-id="a5d09-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="a5d09-129">Tik vienas aplinkos duomenų šaltinis gali vienu metu naudoti tą patį „Common Data Service“sutvarkytą ežerą.</span><span class="sxs-lookup"><span data-stu-id="a5d09-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="a5d09-130">„Common Data Service” valdomojo telkinio duomenų šaltinio redagavimas</span><span class="sxs-lookup"><span data-stu-id="a5d09-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="a5d09-131">Sukūrus duomenų šaltinį galite redaguoti tik objekto pasirinkimą.</span><span class="sxs-lookup"><span data-stu-id="a5d09-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="a5d09-132">Pavyzdžiui, jei į „Common Data Service“ buvo įtraukti papildomi objektai ir norite importuoti ir juos.</span><span class="sxs-lookup"><span data-stu-id="a5d09-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="a5d09-133">Norėdami prisijungti prie kitos „Common Data Service” tarnybos, [sukurkite naują duomenų šaltinį](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="a5d09-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="a5d09-134">Publikos įžvalgose, eikite į **Duomenys** > **Duomenų šaltiniai**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a5d09-135">Šalia norimo atnaujinti duomenų šaltinio pasirinkite daugtaškį.</span><span class="sxs-lookup"><span data-stu-id="a5d09-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a5d09-136">Sąraše pasirinkite **Redaguoti**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a5d09-137">Pažymėkite papildomus objektus iš galimų objektų sąrašo ir pasirinkite **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="a5d09-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]