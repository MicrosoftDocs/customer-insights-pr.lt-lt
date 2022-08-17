---
title: Prognozių valdymas
description: Sužinokite, kaip valdyti, šalinti triktis ir tikslinti prognozes.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 42abfb305efaccaeef48e32f2cc69f3d36fbe73d
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245475"
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

- **Pavadinimas:** aprašomasis klaidos, įspėjimo arba rekomendacijos pavadinimas.
- **Žingsnis:** Modelio fazė, traukinys ar balas, informacija nurodo.
- **Būsena:** informacijos rimtumas (klaida, įspėjimas, rekomendacija).
- **Stulpelio pavadinimas:** stulpelis objekte, kurį reikia modifikuoti, kad būtų pagerintas modelio našumas.
- **Objekto pavadinimas:** objekto, kurį reikia modifikuoti, kad būtų pagerintas modelio našumas, pavadinimas.
- **Išsami informacija:** išsami informacija apie klaidą, įspėjimą arba rekomendaciją.

## <a name="refresh-a-prediction"></a>Prognozės atnaujinimas

Prognozės automatiškai atsinaujins tuo pačiu parametruose sukonfigūruotu [grafiku, kuriuo atnaujinami jūsų duomenys](schedule-refresh.md). Galite juos paleisti iš naujo ir rankiniu būdu.

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite vertikalius daugtaškius šalia norimos atnaujinti prognozės.

1. Pasirinkite **Atnaujinti**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Prognozės šalinimas

Prognozės panaikinimas taip pat pašalina jos išvesties objektą.

1. Eikite į **Įžvalga** > **Prognozės** ir pasirinkite **Mano prognozės** skirtuką.

1. Pasirinkite vertikalius daugtaškius šalia norimos pašalinti prognozės.

1. Pasirinkite **Naikinti**.
