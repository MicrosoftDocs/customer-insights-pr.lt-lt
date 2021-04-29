---
title: Bendrovės profilių praturtinimas su trečiosios šalies papildymo „Experian“
description: Bendra informacija apie „Experian“ trečiosios šalies praturtinimą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896383"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientų profilių papildymas demografiniais duomenimis iš „Experian” (peržiūros versija)

„Experian“ yra pasaulinis vartotojų ir verslo kreditų ataskaitų bei rinkodaros paslaugų lyderis. Naudodami „Experian” duomenų papildymo paslaugas, galite geriau suprasti savo klientus, papildydami savo klientų profilius tokiais demografiniais duomenimis kaip namų ūkių dydis, pajamos ir kt.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint sukonfigūruoti „Experian“, reikia atitikti toliau nurodytas būtinąsias sąlygas.

- Turite aktyvią „Experian“ prenumeratą. Jei norite gauti prenumeratą, [susisiekite su „Experian“](https://www.experian.com/marketing-services/contact) tiesiogiai. [Sužinokite daugiau apie „Experian“ duomenų papildymą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- „Experian“ ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises. Taip pat jums reikia naudotojo ID, šalies ID ir modelio numerio jūsų saugaus transportavimo (ST) paskyrai su įjungta SSK, kurią „Experian“ jums sukūrė.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. „Experian“ plytelėje pasirinkite **Papildyti mano duomenis**.

   > [!div class="mx-imgBorder"]
   > ![„Experian“ plytelė](media/experian-tile.png "„Experian“ plytelė")
   > 

1. Išskleidžiamajame sąraše pasirinkite [ryšį](connections.md). Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, ryšį galite sukurti ryšį pasirinkdami **Pridėti ryšį** ir išskleidžiamajame meniu pasirinkite „Experian“. 

1. Norėdami patvirtinti ryšio pasirinkimą pasirinkite **Prisijungti prie „Experian“**.

1.  Pasirinkite **Toliau** ir pasirinkite **Kliento duomenų rinkinys**, kurį norite papildyti demografiniais duomenimis iš „Experian“. Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Pažymėkite **Toliau** ir apibrėžkite, kokio tipo laukelius iš vieningųjų profilių reikėtų naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“. Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**. Kad tikslumas būtų didesnis, galima pridėti iki dviejų kitų laukelių. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

    > [!TIP]
    > Daugiau pagrindinių identifikatorių atributų siunčiant „Experian“, tikėtina, kad atitikimo rodiklis bus aukštesnis.

1. Norėdami pradėti laukelių žymėjimą, pasirinkite **Toliau**.

1. Apibrėžkite, kuriuos laukelius iš vieningųjų profilių reikėtų naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“. Laukeliai, kuriuos būtina užpildyti, pažymėti.

1. Pateikite papildymo pavadinimą ir išvesties objekto pavadinimą.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="configure-the-connection-for-experian"></a>„Experian“ ryšio konfigūravimas 

Jei norite konfigūruoti ryšius, turite būti administratorius. Pasirinkite **Pridėti ryšį**, kai konfigūruosite papildymą *arba* eikite į **Administravimas** > **Ryšiai** ir plytelėje „Experian“ pasirinkite **Sąranka**.

1. Pasirinkite **Darbo pradžia**.

1. Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Įveskite galiojantį „Experian“ saugaus transportavimo paskyros naudotojo ID, šalies ID ir modelio numerį.

1. Peržiūrėkite ir pateikite sutikimą dėl **Duomenų privatumo ir atitikties** pažymėdami žymės langelį **Sutinku**

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigę patikrinimą pasirinkite **Išsaugoti**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="„Experian“ ryšio konfigūravimo sritis.":::

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklausys nuo jūsų kliento duomenų dydžio ir „Experian“ nustatytų jūsų kliento papildymo procesų.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md), [matavimus](measures.md) ir net [eksportuokite duomenis](export-destinations.md), kad užtikrintumėte klientų poreikiams pritaikytą aptarnavimą.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Jums įjungus „Dynamics 365 Customer Insights“ duomenų perdavimui į „Experian“, leidžiate perduoti duomenis ne atitikties ribose „Dynamics 365 Customer Insights, įskaitant galimai jautrius duomenis, tokius kaip asmeniniai duomenys. „Microsoft“ perduos tokius duomenis pagal jūsų nurodymą, bet jūs esate atsakingi už tai, kad „Experian“ atitiks visus jūsų galimai prisiimtus privatumo ir saugos įsipareigojimus. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
