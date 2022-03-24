---
title: Papildykite klientų profilius vietos duomenimis iš „Azure” žemėlapių
description: Bendroji informacija apie „Azure“ žemėlapių pirmosios šalies papildymą.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 2cc44f7b453d2aca328c397b14787c8a02c5e490
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376656"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Klientų profilių papildymas „Azure” žemėlapiais (peržiūros versija)

„Azure” žemėlapiai teikia į vietą orientuotus duomenis ir paslaugas, kad būtų galima teikti funkcijas, pagrįstas erdviniais duomenimis naudojant įtaisytąją vietos įžvalgą. „Azure” žemėlapių duomenų papildymo paslaugos pagerina vietos informacijos apie klientus tikslumą. Taip teikiamos funkcijos, pavyzdžiui, adreso normalizavimas ir platumos ir ilgumos išskleidimas į „Dynamics 365 Customer Insights”.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norėdami sukonfigūruoti „Azure” žemėlapių duomenų papildymą turite įvykdyti šias būtinąsias sąlygas:

- Turite turėti aktyvią „Azure“ žemėlapių prenumeratą. Norėdami gauti prenumeratą galite [prisiregistruoti arba gauti nemokamą bandomąją versiją](https://azure.microsoft.com/services/azure-maps/).

- „Azure” žemėlapių [ryšys](connections.md) yra galimas *arba* jūs turite [administratoriaus](permissions.md#admin) teises ir aktyvų „Azure” žemėlapių API raktą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**. 

1. Plytelėje **Vieta** pažymėkite **Papildyti mano duomenis**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure žemėlapių raktas.":::

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei „Azure” žemėlapių ryšys pasiekiamas, kreipkitės į administratorių. Jei esate administratorius, galite [sukonfigūruoti „Azure” žemėlapių ryšį](#configure-the-connection-for-azure-maps). 

1. Pasirinkite **Toliau** pasirinkimo patvirtinimui.

1. Pasirinkite **Kliento duomenų rinkinį**, kurį norite papildyti vietos duomenimis iš „Azure” žemėlapių. Galite pažymėti objektą **Klientas**, kad papildytumėte visus jūsų suvienytus klientų profilius, arba pažymėti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Ekrano kopija klientų duomenų rinkinio pasirinkimo momentu.":::

1. Pasirinkite, ar norite susieti laukus su pirminiu ir (arba) antriniu adresu. Galite nurodyti laukų susiejimą abiems adresams ir papildyti abiejų adresų profilius atskirai&mdash;pavyzdžiui, namų adreso ir verslo adreso. Pasirinkite **Toliau**.

1. Nustatykite, kuriuos jūsų vieningųjų profilių laukus naudoti vietos duomenų atitikimui iš „Azure” žemėlapių. Laukai **Gatvė 1** ir **Zip/Pašto kodo** laukai yra būtini pažymėtam pirminiam arba antriniam adresui. Norėdami užtikrinti aukštesnį atitikties tikslumą, galite įtraukti daugiau laukų.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure žemėlapių papildymo konfigūravimo puslapis.":::

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Įvertinkite, ar norite modifikuoti **Išplėstinius parametrus**. Jie bus teikiami tam, kad būtų galima kuo lanksčiau tvarkyti išplėstinio naudojimo atvejus, tačiau numatytosios reikšmės daugeliu atvejų bus tinkamos:
   - **Adresų tipas**: Numatytasis veikimas yra tas, kad papildymas grąžins geriausią adreso atitikmenį, net jei jis neužbaigtas. Jei norite gauti tik pilnus adresus&mdash;pavyzdžiui, adresus, kuriuose yra namų numeris&mdash;išvalykite visus žymės langelius, išskyrus **Taškų adresus**. 
   - **Kalba**: Pagal numatytuosius nustatymus adresai yra grąžinami regiono, kuriam nustatytas adresas, kalba. Jei norite taikyti standartizuotą adreso kalbą, pasirinkite kalbą iš išplečiamojo meniu. Pavyzdžiui, pasirinkus **Anglų** kalbą bus sugrąžinta **„Copenhagen, Denmark”**, o ne **„København, Danmark”**.

1. Nurodykite papildymo pavadinimą.

1. Peržiūrėkite savo pasirinkimus ir pasirinkite **Įrašyti papildymą**.

## <a name="configure-the-connection-for-azure-maps"></a>„Azure” žemėlapių ryšio konfigūravimas

Turite būti auditorijos įžvalgų administratorius, kad galėtumėte konfigūruoti ryšius. Pasirinkite **Įtraukti ryšį** kai konfigūruojate papildymą arba eikite į **Administratorius** > **Ryšiai** ir pasirinkite **Nustatyti**, esantį „Azure“ žemėlapių plytelėje.

1. Lauke **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Pateikti galiojantį „Azure” žemėlapių API raktą.

1. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigę patikrinimą pasirinkite **Išsaugoti**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure žemėlapių ryšio konfigūravimo puslapis.":::

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklausys nuo kliento duomenų dydžio ir API atsako laiko.

Užbaigę papildymo procesą, galite peržiūrėti naujai papildytų klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Kiti veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai įgalinate „Dynamics 365 Customer Insights“ perduoti duomenis „Azure” žemėlapiams, leidžiate perduoti duomenis už „Dynamics 365 Customer Insights“ atitikties ribos, įskaitant galimai jautrius duomenis, pavyzdžiui, Asmens. „Microsoft" tokius duomenis perkels jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Azure“ žemėlapių privatumo arba saugos reikalavimai. Daugiau informacijos pateikta [„Microsoft” privatumo nuostatose](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
