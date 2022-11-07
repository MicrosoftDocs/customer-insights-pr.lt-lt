---
title: Segmentų eksportavimas į „Sendinblue“ (peržiūra)
description: Sužinokite, kaip konfigūruoti ryšį ir eksportuoti į „Sendinblue“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724904"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentų eksportavimas į „Sendinblue“ (peržiūra)

Eksportuoti vieningųjų kliento profilių segmentus siekiant kurti kampanijas, teikti rinkodaros el. laiškus ir naudoti konkrečias klientų grupes su „Sendinblue“.

## <a name="prerequisites"></a>Būtinosios sąlygos

- " [Sendinblue" paskyra](https://www.sendinblue.com/) ir atitinkami administratoriaus kredencialai.
- SendinBlue [API raktas](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Esami "Sendinblue" sąrašai ir atitinkami ID.
- [Sukonfigūruoti segmentai](segments.md).
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių vienam eksportui į "Sendinblue", o tai gali užtrukti iki 90 minučių. Klientų profilių, kuriuos galite eksportuoti į "Sendinblue", skaičius priklauso nuo jūsų sutarties su "Sendinblue".
- Tik segmentai.

## <a name="set-up-connection-to-sendinblue"></a>Nustatyti ryšį su „Sendinblue“

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Sendinblue**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite savo **SendinBlue API raktą**.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Lauke **Ryšys eksportavimui** pasirinkite ryšį iš skyriaus „Sendinblue“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite savo **Sendinblue sąrašo ID.**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai eksportuokite **vardas**, pavardė **ir** telefoną **,** kad sukurtumėte labiau suasmenintus el. laiškus. Pasirinkite **Įtraukti atributą** siekiant sukurti šių laukelių žemėlapį.

1. Pasirinkite segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
