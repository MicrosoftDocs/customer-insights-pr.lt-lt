---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „Experian“
description: Bendra informacija apie „Experian“ trečiosios šalies praturtinimą.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269570"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientų profilių papildymas demografiniais duomenimis iš „Experian” (peržiūros versija)

„Experian“ yra pasaulinis vartotojų ir verslo kreditų ataskaitų bei rinkodaros paslaugų lyderis. Naudodami „Experian” duomenų papildymo paslaugas, galite geriau suprasti savo klientus, papildydami savo klientų profilius tokiais demografiniais duomenimis kaip namų ūkių dydis, pajamos ir kt.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint sukonfigūruoti „Experian“, reikia atitikti toliau nurodytas būtinąsias sąlygas.

- Turite aktyvią „Experian“ prenumeratą. Jei norite gauti prenumeratą, [susisiekite su „Experian“](https://www.experian.com/marketing-services/contact) tiesiogiai. [Sužinokite daugiau apie „Experian“ duomenų papildymą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Turite vartotojo ID, partijos ID ir modelio numerį, skirtus jūsų SSH įjungtame „Secure Transport“ (ST) kliente, kurį „Experian“ sukūrė jums.
- Turite [Administratoriaus](permissions.md#administrator) teises publikos įžvalgose.

## <a name="configuration"></a>Konfigūracija

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. „Experian“ plytelėje pasirinkite **Papildyti mano duomenis**.

   > [!div class="mx-imgBorder"]
   > ![„Experian“ plytelė](media/experian-tile.png "„Experian“ plytelė")

1. Pasirinkite **Pradžia** ir įveskite vartotojo ID, šalies ID ir savo „Experian“ „Secure Transport“ kliento modelio numerį. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**. Patvirtinkite visas įvestis pasirinkdami **Taikyti**.

## <a name="map-your-fields"></a>Susiekite savo laukus

1.  Pasirinkite **Įtraukti duomenis** ir pasirinkite **kliento duomenų rinkinį,** kurį norite papildyti demografiniais duomenimis iš „Experian“. Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

1. Pasirinkite raktų identifikatorius iš **Vardo ir adreso**, **El. pašto** arba **Telefono**, kad būtų galima siųsti į  „Experian“ tapatybės tikrinimui.

   > [!TIP]
   > Daugiau pagrindinių identifikatorių atributų siunčiant „Experian“, tikėtina, kad atitikimo rodiklis bus aukštesnis.

1. Pasirinkite **Toliau** ir susiekite atitinkamus pasirinktų rakto identifikatoriaus laukų atributus iš savo vieningojo kliento objekto.

1. Pasirinkite **Įtraukti atributą**, kad susietumėte bet kokius papildomus atributus, kuriuos norite siųsti „Experian“.

1.  Spustelėkite **Įrašyti**, kad baigtumėte susieti laukus.

    > [!div class="mx-imgBorder"]
    > ![„Experian“ laukų susiejimas](media/experian-field-mapping.png "„Experian“ laukų susiejimas")

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklausys nuo jūsų kliento duomenų dydžio ir „Experian“ nustatytų jūsų kliento papildymo procesų.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Experian“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Experian“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įpareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]