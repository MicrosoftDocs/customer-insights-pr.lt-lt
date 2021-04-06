---
title: Dirbkite su API
description: Naudokite API ir supraskite apribojimus.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710470"
---
# <a name="work-with-customer-insights-apis"></a>Darbas su „Customer Insights“ API

„Dynamics 365 Customer Insights“ suteikia API siekiant sukurti jūsų nuosavas programas pagrįstas jūsų duomenimis „Customer Insights“.

> [!IMPORTANT]
> Šių API išsami informacija yra išvardyta [„Customer Insights“ API nuorodoje](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Jie apima papildomą informaciją apie operacijas, parametrus ir atsakymus.

Šis straipsnis jus supažindina su prieiga prie „Customer Insights“ API, „Azure“ programos registracijos sukūrimo ir padeda jums pradėti su esančiomis kliento bibliotekomis.

## <a name="get-started-trying-the-customer-insights-apis"></a>Pradėkite bandyti „Customer Insights“ API

1. [Prisijunkite](https://home.ci.ai.dynamics.com) prie „Customer Insights“. Jei dar neturite prenumeravimo, [prisiregistruokite „Customer Insights“ bandymui](https://aka.ms/tryci).

1. Norėdami įjungti API jūsų „Customer Insights“ aplinkoje, eikite į **Administravimas** > **Leidimai**. Jums reikės administravimo teisių, kad tą atliktumėte.

1. Eikite į **API** skirtuką ir pasirinkite **Įjungti** mygtuką.    
   API įjungimas sukuria pirmąjį ir antrąjį prenumeravimo raktą jūsų elementui, kuris yra naudojamas API prašymų. Galite sukurti iš naujo raktus pasirinkdami **Sukurti iš naujo pirminį** ar **Sukurti iš naujo antrinį** skyriuose **Administratorius** > **Teisės** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Įjungti „Customer Insights“ API":::

1. Pasirinkite **Naršyti mūsų API** norėdami [išbandyti API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Pasirinkite API operaciją ir rinkitės **Išbandyti**.

1. Šoninėje juostoje nustatykite vertę **Autorizavimas** iškrentančiame meniu į **numanoma**. `Authorization` antraštė įgauna įtrauktą turinčią žymą. Jūsų prenumeravimo raktas bus automatiškai užpildomas.
  
1. Pasirinktinai, įtraukite visus būtinus laukimo parametrus.

1. Eikite iki šoninės juostos apačios ir pasirinkite **Siųsti**.

HTTP atsakas greitai pasirodys apačioje.


   :::image type="content" source="media/try-apis.gif" alt-text="Animacinis GIF, iš kurio matyti, kaip pasirinkti API tikrinimą.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Sukurkite naują programos registravimą „Azure“ portale

Šie žingsniai jums padės pradėti naudoti „Customer Insights“ API „Azure“ programoje naudojant paskirtas teises. Įsitikinkite, kad visų pirma užpildėte [Pradžios skyrių](#get-started-trying-the-customer-insights-apis).

1. Prisijunkite prie [„Azure“ portalo](https://portal.azure.com) su paskyra, kuri gali prieiti prie „Customer Insights“ duomenų.

1. Kairiojoje pusėje pasirinkite **Programos registracijos**.

1. Rinkitės **Nauja registracija** tam, kad suteiktumėte programai pavadinimą ir pasirinktumėte paskyros tipą.
   Pasirinktinai įtraukite nukreipiantį URL. http://localhost yra pakankamas programos kūrimui jūsų vietiniame kompiuteryje.

1. Jūsų naujos programos registracijoje eikite į **API teisės**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Animacinis GIF, skirtas nustatyti API teisę programos registracijoje.":::

1. Rinkitės **Įtraukti teisę** ir pasirinkite **„Customer Insights“** šoninėje juostoje.

1. **Leidimo tipui**, pasirinkite **Suteikti leidimai** ir pasirinkite **vartotojo_suasmeninimas** leidimą.

1. Pasirinkite **Įtraukti teisių**. Jei jums reikia prieigos prie API neprisijungiant vartotojui, peržiūrėkite [Serveris su serveriu programos leidimus](#server-to-server-application-permissions) skyrių.

1. Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.

Galite naudoti programos/kliento ID šios programos registracijai su „Microsoft“ autentifikavimo biblioteka (MSAL) tam, kad gautumėte būdingą žymą ir siųstumėte ją su savo prašymu į API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Animacinis GIF, skirtas administratoriaus sutikimo suteikimui.":::

Daugiau informacijos apie MSAL, rasite [„Microsoft“ autentifikavimo bibliotekos (MSAL) apžvalga](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Dėl išsamesnės informacijos apie programos registravimą „Azure“, žr. [Nauja „Azure“ portalo programos registracijos patirtis](/azure/active-directory/develop/app-registration-portal-training-guide).

Dėl informacijos apie API mūsų kliento bibliotekų naudojimą, žr. [„Customer Insights“ kliento bibliotekos](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Serveris su serveriu programos teisės

[Programos registracijos skyrius](#create-a-new-app-registration-in-the-azure-portal) nurodo, kaip registruoti programą, kuriai reikia, kad vartotojas prisijungtų autentifikavimui. Sužinokite, kaip sukurti programos registraciją, kuriai nereikia, kad vartotojas sąveikautų ir ją būtų galima vykdyti serveryje.

1. Programos registracijoje „Azure“ portale eikite į **API teisės**.

1. Rinkitės **Įtraukti teisę** ir pasirinkite **„Customer Insights“** šoninėje juostoje.

1. **Leidimo tipui**, pasirinkite **Programos leidimai** ir pasirinkite **„CustomerInsights.Api.All“** leidimą.

1. Pasirinkite **Įtraukti teisių**.

1. Norėdami suteikti administratoriui leidimą šios programos teisėse, jums reikia įtraukti pagrindines paslaugas.

   1. Įdiekite „Azure Active Directory“ (AD) „PowerShell“ modulį: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Prisijunkite prie savo AD paskyros: `Connect-AzureAD -TenantId <your tenant id>`. Galite surasti savo nuomotojo ID **Apžvalgoje** > **„Azure Active Directory“**.
   1. Vykdykite tolesnę komandą tam, kad įtrauktumėte „Azure AD“ pagrindines paslaugas: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Programos ID parametras išlieka „Customer Insights“ API programoje.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Pagrindinių paslaugų pavyzdys":::

1. Eikite atgal į **API teisės** programos registracijai.

1. Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Animacinis GIF, skirtas administratoriaus sutikimo suteikimui.":::

1. Siekiant užbaigti, įtraukėme programos registracijos pavadinimą kaip vartotoją į „Customer Insights“.    
   Atverkite „Customer Insights“, eikite į **Administratorius** > **Leidimai** ir pasirinkite **Įtraukti vartotoją**.

1. Ieškokite savo programos registracijos pavadinimo, pasirinkite iš paieškos rezultatų ir rinkitės **Įrašyti**.

## <a name="customer-insights-client-libraries"></a>„Customer Insights“ kliento bibliotekos

Šis skyrius jums padeda pradėti naudoti kliento bibliotekas esančias „Customer Insights“ API. Visus bibliotekos šaltinio kodus ir taikomųjų programų pavyzdžius galima rasti [„Customer Insights GitHub” puslapyje](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Sužinokite, kaip pradėti naudojant C# kliento bibliotekas iš NuGet.org. Dėl išsamesnės informacijos apie NuGet paketą, žr. [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Šiuo metu šis paketas siekia netstandard2.0 ir netcoreapp2.0 darbotvarkių.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Įtraukite C# kliento biblioteką į C# projektą

1. „Visual Studio“, atverkite **NuGet paketo tvarkytuvą** jūsų projektui.

1. Ieškokite **„Microsoft.Dynamics.CustomerInsights.Api“**.

1. Pasirinkite **Įdiegti** norėdami įtraukti paketą projektui.
   Kitu atveju, vykdykite šią komandą **NuGet paketo tvarkytuvo konsolėje**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Įtraukite NuGet paketą į „Visual Studio“ projektą":::

#### <a name="use-the-c-client-library"></a>Naudokite C# kliento biblioteką

1. Naudokite [„Microsoft“ autentifikavimo biblioteką (MSAL)](/azure/active-directory/develop/msal-overview) tam, kad gautumėte `AccessToken` naudodami esančią savo [„Azure“ programos registraciją](#create-a-new-app-registration-in-the-azure-portal).

1. Po sėkmingo autentifikavimo ir žymos gavimo, sukurkite naują ar naudokite esančią `HttpClient` su papildomu **„DefaultRequestHeaders” leidimu** nustatytu į **Būdingas <access token>** ir **Ocp-Apim-Prenumeravimo-raktu** nustatytu į [**prenumeravimo raktas** iš jūsų „Customer Insights“ aplinkos](#get-started-trying-the-customer-insights-apis).    
   Paleiskite iš naujo **autorizavimo** antraštę, kai būtina. Pavyzdžiui, kai žyma baigė galioti.

1. Praleiskite šį `HttpClient` į `CustomerInsights` kliento sukūrimą.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Http kliento pavyzdys":::

1. Atlieka skambučius su klientu „plėtinio metodams“, pavyzdžiui `GetAllInstancesAsync`. Jei norite prieiti prie po juo esančiu `Microsoft.Rest.HttpOperationResponse`, naudokite „http žinutės metodai”, pavyzdžiui `GetAllInstancesWithHttpMessagesAsync`.

1. Atsakymas greičiausiai bus `object` objekto tipo, nes metodas gali grįžti į keletą tipų (pavyzdžiui, `IList<InstanceInfo>` ir `ApiErrorResult`). Norėdami patikrinti grįžimo tipą, galite saugiai sudėlioti objektus į atsakymų tipus nurodytus [API išsamios informacijos puslapis](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) veikimui.    
   Jei reikia daugiau informacijos, naudokite **http pranešimo metodus** tam, kad prieitumėte prie neapdoroto atsakymo objekto.

### <a name="nodejs-package"></a>„NodeJS” paketas

Naudokite „NodeJS” klientų bibliotekas, pasiekiamas per NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>„Python” paketas

Naudokite „Python” klientų bibliotekas, pasiekiamas per PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
