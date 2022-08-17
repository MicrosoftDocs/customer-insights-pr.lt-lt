---
title: Ryšių (peržiūros) apžvalga
description: Ryšiai su kitomis paslaugomis iš „Customer Insights“.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245521"
---
# <a name="connections-preview-overview"></a>Ryšių (peržiūros) apžvalga

Ryšiai yra pagrindinis duomenų bendrinimo į „Customer Insights“ ir iš jo raktas. Kiekvienas ryšys sukuria duomenų bendrinimą su konkrečia paslauga. Naudokite ryšius, kad sukonfigūruotumėte [trečiųjų šalių papildymus](enrichment-hub.md) ir [sukonfigūruotumėte eksportą](export-destinations.md). Tą patį ryšį galima naudoti kelis kartus. Pavyzdžiui, vienas ryšys su „Dynamics 365 Marketing“ veikia keliems eksportams, o vienas „Leadspace“ ryšys gali būti naudojamas keliems papildymams.

## <a name="export-connections"></a>Ryšių eksportavimas

Tik administratoriai gali konfigūruoti naujus ryšius, bet jie gali [suteikti prieigą bendraautoriams](#allow-contributors-to-use-a-connection-for-exports), kad jie galėtų naudoti esamus ryšius. Administratoriai valdo, kur gali būti perkeliami duomenys, bendradarbiai apibrėžia jų poreikius pagal apkrovą ir dažnumą.

## <a name="enrichment-connections"></a>Sodrinimo jungtys

Tik administratoriai gali konfigūruoti naujus ryšius, tačiau sukurti ryšiai visada pasiekiami tiek administratoriams, tiek bendraautoriams. Administratoriai valdo kredencialus ir sutinka, kad duomenys būtų perduoti. Tada administratoriai ir bendradarbiai ryšius gali naudoti papildymams.

## <a name="add-a-new-connection"></a>Pridėti naują ryšį

### <a name="prerequisites"></a>Būtinosios sąlygos

- [Administratoriaus teisės](permissions.md)
- Kitos "Microsoft" paslaugos, jei tokių yra, priklauso tai pačiai organizacijai

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite **Įtraukti ryšį** ir pasirinkite ryšio, kurį norite sukurti, tipą. Arba eikite į skirtuką **Atrasti** ir pasirinkite **Nustatyti** ryšio plytelėje.

1. Nurodykite atpažįstamą ryšio pavadinimą laukelyje **Rodyti pavadinimą**. Rodomas pavadinimas ir ryšio tipas apibūdina šį ryšį. Rekomenduojame pasirinkti pavadinimą, kuriame būtų paaiškintas ryšio tikslas ir paskirtis.

1. Įveskite reikiamą informaciją. Tikslūs laukai priklauso nuo to, prie kokios tarnybos jungiatės. Išsamesnės informacijos apie konkretų ryšio tipą ieškokite straipsnyje apie tikslinę paslaugą.

1. Jei [naudojate savo „Key Vault“](use-azure-key-vault.md) slaptai saugoti, suaktyvinkite **naudoti Key Vault** ir sąraše pasirinkite slaptą parinktį.

1. Peržiūrėkite duomenų privatumą ir atitiktį ir pasirinkite **Sutinku**.

1. Pasirinkite **Įrašyti**, kad sukurtumėte ryšį.

### <a name="data-privacy-and-compliance"></a>Duomenų privatumas ir atitiktis

Kai leidžiate Dynamics 365 Customer Insights perduoti duomenis trečiosioms šalims ar kitiems "Microsoft" produktams, leidžiate perduoti duomenis už atitikties ribos Dynamics 365 Customer Insights ribų, įskaitant galimai slaptus duomenis, pvz., Asmeninius duomenis. "Microsoft" perduos tokius duomenis jūsų nurodymu, tačiau jūs esate atsakingi už tai, kad trečioji šalis laikytųsi visų jūsų privatumo ar saugos įsipareigojimų. Dėl išsamesnės informacijos, žr. [„Microsoft“ pareiškimas dėl privatumo](https://go.microsoft.com/fwlink/?linkid=396732).

Jūsų Dynamics 365 Customer Insights administratorius gali bet kada pašalinti ryšį, kad nutrauktų funkcijų naudojimą.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Leidimas bendradarbiams naudoti ryšį eksportuojant

Nustatydami arba redaguodami eksportavimo ryšį, pasirinkite, kuriems vartotojams leidžiama naudoti šį konkretų ryšį eksportui [apibrėžti](export-destinations.md). Pagal numatytuosius nustatymus ryšys pasiekiamas vartotojams, turintiems administratoriaus vaidmenį. Pakeiskite parametrą **Pasirinkti, kas gali naudoti šį ryšį**, kad vartotojai, kurių bendradarbio vaidmuo yra, galėtų naudotis šiuo ryšiu.

- Bendradarbiai negalės peržiūrėti ar redaguoti ryšio. Kurdami eksportavimą jie matys tik rodomą pavadinimą ir jo tipą.
- Bendrindami ryšį leidžiate bendradarbiams naudoti ryšį. Nustatydami eksportavimą, bendradarbiai matys bendrai naudojamus ryšius. Jie gali valdyti kiekvieną eksportavimą, kuris naudoja šį konkretų ryšį.
- Šį parametrą galima keisti išlaikant eksportavimą, kurį jau yra nustatę bendradarbiai.

## <a name="manage-existing-connections"></a>Esamų ryšių valdymas

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite skirtuką **Papildymas** arba **Eksportavimas**, kad peržiūrėtumėte papildymo arba eksportavimo ryšių sąrašą, ryšio tipą, kada jis buvo sukurtas ir kas turi prieigą. Ryšių sąrašą galite rūšiuoti pagal bet kurį stulpelį.

1. Pasirinkite ryšį, kad peržiūrėtumėte galimus veiksmus.

   - **Redaguokite** ryšį.
   - [**Pašalinkite**](#remove-a-connection) ryšį.

### <a name="remove-a-connection"></a>Ryšio pašalinimas

Jei pašalinamas ryšys naudojamas praturtinant arba eksportuojant, pirmiausia jį atjunkite arba pašalinkite. Pašalinimo dialogo langas nukreipia jus į atitinkamus papildymus arba eksportavimą.

> [!TIP]
> Išjungti sodrinimas ir atskiras eksportas tampa neaktyvūs. Iš naujo suaktyvinate juos prie jų pridėdami kitą ryšį puslapyje [Papildymai](enrichment-hub.md) arba [Eksporavimai](export-destinations.md).

1. Eikite į **Administravimas** > **Ryšiai**.

1. Pasirinkite skirtuką **Papildymas** arba **Eksportavimas**.

1. Pasirinkite ryšį, kurį norite pašalinti.

1. Išskleidžiamajame meniu pasirinkite **Pašalinti**. Rodomos patvirtinimo dialogas.

   1. Jei naudojant šį ryšį atliekami papildymai ar eksportavimai, pažymėkite mygtuką, kad pamatytumėte, kas naudoja ryšį.
      - **Eksportavimas:** pasirinkite pašalinti **eksportavimą** arba **Atjungti ryšį**. Atjungus ryšį eksportavimo konfigūracija išlaikoma, tačiau ji nebus vykdoma, kol prie jos nebus pridėtas kitas ryšys.
      - **Papildymai:** pasirinkite naikinti **arba** **išjungti** papildymus.
   1. Kai ryšys nebeturi priklausomybių, grįžkite į **Administravimas** > **Ryšiai** ir dar kartą pabandykite pašalinti ryšį.

1. Jei norite patvirtinti trynimą, pasirinkite **Šalinti**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Ryšių su slaptais įrašais, kuriuos valdo jūsų „Key Vault“, nustatymas

Kai kuriems ryšiams reikia slaptai pvz., API raktų arba slaptažodžius. Kai kurie ryšiai palaiko slaptas informacijas, saugomas jūsų saugykloje „Key Vault“. Sužinokite daugiau apie palaikomus ryšius ir kaip nustatyti [savo "Key Vault for Customer Insights](use-azure-key-vault.md)".

[!INCLUDE [footer-include](includes/footer-banner.md)]
