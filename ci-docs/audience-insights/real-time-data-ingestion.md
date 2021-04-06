---
title: Realaus laiko duomenų suvartojimas ir apribojimai
description: Bendra informacija apie realaus laiko galimybes publikos įžvalgose.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598579"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="5e7f5-103">Duomenų įtraukimas realiuoju laiku (peržiūra)</span><span class="sxs-lookup"><span data-stu-id="5e7f5-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="5e7f5-104">Beveik realiojo laiko funkcijos leidžia jums per kelias sekundes pamatyti naujausius klientų veiksmus su jūsų produktais ar paslaugomis.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="5e7f5-105">[Suplanuoti paleidimai iš naujo](system.md#schedule-tab) įtraukiant didelius įrašų skaičius ir keletą sudėtingų veiksmų.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="5e7f5-106">Pirmiausia, duomenys yra įtraukiami iš duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="5e7f5-107">Tada duomenys sujungiami ir papildomi papildoma informacija.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="5e7f5-108">Kiekvieną kartą šis procesas gali trukti nuo kelių minučių iki kelių valandų.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="5e7f5-109">Realaus laiko funkcijos pateikia duomenis nedelsiant suvartojimui, kol tolesnis grafikas iš naujo paleidžia šiuos duomenis iš duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="5e7f5-110">Realiojo laiko atnaujinimai turi galiojimo pabaigos laiką, po kurio jie daugiau neperrašo reikšmės iš duomenų šaltinio.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="5e7f5-111">Profilio atnaujinimai bus saugomi 4 valandas</span><span class="sxs-lookup"><span data-stu-id="5e7f5-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="5e7f5-112">Veiklos bus saugomos 30 dienų</span><span class="sxs-lookup"><span data-stu-id="5e7f5-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="5e7f5-113">Šios reikšmės yra API skambučių parametrai, kuriuos galite keisti.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="5e7f5-114">Jais siekiama užtikrinti, kad jūsų šaltinio duomenys išliktų patikimiausiu šaltiniu.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="5e7f5-115">Jei norite, kad realaus laiko naujinimai būtų įtraukti ilgesnį laikotarpį, jums reikia juos įtraukti į duomenų šaltinį taip, kad jie būtų paimami kito suplanuoto paleidimo iš naujo metu.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="5e7f5-116">Sujungto kliento profilio laukų atnaujinimas realiuoju laiku</span><span class="sxs-lookup"><span data-stu-id="5e7f5-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="5e7f5-117">Naujinti profiliai bus rodomi kliento kortelės rodinyje ar bet kokioje kitoje vizualizacijoje per kelias sekundes.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="5e7f5-118">Kadangi realiojo laiko operacijos vykdomos po duomenų sujungimo, jos taikomos tik sujungtiems klientų profiliams.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="5e7f5-119">Todėl profilio pakeitimais realiuoju laiku nebus atnaujinti matai, segmento narystė ar papildymai.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="5e7f5-120">Apribojimai</span><span class="sxs-lookup"><span data-stu-id="5e7f5-120">Limitations</span></span>

- <span data-ttu-id="5e7f5-121">Klientų profiliai gali būti atnaujinti, bet ne sukurti ar panaikinti.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="5e7f5-122">Šiuo metu realiojo laiko atnaujinimų negalima eksportuoti į išorines sistemas, pvz., „Power BI“.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="5e7f5-123">Veiklų kūrimas realiuoju laiku</span><span class="sxs-lookup"><span data-stu-id="5e7f5-123">Real-time creation of activities</span></span>

<span data-ttu-id="5e7f5-124">Realaus laiko API leidžia jums publikuoti naują veiklą iš jūsų šaltinio sistemos (atskiro šaltinio įrašo) į suvienodintą kliento profilį.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="5e7f5-125">Nauja veikla po kelių sekundžių bus pasiekiama kaip sujungta veikla to sujungto kliento profilio laiko planavimo juostoje.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="5e7f5-126">Galite matyti laiko juostą kliento kortelės rodinyje ar bet kokią kitą laiko juostos integravimą, kurį sukonfigūravote.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="5e7f5-127">Veiklos yra nekintamos.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-127">Activities are immutable.</span></span> <span data-ttu-id="5e7f5-128">Sukūrus veiklas jos nekeičiamos.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-128">They don't change once created.</span></span>
> - <span data-ttu-id="5e7f5-129">Šiuo metu segmentai ir matai nebus atnaujinami pagal naują veiklą.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="5e7f5-130">Veiklos, įtrauktos tik per realiojo laiko API, nėra eksportuojamos ir nebus rodomos „PowerBI“.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="5e7f5-131">Yra du būdai sujungti realaus laiko API:</span><span class="sxs-lookup"><span data-stu-id="5e7f5-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="5e7f5-132">[netiesiogiai](#connect-via-the-dynamics-365-customer-insights-connector), naudojant [„Dynamics 365 Customer Insights connector“](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="5e7f5-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="5e7f5-133">[tiesiogiai](#connect-directly-to-the-real-time-api), naudojant kodą.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="5e7f5-134">Abiems būdams taikomos toliau nurodytos būtinosios sąlygos.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="5e7f5-135">„Customer Insights“ aplinka</span><span class="sxs-lookup"><span data-stu-id="5e7f5-135">A Customer Insights environment</span></span>
- <span data-ttu-id="5e7f5-136">Sujungti klientų profiliai</span><span class="sxs-lookup"><span data-stu-id="5e7f5-136">Unified customer profiles</span></span>
- <span data-ttu-id="5e7f5-137">Sukonfigūruotos ir vykdytos veiklos</span><span class="sxs-lookup"><span data-stu-id="5e7f5-137">Activities configured and run</span></span>
- <span data-ttu-id="5e7f5-138">Dalyvio ar administratoriaus teisės jūsų klientui autentifikuoti</span><span class="sxs-lookup"><span data-stu-id="5e7f5-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="5e7f5-139">Prijungimas naudojant „Dynamics 365 Customer Insights connector“</span><span class="sxs-lookup"><span data-stu-id="5e7f5-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="5e7f5-140">Realiojo laiko API gali gauti duomenis iš skirtosios „Power Platform“ jungties – [„Dynamics 365 Customer Insights connector“](/connectors/customerinsights/) – ir nereikia kurti ir diegti jokio kodo.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="5e7f5-141">Jungtis gali atlikti tuos pačius realiojo laiko veiksmus kaip API.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="5e7f5-142">Turite turėti galiojančią aukščiausios klasės jungčių licenciją.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="5e7f5-143">Daugiau informacijos žr. [DUK apie „Power Apps“ ir „Power Automate“ licencijas](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="5e7f5-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="5e7f5-144">„Power Platform“ [„Power Apps“ ir (arba) „Power Automate“](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="5e7f5-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="5e7f5-145">„Azure“ [„Logic Apps“](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="5e7f5-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="5e7f5-146">Išsamią informaciją apie srautų kūrimą žr. [„Power Automate“ dokumentuose](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="5e7f5-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="5e7f5-147">Tiesioginis prisijungimas prie realiojo laiko API</span><span class="sxs-lookup"><span data-stu-id="5e7f5-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="5e7f5-148">Galite naudoti realaus laiko ypatybes sukurdami jūsų nuosavą vamzdyną ir sujungti tiesiogiai realaus laiko API.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="5e7f5-149">Veiklą galite skelbti savo šaltinio sistemos arba „UnifiedActivity“ formatu.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="5e7f5-150">Formatą galite gauti atlikdami API iškvietimą į /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="5e7f5-151">Šio API išsami informacija, įskaitant parametrus ir atsakymus, gali būti surasti **Objektų duomenys** skyriuje [„Customer Insights“ API ataskaitose](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="5e7f5-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="5e7f5-152">Dėl išsamesnės informacijos, žr. [Darbas su „Customer Insights“ API“](apis.md).</span><span class="sxs-lookup"><span data-stu-id="5e7f5-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="5e7f5-153">Telemetrijos naudojimo realiuoju laiku supratimas</span><span class="sxs-lookup"><span data-stu-id="5e7f5-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="5e7f5-154">Gaukite užklausų apimties apžvalgą realaus laiko API ir informacijai apie problemas, su kuriomis gali susidurti sistema.</span><span class="sxs-lookup"><span data-stu-id="5e7f5-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="5e7f5-155">Galite [prieiti prie telemetrijos realiuoju laiku](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="5e7f5-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]