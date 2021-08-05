---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Marketing“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Marketing“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bd8189f8daee1a6aea75e75e116186f62a360ba4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692491"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>„Dynamics 365 Marketing“ segmentų naudojimas (peržiūra)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Naudokite [segmentus](segments.md) tam, kad sukurtumėte kampanijas ir susisiektumėte su konkrečiomis klientų grupėmis su „Dynamics 365 Marketing“. Daugiau informacijos žr. [Segmentų naudojimas iš „Dynamics 365 Customer Insights“ su „Dynamics 365 Marketing“](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Būtinoji ryšio sąlygą

- Kontaktų įrašai turi būti „Dynamics 365 Marketing”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Marketing”. Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Marketing ”kontaktus naudojant „Microsoft Dataverse”](connect-power-query.md).

  > [!NOTE]
  > Eksportuojant segmentus iš auditorijos įžvalgų į „Marketing” nebus sukurta naujų kontaktų įrašų rinkodaros egzemplioriuose. Kontaktų įrašai iš „Marketing” turi būti įtraukti į auditorijos įžvalgas ir naudojami duomenų šaltinis. Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.

## <a name="set-up-connection-to-marketing"></a>Ryšio su rinkodara sąranka

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **„Dynamics 365 Marketing“**, kad sukonfigūruotumėte ryšį.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Jei jokio veiksmo neimsite, numatytasis parametras bus administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Lauke **Serverio adresas** įveskite savo organizacijos „Marketing“ URL.

1. Skyriuje **Serverio administratoriaus klientas** spustelėkite **Prisijungti** ir pasirinkite „Dynamics 365 Marketing“ klientą.

1. Sudarykite kliento ID laukelių žemėlapį į „Dynamics 365 Contact“ ID.

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
