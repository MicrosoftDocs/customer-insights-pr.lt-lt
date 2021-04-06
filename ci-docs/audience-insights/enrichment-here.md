---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „HERE Technologies“
description: Bendra informacija apie „HERE Technologies“ trečiosios šalies papildymą.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597751"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Tinkintų profilių papildymas su „HERE Technologies“ (peržiūra)

„HERE Technologies“ yra vietos platformos bendrovė, kuri pateikia vietos centro duomenis ir paslaugas. Su „HERE Technologies“ duomenų praturtinimo paslaugomis galite sukurti tikslesnį supratimą apie jūsų klientų vietą su adreso normalizavimu, pločio ir ilgio išplėtimu ir daugiau.

## <a name="prerequisites"></a>Būtinosios sąlygos

Siekiant sukonfigūruoti „HERE Technologies“ papildymus, būtina atitikti tolesnes būtinąsias sąlygas:

- Turite turėti „HERE Technologies“ prenumeratą. Norėdami gauti prenumeratą galite [prisijungti čia](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ar [susisiekti su „HERE Technologies“](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) tiesiogiai. [Sužinokite daugiau apie vietos papildymą su „HERE Technologies“.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Turite „HERE Technologies“ API raktą.

- Turite [Administratoriaus](permissions.md#administrator) teises.

## <a name="configuration"></a>Konfigūracija

1. Eikite į **Duomenys** > **Papildymas**.

1. Pasirinkite **Papildykite savo duomenis** apie „HERE Technologies“ plytą.

   > [!div class="mx-imgBorder"]
   > ![„HERE Technologies“ plytą](media/HERE-tile.png "„HERE Technologies“ plytą")

1. Įveskite aktyvų **„HERE Technologies“ API raktą**. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**. 

1. Patvirtinkite abi įvestis pasirinkdami **Sujungti su „HERE“**.

1.  Pasirinkite **Įtraukti duomenis** ir pasirinkite **kliento duomenų rinkinį,** kurį norite papildyti demografiniais duomenimis iš „HERE Technologies“. Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Pasirinkite, ar laukus norite susieti su pirminiu ir (arba) antriniu adresu. Galite nurodyti laukelio susiejimą abiem adresams (pavyzdžiui, namų ir verslo adresui) ir papildyti profilius abiem adresais atskirai. Pasirinkite **Toliau**.

1. Nustatykite, kurie laukeliai iš jūsų suvienodintų profilių turi būti naudojami ieškoti atitinkančių vietos duomenų iš „HERE Technologies“. **Gatvė 1** ir **Pašto/Zip kodas** laukeliai yra būtini pasirinktam priminiam ir (arba) antrinį adresą. Didesniam atitikties tikslumui, galima įtraukti daugiau laukelių.

   > [!div class="mx-imgBorder"]
   > ![„HERE Technologies“ papildymo konfigūravimo puslapis](media/enrichment-HERE-configuration.png "„HERE Technologies“ papildymo konfigūravimo puslapis")

1. Pasirinkite **Taikyti** tam, kad užbaigtumėte laukelio žemėlapio kūrimą.

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo jūsų kliento duomenų dydžio ir API atsakymo laiko iš „HERE Technologies“.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „HERE Technologies“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „HERE Technologies“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]