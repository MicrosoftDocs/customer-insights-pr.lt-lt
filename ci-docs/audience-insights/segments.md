---
title: Auditorijos įžvalgų segmentai
description: Segmentų apžvalga ir jų kūrimo bei valdymo informacija.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: c58f79c2beda1083d19bd36d94549ff1a46b096e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: lt-LT
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355993"
---
# <a name="segments-overview"></a>Segmentų apžvalga

Segmentai leidžia jums grupuoti jūsų klientus pagal demografiją, perlaidas ar elgesio savybes. Norėdami pasiekti verslo tikslus, galite naudoti segmentus, kad tikslingai vykdytumėte reklamines kampanijas, pardavimo veiklas ir klientų aptarnavimo veiksmus.

Klientų profiliai, atitinkantys segmento apibrėžties filtrus, yra vadinami segmento *nariais*. Kai kurie [paslaugų apribojimai](/dynamics365/customer-insights/service-limits) yra taikomi.

## <a name="create-a-new-segment"></a>Sukurkite naują segmentą

Naują segmentą galima sukurti keliais būdais: 

# <a name="individual-consumers-b-to-c"></a>[Atskiri vartotojai (B2C)](#tab/b2c)

- Sudėtingas segmentas su segmentų kūrimo įrankiu: [Kurkite savo](segment-builder.md#create-a-new-segment) 
- Paprasti segmentai su vienu operatoriumi: [Spartusis segmentas](segment-builder.md#quick-segments) 
- Dirbtiniu intelektu pagrįstas būdas rasti panašius klientus: [Panašūs klientai](find-similar-customer-segments.md) 
- Dirbtiniu intelektu pagrįsti pasiūlymai, paremti priemonėmis arba atributais: [Siūlomi segmentai priemonių patobulinimui](suggested-segments.md) 
- Pasiūlymai, pagrįsti veiklomis: [Siūlomi segmentai, pagrįsti kliento veikla](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Verslo klientai (B2B)](#tab/b2b)

- Sudėtingas segmentas su segmentų kūrimo įrankiu: [Kurkite savo](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Esamų segmentų tvarkymas

Eikite į **Segmentų** puslapį, kad peržiūrėtumėte visus savo įrašytus segmentus ir juos valdytumėte.

Kiekvieną segmentą atitinka eilutė, kurioje pateikta papildoma informacija apie segmentą.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Pažymėtas segmentas su parinkčių išplečiamajame sąraše ir galimose parinktyse.":::

Pasirinkus segmentą pasiekiami toliau nurodyti veiksmai.

- **Peržiūrėti** segmento išsamią informaciją, įskaitant narių skaičių, tendencijas ir segmento narių peržiūrą.
- **Redaguoti** segmentą ir pakeisti jo ypatybes.
- **Kurti dublikatą** segmentui. Galite iš karto pasirinkti redaguoti jo ypatybes arba tiesiog įrašyti dublikatą.
- **Atnaujinti** segmentą, kad būtų įtraukti naujausi duomenys.
- **Aktyvinti** arba **Išjungti** segmentą. Segmentai turi dvi galimas būsenas – aktyvią arba neaktyvią. Šios būsenos yra naudingos redaguojant segmentą. Neaktyvių segmentų aprašas yra, bet į jį dar neįtraukta klientų. Suaktyvinus segmentą, jo būsena keičiasi iš neaktyvios į aktyvią, ir jis pradeda ieškoti klientų, atitinkančių segmento aprašą. Jei [suplanuotas atnaujinimas](system.md#schedule-tab) yra sukonfigūruotas, neaktyvių segmentų **Būsena** nurodoma kaip **Praleista** – tai reiškia, kad net nebuvo bandyta atnaujinti. Suaktyvinus neaktyvų segmentą, jis bus atnaujintas ir įtrauktas į suplanuotus atnaujinimus.
  Taip pat galite naudoti funkciją **Planuoti vėliau**, esančią iškleidžiamajame meniu **Aktyvinti / išjungti**, kad nurodytumėte būsimą datą ir laiką, kada reikia aktyvinti ir išjungti tam tikrą segmentą.
- **Pervardyti** segmentą.
- **Atsisiųsti** narių sąrašą kaip .CSV failą.
- **Valdykite eksportavimus**, kad pamatytumėte susijusius segmentus ir juos valdytumėte. [Sužinokite daugiau apie eksportavimus.](export-destinations.md)
- **Naikinti** segmentą.

## <a name="refresh-segments"></a>Segmentų atnaujinimas

Visus segmentus galite atnaujinti vienu metu pažymėdami **Atnaujinti viską** puslapyje **Segmentai** arba galite atnaujinti vieną ar kelis segmentus, kai juos pažymite ir parinktyse pasirenkate **Atnaujinti**. Taip pat galite sukonfigūruoti pasikartojantį atnaujinimą dalyje **Administravimas** > **Sistemas** > **Planuoti**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Eksportuokite segmentus

Galite eksportuoti segmentą iš segmentų arba [eksportavimo puslapio](export-destinations.md). 

1. Eikite į puslapį **Segmentai**.

1. Pasirinkite **Rodyti daugiau [...]** norimam eksportuoti segmentui.

1. Veiksmų **išplečiamajame srąraše** pasirinkite Valdyti eksportą.

1. Atidaromas **Segmento eksportavimai (peržiūra)** puslapis. Galite matyti visus sukonfigūruotus eksportus, sugrupuotus pagal tai, ar juose yra dabartinis segmentas, ar ne.

   1. Jei pažymėtą segmentą norite įtraukti į eksportavimą, **redaguokite** atitinkamą eksportavimą, kad pažymėtumėte atitinkamą segmentą, tada įrašykite. Vietoj to, galite pažymėti eksportavimą atskirų klientų aplinkose sąraše ir įtraukti segmentą, kad **būtų pasiektas** toks pat rezultatas.

   1. Jei norite sukurti naują eksportavimą su pažymėtu segmentu, pasirinkite **Įtraukti eksportavimą**. Daugiau informacijos apie eksportavimo kūrimą rasite [Naujo eksportavimo nustatymas](export-destinations.md#set-up-a-new-export).

1. Pasirinkite **Atgal**, kad grįžtumėte į pagrindinį segmentų puslapį.

## <a name="view-processing-history-and-segment-members"></a>Apdorojimo retrospektyvos ir segmento narių peržiūra

Konsoliduotus duomenis apie segmentą galite peržiūrėti peržiūrėdami išsamią informaciją.

Puslapyje **Segmentai** pažymėkite segmentą, kurį norite peržiūrėti.

Viršutinėje puslapio dalyje yra tendencijos diagrama, vaizduojanti narių skaičiaus pokyčius. Nukreipkite žymiklį virš duomenų taškų ir peržiūrėkite narių skaičių tam tikra data.

Galite atnaujinti vizualizacijos laiko tarpą.

> [!div class="mx-imgBorder"]
> ![Segmento laiko diapazonas.](media/segment-time-range.png "Segmento laiko diapazonas")

Apatinėje dalyje yra segmento narių sąrašas.

> [!NOTE]
> Šiame sąraše pateikiami laukai grindžiami jūsų segmento objektų atributais.
>
>Šiame sąraše rodomi sutampantys segmento nariai ir pirmieji 100 jūsų segmento įrašai, kad galėtumėte greitai jį įvertinti ir peržiūrėti apibrėžimus, jei to reikia. Norėdami peržiūrėti visu sutampančius įrašus, turite [eksportuoti segmentą](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]