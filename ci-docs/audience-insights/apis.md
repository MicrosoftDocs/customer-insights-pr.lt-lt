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
# <a name="work-with-customer-insights-apis"></a>Darbas su „Customer Insights“ API

„Dynamics 365 Customer Insights“ „Customer Insights" teikia API, kad galėsite kurti savo taikomąsias programas pagal savo duomenis.

> [!IMPORTANT]
> Šių API išsami informacija yra išvardyta [„Customer Insights“ API nuorodoje](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Jie apima papildomą informaciją apie operacijas, parametrus ir atsakymus.

Šiame straipsnyje aprašoma, kaip pasiekti „Customer Insights" API, sukurti „Azure" programos registravimą ir pradėti dirbti su galimų klientų bibliotekomis.

## <a name="get-started-trying-the-customer-insights-apis"></a>Pradėkite bandyti „Customer Insights“ API

1. [Prisijunkite](https://home.ci.ai.dynamics.com) prie „Customer Insights“. Jei dar neturite prenumeravimo, [prisiregistruokite „Customer Insights“ bandymui](https://aka.ms/tryci).

1. Norėdami įjungti API jūsų „Customer Insights“ aplinkoje, eikite į **Administravimas** > **Leidimai**. Jums reikės administravimo teisių, kad tą atliktumėte.

1. Eikite į **API** skirtuką ir pasirinkite **Įjungti** mygtuką.    
 
   API įjungimas sukuria pirmąjį ir antrąjį prenumeravimo raktą jūsų elementui, kuris yra naudojamas API prašymų. Galite sukurti iš naujo raktus pasirinkdami **Sukurti iš naujo pirminį** ar **Sukurti iš naujo antrinį** skyriuose **Administratorius** > **Teisės** > **API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Įjungti „Customer Insights“ API":::

1. Pasirinkite **Naršyti mūsų API** norėdami [išbandyti API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Pasirinkite API operaciją ir rinkitės **Išbandyti**.

1. Šoninioje srityje nustatykite autorizavimo **išplečiamajame** meniu reikšmę kaip **netiesioginę**. Antraštė `Authorization` įtraukiama su meškietiniu atpažinimo ženklu. Jūsų prenumeravimo raktas bus automatiškai užpildomas.
  
1. Pasirinktinai, įtraukite visus būtinus laukimo parametrus.

1. Eikite iki šoninės juostos apačios ir pasirinkite **Siųsti**.

HTTP atsakas greitai pasirodys apačioje.

   :::image type="content" source="media/try-apis.gif" alt-text="Kaip patikrinti API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Sukurkite naują programos registravimą „Azure“ portale

Šie veiksmai padės pradėti naudotis „Azure" programos „Customer Insights" API naudojant leidimus naudoti leidimus naudoti. Pirmiausia užbaikite [skyrių Darbo](#get-started-trying-the-customer-insights-apis) pradžia.

1. Prisijunkite prie [„Azure“ portalo](https://portal.azure.com) su paskyra, kuri gali prieiti prie „Customer Insights“ duomenų.

1. Kairiojoje pusėje pasirinkite **Programos registracijos**.

1. Rinkitės **Nauja registracija** tam, kad suteiktumėte programai pavadinimą ir pasirinktumėte paskyros tipą.
 
   Pasirinktinai įtraukite nukreipiantį URL. http://localhost yra pakankamas programos kūrimui jūsų vietiniame kompiuteryje.

1. Jūsų naujos programos registracijoje eikite į **API teisės**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="Kaip nustatyti API teises registruojant programą.":::

1. Rinkitės **Įtraukti teisę** ir pasirinkite **„Customer Insights“** šoninėje juostoje.

1. Jei **tai teisės** tipas, pažymėkite **Išsamūs leidimai**, tada pažymėkite **user_impersonation** teisę.

1. Pasirinkite **Įtraukti teises**. Jei jums reikia prieigos prie API neprisijungiant vartotojui, peržiūrėkite [Serveris su serveriu programos leidimus](#server-to-server-application-permissions) skyrių.

1. Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.

Galite naudoti programos/kliento ID šios programos registracijai su „Microsoft“ autentifikavimo biblioteka (MSAL) tam, kad gautumėte būdingą žymą ir siųstumėte ją su savo prašymu į API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Kaip suteikti administratoriaus sutikimą.":::

Daugiau informacijos apie MSAL, rasite [„Microsoft“ autentifikavimo bibliotekos (MSAL) apžvalga](/azure/active-directory/develop/msal-overview).

Daugiau informacijos apie programos registravimą „Azure" [žr. Taikomosios programos registravimas](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Informacijos apie API naudojimas mūsų klientų bibliotekose ieškokite [„Customer Insights“ klientų bibliotekose](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Serveris su serveriu programos teisės

[Programos registracijos skyrius](#create-a-new-app-registration-in-the-azure-portal) nurodo, kaip registruoti programą, kuriai reikia, kad vartotojas prisijungtų autentifikavimui. Sužinokite, kaip sukurti programos registraciją, kuriai nereikia, kad vartotojas sąveikautų ir ją būtų galima vykdyti serveryje.

1. Programos registracijoje „Azure“ portale eikite į **API teisės**.

1. Pasirinkite **Įtraukti teisę**. 

1. Pažymėkite skirtuką **Mano organizacijos naudojama API** ir iš sąrašo pasirinkite **„Dynamics 365 AI”, skirta „Customer Insights”**. 

1. Jei **tai teisės** tipas, pažymėkite **Programos leidimai**, tada pažymėkite **CustomerInsights.Api.All** teisę.

1. Pasirinkite **Įtraukti teises**.

1. Eikite atgal į **API teisės** programos registracijai.

1. Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Kaip suteikti administratoriaus sutikimą.":::

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

1. Atlieka skambučius su klientu „plėtinio metodams“, pavyzdžiui  `GetAllInstancesAsync`. Jei norite prieiti prie po juo esančiu `Microsoft.Rest.HttpOperationResponse`, naudokite „http žinutės metodai”, pavyzdžiui `GetAllInstancesWithHttpMessagesAsync`.

1. Atsakymas greičiausiai bus `object` objekto tipo, nes metodas gali grįžti į keletą tipų (pavyzdžiui, `IList<InstanceInfo>` ir `ApiErrorResult`). Norėdami patikrinti grįžimo tipą, galite saugiai sudėlioti objektus į atsakymų tipus nurodytus [API išsamios informacijos puslapis](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) veikimui.    
   
   Jei reikia daugiau informacijos, naudokite **http pranešimo metodus** tam, kad prieitumėte prie neapdoroto atsakymo objekto.

### <a name="nodejs-package"></a>„NodeJS” paketas

Naudokite „NodeJS” klientų bibliotekas, pasiekiamas per NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>„Python” paketas

Naudokite „Python” klientų bibliotekas, pasiekiamas per PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
