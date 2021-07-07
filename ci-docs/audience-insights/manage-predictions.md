---
title: Bendrai naudojamos prognozės scenarijų užduotys
description: Sužinokite, kaip valdyti, šalinti triktis ir tikslinti prognozes.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315888"
---
# <a name="manage-predictions"></a>Prognozių valdymas

Šiame straipsnyje aptariama keletas užduočių, kurios yra bendros daugumai prognozės scenarijų.

## <a name="troubleshoot-a-failed-prediction"></a>Nepavykusios prognozės trikčių šalinimas

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite vertikalias elipses šalia prognozės, kuriose norite peržiūrėti klaidų žurnalus.

1. Pasirinkite **Žurnalai**.

1. Peržiūrėkite visas klaidas. Galimos kelių tipų klaidos, kurios aprašo, kokia būsena sukėlė klaidą. Pavyzdžiui, klaida, kuri įvyko, nes nepakanka duomenų tiksliai prognozei, įprastai yra išsprendžiama įkeliant papildomų duomenų į „Customer Insights“.

## <a name="input-data-usability-report"></a>Įvesties duomenų naudojimo ataskaita

Įvesties duomenų naudojimo ataskaita pateikia klaidų ir įspėjimų, kuriuos gali sugeneruoti jūsų visiškai parengtos prognozės, apibendrintą rodinį. Joje taip pat pateikiama rekomendacijų, kaip pagerinti modelio efektyvumą.

Ataskaita yra pasiekiama atlikus modelio mokymo procesą. Ji sukuriama kiekvienam modeliui atskirai, neatsižvelgiant į tai, ar jis užbaigtas sėkmingai.

### <a name="view-the-input-data-usability-report"></a>Peržiūrėti įvesties duomenų naudojimo ataskaitą

Užbaigę mokymo veiksmą visiškai parengtam modeliui, peržiūrėkite ataskaitą:
- Pasirinkite elipses prie modelio pavadinimo ir pasirinkite **Įvesties duomenų naudojimo ataskaita**.
- Pasirinkite modelio būseną ir **Peržiūrėti įvesties duomenų naudojimo ataskaitą** šoninėje srityje.
- Pasirinkite vieną modelį iš sąrašo ir **Įvesties duomenų naudojimo ataskaita** komandų juostoje.
- Atidarykite modelio rezultatų puslapį ir pasirinkite **Įvesties duomenų naudojimo ataskaita** komandų juostoje.

### <a name="information-in-the-input-data-usability-report"></a>Informacija įvesties duomenų naudojimo ataskaitoje

Toliau pateiktuose ataskaitos stulpeliuose yra naudingos informacijos apie tai, kaip patobulinti modelio duomenis.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Įvesties duomenų naudojimo ataskaitos, rodančios lentelę su klaidomis, įspėjimais ir rekomendacijomis, pavyzdys.":::

- Pavadinimas: Aprašomasis klaidos, įspėjimo arba rekomendacijos pavadinimas.
- Veiksmas: Modelio etapas, mokymas ar įvertinimas, nurodoma informacija.
- Būsena: Informacijos svarba (klaida, įspėjimas, rekomendacija).
- Stulpelio pavadinimas: Objekto, kurį reikia modifikuoti, kad būtų pagerintas modelio efektyvumas, stulpelis.
- Objekto pavadinimas: Objekto, kurį reikia modifikuoti, kad būtų pagerintas modelio efektyvumas, pavadinimas.
- Išsami informacija: Išsami informacija apie klaidą, įspėjimą arba rekomendaciją.

## <a name="refresh-a-prediction"></a>Prognozės atnaujinimas

Prognozės automatiškai atsinaujins tuo pačiu parametruose sukonfigūruotu [grafiku, kuriuo atnaujinami jūsų duomenys](system.md#schedule-tab). Galite juos paleisti iš naujo ir rankiniu būdu.

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite vertikalius daugtaškius šalia norimos atnaujinti prognozės.

1. Pasirinkite **Atnaujinti**.

## <a name="delete-a-prediction"></a>Prognozės šalinimas

Prognozės panaikinimas taip pat pašalina jos išvesties objektą.

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite vertikalius daugtaškius šalia norimos pašalinti prognozės.

1. Pasirinkite **Naikinti**.