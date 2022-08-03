---
title: Segmentų eksportavimas į "Dynamics 365 Marketing" (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Marketing“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196634"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentų eksportavimas į "Dynamics 365 Marketing" (peržiūra)

Naudokite [segmentus](segments.md) kampanijoms generuoti ir susisiekti su konkrečiomis klientų grupėmis naudodami ["Dynamics 365 Marketing"](/dynamics365/marketing/customer-insights-segments).

Jei naudojate naujas "Dynamics 365 Marketing" galimybes realiuoju klientų instrumentavimo ciklo metu Dataverse organizacijoje, jums nereikia kurti standartinio eksportavimo į "Dynamics 365 Marketing". Kontaktai ir segmentai iš "Customer Insights" pasiekiami tiesiogiai "Dynamics 365 Marketing", prijungus "Marketing" ir "Customer Insights". Prieš panaikindami esamus eksportavimus, peržiūrėkite dokumentaciją [, kaip prijungti "Customer Insights" ir "Dynamics 365 Marketing" klientų veiklos ciklas orkestravimą](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Būtinoji sąlyga

Kontaktų įrašai turi būti „Dynamics 365 Marketing”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Marketing”. Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Marketing ”kontaktus naudojant „Microsoft Dataverse”](connect-dataverse-managed-lake.md).

> [!NOTE]
> Segmentų eksportavimas iš "Customer Insights" į "Marketing" nekurs naujų kontaktų įrašų "Marketing" egzemplioriuose. Kontaktų įrašai iš "Marketing" turi būti praryti programoje "Customer Insights" ir naudojami kaip duomenų šaltinis. Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.

## <a name="set-up-connection-to-marketing"></a>Ryšio su rinkodara sąranka

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite **"Dynamics 365 Marketing"**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.

1. Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.

1. Susiekite objekto Kliento kontakto ID lauką su "Dynamics 365" kontakto ID.

1. Peržiūrėkite duomenų privatumą [ir atitiktį](connections.md#data-privacy-and-compliance) ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Pridėti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Dynamics 365 Marketing“ talpykla. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Objekte Klientas pasirinkite lauką Kontakto ID, kuris atitinka "Dynamics 365" kontakto ID.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
