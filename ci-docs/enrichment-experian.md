---
title: Papildymas trečiųjų šalių pratinimas „Experian“
description: Bendroji informacija apie „Experian“ trečiosios šalies pratinimą.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954097"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Klientų profilių pagerinimo naudojant demografijas „Experian“ (peržiūra)

„Experian“ yra visuotinis vartotojų ir verslo kredito ataskaitų ir rinkodaros paslaugų lyderis. Savo duomenų gerinimo paslaugomis galite geriau suprasti savo klientus, praturtindami savo klientų profilius demografiniais duomenimis, pvz., dėl demografinių duomenų, pvz., dėl demografinių priežasčių dydžio, pajamų ir „Experian“ kt.

## <a name="supported-countriesregions"></a>Palaikomos šalys ir (arba) regionai

Šiuo metu palaikome tik Jungtinių Amerikos Valstijų klientų profilių gerinimo palaikymą.

## <a name="prerequisites"></a>Būtinosios sąlygos

- Aktyvi Experian prenumerata. Norėdami gauti prenumeratą, [kreipkitės„ Experian“](https://www.experian.com/marketing-services/contact) tiesiai. [Sužinokite daugiau apie „Experian“ duomenų praturtinimą](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Ryšį Experian [...](connections.md)[konfigūruoja](#configure-the-connection-for-experian) administratorius.

- Experian Vartotojo ID, šalies ID ir modelio numeris jūsų SSH palaikančiai saugaus transporto (ST) paskyrai, kuri Experian buvo sukurta jums.

## <a name="configure-the-connection-for-experian"></a>Ryšio konfigūravimas „Experian“

Turite būti "Customer Insights" administratorius [ir](permissions.md#admin) turėti Experian vartotojo ID, šalies ID ir modelio numerį.

1. Konfigūruodami sodrinimą pasirinkite **Įtraukti ryšį** arba eikite į **Administravimo** > **ryšiai** ir plytelėje **pasirinkite** Nustatyti Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ryšio konfigūravimo juosta.":::

1. Įveskite ryšio pavadinimą ir galiojantį saugaus transporto abonemento vartotojo ID, šalies ID ir modelio numerį Experian.

1. Pasirinkdami Sutinku, peržiūrėkite [ir pateikite savo sutikimą dėl](#data-privacy-and-compliance) duomenų privatumo ir sąlygų **sutinku**.

1. Pasirinkite **Tikrinti**, kad patikrintumėte konfigūraciją, tada pasirinkite **Įrašyti**.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate perduoti duomenis į, leidžiate perduoti duomenis už tos sienos ribų, įskaitant galimai slaptus duomenis, „Dynamics 365 Customer Insights“ ir „Experian“ bei „Dynamics 365 Customer Insights“ pvz., Asmeninius duomenis. „Microsoft" tokius duomenis perims jūsų nurodymu, tačiau esate atsakingas už tai, kad būtų užtikrinta „Experian“ privatumo arba saugos apsauga. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732). Jūsų „Dynamics 365 Customer Insights“ administratorius gali pašalinti šį praturtinimą bet kuriuo metu siekiant nutraukti šios funkcijos naudojimą.

## <a name="configure-the-enrichment"></a>Papildymo konfigūravimas

1. Pasirinkite **Duomenys** > **Papildymas** ir pasirinkite skirtuką **Atrasti**.

1. Plytelėje **pasirinkite** Praturtinti mano duomenis **demografinėje** Experian raidėje.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian plytelė sodrinimo apžvalgos puslapyje.":::

1. Peržiūrėkite apžvalgą ir pasirinkite **Pirmyn**.

1. Pasirinkite ryšį. Jei jo nėra, kreipkitės į administratorių.

1. Pasirinkite **Toliau**.

1. **Pasirinkite kliento duomenų rinkinį** ir pasirinkite profilį arba segmentą, kurį norite praturtinti demografiniais duomenimis iš Experian. Kliento *subjektas* praturtina visus jūsų klientų profilius, o segmentas praturtina tik tame segmente esančius klientų profilius.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Klientų duomenų rinkinio pasirinkimo momentas.":::

1. Nurodykite, kokio tipo laukus iš vieningų profilių naudoti demografiniams duomenims iš Experian. Būtina užpildyti bent vieną iš šių laukelių: **Vardas, pavardė ir adresas**, **Telefonas** arba **El. paštas**. Jei norite didesnio rungtynių tikslumo, pridėkite kitų laukų. Pasirinkite **Toliau**.

1. Susiekite laukus su demografiniais duomenimis iš Experian.

1. Norėdami baigti laukelių žymėjimą, pasirinkite **Toliau**.

1. **Pateikite sodrinimo pavadinimą** ir išvesties objekto **pavadinimą**.

1. Peržiūrėję pasirinkimus pasirinkite **Išsaugoti papildymą**.

1. Pasirinkite **Vykdyti**, kad pradėtumėte sodrinimo procesą, arba beveik, kad grįžtumėte į **puslapį Praturtinimai**.

## <a name="enrichment-results"></a>Papildymo rezultatai

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Klientų **, praturtintų pagal lauką**, skaičius suteikia detalizuotą kiekvieno praturtinto lauko aprėptį.

## <a name="next-steps"></a>Paskesni veiksmai

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
