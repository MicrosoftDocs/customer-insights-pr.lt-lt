---
title: Darbo sričių ir aplinkos valdymas
description: Kaip kurti, pervardyti ir panaikinti darbo sritis ir aplinkas.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: lt-LT
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486045"
---
# <a name="manage-environments-and-workspaces"></a>Valdyti aplinkas ir darbo aplinkas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Apžvalga

Darbo sritis – tai vieta įvykiams ir ataskaitoms saugoti ir valdyti. Čia galite peržiūrėti vartotojo veiklą tikruuoju laiku. Kurdami darbo sritį, pažymėkite duomenų, ties kuriuos siųsite į darbo sritį. Šiuo metu palaikomi žiniatinklio duomenys ir mobiliųjų įrenginių programos.

Aplinka yra vieta, kurioje valdote savo darbo sritis ir ryšius. Kaip naudoti aplinkas, priklauso nuo jūsų organizacijos ir atvejo. Pavyzdžiui, galite kurti:

-   Vieną aplinką.
-   Atskiros tikrinimo ir gamybos aplinkos.
-   Atskiros konkrečių jūsų organizacijos komandų ar skyrių aplinkos, kuriose yra kiekvienos auditorijos aktualių įvykių.
-   Atskiras skirtingų jūsų įmonės visuotinių šakų aplinkas.
-   Jungtys su „Customer Insights“ publikos įžvalgų galimybėmis.

## <a name="choose-an-environment-and-create-a-workspace"></a>Aplinkos pasirinkimas ir darbo srities kūrimas 

Kiekviena darbo sritis turi būti aplinkoje. Galite pažymėti iš anksto esamą aplinką arba sukurti naują, kai kuriate darbo sritį. Tada galėsite įtraukti darbo srities narių ir pradėti rinkti duomenis.

**Norėdami kurti savo pirmą darbo sritį**

1. Įtraukimo įžvalgose pasirinkite **Naujas** iš darbo srities perjungtuvo. 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights puslapio darbo srities parinkėjas.":::

1. Sąraše pasirinkite vieną aplinką arba **Kurti naują aplinką**.

1. Įveskite **Darbo srities** pavadinimą. 

1. Atsižvelgdami į tai, ką norite įvertinti svetainėje, ar mobilioje programoje, pasirinkite norimos kurti aplinkos tipą. 

1. Vaidmenų sąraše galite įtraukti narių ir priskirti jų **teisių** lygį. Tada pasirinkite **Baigti**, kad sukurtumėte darbo sritį, arba **Kitas**, kad įdiegtumėte kodą. 

1. Įdiekite šį kodo fragmentas, kad būtų pradėti gauti duomenys, tada pasirinkite **Atlikta**. 

## <a name="manage-a-workspace"></a>Tvarkyti darbo sritį

Aplinkoje galite turėti kelias darbo sritis, kurios veikia sklandžiai. Jūsų [vaidmuo](user-roles.md) apibrėžia, kaip galite su jais dirbti. 

 - Jei norite valdyti aplinką, turite būti darbo srities administratorius arba darbo srities administratorius.
 - Kaip darbo srities administratorius galite pervardyti esamas darbo sritis arba jas panaikinti. 

### <a name="edit-a-workspace-name"></a>Redaguoti darbo srities pavadinimą

1. Eikite į **Administratorius** > **Darbo sritis** ir rinkitės **Nustatymai**.

1. Laukelyje **Darbo srities pavadinimas** įveskite naują pavadinimą.

1. Pasirinkite **Įrašyti**, kad pritaikytumėte keitimus.

### <a name="delete-a-workspace"></a>Naikinti darbo sritį

Panaikinus darbo sritį, bus visam laikui pašalintas visas jos turinys, duomenys, parametrai ir teisės. Anuliuoti negalėsite.

1. Eikite į **Administratorius** > **Darbo sritis** ir rinkitės **Nustatymai**.

1. Pasirinkite **Naikinti darbo sritį**. 

1. Laukelyje **Naikinti darbo sritį** įveskite **PATVIRTINTI NAIKINIMĄ**. 

1. Rinkitės **Naikinti** norėdami visam laikui panaikinti darbo sritį.

### <a name="manage-workspace-members"></a>Valdyti darbo srities narius

1. Eikite į **Administratorius** > **Darbo sritis** ir rinkitės **Nariai**.

1. Norėdami **suteikti prieigą prie** vaidmenų ir juos priskirti, pažymėkite [Įtraukti narius](user-roles.md). Šiuo metu pasiekiamas **tik darbo** srities administratorius.

1. Pasirinkite **Įtraukti narius** ir įtraukite juos į savo darbo sritį.

## <a name="manage-an-environment"></a>Aplinkos valdymas

Kaip aplinkos administratorius, kairiojoje naršymo srityje galite pasiekti aplinką. Galite konfigūruoti aplinkos parametrus, kitus aplinkos administratorius ir darbo sritis. Pažymėkite skirtukus, kad administravimo centre būtų galima pereiti iš vienos vietos į kitą.

:::image type="content" source="media/New-environment.png" alt-text="Aplinkos administravimo centras.":::

### <a name="create-an-environment"></a>Sukurkite aplinką

1. Darbo srities parinkiklyje pasirinkite **+Nauja**.

1. Interaktyviojoje aplinkoje atidarykite išplečiamąjį meniu **Aplinka** ir pasirinkite **Kurti naują aplinką**. 

1. Pateikite **Aplinkos pavadinimą**.

   :::image type="content" source="media/create-environment.png" alt-text="Naudokite interaktyviąją patirtį, kad nurodytumėte išsamią informaciją apie aplinką.":::

1. Pasirinkite **Regioną** ir pasirinkite **Kitas**. 

1. Pateikite darbo srities pavadinimą ir pasirinkite, kurį darbo srities tipą norite sukurti. 

1.  Pasirinktinai įtraukite narių ir nukopijuokite kodo fragmentą, kad užbaigtumėte kūrimo procesą.

### <a name="rename-an-environment"></a>Pervardyti aplinką

1. Eikite į **Administratorius** > **Aplinka** ir rinkitės **Nustatymai**.

1. Atnaujinkite **aplinkos pavadinimą** ir pasirinkite **Įrašyti,** kad pakeitimai būtų pritaikyti.

### <a name="manage-environment-members"></a>Valdyti aplinkos narius

1. Eikite į **Administratorius** > **Aplinka** ir rinkitės **Nariai**.

1. Norėdami **atnaujinti narius** ir juos priskirti, pažymėkite [Įtraukti narius](user-roles.md). Šiuo metu pasiekiamas **tik aplinkos** srities administratorius.

1. Pasirinkite **Įtraukti narius** ir įtraukite juos į savo aplinką.

### <a name="delete-an-environment"></a>Aplinkos naikinimas

Aplinkos administratoriai gali panaikinti aplinkas. Kad aplinką būtų galima panaikinti, prieš tai turite pašalinti visas jos darbo sritis.

1. Eikite į **Administratorius** > **Aplinka** ir rinkitės **Nustatymai**.

1. Pasirinkite **Naikinti aplinką**. 

1. Laukelyje **Naikinti darbo sritį** įveskite **PATVIRTINTI NAIKINIMĄ**. 

1. Pasirinkite **Naikinti**, kad visam laikui panaikintumėte aplinką.

## <a name="manage-connections"></a>Ryšių valdymas

Užmesę ryšį su auditorijos įžvalgomis galite peržiūrėti ataskaitas įtraukimo įžvalgose, pagrįstose unifikuotais klientų profiliais. 

Daugiau informacijos, žr. [Sąsajos tarp auditorijos įžvalgų ir įtraukimo įžvalgų kūrimas](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Tvarkyti asmeninius duomenis

Norėdami apsaugoti kliento asmeninius duomenis, galite panaikinti arba eksportuoti galutinio vartotojo identifikavimo duomenis.

Dėl išsamesnės informacijos, žr. [Naikinti ir eksportuoti įvykių duomenis, kuriuose yra asmeninė informacija](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
