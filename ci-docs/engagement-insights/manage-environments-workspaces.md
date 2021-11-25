---
title: Darbo sričių ir aplinkos valdymas
description: Kaip kurti, pervardyti ir panaikinti darbo sritis ir aplinkas.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673807"
---
# <a name="manage-environments-and-workspaces"></a>Valdyti aplinkas ir darbo aplinkas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Apžvalga

Šioje temoje aptariama, kaip valdyti darbo sritis ir aplinkas jau sukūrus. 

- Tai *Darbo sritis* yra vieta įvykiams ir ataskaitoms saugoti ir valdyti. Čia galite peržiūrėti vartotojo veiklą tikruuoju laiku. Kurdami darbo sritį, pažymėkite duomenų, ties kuriuos siųsite į darbo sritį. Šiuo metu palaikomi žiniatinklio duomenys ir mobiliųjų įrenginių programos. Daugiau informacijos ieškokite [Create a new workspace and add members](create-workspace.md).

- Tai *Aplinka* yra vieta, kurioje valdote savo darbo sritis ir ryšius. Daugiau informacijos žiūrėkite [Naujos aplinkos kūrimas](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Valdyti esamą darbo sritį

Aplinkoje galite turėti kelias darbo sritis, kurios veikia sklandžiai. Jūsų [vaidmuo](user-roles.md) apibrėžia, kaip galite su jais dirbti. 

 - Jei norite valdyti aplinką, turite būti darbo srities administratorius arba darbo srities administratorius.
 - Kaip darbo srities administratorius galite pervardyti esamas darbo sritis arba jas panaikinti. 

:::image type="content" source="media/workspace-edit.png" alt-text="Darbo srities administratorius centras.":::

### <a name="edit-a-workspace-name"></a>Redaguoti darbo srities pavadinimą

1. Eikite į **Administratorius** > **Darbo sritis** ir rinkitės **Nustatymai**.

1. Laukelyje **Darbo srities pavadinimas** įveskite naują pavadinimą.

1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

### <a name="delete-a-workspace"></a>Naikinti darbo sritį

Panaikinus darbo sritį visam laikui pašalinamas visas jos turinys, duomenys, parametrai ir teisės. Anuliuoti negalėsite.

1. Eikite į **Administratorius** > **Darbo sritis** ir rinkitės **Nustatymai**.

1. Pasirinkite **Naikinti darbo sritį**. 

1. Dialogo lange **Naikinti darbo aplinkos** lauką ir įveskite **PATVIRTINTI NAIKINIMĄ** visose didžiosiose raidėse. 

1. Rinkitės **Naikinti** norėdami visam laikui panaikinti darbo sritį.

### <a name="manage-workspace-members"></a>Valdyti darbo srities narius

1. Eikite į **Administratorius** > **Darbo sritis** ir rinkitės **Nariai**.

1. Norėdami **suteikti prieigą prie** vaidmenų ir juos priskirti, pažymėkite [Įtraukti narius](user-roles.md). Šiuo metu pasiekiamas **tik darbo** srities administratorius.

1. Pasirinkite **Įtraukti narius** ir įtraukite juos į savo darbo sritį.

## <a name="manage-an-existing-environment"></a>Valdyti esančią aplinką

Kaip aplinkos administratorius, kairiojoje naršymo srityje galite pasiekti aplinką. Galite konfigūruoti aplinkos parametrus, kitus aplinkos administratorius ir darbo sritis. Pažymėkite skirtukus, kad administravimo centre būtų galima pereiti iš vienos vietos į kitą.

:::image type="content" source="media/environment-edit.png" alt-text="Aplinkos administravimo centras.":::

### <a name="edit-an-environment-name"></a>Aplinkos pavadinimo redagavimas

1. Eikite į **Administratorius** > **Aplinka** ir rinkitės **Nustatymai**.

1. Atnaujinkite **aplinkos pavadinimą** ir pasirinkite **Įrašyti,** kad pakeitimai būtų pritaikyti.

### <a name="delete-an-environment"></a>Aplinkos naikinimas

Aplinkos administratoriai gali panaikinti aplinkas. Kad aplinką būtų galima panaikinti, prieš tai turite pašalinti visas jos darbo sritis.

1. Eikite į **Administratorius** > **Aplinka** ir rinkitės **Nustatymai**.

1. Pasirinkite **Naikinti aplinką**. 

1. Dialogo lange **Naikinti darbo aplinkos** lauką ir įveskite **PATVIRTINTI NAIKINIMĄ** visose didžiosiose raidėse. 

1. Pasirinkite **Naikinti**, kad visam laikui panaikintumėte aplinką.

### <a name="manage-environment-members"></a>Valdyti aplinkos narius

1. Eikite į **Administratorius** > **Aplinka** ir rinkitės **Nariai**.

1. Norėdami **atnaujinti narius** ir juos priskirti, pažymėkite [Įtraukti narius](user-roles.md). Šiuo metu pasiekiamas **tik aplinkos** srities administratorius.

1. Pasirinkite **Įtraukti narius** ir įtraukite juos į savo aplinką.

## <a name="manage-connections"></a>Ryšių valdymas

Užmesę ryšį su auditorijos įžvalgomis galite peržiūrėti ataskaitas įtraukimo įžvalgose, pagrįstose unifikuotais klientų profiliais. 

Daugiau informacijos, žr. [Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Tvarkyti asmeninius duomenis

Norėdami apsaugoti kliento asmeninius duomenis, galite panaikinti arba eksportuoti galutinio vartotojo identifikavimo duomenis.

Dėl išsamesnės informacijos, žr. [Naikinti ir eksportuoti įvykių duomenis, kuriuose yra asmeninė informacija](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
