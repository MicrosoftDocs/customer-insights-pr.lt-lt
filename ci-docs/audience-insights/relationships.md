---
title: Ryšiai tarp objektų ir objektų kelių
description: Sukurkite ir valdykite ryšius tarp objektų daugeliui duomenų šaltinių.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269891"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="65326-103">Objektų ryšiai</span><span class="sxs-lookup"><span data-stu-id="65326-103">Relationships between entities</span></span>

<span data-ttu-id="65326-104">Ryšiai padeda susieti objektus ir generuoti duomenų grafikus, kai objektų duomenys dalijasi bendru identifikatoriumi (išoriniu raktu), kuriam galima priskirti nuorodą iš vieno objekto į kitą.</span><span class="sxs-lookup"><span data-stu-id="65326-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="65326-105">Susieti objektai leidžia apibrėžti segmentus ir matus, remiantis keliais duomenų šaltiniais.</span><span class="sxs-lookup"><span data-stu-id="65326-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="65326-106">Esama dviejų tipų ryšių.</span><span class="sxs-lookup"><span data-stu-id="65326-106">There are two types of relationships.</span></span> <span data-ttu-id="65326-107">Neredaguojami sistemos ryšiai, kurie sukuriami automatiškai, ir vartotojų sukurti ir sukonfigūruoti pasirinktiniai ryšiai.</span><span class="sxs-lookup"><span data-stu-id="65326-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="65326-108">Atliekant sutapdinimo ir suliejimo procesus, sistemos ryšiai sukuriami be vartotojo įsikišimo, naudojant išmanųjį sutapdinimą.</span><span class="sxs-lookup"><span data-stu-id="65326-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="65326-109">Šie ryšiai padeda susieti kliento profilį su kitais atitinkamais objektų įrašais.</span><span class="sxs-lookup"><span data-stu-id="65326-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="65326-110">Toliau pateikiamoje diagramoje vaizduojama, kaip sukuriami trys sistemos ryšiai, kai kliento objektas yra sutapdintas su papildomais objektais, kad būtų sukurtas galutinis kliento profilio objektas.</span><span class="sxs-lookup"><span data-stu-id="65326-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="65326-111">![Ryšių sukūrimas](media/relationships-entities-merge.png "Ryšio sukūrimas")</span><span class="sxs-lookup"><span data-stu-id="65326-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="65326-112">***CustomerToContact* ryšys** buvo sukurtas tarp kliento objekto ir kontakto objekto.</span><span class="sxs-lookup"><span data-stu-id="65326-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="65326-113">Kliento objekto rakto laukas **Contact_contactId** susiejamas su kliento objekto rakto lauku **contactId**.</span><span class="sxs-lookup"><span data-stu-id="65326-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="65326-114">***CustomerToAccount* ryšys** buvo sukurtas tarp kliento objekto ir abonemento objekto.</span><span class="sxs-lookup"><span data-stu-id="65326-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="65326-115">Kliento objekto rakto laukas **Account_accountId** susiejamas su abonemento objekto rakto lauku **accountId**.</span><span class="sxs-lookup"><span data-stu-id="65326-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="65326-116">***CustomerToWebAccount* ryšys** buvo sukurtas tarp kliento objekto ir „WebAccount“ objekto.</span><span class="sxs-lookup"><span data-stu-id="65326-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="65326-117">Kliento objekto rakto laukas **WebAccount_webaccountId** susiejamas su „WebAccount“ objekto rakto lauku **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="65326-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="65326-118">Ryšio kūrimas</span><span class="sxs-lookup"><span data-stu-id="65326-118">Create a relationship</span></span>

<span data-ttu-id="65326-119">Puslapyje **Ryšiai** apibrėžkite pasirinktinius ryšius.</span><span class="sxs-lookup"><span data-stu-id="65326-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="65326-120">Kiekvieną ryšį sudaro šaltinio objektas (objektas, turintis išorinį raktą) ir tikslo objektas (objektas, į kurį nurodo šaltinio objekto išorinis raktas).</span><span class="sxs-lookup"><span data-stu-id="65326-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="65326-121">Publikos įžvalgose, eikite į **Duomenys** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="65326-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="65326-122">Pasirinkite **Naujas ryšys**.</span><span class="sxs-lookup"><span data-stu-id="65326-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="65326-123">Srityje **Įtraukti ryšį** nurodykite tolesnę informaciją:</span><span class="sxs-lookup"><span data-stu-id="65326-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65326-124">![Įveskite išsamią ryšio informaciją](media/relationships-add.png "Ryšio detalių įvedimas")</span><span class="sxs-lookup"><span data-stu-id="65326-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="65326-125">**Ryšio pavadinimas**: pavadinimas, atspindintis ryšio paskirtį (pavyzdžiui, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="65326-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="65326-126">**Aprašymas**: ryšio aprašymas.</span><span class="sxs-lookup"><span data-stu-id="65326-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="65326-127">**Šaltinio objektas**: pasirinkite objektą, kuris ryšyje naudojamas kaip šaltinis (pavyzdžiui, „WebLog“).</span><span class="sxs-lookup"><span data-stu-id="65326-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="65326-128">**Svarba**: pasirinkite šaltinio objekto įrašų svarbą.</span><span class="sxs-lookup"><span data-stu-id="65326-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="65326-129">Pavyzdžiui, „daug“ reiškia, kad su vienu „WebAccount“ yra susieti keli „Weblog“ įrašai.</span><span class="sxs-lookup"><span data-stu-id="65326-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="65326-130">**Šaltinio rakto laukas**: šaltinio objekte jis nurodo išorinio rakto lauką.</span><span class="sxs-lookup"><span data-stu-id="65326-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="65326-131">Pavyzdžiui, „WebLog“ turi išorinio rakto lauką **accountId**.</span><span class="sxs-lookup"><span data-stu-id="65326-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="65326-132">**Tikslo objektas**: pasirinkite objektą, kuris ryšyje naudojamas kaip tikslas (pavyzdžiui, „WebAccount“).</span><span class="sxs-lookup"><span data-stu-id="65326-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="65326-133">**Tikslo svarba**: pasirinkite tikslo objekto įrašų svarbą.</span><span class="sxs-lookup"><span data-stu-id="65326-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="65326-134">Pavyzdžiui, „vienas“ reiškia, kad su vienu „WebAccount“ yra susieti keli „Weblog“ įrašai.</span><span class="sxs-lookup"><span data-stu-id="65326-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="65326-135">**Tikslo rakto laukas**: šiame lauke pateikiamas tikslo objekto rakto laukas.</span><span class="sxs-lookup"><span data-stu-id="65326-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="65326-136">Pavyzdžiui, „WebAccount“ turi rakto lauką **accountId**.</span><span class="sxs-lookup"><span data-stu-id="65326-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="65326-137">Palaikomi tik „daugelis su vienu“ ir „vienas su vienu“ tipo ryšiai.</span><span class="sxs-lookup"><span data-stu-id="65326-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="65326-138">Ryšius „daug su daug“ galima sukurti panaudojus du „daug su vienu“ ryšius ir nuorodos objektą (objektą, kuris naudojamas sujungti šaltinio objektą ir tikslo objektą).</span><span class="sxs-lookup"><span data-stu-id="65326-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="65326-139">Ryšio pašalinimas</span><span class="sxs-lookup"><span data-stu-id="65326-139">Delete a relationship</span></span>

1. <span data-ttu-id="65326-140">Publikos įžvalgose, eikite į **Duomenys** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="65326-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="65326-141">Pažymėkite ryšių, kuriuos norite pašalinti, žymės langelius.</span><span class="sxs-lookup"><span data-stu-id="65326-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="65326-142">Lentelės **Ryšiai** viršuje pasirinkite **Pašalinti**.</span><span class="sxs-lookup"><span data-stu-id="65326-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="65326-143">Patvirtinkite šį naikinimą.</span><span class="sxs-lookup"><span data-stu-id="65326-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="65326-144">Kitas veiksmas</span><span class="sxs-lookup"><span data-stu-id="65326-144">Next step</span></span>

<span data-ttu-id="65326-145">Sistema ir pasirinktiniai ryšiai naudojami segmentams kurti, remiantis keliais duomenų šaltiniais, kurie nebėra izoliuoti.</span><span class="sxs-lookup"><span data-stu-id="65326-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="65326-146">Daugiau informacijos galite rasti čia [segmentas](segments.md).</span><span class="sxs-lookup"><span data-stu-id="65326-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]