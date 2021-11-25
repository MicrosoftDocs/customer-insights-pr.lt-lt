---
title: Kurti naują aplinką
description: Aplinkos tikslas ir kaip kurti naują aplinką.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673652"
---
# <a name="create-a-new-environment"></a>Kurti naują aplinką 

## <a name="overview"></a>Apžvalga

Aplinka yra vieta, kurioje valdote savo darbo sritis ir ryšius. Kaip naudoti aplinkas, priklauso nuo jūsų organizacijos ir atvejo. Pavyzdžiui, galite kurti:

- Vieną aplinką.
- Atskiros tikrinimo ir gamybos aplinkos.
- Atskiros konkrečių jūsų organizacijos komandų ar skyrių aplinkos, kuriose yra kiekvienos auditorijos aktualių įvykių.
- Atskiras skirtingų jūsų įmonės visuotinių šakų aplinkas.
- Jungtys su „Customer Insights“ publikos įžvalgų galimybėmis.

## <a name="create-a-new-environment"></a>Kurti naują aplinką

1. Dešinėje pagrindinės reklaminės juostos pusėje pažymėkite aplinkos parinktuvą, tada **+ Naujas**.

   :::image type="content" source="media/environment-picker.png" alt-text="Rinkitės aplinkos parinkiklį..":::

1. Sąrankos **srityje** įveskite **aplinkos pavadinimą**.

1. Atsižvelgdami į **savo** plano tipą, pasirinkite kliento tipą.

1. Pasirinkite **Regioną** ir pasirinkite **Kitas**. 

1. Įveskite **darbo srities pavadinimą**, kuris leidžia rinkti duomenis konkrečioms svetainėms ar programoms. Daugiau informacijos žr. dalyje [Darbo srities kūrimas](create-workspace.md).

1. Pasirinkite darbo **srities tipą** (žiniatinklį arba mobilųjį), kurį norite sukurti. 

1. Pasirinkite **Rodyti išplėstinius parametrus** kad įjungtumėte arba išjungtumėte šiuos pasirinktinius parametrus:

   - Perjunkite **nežinomas ir žinomą** kaip "įjungtas", kad susietumėte žiniatinklio įvykius su vartotojais, kurie anksčiau buvo autentifikuoti. Daugiau informacijos ieškokite [Atpažinkite anksčiau autentifikuotų lankytojų žiniatinklio įvykius](unknown-to-known.md).
   - Perjunkite **filtro žiniatinklio srautą** į „įjungtas", kad pašalintumėte žiniatinklio srautą iš šios darbo srities. 

1. Rinkitės **Atlikti** baigę veiksmus. 

1. Įdiekite duomenų kodo fragmentas, kad būtų pradėti gauti duomenys, tada pasirinkite **Baigti** kad sukurtumėte darbo sritį. Daugiau informacijos žr. [Kūrėjų resursų apžvalga](developer-resources.md).

> [!NOTE]
> Dabar galite įtraukti narius ir priskirti jų teisių lygį iš **vaidmenų** sąrašo. Daugiau informacijos, žr. [Vaidmenys ir teisės](user-roles.md). 

Daugiau informacijos žr. [Aplinkos ir darbo sričių valdymas](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Darbas su nauja aplinka

- [Kurti darbo sritį](../engagement-insights/create-workspace.md) ir įtraukti narius.
- [Įtraukite kodą į svetainę](../engagement-insights/instrument-website.md) arba [„mobile app“](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Peržiūrėkite [ataskaitą realiuoju laiku](../engagement-insights/view-reports.md) arba kurkite [pasirinktines ataskaitas](../engagement-insights/custom-reports.md).
- [Kurti tobulintimus eksportavimo](../engagement-insights/refined-events.md) įvykius.
- [Eksportuokite duomenis į](../engagement-insights/export-events.md) „Data Lake Storage“.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
