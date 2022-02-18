---
title: Eksportuoti „Customer Insights“ duomenis į „Dynamics 365 Sales“
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Dynamics 365 Sales“.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d8a35424f4271b350b8d84e72a01deb6d69652a0
ms.sourcegitcommit: 08a5dfcc4f9d293c8e7ac4fef604bc52985b1b78
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090933"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>„Dynamics 365 Sales“ segmentų naudojimas (peržiūra)



Naudokite savo klientų duomenis kurdami rinkodaros sąrašus, vykdydami darbo eigas ir siųsdami pasiūlymus su „Dynamics 365 Sales“.

## <a name="known-limitations"></a>Žinomi apribojimai

- Eksportas į "Dynamics 365 Sales" ribojamas iki 100 000 narių segmente.
- Segmento eksportavimas į "Dynamics 365 Sales" gali užtrukti iki 3 valandų. 

## <a name="prerequisite-for-connection"></a>Būtinoji ryšio sąlyga

1. Kontaktų įrašai turi būti „Dynamics 365 Sales”, kad segmentą būtų galima eksportuoti iš „Customer Insights” į „Sales”. Sužinokite daugiau, kaip pasiekti [„Dynamics 365 Sales” kontaktus naudojant „Microsoft Dataverse”](connect-power-query.md).

   > [!NOTE]
   > Eksportuojant segmentus iš auditorijos įžvalgų į „Sales” nebus sukurta naujų kontaktų įrašų pardavimo egzemplioriuose. Kontaktų įrašai iš „Sales” turi būti įtraukti į auditorijos įžvalgas ir naudojami kaip duomenų šaltinis. Be to, juos reikia įtraukti į vieningą kliento objektą, kad būtų galima susieti klientų ID su kontaktų ID prieš eksportuojant segmentus.

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
