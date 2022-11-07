---
title: Segmentų eksportavimas į "Braze" (peržiūra)
description: Sužinokite, kaip sukonfigūruoti ryšį ir eksportuoti į "Braze".
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725226"
---
# <a name="export-segments-to-braze-preview"></a>Segmentų eksportavimas į "Braze" (peržiūra)

Eksportuokite vieningų klientų profilių segmentus į "Braze" ir naudokite juos rinkodaros veiklai.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Braze [paskyra](https://www.braze.com/) ir atitinkami administratoriaus kredencialai.
- [Braze API raktas](https://www.braze.com/docs/api/basics/)
- Jūsų ["Braze REST" galinis punktas](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Sukonfigūruoti segmentai](segments.md) programoje "Customer Insights".
- Eksportuotų segmentų vieninguose klientų profiliuose yra laukas, nurodantis el. pašto adresą ir "Braze" kliento ID.

## <a name="known-limitations"></a>Žinomi apribojimai

- Privati nuoroda kartu su "Bring your own storage" (BYOS) nepalaikoma.
- Iki 1 milijono klientų profilių iki "Braze", o tai gali užtrukti iki 40 minučių. Klientų profilių, kuriuos galite eksportuoti į "Braze", skaičius priklauso nuo jūsų sutarties su "Braze".
- Tik segmentai.
- "Azure Private Link" nepalaikomas "Braze" eksportavimui.

## <a name="set-up-connection-to-braze"></a>Nustatykite ryšį su Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Pridėti ryšį** ir pasirinkite **Braze**.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Pasirinkite, kas gali naudoti šį ryšį. Pagal numatytuosius nustatymus, tik administratoriai. Daugiau informacijos ieškokite skyriuje [Leisti bendradarbiams naudoti ryšį eksportuojant](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pateikite savo Braze API raktą, kad galėtumėte toliau prisijungti.

1. Peržiūrėkite duomenų privatumą ir atitiktį [ir](connections.md#data-privacy-and-compliance) pasirinkite **Sutinku**.

1. Pasirinkite **Prisijungti**, kad inicijuotumėte ryšį.

1. Pasirinkite **Įtraukti save kaip eksportavimo vartotoją** ir suteikite jūsų „Customer Insights“ prisijungimo duomenis.

1. Pasirinkite **Įrašyti**, kad užbaigtumėte ryšį.

## <a name="configure-an-export"></a>Eksportavimo konfigūravimas

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Eikite į **Duomenys** > **Eksportavimas**.

1. Pasirinkite **Įtraukti eksportavimą**.

1. **Lauke Ryšys eksportui** pasirinkite ryšį iš skyriaus Braze. Jei ryšio nėra, kreipkitės į administratorių.

1. Įveskite savo REST galinį punktą į **lauką Hostname** tokiu formatu:`rest.iad-03.braze.com`.

1. Įveskite eksportavimo pavadinimą.

1. Skyriaus **Duomenų atitikimas** lauke El. paštas pažymėkite **lauką** kuris rodo kliento el. pašto adresą. **Lauke Kliento ID pasirinkite lauką, kuris atitinka kliento Braze ID**. "Braze" segmentai bus sukurti tuo pačiu segmento pavadinimu kaip ir Dynamics 365 Customer Insights. Galite pasirinkti daugiau pasirinktinių laukų, kad atitiktumėte duomenis.

1. Pasirinkite objektus arba segmentus, kuriuos norite eksportuoti.

1. Pasirinkite **Įrašyti**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
