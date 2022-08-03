---
title: Klientų profilių pagerinimo naudojant demografijas „Experian“ (peržiūra)
description: Bendroji informacija apie „Experian“ trečiosios šalies pratinimą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 876853ab42e8c08ad1abacb8d8a205c0aadabcf7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195946"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientų profilių pagerinimo naudojant demografijas „Experian“ (peržiūra)

„Experian“ yra visuotinis vartotojų ir verslo kredito ataskaitų ir rinkodaros paslaugų lyderis. Savo duomenų gerinimo paslaugomis galite geriau suprasti savo klientus, praturtindami savo klientų profilius demografiniais duomenimis, pvz., dėl demografinių duomenų, pvz., dėl demografinių priežasčių dydžio, pajamų ir „Experian“ kt.

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikome tik Jungtinių Amerikos Valstijų klientų profilių gerinimo palaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi Experian prenumerata. Norėdami gauti prenumeratą, [kreipkitės„ Experian“](https://www.experian.com/marketing-services/contact) tiesiai. [Sužinokite daugiau apie „Experian“ duomenų praturtinimą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Ryšį Experian [...](connections.md)[sukonfigūruoja](#configure-the-connection-for-experian) administratorius.

- Experian Jums sukurtos saugaus transporto (ST) paskyros, kurioje Experian įgalintas SSH, vartotojo ID, šalies ID ir modelio numeris.

## <a name="configure-the-connection-for-experian"></a>Ryšio konfigūravimas „Experian“

Turite būti ["Customer Insights" administratorius](permissions.md#admin) ir turėti Experian vartotojo ID, šalies ID ir modelio numerį.

1. Konfigūruojant papildymą pasirinkite **Įtraukti ryšį** arba eikite į **Administratoriaus** > **ryšiai** ir plytelėje **pasirinkite** Nustatyti Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ryšio konfigūravimo juosta.":::

1. Įveskite ryšio pavadinimą ir galiojantį saugaus transportavimo paskyros vartotojo ID, šalies ID ir modelio numerį Experian.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patvirtintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis, „Dynamics 365 Customer Insights“ ir „Experian“ bei „Dynamics 365 Customer Insights“ pvz., Asmeninius duomenis. „Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Experian“ privatumo arba saugos apsauga. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732). Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Pasirinkite **Papildyti mano duomenis, esantį plytelėje** Demografiniai **rodikliai** iš Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian plytelė papildymo apžvalgos puslapyje.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei ryšio nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite papildyti demografinių rodiklių duomenimis iš Experian. *Kliento* objektas praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Apibrėžkite, kokio tipo laukus iš savo vieningųjų profilių naudoti demografinių rodiklių duomenims iš Experian. Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**. Norėdami gauti didesnį atitikties tikslumą, įtraukite kitus laukus. Pasirinkite **Toliau**.

1. Susiekite laukus su demografiniais duomenimis iš Experian.

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite papildymo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte papildymo procesą, arba uždarykite, kad grįžtumėte į **puslapį Papildymai**.

## <a name="view-enrichment-results"></a>Papildymo rezultatų peržiūra

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lauku **praturtintų** klientų skaičius leidžia detalizuoti kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
