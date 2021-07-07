---
title: Papildymas trečiųjų šalių pratinimas „Experian“
description: Bendroji informacija apie „Experian“ trečiosios šalies pratinimą.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309830"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientų profilių pagerinimo naudojant demografijas „Experian“ (peržiūra)

„Experian“ yra visuotinis vartotojų ir verslo kredito ataskaitų ir rinkodaros paslaugų lyderis. Savo duomenų gerinimo paslaugomis galite geriau suprasti savo klientus, praturtindami savo klientų profilius demografiniais duomenimis, pvz., dėl demografinių duomenų, pvz., dėl demografinių priežasčių dydžio, pajamų ir „Experian“ kt.

## <a name="prerequisites"></a>Būtinosios sąlygos

Norint konfigūruoti „Experian“, reikia įvykdyti šias būtinąsias sąlygas:

- Turite turėti aktyvią „Experian“ prenumeratą. Norėdami gauti prenumeratą, [kreipkitės„ Experian“](https://www.experian.com/marketing-services/contact) tiesiai. [Sužinokite daugiau apie „Experian“ duomenų praturtinimą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- „Experian“ ryšį jau sukonfigūravo administratorius *arba* turite [administratoriaus](permissions.md#administrator) teises. Taip pat jums reikia sukurto jūsų SSH apsaugoto transportavimo (ST) abonemento vartotojo ID, šalies ID ir „Experian“ modelio numerio.

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikome tik Jungtinių Amerikos Valstijų klientų profilių gerinimo palaikymą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje pažymėkite **Papildyti mano**, kuris yra „Experian“ duomenis.

   > [!div class="mx-imgBorder"]
   > ![Experian plytele](media/experian-tile.png "Experian tile")
   > 

1. Pasirinkite [ryšį](connections.md) iš iškrentančiojo sąrašo. Jei ryšio nėra, kreipkitės į administratorių. Jei esate administratorius, galite sukurti ryšį pasirinkdami **Įtraukti ryšį** ir „Experian“ pasirinkdami iš išplečiamojo sąrašo. 

1. Pasirinkite **Prisijungti ir Experian** patvirtinkite pasirinktą ryšį.

1.  Pasirinkite **Kitas** ir rinkitės **Kliento duomenų rinkinys** , kurį norite papildyti demografiniais duomenimis iš „Experian“. Galite pažymėti objektą **Klientas**, kad pagerintumėte visus jūsų klientų profilius, arba pasirinkti segmento objektą, kad būtų papildyti tik to segmento klientų profiliai.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Pažymėkite **Kitas** ir apibrėžkite, kokio tipo laukus iš vieningųjų profilių reikia naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“. Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**. Kad tikslumas būtų didesnis, galima pridėti iki dviejų kitų laukelių. Šis pasirinkimas turės įtakos žymėjimo laukeliams, prie kurių turite prieigą atlikdami kitą veiksmą.

    > [!TIP]
    > Daugiau pagrindinių identifikatoriaus atributų, siunčiamų „Experian“ taip, kad atitikties lygis tikriausiai būtų didesnis.

1. Norėdami pradėti laukelių žymėjimą, pasirinkite **Toliau**.

1. Nustatykite laukus ir apibrėžkite, kokio tipo laukus iš vieningųjų profilių reikia naudoti, kad būtų ieškoma sutampančių demografinių duomenų iš „Experian“. Laukeliai, kuriuos būtina užpildyti, pažymėti.

1. Pateikite papildymo pavadinimą ir išvesties objekto pavadinimą.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

## <a name="configure-the-connection-for-experian"></a>Ryšio konfigūravimas „Experian“ 

Jei norite konfigūruoti ryšius, turite būti administratorius. Rinkitės **Įtraukti ryšį** kai konfigūruojate papildymą *ar* eikite į **Administratorius** > **ryšiai** ir rinkitės **Nustatyti** esantį „Experian“ plytelėje.

1. Pasirinkite **Darbo pradžia**.

1. Laukelyje **Rodomas pavadinimas** įveskite ryšio pavadinimą.

1. Įveskite galiojantį apsaugoto transportavimo abonemento vartotojo ID, šalies ID „Experian“ ir modelio numerį.

1. Pasirinkdami Sutinku, peržiūrėkite **ir pateikite savo sutikimą dėl** duomenų privatumo ir sąlygų **sutinku**.

1. Pažymėkite **Patvirtinti**, kad patvirtintumėte konfigūraciją.

1. Baigę patikrinimą pasirinkite **Išsaugoti**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ryšio konfigūravimo juosta.":::

## <a name="enrichment-results"></a>Papildymo rezultatai

Norėdami pradėti papildymo procesą, komandų juostoje pasirinkite **Vykdyti**. Taip pat galite leisti sistemai vykdyti papildymą automatiškai kaip [suplanuoto atnaujinimo](system.md#schedule-tab) dalį. Apdorojimo laikas priklauso nuo kliento duomenų dydžio ir jūsų klientui nustatytų gerinimo „Experian“ procesų.

Pasibaigus papildymo procesui, galite peržiūrėti naujai papildytus klientų profilių duomenis dalyje **Mano papildymai**. Be to, rasite vėliausio naujinimo laiką ir papildytų profilių skaičių.

Išsamų kiekvieno papildyto profilio rodinį galite pasiekti pasirinkę **Peržiūrėti papildytus duomenis**.

## <a name="next-steps"></a>Tolesni veiksmai

Atlikite veiksmus su papildytais klientų duomenimis. Kurkite [segmentus](segments.md) ir [priemones](measures.md) bei net [eksportuokite duomenis,](export-destinations.md) kad klientams būtų galima teikti personalizuotas funkcijas.

## <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis, „Dynamics 365 Customer Insights“ ir „Experian“ bei „Dynamics 365 Customer Insights“ pvz., Asmeninius duomenis. „Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Experian“ privatumo arba saugos apsauga. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).
Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
