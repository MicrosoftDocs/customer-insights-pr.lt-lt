---
title: Segmentų eksportavimas į „SendGrid“ (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į „SendGrid“.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724858"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentų eksportavimas į „SendGrid“ (peržiūra)

Eksportuokite vieningųjų klientų profilių segmentus į „SendGrid” kontaktų sąrašus ir naudokite juos kampanijoms bei el. pašto rinkodarą naudojant „SendGrid”.

## <a name="prerequisites"></a>Būtinosios sąlygos

- "SendGrid" abonementas [ir](https://sendgrid.com/) atitinkami administratoriaus kredencialai.
- [Esami kontaktų sąrašai "SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) " ir atitinkami ID.
- "SendGrid" API [raktas](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Suvienodinti klientų profiliai eksportuotuose segmentuose turi laukelį rodančius el. pašto adresą, vardą ir pavardę.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iš viso iki 100 000 "SendGrid" klientų profilių, o tai gali užtrukti iki kelių valandų. Klientų profilių, kuriuos galite eksportuoti į "SendGrid", skaičius priklauso nuo jūsų sutarties su "SendGrid".
- Tik segmentai.

## <a name="set-up-connection-to-sendgrid"></a>Ryšio su „SendGrid“ nustatymas

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **SendGrid**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Įveskite " **SendGrid" API raktą**.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. Laukelyje **Ryšys eksportavimui** pasirinkite ryšį dalyje „SendGrid“. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite eksportavimo pavadinimą.

1. Įveskite savo **"SendGrid" sąrašo ID.**

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą.

1. Pasirinktinai pasirinkite laukus, pvz., **vardas**, pavardė **, Šalis / regionas**, Valstija **,** **·** **Miestas** ir **Pašto kodas.**

1. Pasirinkite segmentus, kuriuos norite eksportuoti, laikydamiesi žinomų apribojimų.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
