---
title: Papildymas trečiųjų šalių pratinimas „HERE Technologies“
description: Bendra informacija apie „HERE Technologies“ trečiosios šalies papildymą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376361"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tinkintų profilių papildymas su „HERE Technologies“ (peržiūra)

„HERE Technologies“ yra vietos platformos bendrovė, kuri pateikia vietos centro duomenis ir paslaugas. Su „HERE Technologies“ duomenų praturtinimo paslaugomis galite sukurti tikslesnį supratimą apie jūsų klientų vietą su adreso normalizavimu, pločio ir ilgio išplėtimu ir daugiau.

## <a name="prerequisites"></a>Būtinosios sąlygos

Siekiant sukonfigūruoti „HERE Technologies“ papildymus, būtina atitikti tolesnes būtinąsias sąlygas:

- Turite turėti „HERE Technologies“ prenumeratą. Norėdami gauti prenumeratą galite [prisijungti čia](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ar [susisiekti su „HERE Technologies“](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tiesiogiai. [Sužinokite daugiau apie vietos papildymą su „HERE Technologies“.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [ryšys](connections.md) yra prieinamas *ar* turite [administratoriaus](permissions.md#admin) teises ir „HERE Technologies“ API raktą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Eikite į **Duomenys** > **Papildymas**. 

1. „HERE Technologies“ plytelėje pasirinkite **Papildyti mano duomenis** ir pasirinkite **Darbo pradžia**.

   > [!div class="mx-imgBorder"]
   > ![„HERE Technologies“ plytelė.](media/HERE-tile.png "„HERE Technologies“ plytą")

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, ryšį galite nustatyti pasirinkdami **Pridėti ryšį**. Rinkitės **HERE Technologies** iš iškrentančiojo sąrašo. 

1. Norėdami patvirtinti pasirinkimą rinkitės **Jungtis prie „HERE Technologies“**.

1.  Pasirinkite **Toliau** ir rinkitės tą **kliento duomenų rinkinį**, kurį norite papildyti vietos duomenimis iš „HERE Technologies“. Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Pasirinkite, ar laukus norite susieti su pirminiu ir (arba) antriniu adresu. Laukelių žymėjimą galima nurodyti abiem adresams ir papildyti profilius abiems adresams atskirai. Pavyzdžiui, jei yra namų ir įmonės adresas. Pasirinkite **Toliau**.

1. Nustatykite, kurie laukeliai iš jūsų suvienodintų profilių turi būti naudojami ieškoti atitinkančių vietos duomenų iš „HERE Technologies“. **Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą. Didesniam atitikties tikslumui, galima įtraukti daugiau laukelių.

   > [!div class="mx-imgBorder"]
   > ![„HERE Technologies“ papildymo konfigūravimo puslapis.](media/enrichment-HERE-configuration.png "„HERE Technologies“ papildymo konfigūravimo puslapis")

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. Nurodykite papildymo pavadinimą. 

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="configure-the-connection-for-here-technologies"></a>„HERE Technologies“ ryšio konfigūravimas 

Jei norite konfigūruoti ryšius, turite būti administratorius. Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir plytelėje „HERE Technologies“ pasirinkite **Sąranka**.

1. Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Pateikite galiojantį „HERE Technologijų“ API raktą.

1. Pasirinkdami Sutinku, peržiūrėkite **ir pateikite savo sutikimą dėl** duomenų privatumo ir sąlygų **sutinku**.

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigę patikrinimą pasirinkite **Išsaugoti**.

   > [!div class="mx-imgBorder"]
   > ![„HERE Technologies“ ryšio konfigūravimo puslapis.](media/enrichment-HERE-connection.png "„HERE Technologies“ ryšio konfigūravimo puslapis")

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio ir API atsakymo laiko iš „HERE Technologies“.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Kiti veiksmai

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „HERE Technologies“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „HERE Technologies“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
