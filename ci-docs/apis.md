---
title: Darbas su „Customer Insights“ API
description: Naudokite API ir supraskite apribojimus.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387350"
---
# <a name="work-with-customer-insights-apis"></a>Darbas su „Customer Insights“ API

„Dynamics 365 Customer Insights“ „Customer Insights" teikia API, kad galėsite kurti savo taikomąsias programas pagal savo duomenis.

> [!IMPORTANT]
> Šių API išsami informacija yra išvardyta [„Customer Insights“ API nuorodoje](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Jie apima papildomą informaciją apie operacijas, parametrus ir atsakymus.

Išbandykite "Customer Insights" API, sukurkite "Azure" programų registraciją ir pradėkite naudoti klientų bibliotekas.

## <a name="get-started-trying-the-customer-insights-apis"></a>Pradėkite bandyti „Customer Insights“ API

Įgalinkite "Customer Insights" API ir išbandykite jas. "Customer Insights" administratorius turi įgalinti API prieigą prie "Customer Insights". Įjungus prieigą, bet kuris vartotojas gali naudoti API su prenumeratos raktu.

1. [Prisijunkite](https://home.ci.ai.dynamics.com) prie „Customer Insights“. Jei dar neturite prenumeravimo, [prisiregistruokite „Customer Insights“ bandymui](https://aka.ms/tryci).

1. Eikite į **Administratoriaus** > **sauga** ir pasirinkite skirtuką **API** .

1. Jei API prieiga prie aplinkos nenustatyta, pasirinkite **Įgalinti**.

   API įjungimas sukuria pirmąjį ir antrąjį prenumeravimo raktą jūsų elementui, kuris yra naudojamas API prašymų. Norėdami atkurti raktus, skirtuke API pasirinkite **Atkurti pirminį** arba **Atkurti antrinį** variantą **.**

1. Pasirinkite [**Naršyti mūsų API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) , kad išbandytumėte API.

1. Ieškokite ir pasirinkite API operaciją ir pasirinkite **Išbandyti**.

   :::image type="content" source="media/try-api.png" alt-text="Kaip patikrinti API.":::

1. Šoninioje srityje nustatykite autorizavimo **išplečiamajame** meniu reikšmę kaip **netiesioginę**. Antraštė `Authorization` įtraukiama su meškietiniu atpažinimo ženklu. Jūsų prenumeratos raktas užpildomas automatiškai.
  
1. Pasirinktinai, įtraukite visus būtinus laukimo parametrus.

1. Eikite iki šoninės juostos apačios ir pasirinkite **Siųsti**.

   HTTP atsakymas rodomas srities apačioje.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Sukurkite naują programos registravimą „Azure“ portale

Sukurkite naują [programos registraciją](/graph/auth-register-app-v2) , kad galėtumėte naudoti "Customer Insights" API "Azure" programoje naudodami deleguotąsias teises.

1. Užbaikite [skyrių](#get-started-trying-the-customer-insights-apis) Darbo pradžia.

1. Prisijunkite prie [„Azure“ portalo](https://portal.azure.com) su paskyra, kuri gali prieiti prie „Customer Insights“ duomenų.

1. Ieškokite ir pasirinkite **Programų registracijos.**

1. Rinkitės **Nauja registracija** tam, kad suteiktumėte programai pavadinimą ir pasirinktumėte paskyros tipą.

   Pasirinktinai įtraukite nukreipiantį URL. http://localhost yra pakankamas programos kūrimui jūsų vietiniame kompiuteryje.

1. Pasirinkite **Registruoti**.

1. Jūsų naujos programos registracijoje eikite į **API teisės**.

1. Pasirinkite **Įtraukti leidimą** ir šoninėje srityje pasirinkite **"Dynamics 365 AI for Customer Insights** ".

1. Jei **tai teisės** tipas, pažymėkite **Išsamūs leidimai**, tada pažymėkite **user_impersonation** teisę.

1. Pasirinkite **Įtraukti teises**.

1. Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.

1. Norėdami pasiekti API be vartotojo prisijungimo, eikite į [Serverio į serverį programos teisės](#server-to-server-application-permissions).

Programos / kliento ID galite naudoti registruodamiesi [šioje programoje "Microsoft" autentifikavimo bibliotekoje (MSAL),](/azure/active-directory/develop/msal-overview) kad gautumėte pareikštinį atpažinimo ženklą, kurį kartu su jūsų užklausa siųstumėte į API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Informacijos apie API naudojimas mūsų klientų bibliotekose ieškokite [„Customer Insights“ klientų bibliotekose](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Serveris su serveriu programos teisės

Sukurkite programos registraciją, kuriai nereikia vartotojo sąveikos ir kurią galima vykdyti serveryje.

1. Programos registracijoje „Azure“ portale eikite į **API teisės**.

1. Pasirinkite **Įtraukti teisę**.

1. Pažymėkite skirtuką **Mano organizacijos naudojama API** ir iš sąrašo pasirinkite **„Dynamics 365 AI”, skirta „Customer Insights”**.

1. Jei **tai teisės** tipas, pažymėkite **Programos leidimai**, tada pažymėkite **CustomerInsights.Api.All** teisę.

1. Pasirinkite **Įtraukti teises**.

1. Eikite atgal į **API teisės** programos registracijai.

1. Pasirinkite **Suteikite administratoriaus leidimą...** tam, kad užbaigtumėte programos registraciją.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Įtraukite programos, kaip naudotojos, pavadinimą į "Customer Insights".

   1. Atidarykite "Customer Insights", eikite į **Administratoriaus** > **sauga** ir pasirinkite **Įtraukti vartotojų**.

   1. Ieškokite savo programos registracijos pavadinimo, pasirinkite iš paieškos rezultatų ir rinkitės **Įrašyti**.

## <a name="sample-queries"></a>Užklausų pavyzdžiai

Trumpą "OData" pavyzdinių užklausų, kurios turi veikti su API, sąrašą rasite ["OData" užklausų pavyzdžiuose](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>„Customer Insights“ kliento bibliotekos

Pradėkite naudoti klientų bibliotekas, prieinamas "Customer Insights" API. Visus bibliotekos šaltinio kodus ir taikomųjų programų pavyzdžius galima rasti [„Customer Insights GitHub” puslapyje](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Naudokite C# kliento bibliotekas iš NuGet.org. Šiuo metu paketas skirtas netstandard2.0 ir netcoreapp2.0 sistemoms. Daugiau informacijos apie NuGet paketą rasite [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Įtraukite C# kliento biblioteką į C# projektą

1. „Visual Studio“, atverkite **NuGet paketo tvarkytuvą** jūsų projektui.

1. Ieškokite **„Microsoft.Dynamics.CustomerInsights.Api“**.

1. Pasirinkite **Įdiegti** norėdami įtraukti paketą projektui.

   Kitu atveju, vykdykite šią komandą **NuGet paketo tvarkytuvo konsolėje**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Naudokite C# kliento biblioteką

1. Naudokite [„Microsoft“ autentifikavimo biblioteką (MSAL)](/azure/active-directory/develop/msal-overview) tam, kad gautumėte `AccessToken` naudodami esančią savo [„Azure“ programos registraciją](#create-a-new-app-registration-in-the-azure-portal).

1. Sėkmingai autentifikavę ir įsigiję atpažinimo ženklą, sukurkite naują arba naudokite esamą `HttpClient` su **DefaultRequestHeaders "Autorizacija", nustatyta kaip** Bearer "prieigos atpažinimo ženklas"**ir** Ocp-Apim-Subscription-Key **, nustatytas kaip** prenumeratos raktas [**iš jūsų "Customer Insights"** aplinkos](#get-started-trying-the-customer-insights-apis).   

   Paleiskite iš naujo **autorizavimo** antraštę, kai būtina. Pavyzdžiui, kai žyma baigė galioti.

1. Praleiskite šį `HttpClient` į `CustomerInsights` kliento sukūrimą.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Atlieka skambučius su klientu „plėtinio metodams“, pavyzdžiui `GetAllInstancesAsync`. Jei pirmenybė teikiama prieigai prie pagrindo `Microsoft.Rest.HttpOperationResponse` , naudokite "http pranešimo metodus", pvz., `GetAllInstancesWithHttpMessagesAsync`.

1. Tikėtina, kad `object` atsakymo tipas yra, nes metodas gali grąžinti kelis tipus (pvz., `IList<InstanceInfo>` ir `ApiErrorResult`). Norėdami patikrinti grąžinimo tipą, naudokite objektus atsakymų tipuose, nurodytuose tos [operacijos API išsamios informacijos puslapyje](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) .

   Jei reikia daugiau informacijos, naudokite **http pranešimo metodus** tam, kad prieitumėte prie neapdoroto atsakymo objekto.

### <a name="nodejs-package"></a>„NodeJS” paketas

Naudokite „NodeJS” klientų bibliotekas, pasiekiamas per NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>„Python” paketas

Naudokite „Python” klientų bibliotekas, pasiekiamas per PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
