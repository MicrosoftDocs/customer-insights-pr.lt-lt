---
title: Ryšiai tarp objektų ir objektų kelių
description: Sukurkite ir valdykite ryšius tarp objektų daugeliui duomenų šaltinių.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171174"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="78856-103">Objektų ryšiai</span><span class="sxs-lookup"><span data-stu-id="78856-103">Relationships between entities</span></span>

<span data-ttu-id="78856-104">Ryšiai jungia objektus ir apibrėžia jūsų duomenų grafą, kai objektai turi bendrą identifikatorių – išorinį raktą.</span><span class="sxs-lookup"><span data-stu-id="78856-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="78856-105">Šis išorinis raktas gali būti nurodomas iš vieno objekto į kitą.</span><span class="sxs-lookup"><span data-stu-id="78856-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="78856-106">Sujungti objektai įgalina segmentų ir matavimų apibrėžimus, remiantis keliais duomenų šaltiniais.</span><span class="sxs-lookup"><span data-stu-id="78856-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="78856-107">Yra trys ryšių tipai:</span><span class="sxs-lookup"><span data-stu-id="78856-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="78856-108">Neredaguotini sistemos ryšiai, kurios sukūrė sistema kaip duomenų suvienodinimo proceso dalį</span><span class="sxs-lookup"><span data-stu-id="78856-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="78856-109">Neredaguotini paveldėti ryšiai, automatiškai sukuriami įtraukiant duomenų šaltinius</span><span class="sxs-lookup"><span data-stu-id="78856-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="78856-110">Redaguotini pasirinktiniai ryšiai, kuriuos sukūrė ir sukonfigūravo vartotojai</span><span class="sxs-lookup"><span data-stu-id="78856-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="78856-111">Neredaguotini sistemos ryšiai</span><span class="sxs-lookup"><span data-stu-id="78856-111">Non-editable system relationships</span></span>

<span data-ttu-id="78856-112">Duomenų suvienodinimo metu sistemos ryšiai yra sukuriami automatiškai pagal pažangųjį gretinimą.</span><span class="sxs-lookup"><span data-stu-id="78856-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="78856-113">Šie ryšiai padeda susieti kliento profilį su atitinkamais įrašais.</span><span class="sxs-lookup"><span data-stu-id="78856-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="78856-114">Šioje diagramoje pavaizduotas trijų sistema pagrįstų ryšių kūrimas.</span><span class="sxs-lookup"><span data-stu-id="78856-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="78856-115">Kliento objektas sugretinamas su kitais objektais, kad būtų galima sukurti vieningąjį *Kliento* objektą.</span><span class="sxs-lookup"><span data-stu-id="78856-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama su ryšio keliais į kliento objektą su trimis 1-n ryšiais.":::

- <span data-ttu-id="78856-117">***„Kliento su Kontaktu”* ryšys** buvo sukurtas tarp *Kliento* ir *Kontakto* objektų.</span><span class="sxs-lookup"><span data-stu-id="78856-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="78856-118">*Kliento* objektas gauna rakto lauką **„Contact_contactID”**, susiejamą su *Kontakto* objekto rakto lauku **Kontakto ID**.</span><span class="sxs-lookup"><span data-stu-id="78856-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="78856-119">***„Kliento su Abonementu”* ryšys** buvo sukurtas tarp *Kliento* ir *Abonemento* objektų.</span><span class="sxs-lookup"><span data-stu-id="78856-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="78856-120">*Kliento* objektas gauna rakto lauką **„Account_accountID”**, susiejamą su *Abonemento* objekto rakto lauku **Abonemento ID**.</span><span class="sxs-lookup"><span data-stu-id="78856-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="78856-121">***„Kliento su Žiniatinklio abonementu”* ryšys** buvo sukurtas tarp *Kliento* ir *Žiniatinklio abonemento* objektų.</span><span class="sxs-lookup"><span data-stu-id="78856-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="78856-122">*Kliento* objektas gauna rakto lauką **„AWebAccount_webaccountID”**, susiejamą su *Žiniatinklio abonemento* objekto rakto lauku **Žiniatinklio abonemento ID**.</span><span class="sxs-lookup"><span data-stu-id="78856-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="78856-123">Neredaguotini paveldėti ryšiai</span><span class="sxs-lookup"><span data-stu-id="78856-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="78856-124">Duomenų įtraukimo proceso metu sistema patikrina duomenų šaltinius esamiems ryšiams.</span><span class="sxs-lookup"><span data-stu-id="78856-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="78856-125">Jei nėra jokių ryšių, sistema juos sukuria automatiškai.</span><span class="sxs-lookup"><span data-stu-id="78856-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="78856-126">Šie ryšiai taip pat naudojami procesų pabaigose.</span><span class="sxs-lookup"><span data-stu-id="78856-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="78856-127">Pasirinktinio ryšio kūrimas</span><span class="sxs-lookup"><span data-stu-id="78856-127">Create a custom relationship</span></span>

<span data-ttu-id="78856-128">Ryšys susideda iš *šaltinio objekto*, kuriame yra išorinis raktas, ir *paskirties objekto*, kurį nurodo šaltinio objekto išorinis raktas.</span><span class="sxs-lookup"><span data-stu-id="78856-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="78856-129">Auditorijos įžvalgose eikite į **Duomenys** > **Ryšiai**.</span><span class="sxs-lookup"><span data-stu-id="78856-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="78856-130">Pasirinkite **Naujas ryšys**.</span><span class="sxs-lookup"><span data-stu-id="78856-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="78856-131">Srityje **Naujas ryšys** nurodykite tolesnę informaciją:</span><span class="sxs-lookup"><span data-stu-id="78856-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Naujo ryšio šoninė sritis su tuščiais įvesties laukais.":::

   - <span data-ttu-id="78856-133">**Ryšio pavadinimas**: Pavadinimas, atspindintis ryšio tikslą.</span><span class="sxs-lookup"><span data-stu-id="78856-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="78856-134">Pavyzdys: „Klientas į Palaikymo atvejį”.</span><span class="sxs-lookup"><span data-stu-id="78856-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="78856-135">**Aprašymas**: Ryšio aprašymas.</span><span class="sxs-lookup"><span data-stu-id="78856-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="78856-136">**Šaltinio objektas**: Objektas, naudojamas kaip ryšio šaltinis.</span><span class="sxs-lookup"><span data-stu-id="78856-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="78856-137">Pavyzdys: Palaikymo atvejis.</span><span class="sxs-lookup"><span data-stu-id="78856-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="78856-138">**Paskirties objektas**: Objektas, naudojamas kaip ryšio paskirtis.</span><span class="sxs-lookup"><span data-stu-id="78856-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="78856-139">Pavyzdys: Klientas.</span><span class="sxs-lookup"><span data-stu-id="78856-139">Example: Customer.</span></span>
   - <span data-ttu-id="78856-140">**Šaltinio skaičius**: Nurodykite šaltinio objekto skaičių.</span><span class="sxs-lookup"><span data-stu-id="78856-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="78856-141">Skaičius apibūdina galimų rinkinio elementų skaičių.</span><span class="sxs-lookup"><span data-stu-id="78856-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="78856-142">Jis visada susijęs su paskirties skaičiumi.</span><span class="sxs-lookup"><span data-stu-id="78856-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="78856-143">Galite pasirinkti iš **Vieno** ir **Daugelio**.</span><span class="sxs-lookup"><span data-stu-id="78856-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="78856-144">Palaikomi tik „daugelis su vienu“ ir „vienas su vienu“ tipo ryšiai.</span><span class="sxs-lookup"><span data-stu-id="78856-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="78856-145">„Daugelis su vienu”: Keli šaltinio įrašai gali būti susiję su vienu paskirties įrašu.</span><span class="sxs-lookup"><span data-stu-id="78856-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="78856-146">Pavyzdys: Keli palaikymo atvejai iš vieno kliento.</span><span class="sxs-lookup"><span data-stu-id="78856-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="78856-147">„Vienas su vienu”: Vienas šaltinio įrašas susijęs su vienu paskirties įrašu.</span><span class="sxs-lookup"><span data-stu-id="78856-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="78856-148">Pavyzdys: Vienas lojalumo ID vienam klientui.</span><span class="sxs-lookup"><span data-stu-id="78856-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="78856-149">Ryšius „daugelis su daugeliu” galima kurti naudojant du „daugelis su vienu” ryšius ir susiejimo objektą, sujungiantį šaltinio ir paskirties objektus.</span><span class="sxs-lookup"><span data-stu-id="78856-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="78856-150">**Paskirties skaičius**: Pasirinkite paskirties objekto įrašų skaičių.</span><span class="sxs-lookup"><span data-stu-id="78856-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="78856-151">**Šaltinio rakto laukas**: Išorinio rakto laukas šaltinio objekte.</span><span class="sxs-lookup"><span data-stu-id="78856-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="78856-152">Pavyzdys: Atvejo palaikymas gali naudoti Atvejo ID kaip išorinio rakto lauką.</span><span class="sxs-lookup"><span data-stu-id="78856-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="78856-153">**Paskirties rakto laukas**: Paskirties objekto rakto laukas.</span><span class="sxs-lookup"><span data-stu-id="78856-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="78856-154">Kliento pavyzdys gali naudoti **Kliento ID** rakto lauką.</span><span class="sxs-lookup"><span data-stu-id="78856-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="78856-155">Pasirinkite **Įrašyti** pasirinktinio ryšio kūrimui.</span><span class="sxs-lookup"><span data-stu-id="78856-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="78856-156">Ryšių peržiūra</span><span class="sxs-lookup"><span data-stu-id="78856-156">View relationships</span></span>

<span data-ttu-id="78856-157">Ryšių puslapyje išvardyti visi sukurti ryšiai.</span><span class="sxs-lookup"><span data-stu-id="78856-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="78856-158">Kiekviena eilutė nurodo ryšį, kuriame taip pat pateikiama išsami informacija apie šaltinio objektą, paskirties objektą ir skaičių.</span><span class="sxs-lookup"><span data-stu-id="78856-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Ryšių ir parinkčių sąrašas Ryšių puslapio veiksmų juostoje.":::

<span data-ttu-id="78856-160">Šiame puslapyje pateikiamas esamų ir naujų ryšių parinkčių rinkinys:</span><span class="sxs-lookup"><span data-stu-id="78856-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="78856-161">**Naujas ryšys**: [Kurti pasirinktinį ryšį](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="78856-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="78856-162">**Vizualizavimo priemonė**: [Naršykite ryšių vizualizavimo priemonę](#explore-the-relationship-visualizer), kad matytumėte esamų ryšių ir jų skaičiaus tinklo diagramą.</span><span class="sxs-lookup"><span data-stu-id="78856-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="78856-163">**Filtruoti pagal**: Pasirinkite sąraše norimų rodyti ryšių tipą.</span><span class="sxs-lookup"><span data-stu-id="78856-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="78856-164">**Ieškoti ryšių**: Naudokite tekstinę iešką ryšių ypatybėms.</span><span class="sxs-lookup"><span data-stu-id="78856-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="78856-165">Ryšių vizualizavimo priemonės naršymas</span><span class="sxs-lookup"><span data-stu-id="78856-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="78856-166">Ryšių vizualizavimo priemonė rodo esamų ryšių tarp susietų objektų ir jų skaičiaus tinklo diagramą.</span><span class="sxs-lookup"><span data-stu-id="78856-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="78856-167">Norėdami tinkinti rodinį, galite pakeisti laukų padėtį nuvilkdami juos į drobę.</span><span class="sxs-lookup"><span data-stu-id="78856-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Ryšių vizualizavimo priemonės tinklo diagramos su ryšiais tarp susijusių objektų ekrano kopija.":::

<span data-ttu-id="78856-169">Galimos parinktys:</span><span class="sxs-lookup"><span data-stu-id="78856-169">Available options:</span></span> 
- <span data-ttu-id="78856-170">**Eksportuoti kaip vaizdą**: Įrašo dabartinį rodinį kaip vaizdinį failą.</span><span class="sxs-lookup"><span data-stu-id="78856-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="78856-171">**Pakeisti į horizontalų/vertikalų išdėstymą**: Pakeičia objektų ir ryšių lygiuotę.</span><span class="sxs-lookup"><span data-stu-id="78856-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="78856-172">**Redaguoti**: Atnaujina pasirinktinių ryšių ypatybes redagavimo srityje ir įrašo pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="78856-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="78856-173">Esamų ryšių valdymas</span><span class="sxs-lookup"><span data-stu-id="78856-173">Manage existing relationships</span></span> 

<span data-ttu-id="78856-174">Ryšių puslapyje kiekvieną ryšį atspindi eilutė.</span><span class="sxs-lookup"><span data-stu-id="78856-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="78856-175">Pasirinkite ryšį ir vieną iš šių parinkčių:</span><span class="sxs-lookup"><span data-stu-id="78856-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="78856-176">**Redaguoti**: Atnaujina pasirinktinių ryšių ypatybes redagavimo srityje ir įrašo pakeitimus.</span><span class="sxs-lookup"><span data-stu-id="78856-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="78856-177">**Naikinti**: Naikina pasirinktinius ryšius.</span><span class="sxs-lookup"><span data-stu-id="78856-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="78856-178">**Peržiūrėti**: Rodomi sistemos sukurti ir paveldėti ryšiai.</span><span class="sxs-lookup"><span data-stu-id="78856-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="78856-179">Tolesnis veiksmas</span><span class="sxs-lookup"><span data-stu-id="78856-179">Next step</span></span>

<span data-ttu-id="78856-180">Sistemos ir pasirinktiniai ryšiai naudojami [segmentams kurti](segments.md), remiantis keliais duomenų šaltiniais, kurie nebėra izoliuoti.</span><span class="sxs-lookup"><span data-stu-id="78856-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
