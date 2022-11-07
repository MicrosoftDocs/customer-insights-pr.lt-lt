---
title: Segmentų eksportavimas į „DotDigital“ (peržiūros versija)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „DotDigital“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724996"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentų eksportavimas į „DotDigital“ (peržiūros versija)

Eksportuokite suvienodintų klientų profilio segmentus į „DotDigital“ adresų knygas ir naudokite juos kampanijos, el. pašto reklamavimui ir siekiant kurti tinkintus segmentus su „DotDigital“.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [DotDigital" paskyra](https://dotdigital.com/) ir [API vartotojas](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- "DotDigital" ID iš naujos [arba esamos "DotDigital"](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) adresų knygelės. ID gali būti prieinamas URL, kurį pasirinkote ir atvėrėte adresų knygoje.
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių vienam eksportui į "DotDigital", kuris gali užtrukti iki trijų valandų dėl paslaugų teikėjo apribojimų. Klientų profilių, kuriuos galite eksportuoti į "DotDigital", skaičius priklauso nuo jūsų sutarties su "DotDigital".
- Tik segmentai.

## <a name="set-up-connection-to-dotdigital"></a>„DotDigital“ ryšio sąranka

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **DotDigital**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **„DotDigital“ API vartotojo vardą ir slaptažodį**.

1. Įveskite savo **DotDigital adresų knygos ID.**

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „DotDigital“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai eksportuokite vardas, pavardė **, vardą ir pavardę**, **·** **lytį** ir **pašto kodą**.**·**

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

"DotDigital" raskite savo segmentus "DotDigital" adresų [knygelėse](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
