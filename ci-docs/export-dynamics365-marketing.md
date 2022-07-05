---
title: Segmentų eksportavimas į "Dynamics 365 Marketing" (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Marketing“.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054626"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentų eksportavimas į "Dynamics 365 Marketing" (peržiūra)

Naudokite [segmentus](segments.md) tam, kad sukurtumėte kampanijas ir susisiektumėte su konkrečiomis klientų grupėmis su „Dynamics 365 Marketing“. Daugiau informacijos žr. [Segmentų naudojimas iš „Dynamics 365 Customer Insights“ su „Dynamics 365 Marketing“](/dynamics365/marketing/customer-insights-segments).

Jei naudojate naujas "Dynamics 365 Marketing" galimybes realiuoju klientų instrumentavimo ciklo metu Dataverse organizacijoje, jums nereikia kurti standartinio eksportavimo į "Dynamics 365 Marketing". Kontaktai ir segmentai iš "Customer Insights" pasiekiami tiesiogiai "Dynamics 365 Marketing", prijungus "Marketing" ir "Customer Insights". Prieš panaikindami esamus eksportavimus, peržiūrėkite dokumentaciją [, kaip prijungti "Customer Insights" ir "Dynamics 365 Marketing" klientų veiklos ciklas orkestravimą](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Būtinoji ryšio sąlygą

- Kontaktų įrašai turi būti „Dynamics 365 Marketing”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Marketing”. Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Marketing ”kontaktus naudojant „Microsoft Dataverse”](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Segmentų eksportavimas iš "Customer Insights" į "Marketing" nekurs naujų kontaktų įrašų "Marketing" egzemplioriuose. Kontaktų įrašai iš "Marketing" turi būti praryti programoje "Customer Insights" ir naudojami kaip duomenų šaltinis. Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.

## <a name="set-up-connection-to-marketing"></a>Ryšio su rinkodara sąranka

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Dynamics 365 Marketing“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.

1. Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.

1. Susiekite objekto Kliento kontakto ID lauką su "Dynamics 365" kontakto ID.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Dynamics 365 Marketing“ talpykla. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pasirinkite vieną ar daugiau segmentų.

1. Pasirinkite **Įrašyti**.

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
