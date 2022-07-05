---
title: Segmentų eksportavimas į "Dynamics 365 Sales" (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Sales“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082390"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmentų eksportavimas į "Dynamics 365 Sales" (peržiūra)

Naudokite savo klientų duomenis kurdami rinkodaros sąrašus, vykdydami darbo eigas ir siųsdami pasiūlymus su „Dynamics 365 Sales“.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportavimas į "Dynamics 365 Sales" ribojamas iki 100 000 narių viename segmente.
- Segmentų eksportavimas į "Dynamics 365 Sales" gali užtrukti iki 3 valandų. 

## <a name="prerequisite-for-connection"></a>Būtinoji ryšio sąlyga

1. Kontaktų įrašai turi būti „Dynamics 365 Sales”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Sales”. Skaitykite daugiau apie tai, kaip praryti kontaktus iš ["Dynamics 365 Sales" naudojant Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Segmentų eksportavimas iš "Customer Insights" į "Sales" nesukurs naujų kontaktų įrašų pardavimo egzemplioriuose. Kontaktų įrašai iš "Sales" turi būti praryti "Customer Insights" ir naudojami kaip duomenų šaltinis. Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.

## <a name="set-up-the-connection-to-sales"></a>„Sales“ ryšio sąranka

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Dynamics 365 Sales“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Lauke **Serverio adresas** įveskite savo organizacijos „Sales“ URL.

1. Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Sales“ klientą.

1. Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį. 

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

Šį eksportavimą galite sukonfigūruoti, jei turite prieigą prie šio tipo ryšio. Daugiau informacijos žr. [Eksportavimui konfigūruoti reikalingi leidimai](export-destinations.md#set-up-a-new-export).

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Jei norite sukurti naują eksportavimą, pasirinkite **Pridėti paskirties vietą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Dynamics 365 Sales“ talpykla. Jei šio skyriaus pavadinimo nematote, nėra jums skirtų šio tipo ryšių.

1. Pasirinkite vieną ar daugiau segmentų.

1. Pasirinkite **Įrašyti**

Eksportavimo įrašymas eksportavimo iš karto nevykdo.

Eksportavimas vykdomas kiekvieno [suplanuoto atnaujinimo metu](system.md#schedule-tab). Taip pat galite [eksportuoti duomenis pagal pareikalavimą](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
