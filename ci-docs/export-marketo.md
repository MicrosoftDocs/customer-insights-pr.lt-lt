---
title: Segmentų eksportavimas į „Marketo“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „Marketo“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724950"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentų eksportavimas į „Marketo“ (peržiūra)

Eksportuokite suvienodintų klientų profilio segmentus siekiant sugeneruoti kampanijas, pateikti el. pašto reklamavimą ir naudoti konkrečias klientų grupes su „Marketo“.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Marketo" paskyra](https://login.marketo.com/) ir atitinkami administratoriaus kredencialai.
- " [Marketo" kliento ID, kliento paslaptis ir REST galinio punkto pagrindinio kompiuterio pavadinimas](https://developers.marketo.com/rest-api/authentication/).
- [Esami "Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) " sąrašai ir atitinkami ID.
- [Sukonfigūruoti segmentai](segments.md).
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių vienam eksportui į "Marketo", kuris gali užtrukti iki 3 valandų. Klientų profilių, kuriuos galite eksportuoti į "Marketo", skaičius priklauso nuo jūsų sutarties su "Marketo".
- Tik segmentai.

## <a name="set-up-connection-to-marketo"></a>Ryšio su „Marketo“ sąranka

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Marketo**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **"Marketo" kliento ID, kliento slaptąjį raktą ir "REST Endpoint Hostname**". REST galinio punkto pagrindinio kompiuterio vardas yra tik pagrindinio kompiuterio vardas be https://. Pavyzdys: xyz-abc-123.mktorest.com.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „Marketo“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite savo **"Marketo" sąrašo ID.** Sąrašo ID yra grynai skaitinė vertė. Pavyzdžiui, jei jūsų "Marketo" sąrašo ID yra ST12345A7, pašalinkite simbolį prieš ir po skaitmenų ir įveskite *12345*.

1. Sekcijoje **Duomenų atitikimas** pasirinkite bent vieną lauką, nurodantį kliento el. pašto adresą arba kliento "Marketo" ID.

1. Pasirinktinai eksportuokite **vardas**, pavardė **,** **miestą**, valstiją **ir** šalį / regioną **,** kad sukurtumėte labiau suasmenintus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

"Marketo" raskite savo segmentus " [Marketo" sąrašuose](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
