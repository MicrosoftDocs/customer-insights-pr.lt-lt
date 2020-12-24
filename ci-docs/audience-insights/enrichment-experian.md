---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „Experian“
description: Bendra informacija apie „Experian“ trečiosios šalies praturtinimą.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668822"
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

1. Pasirinkite **Įtraukti duomenis** ir pasirinkite savo pagrindinius identifikatorius laukų **Vardas ir adresas**, **El. pašto adresas** arba **Telefono numeris**, kad jie būtų siunčiami „Experian“ tapatybei patvirtinti.

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