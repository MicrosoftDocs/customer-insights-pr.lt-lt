---
title: Dirbkite su API
description: Naudokite API ir supraskite apribojimus.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304752"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="c2cc9-103">Darbas su „Customer Insights“ API</span><span class="sxs-lookup"><span data-stu-id="c2cc9-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="c2cc9-104">„Dynamics 365 Customer Insights“ „Customer Insights" teikia API, kad galėsite kurti savo taikomąsias programas pagal savo duomenis.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2cc9-105">Šių API išsami informacija yra išvardyta [„Customer Insights“ API nuorodoje](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="c2cc9-106">Jie apima papildomą informaciją apie operacijas, parametrus ir atsakymus.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="c2cc9-107">Šiame straipsnyje aprašoma, kaip pasiekti „Customer Insights" API, sukurti „Azure" programos registravimą ir pradėti dirbti su galimų klientų bibliotekomis.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="c2cc9-108">Pradėkite bandyti „Customer Insights“ API</span><span class="sxs-lookup"><span data-stu-id="c2cc9-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="c2cc9-109">[Prisijunkite](https://home.ci.ai.dynamics.com) prie „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="c2cc9-110">Jei dar neturite prenumeravimo, [prisiregistruokite „Customer Insights“ bandymui](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="c2cc9-111">Norėdami įjungti API jūsų „Customer Insights“ aplinkoje, eikite į **Administravimas** > **Leidimai**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="c2cc9-112">Jums reikės administravimo teisių, kad tą atliktumėte.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="c2cc9-113">Eikite į **API** skirtuką ir pasirinkite **Įjungti** mygtuką.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="c2cc9-114">API įjungimas sukuria pirmąjį ir antrąjį prenumeravimo raktą jūsų elementui, kuris yra naudojamas API prašymų.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="c2cc9-115">Galite sukurti iš naujo raktus pasirinkdami **Sukurti iš naujo pirminį** ar **Sukurti iš naujo antrinį** skyriuose **Administratorius** > **Teisės** > **API**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Įjungti „Customer Insights“ API":::

1. <span data-ttu-id="c2cc9-117">Pasirinkite **Naršyti mūsų API** norėdami [išbandyti API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="c2cc9-118">Pasirinkite API operaciją ir rinkitės **Išbandyti**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="c2cc9-119">Šoninioje srityje nustatykite autorizavimo **išplečiamajame** meniu reikšmę kaip **netiesioginę**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="c2cc9-120">Antraštė `Authorization` įtraukiama su meškietiniu atpažinimo ženklu.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="c2cc9-121">Jūsų prenumeravimo raktas bus automatiškai užpildomas.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="c2cc9-122">Pasirinktinai, įtraukite visus būtinus laukimo parametrus.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="c2cc9-123">Eikite iki šoninės juostos apačios ir pasirinkite **Siųsti**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="c2cc9-124">HTTP atsakas greitai pasirodys apačioje.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Kaip patikrinti API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="c2cc9-126">Sukurkite naują programos registravimą „Azure“ portale</span><span class="sxs-lookup"><span data-stu-id="c2cc9-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="c2cc9-127">Šie veiksmai padės pradėti naudotis „Azure" programos „Customer Insights" API naudojant leidimus naudoti leidimus naudoti.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="c2cc9-128">Pirmiausia užbaikite [skyrių Darbo](#get-started-trying-the-customer-insights-apis) pradžia.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="c2cc9-129">Prisijunkite prie [„Azure“ portalo](https://portal.azure.com) su paskyra, kuri gali prieiti prie „Customer Insights“ duomenų.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="c2cc9-130">Kairiojoje pusėje pasirinkite **Programos registracijos**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="c2cc9-131">Rinkitės **Nauja registracija** tam, kad suteiktumėte programai pavadinimą ir pasirinktumėte paskyros tipą.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="c2cc9-132">Pasirinktinai įtraukite nukreipiantį URL.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="c2cc9-133">http://localhost yra pakankamas programos kūrimui jūsų vietiniame kompiuteryje.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="c2cc9-134">Jūsų naujos programos registracijoje eikite į **API teisės**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Kaip nustatyti API teises registruojant programą.":::

1. <span data-ttu-id="c2cc9-136">Rinkitės **Įtraukti teisę** ir pasirinkite **„Customer Insights“** šoninėje juostoje.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="c2cc9-137">Jei **tai teisės** tipas, pažymėkite **Išsamūs leidimai**, tada pažymėkite **user_impersonation** teisę.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="c2cc9-138">Pasirinkite **Įtraukti teises**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-138">Select **Add permissions**.</span></span> <span data-ttu-id="c2cc9-139">Jei jums reikia prieigos prie API neprisijungiant vartotojui, peržiūrėkite [Serveris su serveriu programos leidimus](#server-to-server-application-permissions) skyrių.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="c2cc9-140">Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="c2cc9-141">Galite naudoti programos/kliento ID šios programos registracijai su „Microsoft“ autentifikavimo biblioteka (MSAL) tam, kad gautumėte būdingą žymą ir siųstumėte ją su savo prašymu į API.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Kaip suteikti administratoriaus sutikimą.":::

<span data-ttu-id="c2cc9-143">Daugiau informacijos apie MSAL, rasite [„Microsoft“ autentifikavimo bibliotekos (MSAL) apžvalga](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="c2cc9-144">Daugiau informacijos apie programos registravimą „Azure" [žr. Taikomosios programos registravimas](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="c2cc9-145">Informacijos apie API naudojimas mūsų klientų bibliotekose ieškokite [„Customer Insights“ klientų bibliotekose](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="c2cc9-146">Serveris su serveriu programos teisės</span><span class="sxs-lookup"><span data-stu-id="c2cc9-146">Server-to-server application permissions</span></span>

<span data-ttu-id="c2cc9-147">[Programos registracijos skyrius](#create-a-new-app-registration-in-the-azure-portal) nurodo, kaip registruoti programą, kuriai reikia, kad vartotojas prisijungtų autentifikavimui.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="c2cc9-148">Sužinokite, kaip sukurti programos registraciją, kuriai nereikia, kad vartotojas sąveikautų ir ją būtų galima vykdyti serveryje.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="c2cc9-149">Programos registracijoje „Azure“ portale eikite į **API teisės**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="c2cc9-150">Pasirinkite **Įtraukti teisę**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="c2cc9-151">Pažymėkite skirtuką **Mano organizacijos naudojama API** ir iš sąrašo pasirinkite **„Dynamics 365 AI”, skirta „Customer Insights”**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="c2cc9-152">Jei **tai teisės** tipas, pažymėkite **Programos leidimai**, tada pažymėkite **CustomerInsights.Api.All** teisę.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="c2cc9-153">Pasirinkite **Įtraukti teises**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="c2cc9-154">Eikite atgal į **API teisės** programos registracijai.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="c2cc9-155">Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Kaip suteikti administratoriaus sutikimą.":::

1. <span data-ttu-id="c2cc9-157">Siekiant užbaigti, įtraukėme programos registracijos pavadinimą kaip vartotoją į „Customer Insights“.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="c2cc9-158">Atverkite „Customer Insights“, eikite į **Administratorius** > **Leidimai** ir pasirinkite **Įtraukti vartotoją**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="c2cc9-159">Ieškokite savo programos registracijos pavadinimo, pasirinkite iš paieškos rezultatų ir rinkitės **Įrašyti**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="c2cc9-160">„Customer Insights“ kliento bibliotekos</span><span class="sxs-lookup"><span data-stu-id="c2cc9-160">Customer Insights client libraries</span></span>

<span data-ttu-id="c2cc9-161">Šis skyrius jums padeda pradėti naudoti kliento bibliotekas esančias „Customer Insights“ API.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="c2cc9-162">Visus bibliotekos šaltinio kodus ir taikomųjų programų pavyzdžius galima rasti [„Customer Insights GitHub” puslapyje](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="c2cc9-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="c2cc9-163">C# NuGet</span></span>

<span data-ttu-id="c2cc9-164">Sužinokite, kaip pradėti naudojant C# kliento bibliotekas iš NuGet.org. Dėl išsamesnės informacijos apie NuGet paketą, žr. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="c2cc9-165">Šiuo metu šis paketas siekia netstandard2.0 ir netcoreapp2.0 darbotvarkių.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="c2cc9-166">Įtraukite C# kliento biblioteką į C# projektą</span><span class="sxs-lookup"><span data-stu-id="c2cc9-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="c2cc9-167">„Visual Studio“, atverkite **NuGet paketo tvarkytuvą** jūsų projektui.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="c2cc9-168">Ieškokite **„Microsoft.Dynamics.CustomerInsights.Api“**.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="c2cc9-169">Pasirinkite **Įdiegti** norėdami įtraukti paketą projektui.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="c2cc9-170">Kitu atveju, vykdykite šią komandą **NuGet paketo tvarkytuvo konsolėje**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="c2cc9-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Įtraukite NuGet paketą į „Visual Studio“ projektą":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="c2cc9-172">Naudokite C# kliento biblioteką</span><span class="sxs-lookup"><span data-stu-id="c2cc9-172">Use the C# client library</span></span>

1. <span data-ttu-id="c2cc9-173">Naudokite [„Microsoft“ autentifikavimo biblioteką (MSAL)](/azure/active-directory/develop/msal-overview) tam, kad gautumėte `AccessToken` naudodami esančią savo [„Azure“ programos registraciją](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="c2cc9-174">Po sėkmingo autentifikavimo ir žymos gavimo, sukurkite naują ar naudokite esančią `HttpClient` su papildomu **„DefaultRequestHeaders” leidimu** nustatytu į **Būdingas <access token>** ir **Ocp-Apim-Prenumeravimo-raktu** nustatytu į [**prenumeravimo raktas** iš jūsų „Customer Insights“ aplinkos](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="c2cc9-175">Paleiskite iš naujo **autorizavimo** antraštę, kai būtina.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="c2cc9-176">Pavyzdžiui, kai žyma baigė galioti.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="c2cc9-177">Praleiskite šį `HttpClient` į `CustomerInsights` kliento sukūrimą.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Http kliento pavyzdys":::

1. <span data-ttu-id="c2cc9-179">Atlieka skambučius su klientu „plėtinio metodams“, pavyzdžiui  `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="c2cc9-180">Jei norite prieiti prie po juo esančiu `Microsoft.Rest.HttpOperationResponse`, naudokite „http žinutės metodai”, pavyzdžiui `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="c2cc9-181">Atsakymas greičiausiai bus `object` objekto tipo, nes metodas gali grįžti į keletą tipų (pavyzdžiui, `IList<InstanceInfo>` ir `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="c2cc9-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="c2cc9-182">Norėdami patikrinti grįžimo tipą, galite saugiai sudėlioti objektus į atsakymų tipus nurodytus [API išsamios informacijos puslapis](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) veikimui.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="c2cc9-183">Jei reikia daugiau informacijos, naudokite **http pranešimo metodus** tam, kad prieitumėte prie neapdoroto atsakymo objekto.</span><span class="sxs-lookup"><span data-stu-id="c2cc9-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="c2cc9-184">„NodeJS” paketas</span><span class="sxs-lookup"><span data-stu-id="c2cc9-184">NodeJS package</span></span>

<span data-ttu-id="c2cc9-185">Naudokite „NodeJS” klientų bibliotekas, pasiekiamas per NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="c2cc9-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="c2cc9-186">„Python” paketas</span><span class="sxs-lookup"><span data-stu-id="c2cc9-186">Python package</span></span>

<span data-ttu-id="c2cc9-187">Naudokite „Python” klientų bibliotekas, pasiekiamas per PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="c2cc9-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
